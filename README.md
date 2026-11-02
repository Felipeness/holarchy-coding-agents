# Holarchy on Paper, Hierarchy in Code

**An industrial experience report on a Koestler-inspired multi-agent system for ticket-to-pull-request automation.**

Luis Felipe Soares Coelho, independent researcher, Brazil.

[Read the paper (PDF)](paper/main.pdf)

## Abstract

Autonomous coding agents are moving from single sessions toward systems of agents that react to tickets and events and return pull requests. A recurring architectural answer is a flat router/worker split, recently proposed again by DeepSeek's "super-agent" design. This report covers an alternative built and deployed at a Brazilian B2B SaaS company between March and August 2026: a multi-agent system designed as a *holarchy* in Koestler's sense, where each agent (*holon*) is at once an autonomous whole and a cooperative part.

The system takes an issue-tracker ticket, localises code through a seven-layer search, runs fifteen parallel LLM runners with distinct repair strategies, ranks them with deterministic scores, and opens a PR. The paper describes two generations of the system, a code audit comparing the intended holarchy with what the code actually does, and field data:

- 22 PRs on 11 tickets in 6 repositories, opened by 4 engineers, of which 2 PRs (one ticket) were merged.
- 17 autonomous investigation PRs.
- 9 ticket analyses.

Two properties of the holarchy survived production:

- delegated authority over an irreversible action;
- an upward channel through which runner behaviour revises the parent's diagnosis.

Peer negotiation, refusal and veto did not survive.

## Timeline of public artefacts

| Date | Artefact |
|---|---|
| 2026-03-08 | [The Whole and the Part](https://github.com/Felipeness/the-whole-and-the-part), an open-source book on holonomic software architecture |
| 2026-03-17/18 | Holon prototypes: [claude-holonomic](https://github.com/Felipeness/claude-holonomic), [holon-daedalus](https://github.com/Felipeness/holon-daedalus), [holon-argos](https://github.com/Felipeness/holon-argos) |
| 2026-03-20 to 04-07 | First generation (Brain, Daedalus, Argos), used on production repositories |
| 2026-05-02 to 08-18 | Second generation (Nous meta-holon) |
| 2026-10-31 | DeepSeek publishes its super-agent (router/worker) design |
| 2026-11-02 | This report |

## Build

The paper is plain LaTeX with the IEEE conference template.

```sh
cd paper
tectonic main.tex      # or: pdflatex main && bibtex main && pdflatex main && pdflatex main
```

## Cite

See [CITATION.cff](CITATION.cff).

## License

The text and figures are licensed under [CC BY 4.0](LICENSE).
