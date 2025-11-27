---
name: ErrorBox
---
<br />

export default function ErrorBox({ children }) {
  return (
    <div style={{
      padding: "12px 16px",
      borderLeft: "4px solid #ef4444",
      background: "#fef2f2",
      borderRadius: 6,
      color: "#991b1b"
    }}>
      {children}
    </div>
  );
}
