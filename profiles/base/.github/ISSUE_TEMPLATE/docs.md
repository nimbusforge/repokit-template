name: Docs
description: Documentation updates, clarifications, or additions
title: "[Docs] "
labels: ["type:docs", "status:triage"]
body:
  - type: textarea
    id: context
    attributes:
      label: Context / Problem
      description: What documentation is missing, unclear, or outdated.
    validations:
      required: true

  - type: textarea
    id: goals
    attributes:
      label: Goals
      description: Bullet list of outcomes.
      value: |
        - 
    validations:
      required: true

  - type: textarea
    id: non_goals
    attributes:
      label: Non-goals
      description: Explicitly out of scope.
    validations:
      required: false

  - type: textarea
    id: acceptance
    attributes:
      label: Acceptance criteria
      description: Concrete checks (Given/When/Then or bullets).
      value: |
        - 
    validations:
      required: true

  - type: textarea
    id: dependencies
    attributes:
      label: Dependencies / Blockers
      description: External dependencies or open questions.
    validations:
      required: false

  - type: textarea
    id: plan
    attributes:
      label: Agent plan (tasks/subtasks)
      description: Maintained during implementation.
      value: |
        - [ ] Task 1
        - [ ] Task 2
        - [ ] Task 3
    validations:
      required: false

  - type: dropdown
    id: status
    attributes:
      label: Status
      description: Represents current implementation status.
      options:
        - status:triage
        - status:in-progress
        - status:blocked
        - status:review
        - status:done
    validations:
      required: true

  - type: dropdown
    id: priority
    attributes:
      label: Priority
      options:
        - priority:P0
        - priority:P1
        - priority:P2
        - priority:P3
    validations:
      required: true

  - type: dropdown
    id: size
    attributes:
      label: Size
      options:
        - size:S
        - size:M
        - size:L
    validations:
      required: false

  - type: dropdown
    id: risk
    attributes:
      label: Risk
      options:
        - risk:low
        - risk:medium
        - risk:high
    validations:
      required: false

  - type: dropdown
    id: area
    attributes:
      label: Area
      multiple: true
      options:
        - area:core
        - area:api
        - area:persistence
        - area:cli
        - area:infra
        - area:docs
        - area:workflow
    validations:
      required: false