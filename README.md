# Brain Worker Bootstrap

Minimal checkout for unattended Claude Code Routines that work for Cloud Brain.

This repository is intentionally **not** the Brain application. It contains no application code, project data, credentials, API tokens, or deployment configuration.

## What it provides

The committed `.claude/settings.json` allows a cloud Routine to use the `cloud-brain` MCP tools without stopping for interactive approval.

## Routine setup

1. Create a cloud Claude Code Routine.
2. Attach this repository on the default `main` branch.
3. Attach and authorize the `cloud-brain` connector.
4. Use the current permanent Brain Worker prompt. It must not name a bin, project, packet, or research subject.
5. Add an API trigger so Brain can start the Routine when work is ready.
6. Store the trigger bearer token only in the deployment secret store. Never commit or paste it here.

The Routine checks in with Brain, accepts only the bin Brain leases it, drains that bin according to its manifest, and asks Brain for another assignment.

## Security boundary

- Never add secrets, tokens, credentials, private project data, or application source code.
- Worker accounts do not need access to the main Brain repository.
- Repository access alone grants no Brain authority; the connector's worker identity and Brain-side scopes control what the Routine may do.
- Keep the worker prompt generic. Brain—not the Routine—chooses the work.
