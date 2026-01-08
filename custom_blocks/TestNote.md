---
name: TestNote
---
<br />

export default function ExampleNote({ children }) {
  return (
    <div style={{
      padding: "12px 16px",
      background: "#ecfeff",
      borderLeft: "4px solid #06b6d4",
      borderRadius: 6,
      color: "#155e75"
    }}>
      {children}
    </div>
  );
}
