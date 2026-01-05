---
name: EnvVar
---
<br />

export default function EnvVar({ name, children }) {
  return (
    <div style={{
      padding: "10px 14px",
      background: "#111827",
      color: "#f9fafb",
      borderRadius: 6,
      fontSize: "13px"
    }}>
      <strong>{name}</strong> — {children}
    </div>
  );
}
