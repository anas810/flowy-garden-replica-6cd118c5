# Rebuild the Central Bank site from GitHub, unchanged

Copy the public repo `anas810/flowy-garden-replica` into this project exactly as it is, so this project renders the same interactive "The Central Bank — Standard Reserve, Explained" page.

## What you'll get

- A single page with the expansion/contraction switch, the bank canvas animation, and the issuance rate, fee routing, licenses, and exits sections.
- Same wording, colors, layout, and page title/description as the source — nothing redesigned or "improved".

## Steps

1. Download the repository's latest `main` snapshot.
2. Replace this project's page and styling files with the source versions:
   - `src/routes/index.tsx`, `src/routes/__root.tsx`, `src/router.tsx`, `src/styles.css`
   - `src/components/BankCanvas.tsx`, `IssuanceRate.tsx`, `FeeRouting.tsx`, `Licenses.tsx`, `Exits.tsx`
   - the `src/components/ui/*` set, `src/hooks`, `src/lib`, `src/server.ts`, `src/start.ts`
   - `public/favicon.ico`, `public/robots.txt`, config files (`components.json`, `eslint.config.js`, `tsconfig.json`, `vite.config.ts`)
3. Leave `src/routeTree.gen.ts` to regenerate automatically.
4. Verify: no new dependencies are needed — the source uses the identical package list already installed here.

## Technical notes

- Both projects run the same TanStack Start v1 + Tailwind v4 stack, and `package.json` matches dependency-for-dependency, so this is a straight file copy with no porting.
- Source has one route (`/`); no backend, database, or secrets are involved.
- Verification: build/typecheck clean, then load `/` in the preview and exercise the expansion/contraction toggle.
