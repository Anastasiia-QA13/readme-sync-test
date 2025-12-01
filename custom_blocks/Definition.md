---
name: Definition
---
<br />

export default function Definition({ term, children }) {
  return (
    <div style={{
      padding: "12px 16px",
      background: "#f9fafb",
      borderLeft: "4px solid #3b82f6",
      borderRadius: 6
    }}>
      <strong style={{ color: "#1e3a8a" }}>{term}:</strong>
      <span style={{ marginLeft: 6 }}>{children}</span>
    </div>
  );
}
