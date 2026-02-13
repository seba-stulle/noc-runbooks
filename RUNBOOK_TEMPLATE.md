# Runbook Template (Single Block)

## When to use
(1–2 lines)

## Symptoms
- ...

## Commands (evidence + fix + validate)
~~~bash
# === QUICK CHECKS / EVIDENCE ===
# commands to understand the issue + paste outputs under each command

# Example:
# systemctl status <service> --no-pager
# journalctl -u <service> -n 80 --no-pager
# ss -tulpn | grep ':22' || echo "Port 22 not listening"
# df -h

# --- PASTE OUTPUTS HERE ---
# (paste real output right below each command)

# === FIX / MITIGATION ===
# Example:
# sudo systemctl restart <service>
# sudo systemctl enable <service>

# === VALIDATE ===
# Example:
# systemctl is-active <service>
# ss -tulpn | grep ':22'
# curl -I http://127.0.0.1:80

# === ESCALATE IF ===
# - Not solved in 15 minutes
# - Need permissions / access / higher level change
# Include: commands + key outputs + timeline

# === MY NOTES ===

~~~ 
