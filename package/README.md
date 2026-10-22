# Agent Safety Atlas: paper package (analysis A7.1, data release R071)

Inputs and scripts that recompute every value of the report's paper section (findings.json, key "paper") without full
texts, content vectors, or network access:

    python3 scripts/recompute_paper.py --snapshot .      (Python 3.10 or later, numpy)

The script rebuilds the analyses from paper-inputs/ and compares the result with findings.json value by value.

- paper-inputs/works.jsonl: one line per analysed work (date and its precision, citations, authors as recorded, research
  lines, references inside the Atlas, reference years, matched classic reference titles, and only the title and abstract
  phrases that the analyses' text rules match)
- paper-inputs/lines.json: research lines and algorithmic clusters with their members
- paper-inputs/benchmarks.json, benchmark-routes.jsonl: benchmark names, uses (with the supporting sentence) and mentions
- paper-inputs/labels/: model-produced labels and readings as produced, each with its quoted evidence
- paper-inputs/citations.jsonl: the citations whose intent was read, with their citing sentences
- paper-inputs/repositories/: repository records reduced to the fields the analyses read
- MANIFEST.json: file hashes of the analysis version's snapshot

Full texts, embeddings, and repository README files are not included.
