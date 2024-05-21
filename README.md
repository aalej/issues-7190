# Repro for issue 7190

## Versions

firebase-tools: v13.9.0

## Steps to reproduce

1. Run `export GOOGLE_APPLICATION_CREDENTIALS=./service-account.json`
   - The service account has no permissions
1. Run `firebase deploy --only hosting --non-interactive --project PROJECT_ID`
   - Raises an error message:

```
Error: Assertion failed: resolving hosting target of a site with no site name or target name. This should have caused an error earlier
```

## Notes

Also setup Firestore rules for deployment as reference. Running the steps below:

1. Run `export GOOGLE_APPLICATION_CREDENTIALS=./service-account.json`
   - The service account has no permissions
1. Run `firebase deploy --only firestore --non-interactive --project PROJECT_ID`
   - Raises an error message:

```
Error: HTTP Error: 403, The caller does not have permission
```
