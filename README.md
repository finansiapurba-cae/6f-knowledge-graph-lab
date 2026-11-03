# SGR building information review

A demonstration of how SGR (Symbolic-Guided Regeneration) helps facility operators govern changes to building information.

Live site: https://finansiapurba-cae.github.io/6f-knowledge-graph-lab/

The knowledge graph stores the building information; this website makes it understandable and lets an operator review each proposed correction before anything changes.

## The knowledge graph inside

The building information for the demo is stored in the page as a small knowledge graph (Brick and RealEstateCore terms, about 77 triples at the start). Everything on the Review tab is read from it:

- the rule checks run on the stored triples every time, so a fixed problem disappears on its own;
- an approved correction is written into the graph, with a decision record (reviewer, time, answer, reason, evidence) in PROV-O terms;
- rejections and investigation requests are recorded too, without changing the building data;
- the **Knowledge graph** tab shows the whole graph as a diagram, the triples of any node, and the live graph as Turtle.

## The review flow

| Step | What the operator sees or does | What happens behind the website |
|---|---|---|
| 1. Select equipment | Selects "AHU-02" | The equipment and its links are read from the knowledge graph |
| 2. See a problem | "AHU-02 is missing its location." | A SHACL rule requiring a location reports a violation |
| 3. Review a proposed correction | "Suggested location: Mechanical Room 01", with the drawing and record behind it | SGR proposes a patch from the evidence and pre-checks it |
| 4. Make a decision | Answers a question ("I don't know" is allowed), then approves, rejects, or requests further investigation | Review rules apply: an answer that contradicts the evidence blocks approval, and a reason is required |
| 5. See the result | "Location updated", with who approved it and why | The change is validated again, recorded with provenance, and saved; a site check becomes a work order |

An operator's answer alone never makes a correction trusted. An optional view shows the stored connections (for example AHU-02 supplies air to VAV-03), and a "What the system does" panel shows the SHACL rule, the patch and the provenance record for each step.

## Notes

- `index.html` is the whole site in one file. No build step, no server, no API key.
- The graph and the rule checks run in the page (JavaScript checks written like SHACL shapes). The proposed corrections, evidence and work orders are scripted. No language model, SHACL engine or database runs, and nothing is sent anywhere.
- AHU-02, VAV-03, Mechanical Room 01 and Room R6-12 are example data. FCU-6F-10, CH-1 and room R6-08 follow the documented 6F baseline graph.
