---
name: LineTest
---
<br />

export default function WarningInline({ children }) {
  return (
    <span style={{
      background: "#fef3c7",
      padding: "2px 6px",
      borderRadius: 4,
      color: "#92400e",
      fontSize: "13px"
    }}>
      {children}
    </span>
  );
}
