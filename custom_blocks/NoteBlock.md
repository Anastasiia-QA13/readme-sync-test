---
name: NoteBlock
---
<br />

export default function NoteBlock({ children }) {
  return (
    <div style={{
      padding: "12px 16px",
      borderLeft: "4px solid #9ca3af",
      background: "#f3f4f6",
      borderRadius: 6,
      color: "#374151"
    }}>
      {children}
    </div>
  );
}
