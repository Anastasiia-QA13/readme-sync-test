---
name: TestTab
---
<br />

export default function Callout({ children }) {
  return (
    <div style={{
      borderLeft: "3px solid #3b82f6",
      background: "#eff6ff",
      padding: "10px 14px",
      borderRadius: 6,
      marginTop: 12
    }}>
      {children}
    </div>
  );
}
