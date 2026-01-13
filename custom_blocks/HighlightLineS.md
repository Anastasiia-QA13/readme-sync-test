---
name: HighlightLineS
---
<br />

export default function HighlightLine({ children }) {
  return (
    <div style={{
      padding: "14px 16px",
      background: "#fef3c7",
      borderLeft: "4px solid #f59e0b",
      borderRadius: 6,
      color: "#92400e"
    }}>
      {children}
    </div>
  );
}
