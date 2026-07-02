# cloud-itonami-isco-4120

Open Occupation Blueprint for **ISCO-08 4120**: Secretaries (general).

This repository designs a forkable OSS business for an independent secretary: a document-handling robot performs physical filing and mail sorting under a governor-gated actor, so the practice keeps its own correspondence and scheduling records instead of renting a closed office-support SaaS.

## Robotics premise

All cloud-itonami verticals are designed on the premise that a **robot performs
the physical domain work**. Here a document-handling robot performs physical filing, mail sorting and meeting-room preparation under an actor that proposes
actions and an independent **Secretarial Governor** that gates them. The governor never
dispatches hardware itself; `:high`/`:safety-critical` actions (such as
disclosing confidential correspondence, or committing an employer to a contract without authorization) require human sign-off.

A live sample of the operator console (robotics safety console, shared template) is rendered in [docs/samples/operator-console.html](docs/samples/operator-console.html) — pure-data HTML output of `kotoba.robotics.ui`.

## Core Contract

```text
client mandate + calendar scope + confidentiality policy
        |
        v
Secretarial Advisor -> Secretarial Governor -> correspond/file, or human sign-off
        |
        v
robot actions (gated) + operating records + audit ledger
```

No automated advice can dispatch a robot action the governor refuses, suppress
an operating record, or disclose sensitive data without governor approval and
audit evidence.

## Capability layer

Resolves via [`kotoba-lang/occupation`](https://github.com/kotoba-lang/occupation)
(ISCO-08 `4120`). Required capabilities:

- :robotics
- :forms
- :identity
- :audit-ledger
- :bpmn

See [`docs/business-model.md`](docs/business-model.md) and
[`docs/operator-guide.md`](docs/operator-guide.md).

## License

AGPL-3.0-or-later.
