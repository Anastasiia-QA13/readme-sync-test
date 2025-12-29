---
name: Note
---
<br />

export default function MiniNote({ children }) {
  return (
    <div style={{
      padding: "10px 14px",
      background: "#f3f4f6",
      borderRadius: 6,
      color: "#4b5563"
    }}>
      {children}
    </div>
  );
}
