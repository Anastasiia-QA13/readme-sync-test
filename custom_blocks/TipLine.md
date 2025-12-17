---
name: TipLine
---
<br />

export default function TipLine({ children }) {
  return (
    <div style={{
      padding: "12px 16px",
      background: "#f0fdf4",
      borderLeft: "4px solid #22c55e",
      borderRadius: 6,
      color: "#166534"
    }}>
      {children}
    </div>
  );
}
