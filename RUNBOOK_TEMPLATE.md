# Runbook: <Problema> (RB-XXX)

## Objetivo
Resolver/diagnosticar <problema> sin improvisar.

## Cuándo usar
- Alertas típicas: ...
- Síntomas: ...

## Alcance / Suposiciones
- Sistema: Debian / systemd
- Servicio: <service>
- Qué NO cubre: ...

## Checklist rápido (2–3 min)
1) Estado del servicio:
   - `systemctl status <service> --no-pager`
   - Señales: active/failed, exit-code, últimas líneas
2) Logs recientes:
   - `journalctl -u <service> -n 80 --no-pager`
   - Señales: “permission denied”, “bind”, “config error”
3) ¿Está escuchando?
   - `ss -tulpn | grep -E ':<port>\b' || echo "No escucha en <port>"`
   - Señales: proceso + puerto

## Diagnóstico (si no salió en el rápido)
- Disco/memoria:
  - `df -h`
  - `free -h`
- Config:
  - ubicación: ...
  - validar: ...

## Mitigación / Fix (opciones)
- Opción 1 (segura): ...
- Opción 2 (si aplica): ...
- Comandos:
  - `sudo systemctl restart <service>`

## Validación
- `systemctl is-active <service>`
- `ss -tulpn | grep -E ':<port>\b'`
- Prueba funcional:
  - `curl -I http://127.0.0.1:<port>`

## Riesgos / Rollback
- Riesgo:
- Rollback:

## Escalar si…
- No hay permisos / requiere cambio mayor
- Impacto alto
- Error de infraestructura (red/firewall/almacenamiento)
