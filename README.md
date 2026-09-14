# rapla-release

Releases and nightly test builds of [rapla/rapla](https://github.com/rapla/rapla). Only the maintainer can publish here.

## Nightly (`master`, not for production)

- JAR: https://github.com/rapla/rapla-release/releases/download/nightly/rapla.jar
- Image: `ghcr.io/rapla/rapla:nightly`

Built and published only by `.github/workflows/nightly.yml` in this repository, with its own `GITHUB_TOKEN` — no stored secrets.

Verify a download:

```sh
gh attestation verify rapla.jar --repo rapla/rapla-release \
  --signer-workflow rapla/rapla-release/.github/workflows/nightly.yml --source-ref refs/heads/main
gh attestation verify oci://ghcr.io/rapla/rapla:nightly --repo rapla/rapla-release \
  --signer-workflow rapla/rapla-release/.github/workflows/nightly.yml --source-ref refs/heads/main
```

Builds published before the rename from `rapla-nightly` carry attestations for `rapla/rapla-nightly`.

## Releases

New releases are published here. Releases up to 2.0 remain at [rapla/rapla releases](https://github.com/rapla/rapla/releases).
