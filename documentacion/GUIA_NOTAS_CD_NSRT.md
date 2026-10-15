# Notas de cooldowns en NSRT

## Nota personal

1. Escribe `/ns pr` para abrir **Personal Notes**.
2. Pulsa **+ Create Note** y elige jefe y dificultad.
3. Pega la nota. Pulsa **Save** y luego **Load**.

Una nota personal solo la ves tú.

## Avisos de cooldown

Elige el jefe en NSRT para que cree los metadatos de la nota. Una línea de aviso se escribe así:

```text
tag:healer;time:45;ph:1;text:CD de raid;dur:8;TTS:false
```

- `tag`: jugador, rol, clase o grupo que recibirá el aviso.
- `time`: segundo del aviso dentro de la fase.
- `ph`: fase. Si no se indica, es la fase 1.
- `text`: mensaje. También puedes usar `spellid:ID` para mostrar el icono de un hechizo.
- `dur`: cuántos segundos antes aparece el aviso. En el ejemplo, aparece en el segundo 37.
- `TTS:false`: desactiva la voz. `TTS:true` lee el texto del aviso; también puedes indicar una frase.
- `sound:Nombre`: reproduce ese sonido en el aviso. Usa un nombre registrado en NSRT o una ruta de archivo.
- `TTSTimer`: segundo en que se reproduce la voz o el sonido; admite enteros.
- `countdown`: cuenta atrás de voz desde ese número de segundos; `0` la desactiva.
- `DisplayType`: presentación del aviso: `Text`, `Bar`, `Icon` o `Circle`.
- `colors`: componentes numéricos RGB/RGBA separados por espacios o dos puntos, por ejemplo `1 0.5 0`.
- `glowunit`: unidad o nombre cuyo marco se ilumina, por ejemplo `player` o `raid1`.
- `bossSpell`: ID entero de un hechizo válido del jefe; NSRT muestra su icono si lo encuentra.

Ejemplos de etiquetas: `tag:NombreJugador`, `tag:tank`, `tag:healer`, `tag:group1`, `tag:melee` y `tag:everyone`.

Pon una asignación por línea para que sea fácil de leer. `assign:` es para asignaciones de Ready Check; no sirve como etiqueta de aviso de CD. Se admiten tiempos negativos para avisos antes del pull.

## Mostrar u ocultar

Si no ves la nota, cárgala y comprueba las opciones **Reminders** y **Note-Display** en `/ns`.

| Comando | Acción |
|---|---|
| `/ns note` | Mostrar/ocultar todas las notas |
| `/ns pnote` | Mostrar/ocultar nota personal |
| `/ns clear` | Descargar nota compartida |
| `/ns pclear` | Descargar nota personal |

## Antes del pull

- Jefe y dificultad correctos.
- Nombre del jugador bien escrito en `tag`.
- Fase y tiempo correctos.
- Nota cargada. Si cambias de grupo, revisa las asignaciones.

## Si no funciona

- **No aparece el aviso:** revisa `tag`, `time`, `ph` y que exista `text` o `spellid`.
- **Aparece demasiado pronto:** reduce `dur`.
- **No puedes abrir el editor:** habilita también `NorthernSkyRaidTools_UI`.
- **No se comparte:** las notas personales son solo tuyas; para compartir se usa **Shared Notes** y **Load & Send**.

## Fuentes

- [NSRT en CurseForge](https://www.curseforge.com/wow/addons/northern-sky-raid-tools)
- [Parser de avisos](https://github.com/Reloe/NorthernSkyRaidTools/blob/af15794e7de6097e12a94e7db80189ef8f06b412/NorthernSkyRaidTools/Reminders.lua)
- [Editor de notas](https://github.com/Reloe/NorthernSkyRaidTools/blob/af15794e7de6097e12a94e7db80189ef8f06b412/NorthernSkyRaidTools_UI/UI/Reminders.lua)
- [Comandos](https://github.com/Reloe/NorthernSkyRaidTools/blob/af15794e7de6097e12a94e7db80189ef8f06b412/NorthernSkyRaidTools/SlashCommands.lua)
