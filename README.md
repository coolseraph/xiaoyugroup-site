# Xiaoyu Group site

This is the clean publication repository for Xiaoyu Group. The initial branch is `staging/github-pages`, served by GitHub Pages from `/ (root)`. It contains only the two reviewed HTML pages and their required public assets. The local project hub and the former Bolt repository are outside this repository.

The root `CNAME` selects `staging.xiaoyugroup.com`. Both pages carry `noindex, nofollow`, and `robots.txt` disallows crawlers. These instructions do not make staging private. Fees, delivery details and case-study permissions still need owner approval before the site is promoted to `www`.

## Publish staging

1. Review the file list, commit this branch, create `coolseraph/xiaoyugroup-site` on GitHub, and push `staging/github-pages`.
2. In the new repository's **Settings → Pages**, select **Deploy from a branch**, `staging/github-pages`, `/ (root)`, then save. Confirm that the custom domain shown is `staging.xiaoyugroup.com`. A workflow is not required.
3. At the current DNS provider, create a `staging` CNAME pointing to `coolseraph.github.io` (no protocol or path), replacing any conflicting record for that label. Leave nameservers, the apex and `www` unchanged. Complete GitHub's domain verification if requested.
4. Wait for the Pages build, DNS and certificate. Check `https://staging.xiaoyugroup.com/` and `/engagements.html`: navigation, anchors, mobile menu, mail links, logo, favicon, HTTPS, source metadata and `/robots.txt`. Enable **Enforce HTTPS** when available. Record sign-off on public claims, fees, delivery terms and case-study permissions.

## Promote to `www` after sign-off

1. Record the current `www` DNS target and TTL, Vercel configuration and staging test results. Recheck the live DNS before any cutover. Changing `www` alone does not change the apex.
2. In a reviewed production revision, remove the noindex metadata from both pages, allow crawling in `robots.txt`, and change `CNAME` to `www.xiaoyugroup.com`. GitHub Pages supports one custom domain per repository, so the staging domain will be replaced. Keep a separate staging repository if a permanent staging address is needed.
3. Deploy that revision. Confirm the Pages custom domain is `www.xiaoyugroup.com`, then change only the existing `www` CNAME to `coolseraph.github.io`. Leave nameservers and unrelated DNS records unchanged.
4. Check DNS, HTTPS, both pages and links on `www`; enable **Enforce HTTPS** when GitHub offers it. Monitor the site. If cutover fails, restore the recorded `www` DNS target and former hosting configuration. DNS rollback may take the prior TTL to propagate.

No remote repository, Pages setting, DNS record or deployment is changed by this local preparation.
