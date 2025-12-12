---
name: Link
---
<br />

export default function LinkCard({ title, href, children }) {
  return (
    <a
      href={href}
      style={{
        display: "block",
        padding: "16px",
        borderRadius: 8,
        background: "#ffffff",
        border: "1px solid #e5e7eb",
        textDecoration: "none"
      }}
    >
      <strong style={{ color: "#111827", fontSize: "15px" }}>{title}</strong>
      <p style={{ color: "#6b7280", marginTop: 6 }}>{children}</p>
    </a>
  );
}
