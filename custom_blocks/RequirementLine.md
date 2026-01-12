---
name: RequirementLine
---
<br />

export default function RequirementLine({ children }) {
  return (
    <div style={{
      padding: "12px 16px",
      background: "#eef2ff",
      borderLeft: "4px solid #6366f1",
      borderRadius: 6,
      color: "#312e81"
    }}>
      {children}
    </div>
  );
}
