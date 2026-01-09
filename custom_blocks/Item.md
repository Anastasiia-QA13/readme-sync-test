---
name: Item
---
<br />

export default function ChecklistItem({ children }) {
  return (
    <div style={{
      display: "flex",
      alignItems: "center",
      gap: "8px",
      color: "#374151"
    }}>
      <span style={{ color: "#10b981" }}>✔</span>
      {children}
    </div>
  );
}
