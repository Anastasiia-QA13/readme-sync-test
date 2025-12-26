---
name: QuoteCard
---
<br />

<br />

export default function QuoteCard({ children }) {
  return (
    <blockquote style={{
      padding: "16px",
      background: "#f9fafb",
      borderLeft: "4px solid #9ca3af",
      borderRadius: 6,
      fontStyle: "italic",
      color: "#374151"
    }}>
      {children}
    </blockquote>
  );
}
