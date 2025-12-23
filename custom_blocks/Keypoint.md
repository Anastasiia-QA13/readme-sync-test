---
name: Keypoint
---
<br />

export default function KeyPoint({ children }) {
  return (
    <div style={{
      padding: "10px 14px",
      background: "#f9fafb",
      borderRadius: 6,
      borderLeft: "4px solid #6b7280",
      color: "#374151"
    }}>
      {children}
    </div>
  );
}
