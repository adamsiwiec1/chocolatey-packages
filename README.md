# chocolatey-packages (example)

Example tree of [Chocolatey](https://chocolatey.org/) package sources for use
with [foss-template](https://github.com/adamsiwiec1/foss-template).

## Why this repo exists

Chocolatey packages are built from a **nuspec + tools scripts**, then pushed to
chocolatey.org (or a private feed). Keeping those sources in a dedicated repo
keeps the app repository smaller and matches how many orgs maintain multiple
CLIs.

Templates: [`foss-template/packaging/chocolatey`](https://github.com/adamsiwiec1/foss-template/tree/main/packaging/chocolatey).

## Layout

```
INSERT_REPO/
  INSERT_REPO.nuspec
  tools/chocolateyinstall.ps1
```

## Publish

```bash
choco pack INSERT_REPO/INSERT_REPO.nuspec
choco push INSERT_REPO.*.nupkg --source https://push.chocolatey.org/ --api-key "$CHOCO_API_KEY"
```

Users: `choco install INSERT_REPO` (after community moderation on first publish).
