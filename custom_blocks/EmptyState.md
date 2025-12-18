---
name: EmptyState
---
<br />

export default function EmptyState({ children }) {
  return (
    <div style={{
      padding: "20px",
      background: "#f3f4f6",
      borderRadius: 8,
      textAlign: "center",
      color: "#6b7280"
    }}>
      {children}
    </div>
  );
}
