---
title: Integrating with the Owlbert Journey Maps API
excerpt: >-
  Learn how to integrate with the Owlbert Journey Maps API to create, manage,
  and analyze customer journey maps in your applications.
deprecated: false
hidden: false
icon: 📣
link:
  new_tab: false
metadata:
  title: ''
  description: ''
  robots: index
---
The Owlbert Journey Maps API provides powerful tools for creating, managing, and analyzing customer journey maps programmatically. This guide will walk you through the integration process, from initial setup to advanced usage patterns.

## Quick Start

Get up and running with the Owlbert Journey Maps API in just a few steps:

<Accordion title="Prerequisites" icon="list-check">
  Before you begin, ensure you have:

  * An active Owlbert account with API access
  * Your API key (found in your account dashboard)
  * Basic knowledge of REST APIs and JSON
  * Your preferred HTTP client or SDK
</Accordion>

## Authentication

The Owlbert Journey Maps API uses API key authentication. Include your API key in the request headers:

```bash
curl -X GET "https://api.owlbert.com/v1/journeys" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json"
```

### Getting Your API Key

1. Log into your Owlbert dashboard
2. Navigate to **Settings > API Access**
3. Click **Generate New API Key**
4. Copy and securely store your key

<Callout icon="🔒" theme="default">
  ### **Security Note**: Never expose your API key in client-side code or public repositories. Use environment variables or secure credential management systems.
</Callout>

## Core Endpoints

<Tabs>
  <Tab title="Journey Maps">
    ### List Journey Maps

    ```http
    GET /v1/journeys
    ```

    Retrieve all journey maps in your account with optional filtering and pagination.

    **Query Parameters:**

    * `page` (integer): Page number for pagination (default: 1)
    * `limit` (integer): Number of items per page (max: 100, default: 20)
    * `status` (string): Filter by status (`active`, `draft`, `archived`)
    * `created_after` (string): ISO 8601 date to filter by creation date

    **Example Response:**

    ```json
    {
      "data": [
        {
          "id": "journey_123",
          "name": "Customer Onboarding Flow",
          "status": "active",
          "created_at": "2023-10-15T10:30:00Z",
          "updated_at": "2023-10-20T14:45:00Z",
          "stages_count": 5,
          "touchpoints_count": 12
        }
      ],
      "pagination": {
        "current_page": 1,
        "total_pages": 3,
        "total_items": 45
      }
    }
    ```

    ### Create Journey Map

    ```http
    POST /v1/journeys
    ```

    Create a new customer journey map with stages and touchpoints.

    **Request Body:**

    ```json
    {
      "name": "New Customer Journey",
      "description": "Journey mapping for new user acquisition",
      "stages": [
        {
          "name": "Awareness",
          "description": "Customer becomes aware of the product",
          "order": 1
        },
        {
          "name": "Consideration",
          "description": "Customer evaluates the product",
          "order": 2
        }
      ]
    }
    ```
  </Tab>

  <Tab title="Touchpoints">
    ### Add Touchpoint

    ```http
    POST /v1/journeys/{journey_id}/touchpoints
    ```

    Add a touchpoint to a specific journey stage.

    **Request Body:**

    ```json
    {
      "stage_id": "stage_456",
      "name": "Email Campaign",
      "type": "email",
      "channel": "marketing",
      "sentiment": "positive",
      "effort_score": 3,
      "description": "Welcome email sent to new subscribers"
    }
    ```

    ### Update Touchpoint

    ```http
    PUT /v1/touchpoints/{touchpoint_id}
    ```

    Update an existing touchpoint with new data or metrics.
  </Tab>

  <Tab title="Analytics">
    ### Journey Analytics

    ```http
    GET /v1/journeys/{journey_id}/analytics
    ```

    Retrieve analytics and insights for a specific journey map.

    **Example Response:**

    ```json
    {
      "journey_id": "journey_123",
      "metrics": {
        "total_interactions": 1250,
        "completion_rate": 0.68,
        "average_duration": "2.5 days",
        "satisfaction_score": 4.2
      },
      "stage_performance": [
        {
          "stage_id": "stage_456",
          "conversion_rate": 0.85,
          "average_time": "4 hours",
          "drop_off_rate": 0.15
        }
      ]
    }
    ```
  </Tab>
</Tabs>

## Integration Patterns

<Cards columns={2}>
  <Card title="Webhook Integration" href="#webhooks" icon="webhook">
    Set up real-time notifications when journey maps are updated or customer interactions occur.
  </Card>

  <Card title="Bulk Operations" href="#bulk" icon="layer-group">
    Learn how to efficiently create and update multiple journey maps using batch endpoints.
  </Card>

  <Card title="Data Export" href="#export" icon="download">
    Export journey data for analysis in external tools or data warehouses.
  </Card>

  <Card title="Custom Fields" href="#custom-fields" icon="sliders">
    Extend journey maps with custom metadata and properties specific to your business.
  </Card>
</Cards>

## Code Examples

