# rapla-nightly

Nightly test builds of [rapla/rapla](https://github.com/rapla/rapla) `master`. **Not for production.**

- JAR: https://github.com/rapla/rapla-nightly/releases/download/nightly/rapla.jar
- Image: `ghcr.io/rapla/rapla:nightly`

Built and published only by `.github/workflows/nightly.yml` in this repository, with its own `GITHUB_TOKEN` — no stored secrets. Only the organization owners have access here.

Verify a download:

```sh
gh attestation verify rapla.jar --repo rapla/rapla-nightly \
  --signer-workflow rapla/rapla-nightly/.github/workflows/nightly.yml --source-ref refs/heads/main
gh attestation verify oci://ghcr.io/rapla/rapla:nightly --repo rapla/rapla-nightly \
  --signer-workflow rapla/rapla-nightly/.github/workflows/nightly.yml --source-ref refs/heads/main
```
