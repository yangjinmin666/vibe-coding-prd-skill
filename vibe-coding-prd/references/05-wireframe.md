# Wireframe And Prototype Frame

Create low-fidelity structure, not visual design.

## Required Content

- page/interface list
- navigation relationship
- core page wireframes
- key controls and buttons
- empty/loading/error/success/permission states
- main click path
- desktop/mobile difference only if relevant

## ASCII Wireframe Rule

Use simple text blocks:

```text
┌────────────────────────────────────────────┐
│ Header: Logo     Search        User menu  │
├───────────────┬────────────────────────────┤
│ Left nav      │ Main work area             │
│ - Item        │ [Primary input]            │
│ - Item        │ [Result / table / editor]  │
│               │ [Primary action]           │
└───────────────┴────────────────────────────┘
```

## Core Flow

Write:

1. user enters from ...
2. user clicks ...
3. system shows ...
4. user confirms ...
5. system saves/exports/generates ...

## States Checklist

For every core page or module, include relevant states:

- empty
- loading
- processing
- success
- failed
- validation error
- permission denied
- retry available

## Confirmation

After wireframe, ask the gate 4 question from `02-confirmation-gates.md`. Do not proceed to final detailed PRD if the core layout is unconfirmed.
