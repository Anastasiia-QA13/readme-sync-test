---
name: GreyBox
---
<br />

export default function GreyBox({ children }) {
  return (
    <div style={{
      padding: "14px 16px",
      background: "#f3f4f6",
      borderRadius: 6,
      color: "#374151"
    }}>
      {children}
    </div>
  );
}
