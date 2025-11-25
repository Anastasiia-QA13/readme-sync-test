---
name: Alert
---
<br />

export default function Notice({ type = "info", children }) {
  const colors = {
    info: "#1e90ff",
    warning: "#ffa500",
    danger: "#ff4d4f",
  };

  return (
    <div style={{
      borderLeft: `4px solid ${colors[type]}`,
      padding: "12px 16px",
      margin: "12px 0",
      background: "#f9f9f9",
      borderRadius: 6
    }}>
      {children}
    </div>
  );
}
