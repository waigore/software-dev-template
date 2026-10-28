# Authoring rules: scenario

Read this before editing `specs/product/scenarios/_template.md` or `specs/product/scenarios/<name>.md`. Do not copy these rules into the spec.

Also read [product.md](product.md) and [ids.md](ids.md). Stories follow [story.md](story.md).

Copy the template to `scenarios/<kebab-name>.md`, one file per scenario. Do not fill the template in place.

A scenario is a defined setup plus worked walkthroughs that show the product in action. Scenarios prove that specs combine. If a walkthrough cannot be resolved step by step from the other specs, those specs are incomplete.

How many scenarios are needed follows spec depth, per [depth.md](../depth.md).

## Header

- **Kind**: use case, edge walkthrough, onboarding, or other.
- **Flow**: a link, or "N/A".
- **Serves**: vision qualities and definition scope items.

## Setup

Starting state as values of named product fields. Participants (roles or entities), as links. The configuration in effect. Objectives. Constraints, such as time, quotas, or forbidden actions. End outcomes (success, failure, cancel).

## Walkthroughs

At least one. Include a success path and a failure path when both are possible. Step IDs are `W<walkthrough>.<step>`, such as `W1.1`.

Columns: what the user does (a verb or a product event), how the product responds (link the rule and cite its qualified ID), and the resulting state. Then the outcome and the user experience at key moments.

Each step's outcome follows its trigger. Scenario-walkthrough stories may chain When/Then pairs in this step order.

## Edge cases covered

Unusual situations this scenario deliberately exercises, or "None".

## Specs exercised

Links to every feature, entity, flow, and condition the scenario depends on.
