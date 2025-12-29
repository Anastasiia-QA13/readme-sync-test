---
name: TagCode
---
<br />

export default function CodeTag({ children }) {
  return (
    <code style={{
      background: "#e5e7eb",
      padding: "2px 6px",
      borderRadius: 4,
      fontSize: "13px",
      color: "#111827"
    }}>
      {children}
    </code>
  );
}
