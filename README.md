# ressim-runner
a Cloud-Compute plugin for HEC-ResSim on Linux based on the cc-java-sdk


# CI/CD for the ressim-runner container image

Publishing a GitHub release builds `Dockerfile.prod` and pushes the image to
`ghcr.io/usace-cloud-compute/ressim-runner`. Triggered by `release: published`, one
job, five steps: work out the tags → buildx → login → build and push → pull the
pushed tag back and smoke test it. Nothing here requires a change to
`Dockerfile.prod`.

For a release tagged `v3.5.1` this publishes three tags: `3.5.1`, `latest`, and
the full commit SHA. Consumers should pin the digest, not the tag.

