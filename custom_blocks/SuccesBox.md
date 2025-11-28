---
name: SuccesBox
---
<br />

export default function SuccessBox({ children }) {
  return (
    <div style={{
      padding: "12px 16px",
      borderLeft: "4px solid #10b981",
      background: "#ecfdf5",
      borderRadius: 6,
      color: "#065f46"
    }}>
      {children}
    </div>
  );
}
