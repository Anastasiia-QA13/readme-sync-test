---
name: ApiHeader
---
<br />

export default function APIHeader({ method, path }) {
  const colors = {
    GET: "#10b981",
    POST: "#3b82f6",
    PUT: "#f59e0b",
    DELETE: "#ef4444"
  };

  return (
    <div style={{
      padding: "14px 16px",
      borderRadius: 8,
      background: "#f9fafb",
      border: "1px solid #e5e7eb",
      display: "flex",
      alignItems: "center",
      gap: "10px"
    }}>
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

      <code style={{ color: "#111827", fontSize: "14px" }}>
        {path}
      </code>
    </div>
  );
}
