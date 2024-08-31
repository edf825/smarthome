Ensure docker starts at boot:
```
sudo systemctl enable --now docker
```

Add cloudflare tunnel token:
```
cat TUNNEL_TOKEN=[...] > cloudflare/.env
```

Start all services:
```
for i in cloudflare homeassistant nginx; do pushd $i && docker compose up -d && popd; done
```
