---
name: Info
---
<br />

export default function InfoBox({ children }) {
  return (
    <div style={{
      padding: "12px 16px",
      borderLeft: "4px solid #3b82f6",
      background: "#eff6ff",
      borderRadius: 6,
      color: "#1e3a8a"
    }}>
      {children}
    </div>
  );
}
