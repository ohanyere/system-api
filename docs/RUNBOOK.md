# Runbook

## Service

- Name: `system-api`
- Team: `Developer Experience`
- Owner: `mooref068@gmail.com`
- Cost center: `developer-experience`

## First Checks

```bash
kubectl get rollout system-api -n system-api-dev
kubectl get pods -l app.kubernetes.io/name=system-api -n system-api-dev
kubectl logs -l app.kubernetes.io/name=system-api -n system-api-dev
```

## Health

```bash
curl https://system-api.dev.platform.ohanyere.internal/healthz
curl https://system-api.dev.platform.ohanyere.internal/readyz
curl https://system-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo system-api -n system-api-dev
```

Escalate to `Developer Experience` through `mooref068@gmail.com` if rollback does not restore service.
