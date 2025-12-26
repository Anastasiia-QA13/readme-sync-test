---
name: TipTag
---
<br />

export default function TipTag({ children }) {
  return (
    <span style={{
      padding: "4px 8px",
      background: "#e0f2fe",
      color: "#0369a1",
      borderRadius: 6,
      fontSize: "12px",
      fontWeight: 600
    }}>
      {children}
    </span>
  );
}
