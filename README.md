# ansoftware-control

Repositorio PUBLICO de control remoto de las extensiones de taller (Ansoftware). **Solo datos de configuracion: nunca codigo, contrasenas ni datos de clientes.**

Cada extension lee cada ~8 minutos `global.json` y `talleres/<codigo>.json` (el codigo de soporte aparece en el panel). Lo del taller sobrescribe lo global.

| Campo | Efecto |
|---|---|
| `pausa: true` | detiene las pasadas AUTOMATICAS (las manuales del panel siguen) |
| `mensaje` | texto de soporte (visible en el estado de soporte) |
| `ejecutar_ahora: N` | cuando N sube, el taller hace una pasada ya |
| `recargar: N` | cuando N sube, la extension se recarga (cuando esta libre) |
| `latido_url` | si se rellena, la extension envia cada hora version y estado tecnico a esa direccion |

Regla: para disparar una orden (`ejecutar_ahora`, `recargar`) sube el numero; no se repite si el numero no cambia.
