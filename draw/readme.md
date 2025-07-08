[User]
  ↓
[ALB (Ingress)]
  ↓
[Backend App (EKS Pod)]
  ├── Store Text → [DynamoDB or RDS]
  ├── Upload Image → [S3 Bucket]
  └── Redis (optional cache)
  
[Scheduled Cleanup]
  └── Lambda (TTL 확인 → 삭제)  or DynamoDB TTL

[Monitoring]
  └── Prometheus ↔ Grafana

[CI]
  └── GitHub Actions → Docker Build + Push

[CD]
  └── ArgoCD → EKS 배포 (GitOps)
