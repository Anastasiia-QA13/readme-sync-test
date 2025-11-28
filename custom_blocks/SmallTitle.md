---
name: SmallTitle
---
<br />

export default function SmallTitle({ children }) {
  return (
    <h3 style={{
      margin: "16px 0 8px",
      fontSize: "16px",
      fontWeight: 600,
      color: "#111827"
    }}>
      {children}
    </h3>
  );
}
