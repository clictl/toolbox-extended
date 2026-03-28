# clictl Extended Toolbox

Full-action tool specs for CLIs that include destructive and write actions. These specs cover actions like stop, rm, delete, apply, and exec that are not in the official toolbox's safe subset.

> **Note:** These specs have been merged into the main [clictl toolbox](https://github.com/clictl/toolbox) with the `destructive` tag. You can use either repo, but the main toolbox is recommended. Workspace ACL rules control access to destructive actions.

## What's Inside

| Tool | Actions |
|------|---------|
| docker | ps, logs, inspect, start, stop, rm, exec, pull, images, volumes |
| git | status, log, diff, branch, checkout, commit, push, pull, stash |
| homebrew | search, info, list, install, uninstall, update, upgrade |
| kubectl | get, describe, logs, apply, delete, scale, rollout, exec |
| redis | ping, info, keys, get, set, del, flushdb |
| terraform-cli | init, plan, apply, destroy, state, output |

## Structure

```
toolbox/
  d/docker/docker.yaml
  g/git/git.yaml
  h/homebrew/homebrew.yaml
  k/kubectl/kubectl.yaml
  r/redis/redis.yaml
  t/terraform-cli/terraform-cli.yaml
```

## Usage

```bash
# Add this toolbox
clictl toolbox add https://github.com/clictl/toolbox-extended

# Or use the main toolbox which includes these specs
clictl toolbox update
```

## Security

Workspace admins can control access to destructive actions via permission rules:

```
DENY tag:destructive group:null      # Block all destructive actions
ALLOW tag:destructive group:devops   # Allow for devops team
```

## Links

- [Main Toolbox](https://github.com/clictl/toolbox) - Official clictl toolbox (includes these specs)
- [clictl.dev](https://clictl.dev) - Website
- [www.soapbucket.org](https://www.soapbucket.org) - Soap Bucket LLC
