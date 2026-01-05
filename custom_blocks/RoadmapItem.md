---
name: RoadmapItem
---
<br />

export default function RoadmapItem({ title, children }) {
  return (
    <div style={{
      padding: "14px 16px",
      borderLeft: "3px solid #6b7280",
      background: "#f9fafb",
      borderRadius: 6
    }}>
      <strong>{title}</strong>
      <p style={{ marginTop: 4, color: "#6b7280" }}>{children}</p>
    </div>
  );
}
