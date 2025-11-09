---
title: GGB Audio Tour for iOS
excerpt: >-
  Download this audio tour—and others!—for your iPhone or iPad. Or integrate
  with our API!
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  title: ''
  description: ''
  robots: index
---
# GGB Audio Tour for iOS

## Overview: Owlbert's Audio Guides

If you're looking to connect the Owlbert's Journey Maps API for your iOS device, you've come to the right place! Keep reading for full instructions on how to get set up for the Golden Gate Bridge Walking Tour and all the other ones that Owlbert offers!

<Image align="center" width="35% " src="https://files.readme.io/ef73f9f-owlbert-ios.png" />

Owlbert's Audio Guides transform your iPhone or iPad into an intelligent tour companion, delivering rich, contextual stories as you explore iconic landmarks. Our Golden Gate Bridge Walking Tour is just the beginning of an immersive journey through San Francisco's most beloved attractions.

## Why Choose Owlbert's iOS Integration?

### 🎧 **Immersive Audio Experience**
- High-quality, professionally narrated content
- Automatic location-based triggering
- Offline playback capabilities
- Multi-language support

### 📱 **Native iOS Features**
- Seamless integration with Core Location
- Background audio playback
- CarPlay compatibility
- Accessibility support with VoiceOver

### 🗺️ **Smart Navigation**
- GPS-guided tour routes
- Interactive maps with points of interest
- Real-time distance and direction calculations
- Weather-aware recommendations

## Getting Started with the iOS SDK

### Prerequisites

Before integrating Owlbert's API into your iOS application, ensure you have:

- **Xcode 14.0+** with iOS 15.0+ deployment target
- **Valid API Key** from your Owlbert developer account
- **Location Services** permissions configured in your app
- **Audio playback** capabilities enabled

### Installation Options

<Tabs>
<Tab title="Swift Package Manager">
Add the following dependency to your `Package.swift` file:

```swift
dependencies: [
    .package(url: "https://github.com/owlbert/ios-sdk.git", from: "2.1.0")
]
```
</Tab>
<Tab title="CocoaPods">
Add to your `Podfile`:

```ruby
pod 'OwlbertSDK', '~> 2.1.0'
```

