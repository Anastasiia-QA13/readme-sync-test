---
name: StepBlock
---
<br />

export default function StepBlock({ number, children }) {
  return (
    <div style={{
      display: "flex",
      alignItems: "flex-start",
      gap: "12px",
      margin: "12px 0"
    }}>
      <div style={{
        width: "28px",
        height: "28px",
        borderRadius: "50%",
        background: "#111827",
        color: "white",
        display: "flex",
        justifyContent: "center",
        alignItems: "center",
        fontSize: "14px",
        fontWeight: 600
      }}>
        {number}
      </div>

      <div style={{ color: "#374151", marginTop: "2px" }}>
        {children}
      </div>
    </div>
  );
}
