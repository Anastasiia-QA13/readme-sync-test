---
name: TestBox
---
<br />

export default function LabelBox({ label, children }) {
  return (
    <div style={{
      padding: "14px 16px",
      background: "#ffffff",
      borderRadius: 6,
      border: "1px solid #e5e7eb"
    }}>
      <strong style={{ color: "#111827" }}>{label}</strong>
      <p style={{ marginTop: 6, color: "#6b7280" }}>{children}</p>
    </div>
  );
}
