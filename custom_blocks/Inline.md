---
name: Inline
---
<br />

export default function InlineNote({ children }) {
  return (
    <span style={{
      padding: "2px 6px",
      background: "#e5e7eb",
      borderRadius: 4,
      fontSize: "12px",
      color: "#374151"
    }}>
      {children}
    </span>
  );
}