Then run:
```bash
pod install
```
</Tab>
<Tab title="Manual Integration">
1. Download the latest SDK from our [releases page](https://github.com/owlbert/ios-sdk/releases)
2. Drag the framework into your Xcode project
3. Ensure it's added to your target's "Frameworks, Libraries, and Embedded Content"
</Tab>
</Tabs>

## Owlbert's Golden Gate Bridge Walking Tour API

### Quick Start Implementation

Here's how to get up and running with the Golden Gate Bridge tour in just a few lines of code:

```swift
import OwlbertSDK
import CoreLocation

class GGBTourViewController: UIViewController {
    private let owlbertClient = OwlbertClient(apiKey: "your_api_key_here")
    private let locationManager = CLLocationManager()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        setupLocationServices()
        loadGoldenGateTour()
    }
    
    private func loadGoldenGateTour() {
        owlbertClient.loadTour(tourId: "golden-gate-bridge") { [weak self] result in
            switch result {
            case .success(let tour):
                self?.startTour(tour)
            case .failure(let error):
                print("Failed to load tour: \(error.localizedDescription)")
            }
        }
    }
    
    private func startTour(_ tour: OwlbertTour) {
        tour.delegate = self
        tour.startMonitoring()
    }
}

extension GGBTourViewController: OwlbertTourDelegate {
    func tour(_ tour: OwlbertTour, didEnterRegion region: OwlbertRegion) {
        // Automatically play audio content when user enters a point of interest
        tour.playAudioContent(for: region)
    }
}
```

### Key Features and Configuration

<Accordion title="Location-Based Triggers" icon="map-marker-alt">

The Golden Gate Bridge tour includes 12 strategically placed geofenced regions that automatically trigger content as visitors approach:

- **Welcome Point**: Tour introduction and safety guidelines
- **South Vista Point**: Historical context and construction facts  
- **Mid-Span**: Engineering marvels and architectural details
- **North Tower**: Art Deco design elements and worker stories
- **Marin Headlands View**: Ecological information and wildlife
- **Battery Spencer**: Military history and strategic importance
- **Crissy Field**: Restoration project and environmental impact
- **Fort Point**: Civil War history beneath the bridge
- **And 4 additional surprise locations!**

Configure trigger sensitivity:
```swift
tour.geofenceRadius = 50.0 // meters
tour.minimumDwellTime = 15.0 // seconds
```

</Accordion>

<Accordion title="Audio Customization" icon="volume-up">

Fine-tune the audio experience to match your app's needs:

```swift
// Audio playback settings
tour.audioSettings.fadeInDuration = 2.0
tour.audioSettings.fadeOutDuration = 1.5
tour.audioSettings.backgroundMusicEnabled = true
tour.audioSettings.narratorVoice = .professional // or .conversational

// Language options
tour.preferredLanguage = .english // Also supports Spanish, French, Mandarin
```

Quality options:
- **High Quality**: 320kbps for WiFi download
- **Standard**: 128kbps for cellular-friendly streaming  
- **Compressed**: 64kbps for data-conscious users

</Accordion>

<Accordion title="Offline Capabilities" icon="download">

Enable offline functionality for areas with poor cellular coverage:

```swift
// Pre-download tour content
owlbertClient.downloadTour(tourId: "golden-gate-bridge") { progress in
    DispatchQueue.main.async {
        self.progressBar.progress = progress
    }
} completion: { result in
    switch result {
    case .success:
        print("Tour downloaded successfully")
    case .failure(let error):
        print("Download failed: \(error)")
    }
}

// Check offline availability
if tour.isAvailableOffline {
    tour.enableOfflineMode(true)
}
```

Downloaded tours include:
- All audio content (approx. 45 minutes)
- High-resolution images and maps
- Interactive tour route data
- Emergency contact information

</Accordion>

### Advanced Integration Features

<Cards columns="2">
<Card title="Real-time Analytics" href="#analytics" icon="chart-line">
Track user engagement, popular stops, and completion rates through our comprehensive analytics dashboard.
</Card>
<Card title="Custom Branding" href="#branding" icon="palette">
Customize the tour interface with your app's colors, fonts, and logo for a seamless user experience.
</Card>
<Card title="Multi-tour Management" href="#multi-tour" icon="route">
Manage multiple tour subscriptions and create custom tour bundles for different user segments.
</Card>
<Card title="Accessibility Features" href="#accessibility" icon="universal-access">
Full VoiceOver support, adjustable text sizes, and hearing-impaired friendly visual cues.
</Card>
</Cards>

### Error Handling and Best Practices

Implement robust error handling for common scenarios:

```swift
func handleTourErrors(_ error: OwlbertError) {
    switch error {
    case .networkUnavailable:
        // Fallback to offline content if available
        if tour.isAvailableOffline {
            tour.enableOfflineMode(true)
        } else {
            showOfflineMessage()
        }
        
    case .locationPermissionDenied:
        // Guide user to enable location services
        showLocationPermissionAlert()
        
    case .audioPermissionDenied:
        // Provide visual-only tour experience
        tour.enableSilentMode(true)
        
    case .tourNotFound:
        // Refresh tour catalog
        owlbertClient.refreshTourCatalog()
        
    default:
        showGenericErrorMessage()
    }
}
```

### Testing and Debugging

<Accordion title="Simulator Testing" icon="mobile-alt">

Test your integration using Xcode Simulator with simulated locations:

1. In Simulator, go to **Features → Location → Custom Location**
2. Enter Golden Gate Bridge coordinates: `37.8199, -122.4783`
3. Use our test tour ID: `golden-gate-bridge-test` for development
4. Enable debug logging: `OwlbertSDK.enableDebugLogging(true)`

</Accordion>

## Next Steps

Ready to enhance your app with Owlbert's audio tours? Here's what to do next:

1. **[Sign up for a developer account](https://developer.owlbert.com/signup)** to get your API keys
2. **[Explore our full tour catalog](https://developer.owlbert.com/tours)** with 50+ available tours
3. **[Join our developer community](https://community.owlbert.com)** for support and best practices
4. **[Review our iOS sample app](https://github.com/owlbert/ios-sample-app)** for complete implementation examples

## Support and Resources

- 📧 **Developer Support**: [ios-support@owlbert.com](mailto:ios-support@owlbert.com)
- 📚 **Complete API Documentation**: [docs.owlbert.com/ios](https://docs.owlbert.com/ios)  
- 💬 **Community Slack**: [owlbert-developers.slack.com](https://owlbert-developers.slack.com)
- 🐛 **Bug Reports**: [GitHub Issues](https://github.com/owlbert/ios-sdk/issues)

Transform your app into an intelligent tour guide today with Owlbert's Golden Gate Bridge Walking Tour API!