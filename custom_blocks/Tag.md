---
name: Tag
---
<br />

export default function MethodTag({ method }) {
  const colors = {
    GET: "#10b981",
    POST: "#3b82f6",
    PUT: "#f59e0b",
    DELETE: "#ef4444"
  };

  return (
    <span style={{
      padding: "4px 8px",
      background: colors[method] || "#6b7280",
      color: "white",
      borderRadius: 6,
      fontSize: "12px",
      fontWeight: 600
    }}>
      {method}
    </span>
  );
}
