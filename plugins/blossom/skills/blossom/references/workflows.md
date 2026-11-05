# Blossom workflows

Start with `help` and `whoami`. Resolve names through lists and inspect the
chosen IDs. Use `help(command:)` for arguments instead of guessing payloads.

## What's running

Use `location_list`, `app_list`, and `environment_list` to establish inventory
and health. Inspect selected Environments with `environment_show`; use
`runtime_issue_list` and `runtime_issue_show` for active issues. State which
Locations were checked. Do not mutate resources while answering an inventory
question.

## Diagnose a deployment

Use `environment_activity` or `activity_list` to find the relevant Activity,
then `activity_show` and bounded `activity_logs`. Use `release_list` and
`release_show` to connect it to a Release. Check `environment_show`,
`service_list`, and runtime issues for present health. Use `logs` only when
recent application output helps explain the failure; redact secret values if
they appear. Explain observed facts separately from suspected causes. A
diagnosis request alone does not authorize rollback, restart, or redeploy.

## Preview and deploy

Collect the Git repository, intended Location, Environment, and required
Services. `quickstart_list` can supply an existing starting point. Consult
`help(command: "app_plan_preview")`, construct the plan, then preview it without
saving. Summarize resources and Capacity effect. Stop after the preview if
that is all the user requested.

For an authorized deployment, use `app_plan_deploy` with the reviewed plan or
an existing plan ID. For an existing Environment, use `environment_deploy`
after inspecting its current configuration. Follow the returned Activity with
`activity_wait` until terminal, honoring cancellation or a user time limit.
`finished` is not synonymous with success: inspect the final status. Report
the actual Environment URL and health from tools, not a guessed hostname.

## Configure or scale

Read the relevant Environment and Service before changing them. Consult the
specific tool's help, apply the requested change, follow any returned Activity,
and read back the resource. Configuration may be pending until a deploy;
`environment_pending_changes_show` distinguishes saved changes from running
behavior. Do not add a deployment when the user only asked to save config.

## Managed Data

Use the database or cache instance list and show tools to select the target.
Inspect backup and restore details before recovery work. Restore, delete,
switchover, and credential rotation can affect availability or data: follow
the tool's confirmation contract and the user's exact scope. Follow Activities
and inspect the resulting resource. Open returned Blossom links when a step
needs credentials or a local file; never invent a file-upload capability.
