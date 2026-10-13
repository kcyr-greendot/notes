---
type: claude-summary
session_id: local_b12bdf73-c2eb-4e05-98ee-3d6009eaaef4
session_title: Strategic fit evaluation dimensions
last_synced: 2026-10-12
status: active
tags: [claude-summary, embedded-finance-strategy, capability-layers, gtm-segmentation]
---
# Embedded Finance Strategy Deck – Capability Layers

## Context
This is a long-running build of an internal Green Dot strategy deck (Green Dot pptx template) on embedded finance market segmentation and the "split the stack" thesis. The transcript available covers the later portion. Earlier work, including the 14 segments, SWOT and the framing section, was done before this excerpt.

## Artifacts
- The strategy deck .pptx and its source files (edited via shell in the session outputs folder; exact path not recorded in the transcript).
- A separate layer-definitions source file.
- Samples: a "you are here" thumbnail and the range-graphic sample.

## Key findings
- **Deck flow:**
  1. How partners buy (dividers in black section-header style; slide counters removed).
  2. The segments: a 2x2 map (funding certainty × feature sophistication), an optional "how to read" slide, then segment slides ordered lower-left → top-left → lower-right → upper-right, with segments Green Dot serves first in each quadrant. Each segment slide has an inline 2x2 thumbnail beside its quadrant label.
  3. The capability layers: a summary slide plus seven layer slides, each with L/M/H features and "Examples."
  4. Patterns and implications (draft).
- **Map summary:** "Our strengths cluster where money already flows and needs are simple. On the sophisticated side, we can attract partners but struggle to keep them."
- **Green Dot ranges on the summary slide** (5-point scale; black labels; sliders run to mid-slide, with "What stands out" text on the right):

| Layer | Range |
|---|---|
| Brand & UX | 1 and 5 only (GD-branded turnkey app or full headless; nothing in between) |
| BaaS APIs | 1–2 |
| Program management | 1–4 |
| Money movement | 1–3 (cash/GDN standout) |
| Processing | 1–2 (no transaction-level spend controls) |
| Issuing | 1–3 |
| Banking | 1–4 |

- **Slide summary:** "We're medium on the regulated layers that are hardest to replicate, and low on the technology layers sophisticated buyers care about most."
- **Karl's L/M/H definitions:**
  - BaaS APIs: L = APIs plus docs and recipes; M = SDKs, PCI widgets, webhooks and real-time data; H = use-case toolkits, MCP/LLM developer tooling, full composability.
  - Processing: L = network certification and system-level controls; M = MCC/MID card-level controls, open and closed loop; H = real-time authorization and highly configurable controls.
- **Key takeaways (draft):**
  1. Programs climb a one-way sophistication curve: zero → point solution → embedded account → split stack. Win early, design for composability, and keep charter, deposits and BIN sponsorship.
  2. Simple embedded accounts win when Green Dot is already in the funds flow; recurring deposits are the challenge.
  3. Strengths cluster in simple, mass-market use cases.
  4. Spend controls (on hold pending the layer grid).
  5. Layers are sold only by exception (GDN; Apple Cash on a split stack via FIS). Plan proactively.
  6. "We sell a headless bundle to buyers who often can't build the head."
- **Other findings:**
  - Payroll is an integration gap: Rapid! integrates with payroll providers but isn't connected to Arc.
  - Marketplace payouts (TikTok and Meta designs) need a new ledger capability.
  - Jackson Hewitt is a tax use case whose RFP describes a branded debit product (use case vs. product).

## Decisions
- Marketplace payouts: tag reverted to "Bundle or layer play"; the "Arc is all-or-nothing" weakness removed; summary softened.
- "Design for composability," not "design for the exit."
- No bundle/layer badges on the map.
- Rejected "both directions" (Samsung is moving up the curve).
- L/M/H labels only.
- Range graphic on segment rows pinned.
- Product-type definitions on hold.
- "In action" renamed to "Examples."

## Open questions
- Soften the program management note to fit the 1–4 range (e.g., "Strong when we run it; less flexible as partners take control")?
- Should individual layer slides show ranges to match the summary?
- Keep or cut the "how to read" slide?
- Finish the use case × layer grid (part 1 done; lower-right and upper-right remaining).
- Use case vs. product-type model.
- Final Section 4 structure (a single takeaways slide, with P1/P2 as backup).

## Next steps
- Resolve the two open consistency checks.
- Define segment-level L/M/H feature needs, then remap to the grid.
- Update the takeaways and build the Section 4 slide.

## Key sources
- None external.

## Resume prompt
> I'm Karl (Director of PSE, Green Dot Bank). We're building an internal embedded-finance strategy deck. Sections: How partners buy → Segments (2x2, 14 segments, inline thumbnails) → Capability layers (summary range-slider slide plus 7 L/M/H layer slides with Examples) → Patterns (draft). GD ranges on a 5-point scale: Brand & UX 1 and 5, BaaS APIs 1–2, Program management 1–4, Money movement 1–3, Processing 1–2, Issuing 1–3, Banking 1–4. Draft takeaways: one-way sophistication curve; design for composability; headless bundle for buyers who can't build the head; layers sold by exception; Rapid!/Arc integration gap; payouts ledger gap. Open: program management note wording, ranges on layer slides, finishing the use case × layer grid. Please help me with: resolving those consistency checks and continuing the use case × layer grid.
