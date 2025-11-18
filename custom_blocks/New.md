---
name: New
---
<br />

export default function Collapsible({ title = "More details", children = "Hidden content here." }) {
  return (
    <details style={{ margin:"10px 0", background:"#F8F9FA", borderRadius:8, padding:"8px 12px" }}>
      <summary style={{ cursor:"pointer", fontWeight:600 }}>▶ {title}</summary>
      <div style={{ marginTop:8 }}>{children}</div>
    </details>
  );
}
