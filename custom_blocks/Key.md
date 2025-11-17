---
name: Key
---
<br />

export default function KeyValueTable({ items = { "Authorization": "Bearer <TOKEN>", "Content-Type": "application/json" } }) {
  const rows = Object.entries(items);
  return (
    <table style={{ width: '100%', borderCollapse: 'collapse', margin: '1rem 0', fontSize: 14 }}>
      <tbody>
        {rows.map(([k, v], i) => (
          <tr key={i} style={{ borderBottom: '1px solid #eee' }}>
            <td style={{ width: '30%', padding: '.5rem', fontWeight: 600, background: '#F8F9FA' }}>{k}</td>
            <td style={{ padding: '.5rem' }}><code>{v}</code></td>
          </tr>
        ))}
      </tbody>
    </table>
  );
}
