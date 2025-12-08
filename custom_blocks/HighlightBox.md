---
name: HighlightBox
---
<br />

export default function HighlightBox({ children }) {
  return (
    <div style={{
      padding: "14px 16px",
      background: "#fef3c7",
      borderRadius: 6,
      borderLeft: "4px solid #f59e0b",
      color: "#92400e"
    }}>
      {children}
    </div>
  );
}
