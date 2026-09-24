# MateLab 🧉

Tienda online de mates personalizables. El usuario elige material (calabaza, madera, cerámica, vidrio, acero térmico), forma, revestimiento, virola, bombilla y grabados, y ve su mate en un modelo 3D antes de comprarlo.

Trabajo práctico full-stack de **Programación Web — ITBA, 2026**.

- **Producción:** _(link de Vercel)_
- **Autor:** Ramón Eppens

## Stack

| Capa         | Tecnología                                                                               |
| ------------ | ---------------------------------------------------------------------------------------- |
| Framework    | Next.js (App Router) + React, JavaScript                                                 |
| Estilos      | Tailwind CSS v4                                                                          |
| Calidad      | ESLint + Prettier                                                                        |
| CI           | GitHub Actions                                                                           |
| Deploy       | Vercel (preview por PR + producción desde `main`)                                        |
| Próximamente | Supabase (BD, auth, storage), Mercado Pago (checkout + webhooks), React Three Fiber (3D) |

## Correr el proyecto

Requisitos: Node.js 22 o superior.

```bash
npm install
npm run dev        # http://localhost:3000
```

| Script                 | Qué hace                             |
| ---------------------- | ------------------------------------ |
| `npm run dev`          | Servidor de desarrollo               |
| `npm run build`        | Build de producción                  |
| `npm run start`        | Sirve el build                       |
| `npm run lint`         | ESLint                               |
| `npm run format`       | Formatea todo con Prettier           |
| `npm run format:check` | Verifica el formato (lo corre el CI) |

## Flujo de trabajo

- `main` está protegida: solo se modifica por Pull Request y con el CI en verde.
- Una rama por tarea: `feat/…`, `fix/…`, `chore/…`, `docs/…`.
- Commits con [Conventional Commits](https://www.conventionalcommits.org/es/) (`feat: agrega catálogo`).
- Cada PR usa la plantilla con checklist de semántica, responsive y accesibilidad.
- Vercel publica un **preview por PR**; al mergear a `main` se despliega a producción.

## CI/CD

```
PR abierto ──► GitHub Actions: lint → formato → build ──► check obligatorio para mergear
          └──► Vercel: deploy de preview (link en el PR)
merge a main ──► Vercel: deploy a producción
```

## Entregables

| #   | Entregable                                                   | Estado |
| --- | ------------------------------------------------------------ | ------ |
| E1  | Repo + pipeline + preview                                    | ✅     |
| E2  | Landing + vistas clave responsivas                           | ⏳     |
| E3  | Formularios dinámicos + fetch + validación (configurador 3D) | —      |
| E4  | Catálogo navegable + API                                     | —      |
| E5  | CRUD en Supabase + admin                                     | —      |
| E6  | Checkout + webhook (Mercado Pago)                            | —      |
