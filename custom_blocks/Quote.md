---
name: Quote
---
<br />

export default function Quote({ children }) {
  return (
    <blockquote style={{
      padding: "12px 16px",
      borderLeft: "4px solid #9ca3af",
      fontStyle: "italic",
      color: "#374151",
      background: "#f9fafb",
      borderRadius: 4
    }}>
      {children}
    </blockquote>
  );
}
