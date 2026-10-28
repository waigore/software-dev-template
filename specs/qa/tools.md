# QA tools

Authoring rules: [`.agents/specs/rules/qa/tools.md`](../../.agents/specs/rules/qa/tools.md).

## Drive

The agent drives through **both** user-facing controls (per UX) and debug commands (below).

## Debug UI (Must)

| ID | Capability | Agent can |
|----|------------|-----------|
| `DBG.1` | Pause / resume | Halt and continue the session without ending it |
| `DBG.2` | Inspect product state | Read key state needed to judge product and UX story outcomes |
| `DBG.3` | Jump to scenario / phase | Enter a named scenario or flow phase so a protocol can start in situ |
| `DBG.4` | Story-ID overlay | See which product or UX story IDs are active or under test |

## Telemetry (Must)

Every QA-relevant event carries at least:

| ID | Field | Meaning |
|----|-------|---------|
| `TEL.1` | Event name | What happened |
| `TEL.2` | Timestamp | When it happened in the session |
| `TEL.3` | Session / build id | Which run and build produced the event |
| `TEL.4` | Story ID | Product or UX story ID when known; omit only when not applicable |
| `TEL.5` | Outcome / severity hint | Pass, fail, or severity cue for correlation |

Sinks and formats are ADR decisions. Seams live in technical verification.

## Capture affordance

A running QA session must be observable. A headless session still yields inspect, telemetry, and logs. A graphical session can capture screenshots when a protocol requires UI evidence. Artifact rules live in [`evidence.md`](evidence.md).

## Situational

| ID | Capability | When it applies |
|----|------------|-----------------|
| `SIT.1` | Deterministic seed | Protocol needs a repeatable start state |
| `SIT.2` | Input replay | Protocol needs recorded input playback |
| `SIT.3` | State dump | Protocol needs a full state snapshot beyond `DBG.2` |

## Constraints on ADR and technical

Accepted ADRs and technical design (including verification seams and observability) must realize every Must row. Each Situational row a protocol cites must be realized before that protocol is required at acceptance.
