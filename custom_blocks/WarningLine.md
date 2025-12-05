---
name: WarningLine
---
<br />

export default function WarningLine({ children }) {
  return (
    <div style={{
      padding: "12px 16px",
      background: "#fffbeb",
      borderLeft: "4px solid #f59e0b",
      borderRadius: 6,
      color: "#92400e"
    }}>
      {children}
    </div>
  );
}
