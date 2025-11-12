# mongo-devops-project
Design, deploy, and operate a highly-available, secure, observable MongoDB service for a sample web app using Infrastructure-as-Code, automation, CI/CD, backups, monitoring, and disaster recovery — all with reproducible artifacts and tests.

High-level architecture
Cloud: AWS (EC2 + VPC + Security Groups) — you can substitute any cloud or on-prem.
MongoDB deployment options: self-managed on VMs (systemd), Docker Compose (dev), and Kubernetes StatefulSet + PersistentVolumes (prod).
HA: Replica Set (3 nodes) + optional Sharding (for scale).
Automation: Terraform (infra) + Ansible (config) + Helm (K8s).
CI/CD: GitHub Actions (schemas/migrations, backup tests, deployment checks).
Monitoring: Prometheus + Grafana + MongoDB Exporter + Alertmanager.
Backup: mongodump (logical) + filesystem snapshots or mongodump to S3 + oplog-based PITR.
Security: TLS, SCRAM auth, least-privilege IAM (for cloud), network policies, key management (KMS).
Observability: logs shipped to ELK or Loki, metrics, dashboards, runbooks and SLA reporting.Milestone 0 — Prep (deliverables: Git repo skeleton, accounts)

Create a Git repo (e.g., mongo-devops-project) with folders: infra/, ansible/, k8s/, docker/, ci/, monitoring/, docs/.
Get AWS account or local VM environment (VirtualBox/Vagrant) for testing.
Install CLI tools locally: terraform, ansible, docker, kubectl, helm, mongo shell, awscli.
Deliverable: README with project overview and prerequisites.

