name: frameworks.devops.intel-devops-framework.lib.shared
guid: 3242e1e4-b82d-4b04-aef5-706e666a3e80
owners:
- bhadur.a.sm@intel.com

topics:
- automation
description: idf common shared functionality
permissions:
  write:
  - IDSE Writers
  admin:
  - IDSE Admins
allow-merge-commit: false
allow-squash-merge: true
allow-rebase-merge: true
branch-protection-rules:
- patterns:
  - *
  requires-approving-reviews: false
  requires-status-checks:
    enabled: false
    requires-strict-status-checks: false
  restricts-pushes:
    enabled: false
  is-admin-enforced: false
webhooks:
  retry:
    total-attempts: 3
  endpoints:
  - description: Trigger Build
    channel: it-jenkins
    url: http://10.114.164.207:8080/github-webhook/
    events:
      matching-filters:
      - event: push
