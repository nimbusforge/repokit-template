name: Story
description: User-facing change or feature
title: "[Story] "
labels: ["type:feature"]
body:
  - type: textarea
    id: context
    attributes:
      label: Context / Problem
      description: What is broken/missing and why it matters.
    validations:
      required: true

  - type: textarea
    id: goals
    attributes:
      label: Goals
      description: Bullet list of outcomes.
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
    validations:
      required: true

  - type: textarea
    id: plan
    attributes:
      label: Agent plan (tasks/subtasks)
      description: Maintained by the agent during implementation.
      value: |
        - [ ] Task 1
        - [ ] Task 2
        - [ ] Task 3
    validations:
      required: false

  - type: dropdown
    id: priority
    attributes:
      label: Priority
      options:
        - prio:p0
        - prio:p1
        - prio:p2
    validations:
      required: true

  - type: dropdown
    id: area
    attributes:
      label: Area
      multiple: true
      options:
        - area:cli
        - area:template
        - area:workflow
        - area:ci
        - area:docs
        - area:domain
        - area:api
        - area:persistence
    validations:
      required: false
