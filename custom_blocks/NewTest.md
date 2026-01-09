---
name: NewTest
---
<br />

export default function MetricBox({ label, value }) {
  return (
    <div style={{
      padding: "16px",
      background: "#f9fafb",
      borderRadius: 8,
      border: "1px solid #e5e7eb",
      textAlign: "center"
    }}>
      <div style={{ fontSize: "20px", fontWeight: 700 }}>{value}</div>
      <div style={{ color: "#6b7280", fontSize: "13px" }}>{label}</div>
    </div>
  );
}
