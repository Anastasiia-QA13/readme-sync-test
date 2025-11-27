---
name: WaitingBox
---
<br />

export default function WarningBox({ children }) {
  return (
    <div style={{
      padding: "12px 16px",
      borderLeft: "4px solid #f59e0b",
      background: "#fffbeb",
      borderRadius: 6,
      color: "#92400e"
    }}>
      {children}
    </div>
  );
}
