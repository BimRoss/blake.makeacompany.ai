# blake.makeacompany.ai

Personalized pitch lander for Blake Carnahan (Sr AE, Salesforce, Nashville). Modeled on `monkey.makeacompany.ai`.

Built as a meet-and-greet leave-behind, June 2026. Static one-pager: sections cover the read, the role shift, opportunities where MaC fits, honest challenges, the career arc.

## Deploy

K8s + GitOps via the standard BimRoss recipe — **NOT** Cloudflare Pages despite the early monkey-lander framing. Pushing to `main` only updates source; nothing ships until a tag is cut.

- Tag `v*` on `main` → `.github/workflows/blake-lander-images.yml` builds + pushes `geeemoney/blake-lander:<ver>` to Docker Hub.
- `gitops-release` reusable workflow auto-opens a PR against `BimRoss/rancher-admin` bumping the image in `admin/apps/blake/deployment.yaml`.
- Merge that PR → Fleet syncs → blake.makeacompany.ai serves the new image.
- DNS CNAME `blake.makeacompany.ai` → cluster ingress, auto-created by the `gh repo create` hook.
