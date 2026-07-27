# Production Workflow

Use this workflow when the user needs more than a concept render: a durable display MOC, a modular model, purchase-ready inventory, BrickLink Studio handoff, or polished instructions.

## 1. Project brief

Capture known information before designing. Reuse preferences already established in the conversation, project files, or prior decisions.

| Area | Capture |
|---|---|
| Purpose | display, play, teaching, gift, exhibition, or prototype |
| Scale | target ratio/tier, maximum width/depth/height, minifigure compatibility |
| Fidelity | silhouette, proportions, colors, interiors, functional/signature details |
| Constraints | piece count, budget, inventory, deadline, legal-technique requirement |
| Structure | handling, transport, removable panels, modular joints, cantilevers |
| Electronics | lights/motors, component envelopes, wire routes, power, switches, service access |
| Deliverables | `build.json`, source generator, HTML/PDF, `.ldr`, BOM/inventory report |

Classify each item as:

- **Hard constraint:** failure makes the result unusable.
- **Preference:** optimize when feasible.
- **Decision:** unresolved choice that materially changes the design.
- **Assumption:** temporary choice that must be disclosed.

Ask only for missing information that would materially change the next design action. Do not repeatedly ask for preferences already present in project context.

## 2. Acceptance criteria

Write a short, testable definition of done before modeling. Include the criteria relevant to the request:

- Fits the agreed physical envelope and scale.
- Preserves the subject's key proportions and signature details.
- Meets the requested structural, handling, modularity, interior, and electronics needs.
- Validates with zero errors; warnings are fixed or individually justified.
- Uses intentional instructions when instruction-ready.
- Resolves every element to an exact part when purchase-ready or Studio-ready.
- Includes every requested artifact and a validation summary.

Do not label a build purchase-ready, Studio-ready, or physically proven unless its corresponding criteria have been checked.

## 3. Module plan

For large or complex MOCs, plan three levels:

1. **Master model:** overall coordinates, footprint, terrain/base, and module interfaces.
2. **Modules:** structurally meaningful assemblies that can be built, revised, moved, or installed independently.
3. **Repeated units:** reusable patterns such as windows, trees, columns, seats, or mechanical units.

For each module record:

- id and title;
- purpose and source reference;
- parent/master coordinates;
- support or attachment interface;
- dependencies;
- installation order;
- access/removal requirements;
- electronics crossings;
- expected pieces and dimensions.

The renderer's `sections` are booklet chapters, not a full nested-submodel format. Represent top-level modules as sections. Keep nested/repeated-unit definitions in the generator and preserve them as Studio/LDraw submodels when the chosen export path supports them. Do not claim the current flat `.ldr` export preserves nesting.

## 4. Instruction sequence

Auto-stepping by layer is for drafts. For instruction-ready output:

1. Build stable foundations and cores.
2. Bridge seams before loading them.
3. Group repeated or mirrored assemblies coherently.
4. Build detachable units separately when that improves access or clarity.
5. Install submodels only after their attachment points exist.
6. Route electronics before enclosing them.
7. Add removable panels, interiors, finishes, and landscaping last.

Keep one build idea per step. Use fewer pieces for ambiguous or delicate placements even when the adaptive cap allows more. Add a note whenever the fixed isometric view does not make orientation or attachment clear.

## 5. Exact-part readiness

The custom renderer uses geometry archetypes. They are useful for planning but do not prove that a real part has the rendered shape or connection behavior.

For purchase-ready or Studio-ready work:

- Set `part` explicitly or use a built-in mapping for every brick.
- Verify unfamiliar part numbers against BrickLink/LDraw; never infer them.
- Run `validate`; resolve every `unresolved part` warning.
- Export `.ldr` and require no `WARNING: no LDraw part mapping` lines.
- Group the BOM by exact part and color, not only by bounding-box size.
- Use exact-part inventory entries when available.
- Flag availability, price, and substitutions as unverified unless checked against a current catalog or inventory source.

An `.ldr` file is a handoff artifact. Import it into Studio and inspect orientation, colors, collisions, steps, and part substitutions before calling the model Studio-verified.

## 6. Electronics and serviceability

When lights, motors, or other electronics are requested, plan them before closing the structure. Record:

- component type and physical envelope;
- mounting location and retention method;
- wire path and clearance;
- power source and connector;
- switch/control access;
- removable service panel;
- strain relief and disassembly order.

Represent electronics with clearly labeled placeholders when exact geometry is unavailable. Do not count a placeholder as a verified LEGO/LDraw element.

## 7. Delivery checklist

Deliver the requested artifacts plus a concise evidence report:

- selected scale, dimensions, and piece count;
- hard constraints met;
- validation command/result;
- warning list with disposition;
- unresolved or approximate parts;
- outputs generated and visually inspected;
- exact versus approximate claims;
- remaining decisions;
- next useful design decision or achievable work-session task, when requested.

For large projects, also include a module index, module-level piece totals, installation order, and source-reference map.
