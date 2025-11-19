---
name: CardsGrid
---
<br />

export default function CardsGrid({
  items = [
    { title:"Get Started", desc:"Start here", href:"/getting-started" },
    { title:"API Reference", desc:"All endpoints", href:"/reference" },
    { title:"Changelog", desc:"What’s new", href:"/changelog" }
  ]
}) {
  return (
    <div style={{ display:"grid", gap:12, gridTemplateColumns:"repeat(auto-fit, minmax(220px, 1fr))", margin:"12px 0" }}>
      {items.map((it, i)=>(
        <a key={i} href={it.href} style={{ textDecoration:"none" }}>
          <div style={{ border:"1px solid #e5e7eb", borderRadius:12, padding:16, height:"100%" }}>
            <h4 style={{ margin:"0 0 6px 0", color:"#111827" }}>{it.title}</h4>
            <p style={{ margin:0, color:"#4b5563" }}>{it.desc}</p>
          </div>
        </a>
      ))}
    </div>
  );
}
