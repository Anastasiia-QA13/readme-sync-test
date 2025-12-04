---
name: Block
---
<br />

export default function JsonBlock({ children }) {
  return (
    <pre style={{
      background: "#1f2937",
      color: "#d1d5db",
      padding: "14px",
      borderRadius: 6,
      fontSize: "14px",
      overflowX: "auto"
    }}>
      {children}
    </pre>
  );
}
