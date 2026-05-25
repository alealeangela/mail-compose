# mail-compose

## Arquitectura del despliegue

- **Postfix**: Servicio SMTP para envío de correos
- **Dovecot**: Servicio IMAP/POP3 para recepción de correos
- **Docker Compose**: Orquestación de ambos servicios
- **Red interna**: `mail_network` (bridge) para comunicación entre contenedores
- **Volúmenes**: `mail_data` para persistencia de buzones

## Puertos expuestos

| Servicio | Puerto interno | Puerto externo |
|----------|---------------|----------------|
| Postfix (SMTP) | 25 | 1025 |
| Dovecot (IMAP) | 143 | 1143 |
| Dovecot (POP3) | 110 | 1110 |

## Despliegue

```bash
docker compose up -d
