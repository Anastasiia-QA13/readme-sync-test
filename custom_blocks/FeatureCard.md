---
name: FeatureCard
---
<br />

export default function FeatureCard({ title, description, href }) {
  return (
    <a href={href} style={{ textDecoration: "none" }}>
      <div style={{
        padding: 18,
        border: "1px solid #e5e7eb",
        borderRadius: 12,
        height: "100%"
      }}>
        <h3 style={{ color: "#111827", margin: "0 0 8px" }}>{title}</h3>
        <p style={{ color: "#4b5563", margin: 0 }}>{description}</p>
      </div>
    </a>
  );
}
