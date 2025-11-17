---
name: Badge
---
<br />

export default function Badge({ text = "Stable", color = "#0CA678", bg = "#E6FCF5" }) {
  return (
    <span style={{
      display: 'inline-block', padding: '0.2rem .5rem', borderRadius: 999,
      background: bg, color, fontWeight: 600, fontSize: 12, border: `1px solid ${color}22`
    }}>{text}</span>
  );
}