<Accordion title="JavaScript/Node.js" icon="js-square">
  ```javascript
  const OwlbertAPI = require('@owlbert/journey-maps-sdk');

  const client = new OwlbertAPI({
    apiKey: process.env.OWLBERT_API_KEY,
    baseURL: 'https://api.owlbert.com/v1'
  });

  // Create a new journey map
  async function createJourney() {
    try {
      const journey = await client.journeys.create({
        name: 'E-commerce Purchase Journey',
        description: 'Complete customer journey from discovery to purchase',
        stages: [
          { name: 'Discovery', order: 1 },
          { name: 'Research', order: 2 },
          { name: 'Purchase', order: 3 },
          { name: 'Post-Purchase', order: 4 }
        ]
      });
      
      console.log('Journey created:', journey.id);
      return journey;
    } catch (error) {
      console.error('Error creating journey:', error.message);
    }
  }

  // Add touchpoints to a journey
  async function addTouchpoint(journeyId, stageId) {
    const touchpoint = await client.touchpoints.create({
      journeyId,
      stageId,
      name: 'Product Page Visit',
      type: 'web_interaction',
      channel: 'website',
      sentiment: 'neutral',
      effort_score: 2
    });
    
    return touchpoint;
  }
  ```
</Accordion>

<Accordion title="Python" icon="python">
  ```python
  import os
  from owlbert_journey_maps import OwlbertClient

  # Initialize client
  client = OwlbertClient(
      api_key=os.getenv('OWLBERT_API_KEY'),
      base_url='https://api.owlbert.com/v1'
  )

  def create_journey_with_touchpoints():
      """Create a complete journey map with stages and touchpoints."""
      
      # Create journey
      journey = client.journeys.create({
          'name': 'SaaS Trial to Paid Conversion',
          'description': 'Journey from trial signup to paid subscription',
          'stages': [
              {'name': 'Trial Signup', 'order': 1},
              {'name': 'Product Exploration', 'order': 2},
              {'name': 'Feature Discovery', 'order': 3},
              {'name': 'Conversion Decision', 'order': 4}
          ]
      })
      
      print(f"Created journey: {journey['id']}")
      
      # Add touchpoints for each stage
      touchpoints = [
          {
              'stage_name': 'Trial Signup',
              'touchpoints': [
                  {'name': 'Landing Page', 'type': 'web', 'sentiment': 'positive'},
                  {'name': 'Signup Form', 'type': 'web', 'effort_score': 3}
              ]
          },
          {
              'stage_name': 'Product Exploration',
              'touchpoints': [
                  {'name': 'Welcome Email', 'type': 'email', 'sentiment': 'positive'},
                  {'name': 'First Login', 'type': 'app', 'effort_score': 2}
              ]
          }
      ]
      
      for stage_data in touchpoints:
          stage = next(s for s in journey['stages'] if s['name'] == stage_data['stage_name'])
          for tp_data in stage_data['touchpoints']:
              tp_data['stage_id'] = stage['id']
              client.touchpoints.create(journey['id'], tp_data)
      
      return journey

  # Get journey analytics
  def get_journey_insights(journey_id):
      """Retrieve comprehensive analytics for a journey."""
      analytics = client.analytics.get_journey_metrics(journey_id)
      
      print(f"Journey Completion Rate: {analytics['metrics']['completion_rate']:.2%}")
      print(f"Average Satisfaction: {analytics['metrics']['satisfaction_score']}/5")
      
      return analytics
  ```
</Accordion>

## Error Handling

The API returns standard HTTP status codes and detailed error messages:

<Columns layout="auto">
  <Column>
    **Common Status Codes:**

    * `200` - Success
    * `201` - Created
    * `400` - Bad Request
    * `401` - Unauthorized
    * `404` - Not Found
    * `429` - Rate Limited
    * `500` - Internal Server Error
  </Column>

  <Column>
    **Error Response Format:**

    ```json
    {
      "error": {
        "code": "validation_error",
        "message": "Invalid journey stage order",
        "details": {
          "field": "stages[0].order",
          "reason": "Order must be a positive integer"
        }
      }
    }
    ```
  </Column>
</Columns>

## Rate Limits and Best Practices

<Accordion title="Rate Limiting" icon="gauge">
  The API enforces the following rate limits:

  * **Standard Plan**: 100 requests per minute
  * **Professional Plan**: 500 requests per minute
  * **Enterprise Plan**: 2000 requests per minute

  Rate limit headers are included in all responses:

  ```
  X-RateLimit-Limit: 100
  X-RateLimit-Remaining: 85
  X-RateLimit-Reset: 1609459200
  ```
</Accordion>

<Accordion title="Best Practices" icon="lightbulb">
  **Performance Optimization:**

  * Use pagination for large datasets
  * Implement proper caching strategies
  * Batch operations when possible
  * Use webhooks for real-time updates instead of polling

  **Error Handling:**

  * Implement exponential backoff for retries
  * Handle rate limiting gracefully
  * Validate data before sending requests
  * Log API interactions for debugging

  **Security:**

  * Never hardcode API keys
  * Use HTTPS for all requests
  * Implement proper access controls
  * Regularly rotate API keys
</Accordion>

## Webhooks

Configure webhooks to receive real-time notifications about journey map changes:

```json
{
  "url": "https://your-app.com/webhooks/owlbert",
  "events": [
    "journey.created",
    "journey.updated",
    "touchpoint.added",
    "analytics.updated"
  ],
  "secret": "your-webhook-secret"
}
```

## Support and Resources

<Cards columns={3}>
  <Card title="API Reference" href="/api-reference" icon="code">
    Complete API documentation with all endpoints and parameters
  </Card>

  <Card title="SDKs & Libraries" href="/sdks" icon="cube">
    Official SDKs for popular programming languages
  </Card>

  <Card title="Community Forum" href="/community" icon="users">
    Get help from other developers and the Owlbert team
  </Card>
</Cards>

Need help? Contact our support team at [api-support@owlbert.com](mailto:api-support@owlbert.com) or check out our comprehensive [troubleshooting guide](/troubleshooting).

<br />

test
