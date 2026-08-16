# SSIS shared GitHub Actions

Reusable workflows for `ssis-edu`.

The security-sensitive workflow is:

`/.github/workflows/deploy-cloud-run.yml`

Teacher app repositories call this workflow from their own `.github/workflows/deploy.yml`.

Apps use `cloudrun-runtime@<project>` by default. An app that needs server-side
data access may pass `runtime-service-account`; that identity must already
exist, carry only the required runtime roles, and grant the deploy identity
`roles/iam.serviceAccountUser` on that service account. The input is optional so
existing callers remain byte-for-byte equivalent in authority.

Maintained by `@ssis-edu/it` with DLS review visibility.
