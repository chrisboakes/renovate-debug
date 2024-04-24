# Replicate renovate bug

When `pnpm overrides` has a dependency out of date, the job fails to run:

```
DEBUG: updateDependency error (branch="renovate/undici-6.x")
{
  "err": {
    "message": "Cannot read properties of undefined (reading 'undici')",
    "stack": "TypeError: Cannot read properties of undefined (reading 'undici')\n    at updateDependency (/usr/local/renovate/lib/modules/manager/npm/update/dependency/index.ts:162:58)\n    at getUpdatedPackageFiles (/usr/local/renovate/lib/workers/repository/update/branch/get-updated.ts:221:30)\n    at processTicksAndRejections (node:internal/process/task_queues:95:5)\n    at processBranch (/usr/local/renovate/lib/workers/repository/update/branch/index.ts:460:19)\n    at writeUpdates (/usr/local/renovate/lib/workers/repository/process/write.ts:166:17)\n    at update (/usr/local/renovate/lib/workers/repository/process/extract-update.ts:214:11)\n    at Object.renovateRepository (/usr/local/renovate/lib/workers/repository/index.ts:87:19)\n    at attributes.repository (/usr/local/renovate/lib/workers/global/index.ts:217:11)\n    at start (/usr/local/renovate/lib/workers/global/index.ts:202:7)\n    at /usr/local/renovate/lib/renovate.ts:18:22"
  }
}
```
