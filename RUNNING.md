# FE Civil practice app — running instance

Local clone of the upstream https://github.com/holdenlesliebole/fe-civil-app.
Pushes go to the personal fork: https://github.com/odui95/fe-civil-app (never to upstream).
Anthropic/Claude integration replaced with the user's Gemini credential (free tier, $0).

## Running now
- Server: Node/Express on **port 3000** (pid via nohup, log: `server.log`)
- Health: `curl http://localhost:3000/api/health`
- Frontend: React build served by Express at `http://localhost:3000/`

## Restart (if the VM reboots or the process dies)
```bash
cd ~/workspace/fe-civil-app/server && nohup node index.js > ../server.log 2>&1 &
```

## Public access — BLOCKED (2026-09-20)
No outbound tunnel works from this sandbox: only HTTP/HTTPS through the
authenticated egress proxy is allowed; raw TCP is intercepted with:
"muse: Other TCP connections is turned off for this assistant. To allow it,
ask the user to open Muse".
Tried: cloudflared quick tunnel (TLS failure via proxy), localtunnel v2
(requires direct TCP to tunnel server), bore (direct TCP intercepted).

## Data
- `data/question_history.json`, `data/tutor_history.json`, `data/usage.json`
  (gitignored, local only)
