---
version: 1
mode: solo
models:
  research: claude-code/claude-sonnet-4-6
  planning: github-copilot/claude-opus-5.5
  discuss: claude-code/claude-opus-4-8
  execution: claude-code/claude-opus-5-5
  completion: claude-code/claude-sonnet-4-6
  validation: claude-code/claude-sonnet-5
  subagent: claude-code/claude-opus-4-6
  uat: claude-code/claude-haiku-5-5
skill_staleness_days: 0
uat_dispatch: false
unique_milestone_ids: false
budget_enforcement: pause
context_pause_threshold: 50
notifications:
  enabled: true
  local_bell: false
  on_complete: true
  on_error: true
  on_budget: true
  on_milestone: true
  on_attention: true
cmux:
  enabled: false
  notifications: false
  sidebar: false
  splits: false
  browser: false
git:
  auto_push: true
  push_branches: true
  snapshots: true
  pre_merge_check: auto
  merge_strategy: merge
  isolation: worktree
dynamic_routing:
  enabled: true
  escalate_on_failure: true
  budget_pressure: true
  cross_provider: true
  hooks: true
  capability_routing: true
  allow_flat_rate_providers: true
  tier_models:
    light: claude-haiku-4-5
    standard: claude-haiku-4-5
    heavy: claude-sonnet-4.6
uok:
  enabled: true
  legacy_fallback:
    enabled: false
  gates:
    enabled: true
  model_policy:
    enabled: true
  execution_graph:
    enabled: true
  audit_unified:
    enabled: true
  plan_v2:
    enabled: true
  gitops:
    enabled: true
    turn_action: commit
    turn_push: false
token_profile: budget
phases:
  skip_slice_research: false
  skip_milestone_validation: false
  reassess_after_slice: true
  require_slice_discussion: true
  mid_execution_escalation: true
  progressive_planning: true
parallel:
  enabled: true
  merge_strategy: per-slice
  auto_merge: confirm
slice_parallel:
  enabled: true
gate_evaluation:
  enabled: true
  task_gates: true
auto_visualize: true
auto_report: true
verification_auto_fix: false
verification_max_retries: 3
enhanced_verification: true
enhanced_verification_pre: true
enhanced_verification_post: true
enhanced_verification_strict: false
discuss_preparation: true
discuss_web_research: true
discuss_depth: thorough
context_selection: smart
context_management:
  observation_masking: true
show_token_cost: true
experimental:
  rtk: false
workspace:
  mode: parent
  repositories:
    orchestrator-ceo:
      path: ./Orchestrator-CEO
      role: Orchestrate workflows and is launching agents
      commit_policy: auto
---

# GSD Skill Preferences

See `~/.gsd/agent/extensions/gsd/docs/preferences-reference.md` for full field documentation and examples.
