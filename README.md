# Karta Email Signatures

Colección de firmas de correo electrónico HTML personalizadas para diferentes marcas y personas.

## Firmas incluidas

| Archivo | Marca/Persona | Sitio web |
|---------|---------------|-----------|
| `karta-emailSignature.html` | Karta | [conkarta.com](https://www.conkarta.com/) |
| `Comandos-emailSignature.html` | Comandos Studio | [comandos.me](https://comandos.me/) |
| `Tolmin-emailSignature.html` | Tolmin | [usetolmin.com](https://usetolmin.com/) |
| `Paladio-emailSignature.html` | Paladio | [usepaladio.com](https://usepaladio.com/) |

## Uso

1. Abre el archivo HTML correspondiente
2. Copia todo el contenido
3. Pégalo en la configuración de firma de tu cliente de correo

### Gmail
1. Configuración → Ver todos los ajustes → General → Firma
2. Pega el código HTML

### Outlook
1. Configuración → Correo → Redactar y responder → Firma de correo electrónico
2. Pega el código HTML

## Estructura

```
karta-signature/
├── README.md
├── karta-emailSignature.html
├── Comandos-emailSignature.html
├── Tolmin-emailSignature.html
└── Paladio-emailSignature.html
```

## Paladio

Misma estructura que la firma de Karta, con la marca de Paladio:

- **Isotipo**: `https://usepaladio.com/brand/isotype-light.png` (versión oscura,
  para fondo blanco). Para firmas sobre fondo oscuro usa `isotype-dark.png`.
  Si prefieres el logotipo con la palabra «PALADIO» en vez del isotipo, cambia
  a `logo-light.png` y sube el `width` a `140`.
- **Color de tinta**: `#0f0f11` (`--color-ink-900` de los tokens de Paladio).
  El azul de marca (`#3d7bfd`) se deja fuera a propósito: sobre fondo claro
  compite con los CTA y la tinta ancla mejor, igual que en el tema claro del
  producto.
- **Cargo**: en español («CEO de Paladio»), como en el sitio. Para
  correspondencia en inglés, cámbialo a «Chief Executive Officer».

### UTMs

El enlace a `usepaladio.com` va etiquetado para poder separar el tráfico que
entra por firma de correo:

| Parámetro | Valor | Por qué |
|---|---|---|
| `utm_source` | `email-signature` | La superficie de la que viene el clic |
| `utm_medium` | `email` | Canal |
| `utm_campaign` | `firma-correo` | Fijo para todo el equipo: agrupa toda la firma como una sola campaña |
| `utm_content` | `carlos-perez` | Quién firma. Al agregar la firma de otra persona, esto es lo único que cambia |

El texto visible del enlace se queda limpio (`usepaladio.com`); los parámetros
solo viven en el `href`. En el HTML los separadores van como `&amp;`, que es lo
que exige un atributo HTML — el navegador los entrega como `&`.

El enlace de LinkedIn no lleva UTMs a propósito: apunta a linkedin.com, donde
nuestra analítica no ve nada.

Nota: hoy `usepaladio.com` carga GA4 (`site/src/components/Analytics.astro`),
no PostHog. Los `utm_*` son estándar y PostHog los autocaptura como
`$initial_utm_*` en cuanto se instale, así que el etiquetado ya queda bien;
mientras tanto estos clics se leen en GA4.

## Personalización

Para crear una nueva firma, copia cualquiera de los archivos existentes y modifica:
- URL de la imagen del logo
- Nombre
- Cargo
- Enlaces de LinkedIn y sitio web

## Licencia

Uso privado.
