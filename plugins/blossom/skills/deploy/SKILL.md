---
description: Preview and deploy a Git repository or an existing Environment on Blossom, then follow it to a live URL.
argument-hint: "[Git repository URL or Environment]"
disable-model-invocation: true
---

# Deploy on Blossom

Follow the Blossom skill in this plugin, including its rules for changes.

1. Call `whoami`. Report the Account and access. Deploying needs Full access;
   with Read only, still preview, then explain how to reconnect with Full
   access.
2. Resolve the target from $ARGUMENTS:
   - A Git repository, or nothing in a project with a Git remote: match the repository
     and subfolder with `catalog_list` filtered to kind quickstart.
     Preview the matching key or the custom repository configuration using
     `app_plan_preview`. Identify any assumptions before seeking approval.
   - An existing Environment: inspect it with `environment_show` and
     `environment_pending_changes_show`.
3. Show what will be created or changed, where it runs, and the Capacity
   effect. Stop for preview-only requests. Otherwise ask for confirmation.
4. With Full access and confirmation, deploy the exact reviewed plan with
   `app_plan_deploy` or the reviewed Environment with `environment_deploy`.
   After reconnecting, check `whoami` again. If the Account or the plan
   changed, preview again and get confirmation for that target.
   Follow the returned Activity with bounded `activity_wait` calls until it
   finishes, and check the final status.

Report the live URL from the tools, the Environment's health, and the Activity
outcome. If the deploy fails, show the first error from `activity_logs` and
suggest a fix. If Blossom says billing or Blossom Cloud activation is needed,
relay its message and link; never change billing yourself.
