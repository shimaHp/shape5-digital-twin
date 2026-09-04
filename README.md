# SHAPE-5 Digital-Twin-Style Proof of Concept

An interactive proof-of-concept dashboard developed for a doctoral application to the
**SHAPE-5** project (*Smart Human-centred Architectures for Process Efficiency in
Industry 5.0*) at Birmingham City University.

**Live demo:** https://shimahp.github.io/shape5-digital-twin/

## What it demonstrates

The dashboard simulates an industrial monitoring scenario and demonstrates the
core idea of the proposed research: turning **live simulated operational context**
into a **graded level of decision support**, while keeping the final decision with
the worker.

It follows a four-layer pipeline that reflects the proposed architecture:

`Machine / Sensor Data → IoT Integration → Context & Decision → Worker Support`

The system uses contextual information including:

- machine state
- temperature
- vibration
- waiting time
- simulated worker workload

A transparent rule-based policy then determines an appropriate level of support:

`Monitor → Inform → Warn → Recommend → Escalate`

The support level is calculated dynamically from the current context rather than
being hard-coded for each scenario.

Three scenarios — **Normal, Degrading and Critical** — allow the user to observe
how changes in operational conditions affect the level of support provided.

Support-level changes are also recorded together with the associated system
rationale.

## Human-centred idea

The purpose of the prototype is not to maximise automation or provide as much
guidance as possible.

Instead, it illustrates the research question at the centre of the proposed PhD:

> How much support should an intelligent industrial system provide in a given
> context while still preserving worker autonomy and decision authority?

When risk is low, the system provides minimal intervention. As operational risk
increases, it progressively moves from information and warning toward
recommendation or escalation.

The worker remains in the decision loop throughout.

## Important scope notes

- **Simulated data:** All machine, sensor and worker-context values are simulated.
  The prototype is not connected to real production equipment.

- **Simulated worker workload:** Worker workload is currently an illustrative
  contextual variable assigned to each scenario rather than a measured human
  state. In the proposed PhD, appropriate empirical measures would be identified
  through the research design.

- **Illustrative decision policy:** The thresholds and rules used to select support
  levels are intended to demonstrate the mechanism. They have not been empirically
  validated or optimised.

- **Digital-twin-style prototype:** This prototype provides a dynamic digital
  representation of a simulated manufacturing process, but it is not intended to
  claim a complete or validated industrial digital twin.

- **Preliminary work:** The prototype demonstrates technical feasibility and the
  proposed data-to-context-to-support workflow. It is not the final research system.

## How it works

The prototype is implemented as a single self-contained `index.html` file using:

- HTML
- CSS
- vanilla JavaScript

There are no external dependencies and no build step.

At runtime:

1. simulated machine and contextual values are updated continuously;
2. the current context is evaluated by a transparent rule-based policy;
3. the policy selects one of five support levels;
4. the interface updates the recommendation, rationale and human-centred
   explanation;
5. changes are recorded in the recent-events log.

Values gradually move toward each scenario's baseline with small random
variations, so the dashboard changes continuously rather than displaying fixed
values.

## Running locally

Download or clone the repository and open:

`index.html`

in any modern web browser.

No server, package installation or build process is required.

## Research context

This prototype was created as preliminary work for a proposed PhD on
**human-centred IoT architecture and adaptive decision support in Industry 5.0
manufacturing SMEs**.

Its purpose is to explore how operational and human context could be used to
provide proportionate decision support without unnecessarily reducing worker
control.
