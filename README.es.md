<div align="center">

<img src="public/mascot.svg" width="140" height="140" alt="FlowShot" />

# FlowShot

**Captura cualquier flujo del navegador y conviértelo en una guía paso a paso.**

Le das a grabar, haces lo tuyo, y obtienes una guía pulida con capturas anotadas. Edítala, reprodúcela o expórtala. Sin cuenta, sin nube, sin rastreo.

[![License][license-shield]][license-link]
[![Manifest V3][mv3-shield]][mv3-link]
[![100% Local][local-shield]][local-link]
[![No Account][no-account-shield]][no-account-link]

</div>

---

## Tabla de Contenidos

- [Qué es FlowShot?](#qué-es-flowshot)
- [Funciones](#funciones)
- [Navegadores Soportados](#navegadores-soportados)
- [Inicio Rápido](#inicio-rápido)
- [Privacidad y Almacenamiento](#privacidad-y-almacenamiento)
- [Contribuir](#contribuir)
- [Licencia](#licencia)

---

## Qué es FlowShot?

FlowShot es una extensión de navegador que captura automáticamente tus flujos de trabajo y los convierte en guías paso a paso con capturas anotadas. Funciona completamente en tu navegador — sin backend, sin cuenta, sin telemetría, y nada sale de tu dispositivo.

Ya sea que estés documentando herramientas internas, escribiendo tutoriales de producto, o formando a un compañero, FlowShot captura cada clic, tecla y navegación automáticamente para que te concentres en lo importante.

Cada acción relevante se convierte en un paso: clics en botones y enlaces, campos de formulario, atajos de teclado, acciones del portapapeles, arrastres y navegaciones. Los clics rápidos sobre elementos cercanos se agrupan para que las guías queden limpias, y el clic se intercepta antes de que la página navegue, así no se pierde nada en SPAs ni en cargas completas.

Cada paso lleva una captura con el elemento pulsado resaltado y ampliado. Sin recortar a mano, sin herramientas de anotación que aprender.

---

## Funciones

### Smart Blur

FlowShot detecta y difumina datos sensibles automáticamente en tus capturas: correos, teléfonos, números de identificación, tarjetas de crédito, IPs, direcciones MAC. Activa o desactiva cada categoría de forma independiente.

¿Necesitas ocultar algo personalizado? El selector manual te deja elegir cualquier elemento del DOM y enmascararlo en todas las capturas donde aparezca.

### Descripciones con IA

Trae tu propia API key (OpenAI o Anthropic) y FlowShot genera descripciones naturales como *"Haz clic en el botón **Enviar** para guardar los cambios"* en lugar de `Click button "Submit"`.

Las descripciones se generan a partir de un contexto ligero del DOM (~50-100 tokens), no desde capturas. Unas 15-30 veces más barato que los modelos con visión. Elige el idioma de las descripciones (inglés, español, portugués, francés).

### Reproducción Guide Me

Reproduce cualquier guía en vivo sobre una página real. FlowShot resalta el siguiente elemento, marca tu progreso paso a paso, y avanza solo conforme vas interactuando. Ideal para formar a un compañero o para guiarte a ti mismo.

### Narración por Voz

Habla en voz alta mientras grabas y FlowShot convierte lo que dijiste en las descripciones de los pasos. El audio se transcribe con tu propia key (OpenAI o Groq) y se empareja con el paso al que corresponde, así narras una vez en lugar de escribir cada paso a mano.

### Editor de Guías

Arregla una guía después sin volver a grabar. Recorta, anota y censura cualquier captura, reescribe un paso con IA sin salir del editor, mete títulos y notas entre pasos, reordena o borra en lote, y vuelve atrás con el historial de versiones.

### Exportación Multi-Formato

Comparte tus guías en el formato que mejor encaje con tu flujo:

| Formato | Detalles |
|---------|----------|
| **Video** | Recorrido narrado, mp4/H.264, con movimiento del cursor |
| **PDF** | Listo para imprimir, A4 vertical con saltos automáticos |
| **DOCX** | Ábrelo y sigue editando en Word |
| **HTML** | Autónomo, imágenes embebidas en base64 |
| **Markdown** | Pega en Notion, GitHub, documentación interna, wikis |

Todas las exportaciones se generan del lado del cliente. Nada pasa por un servidor.

---

## Navegadores Soportados

| Navegador | Estado |
|-----------|--------|
| Google Chrome | Soportado |
| Mozilla Firefox | Soportado |
| Microsoft Edge | Soportado |
| Brave | Soportado |

Disponible en inglés, español, portugués brasileño, francés y alemán. El idioma de las descripciones de IA se configura por separado, así que puedes usar FlowShot en inglés y generar guías en español, o cualquier combinación.

---

## Inicio Rápido

### Prerrequisitos

- Node.js 22+
- [pnpm](https://pnpm.io) 10+
- Chrome, Firefox, Edge o Brave (para pruebas)

### Instalar

```bash
git clone <tu-url-del-repo>
cd flowshot
pnpm install
```

### Ejecutar en Desarrollo

```bash
pnpm dev                   # Chrome (MV3) con HMR
pnpm dev:firefox           # Firefox (MV3) con HMR
```

WXT lanza una nueva instancia del navegador con la extensión cargada.

### Construir

```bash
pnpm build                 # Chrome
pnpm build:firefox         # Firefox
pnpm zip:all               # Empaquetar ambos navegadores
```

### Probar

```bash
pnpm test                  # Ejecutar todas las pruebas
pnpm test:watch            # Modo watch
pnpm test:cov              # Reporte de cobertura
```

### Lint y Formato

```bash
pnpm lint                  # Verificar
pnpm lint:fix              # Auto-corregir
pnpm format                # Solo formatear
```

---

## Privacidad y Almacenamiento

Tus guías, pasos y capturas viven en tu dispositivo. No hay backend, no hay cuenta, no hay telemetría. Tus API keys (si usas alguna) nunca salen del navegador. Se guardan localmente y se usan para llamar directo al proveedor que elegiste.

Dos cosas sí salen del navegador: los iconos de los sitios se piden al servicio de favicons de Google, lo que envía el dominio de ese sitio, y las funciones opcionales de IA y voz mandan texto o audio al proveedor que configuraste.

---

## Contribuir

Se agradece todo tipo de contribución: reportes de bugs, ideas nuevas, PRs y traducciones.

Mira [CONTRIBUTING.md](./CONTRIBUTING.md) para el setup de desarrollo, la estructura del proyecto, y las pautas para contribuidores.

---

## Licencia

Licencia MIT

Copyright (c) 2026 Jojin John

Desarrollado por Jojin John

Ver [LICENSE](./LICENSE) para los detalles.

---

<div align="center">

**Desarrollado por [Jojin John](https://github.com/jojinjohn)**

</div>

<!-- LINK GROUP -->

[license-shield]: https://img.shields.io/badge/license-MIT-4F46E5?style=flat-square&labelColor=1E1B4B
[license-link]: ./LICENSE

[mv3-shield]: https://img.shields.io/badge/manifest-v3-3730A3?style=flat-square&labelColor=1E1B4B
[mv3-link]: https://developer.chrome.com/docs/extensions/mv3/intro/

[local-shield]: https://img.shields.io/badge/storage-100%25%20local-4F46E5?style=flat-square&labelColor=1E1B4B
[local-link]: #-privacidad-y-almacenamiento

[no-account-shield]: https://img.shields.io/badge/account-not%20required-4F46E5?style=flat-square&labelColor=1E1B4B
[no-account-link]: #-privacidad-y-almacenamiento
