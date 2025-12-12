---
name: SimpleCard
---
<br />

export default function SimpleCard({ title, children }) {
  return (
    <div style={{
      padding: "16px",
      background: "#ffffff",
      border: "1px solid #e5e7eb",
      borderRadius: 8
    }}>
      <strong style={{ color: "#111827" }}>{title}</strong>
      <p style={{ marginTop: 6, color: "#6b7280" }}>{children}</p>
    </div>
  );
}
