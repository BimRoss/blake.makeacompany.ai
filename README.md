# blake.makeacompany.ai

Personalized pitch lander for Blake Carnahan (Sr AE, Salesforce, Nashville). Modeled on `monkey.makeacompany.ai`.

Built as a meet-and-greet leave-behind, June 2026. Static one-pager: sections cover the read, the role shift, opportunities where MaC fits, honest challenges, the career arc.

## Deploy

Cloudflare Pages, same recipe as `monkeytilt-lander`:

- CF Pages, Connect Git, this repo, branch `main`, build command empty, output dir `/`.
- DNS CNAME `blake.makeacompany.ai` already auto-created by the `gh repo create` hook.
