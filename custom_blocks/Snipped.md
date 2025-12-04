---
name: Snipped
---
<br />

export default function CurlSnippet({ children }) {
  return (
    <pre style={{
      background: "#111827",
      color: "#f9fafb",
      padding: "12px 16px",
      borderRadius: 6,
      fontSize: "14px",
      overflowX: "auto"
    }}>
      {children}
    </pre>
  );
}
