# Vercel Deployer

Reusable GitHub Action for deploying projects to Vercel with optional commit author rewriting.

## Usage

```yaml
- name: Deploy to Vercel
  uses: azizrosyid/vercel-deployer@v1
  with:
    vercel-token: ${{ secrets.VERCEL_TOKEN }}
    vercel-org-id: ${{ secrets.VERCEL_ORG_ID }}
    vercel-project-id: ${{ secrets.VERCEL_PROJECT_ID }}
```

### With commit author rewriting

```yaml
- name: Deploy to Vercel
  uses: azizrosyid/vercel-deployer@v1
  with:
    vercel-token: ${{ secrets.VERCEL_TOKEN }}
    vercel-org-id: ${{ secrets.VERCEL_ORG_ID }}
    vercel-project-id: ${{ secrets.VERCEL_PROJECT_ID }}
    rewrite-author-name: azizrosyid
    rewrite-author-email: azizrosyid783@gmail.com
```

### Preview deployment

```yaml
- name: Deploy Preview to Vercel
  uses: azizrosyid/vercel-deployer@v1
  with:
    vercel-token: ${{ secrets.VERCEL_TOKEN }}
    vercel-org-id: ${{ secrets.VERCEL_ORG_ID }}
    vercel-project-id: ${{ secrets.VERCEL_PROJECT_ID }}
    environment: preview
```

## Inputs

| Input | Required | Default | Description |
|-------|----------|---------|-------------|
| `vercel-token` | Yes | - | Vercel API token |
| `vercel-org-id` | Yes | - | Vercel Organization ID |
| `vercel-project-id` | Yes | - | Vercel Project ID |
| `environment` | No | `production` | Deployment environment (`production` or `preview`) |
| `node-version` | No | `20` | Node.js version |
| `rewrite-author-name` | No | - | Rewrite commit author name |
| `rewrite-author-email` | No | - | Rewrite commit author email |

## Setup

1. Create a Vercel API token at [vercel.com/account/tokens](https://vercel.com/account/tokens)
2. Get your Org ID and Project ID from your Vercel project settings
3. Add these as repository secrets: `VERCEL_TOKEN`, `VERCEL_ORG_ID`, `VERCEL_PROJECT_ID`
