---
name: BetaTag
---
<br />

export default function BetaTag({ children }) {
  return (
    <span style={{
      padding: "4px 8px",
      background: "#fef3c7",
      color: "#b45309",
      borderRadius: 6,
      fontSize: "12px",
      fontWeight: 600
    }}>
      {children}
    </span>
  );
}
