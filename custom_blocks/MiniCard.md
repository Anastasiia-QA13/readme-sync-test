---
name: MiniCard
---
<br />

export default function MiniCard({ title, children }) {
  return (
    <div style={{
      padding: "14px 16px",
      background: "#ffffff",
      border: "1px solid #e5e7eb",
      borderRadius: 8
    }}>
      <strong style={{ color: "#111827" }}>{title}</strong>
      <p style={{ color: "#6b7280", marginTop: 6 }}>{children}</p>
    </div>
  );
}
