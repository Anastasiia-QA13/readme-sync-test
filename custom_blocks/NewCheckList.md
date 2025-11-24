---
name: NewCheckList
---
export default function Step({ number, text }) {
  return (
    <div style={{ display: "flex", margin: "12px 0" }}>
      <span style={{
        width: 28,
        height: 28,
        borderRadius: "50%",
        background: "#111827",
        color: "#fff",
        display: "flex",
        justifyContent: "center",
        alignItems: "center",
        marginRight: 12
      }}>
        {number}
      </span>
      <p style={{ margin: 0 }}>{text}</p>
    </div>
  );
}


<br />

<br />

<br />

<br />

<br />

<br />

<br />
