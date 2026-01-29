name: Bug
description: Defect or regression in behavior
title: "[Bug] "
labels: ["type:bug", "status:triage"]
body:
  - type: textarea
    id: summary
    attributes:
      label: Summary
      description: Short description of the bug.
    validations:
      required: true

  - type: textarea
    id: context
    attributes:
      label: Context / Impact
      description: Why this matters, who is affected, and severity.
    validations:
      required: true

  - type: textarea
    id: steps
    attributes:
      label: Steps to reproduce
      description: Provide clear steps to reproduce the issue.
      value: |
        1. 
        2. 
        3. 
    validations:
      required: true

  - type: textarea
    id: expected
    attributes:
      label: Expected behavior
      description: What should have happened.
    validations:
      required: true

  - type: textarea
    id: actual
    attributes:
      label: Actual behavior
      description: What happened instead.
    validations:
      required: true

  - type: textarea
    id: evidence
    attributes:
      label: Evidence / Logs
      description: Logs, screenshots, stack traces, or relevant links.
    validations:
      required: false

  - type: textarea
    id: workaround
    attributes:
      label: Workaround
      description: Temporary mitigation, if any.
    validations:
      required: false

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