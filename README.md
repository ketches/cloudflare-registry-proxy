# cloudflare-registry-proxy

![deploy](https://github.com/ketches/cloudflare-registry-proxy/actions/workflows/deploy.yaml/badge.svg)

## Deploy

1. click the "Deploy With Workers" button
2. follow the instructions to fork and deploy
3. update routes as you requirement

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/ketches/cloudflare-registry-proxy)

## Routes configuration tutorial

1. Fork this project
2. use cloudflare worker host: only support proxy one registry
   ```javascript
   const routes = {
     "docker.ketches.cn": dockerHub,
     "quay.ketches.cn": "https://quay.io",
     "gcr.ketches.cn": "https://gcr.io",
     "k8s-gcr.ketches.cn": "https://k8s.gcr.io",
     "k8s.ketches.cn": "https://registry.k8s.io",
     "ghcr.ketches.cn": "https://ghcr.io",
     "cloudsmith.ketches.cn": "https://docker.cloudsmith.io",
     "ecr.ketches.cn": "https://public.ecr.aws",
   };
   ```
3. Enable GitHub Actions in your fork (Actions > I understand my workflows, go ahead and enable them)
4. Add Secrets in your fork (Settings > Secrets > New repository secret)
   - `CLOUDFLARE_API_TOKEN`: Cloudflare API Token
   - `CLOUDFLARE_ACCOUNT_ID`: Cloudflare Account ID
5. Deploy to Cloudflare Workers (Actions > Deploy to **Cloudflare** Workers)
6. Add Custom Domains for your Cloudflare Worker as the routes in `index.js`

