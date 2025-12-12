---
name: DepricatedLine
---
<br />

export default function DeprecatedLine({ children }) {
  return (
    <div style={{
      padding: "12px 16px",
      background: "#fef2f2",
      borderLeft: "4px solid #dc2626",
      borderRadius: 6,
      color: "#7f1d1d"
    }}>
      {children}
    </div>
  );
}
