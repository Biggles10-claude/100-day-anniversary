# Claude Code Notes

## Kasm Chrome VNC Access

### Tailscale Funnel Command
```bash
docker exec chrome-tailscale tailscale funnel --bg 8080
```

### Current Funnel URLs
- **VNC (Kasm Chrome)**: https://a0836970bca6.taildc3fd3.ts.net/

### Container Info
- `chrome-kasm` - Kasm Chrome browser (ports 4901, 5901, 6901)
- `chrome-tailscale` - Tailscale sidecar for public access
- `chrome-proxy` - Nginx proxy (port 8080 -> 6901 with SSL)

### Check Funnel Status
```bash
docker exec chrome-tailscale tailscale funnel status
```

### Container IPs
```bash
docker network inspect bridge --format '{{range .Containers}}{{.Name}}: {{.IPv4Address}}{{"\n"}}{{end}}'
```
