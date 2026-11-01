# Symbolic-Guided Regeneration (SGR)

Website for the SGR journal paper.

Live site: https://finansiapurba-cae.github.io/6f-knowledge-graph-lab/

When a large language model repairs or updates a building's knowledge graph, how do we make sure it does not make things up? SGR lets the model propose a patch, checks the patched graph against SHACL rules, and feeds every violation back until the graph passes or a reviewer takes over.

## What is on the site

1. **Story:** a chiller trips; which rooms get hot? Why the answer depends on a correct graph, and why as-built drawings leave gaps.
2. **Try it on one unit:** inject a defect into the graph around one fan coil unit, run SHACL-style validation, and approve or reject a repair.
3. **The SGR loop:** step through the patch data flow: validate, propose a patch, revalidate, retry up to K, escalate or write back.
4. **Answer key, pipeline, evaluation design, data and code availability.**

The paper's title, authors, abstract, results and citation will be added from the paper.

## Notes

- `index.html` is the whole site in one file. No build step, no server, no API key.
- The interactive parts are illustrations. They do not run an LLM, a SHACL engine or a database, and they report no experimental results.
- The as-built drawings and the baseline graph are internal and are not part of this repository.
