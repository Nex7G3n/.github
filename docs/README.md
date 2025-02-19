# 📜 Documentación General

Este proyecto sigue un enfoque estructurado para la gestión del código, combinando **Conventional Commits** para un historial claro y **Vault Streams** para un flujo de desarrollo eficiente y organizado.  

## 📌 Commits Estructurados  

Usamos [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) para garantizar claridad y consistencia en los mensajes de commit.  

### ✨ Tipos de commits  

- **`feat`**: Agrega una nueva característica.  
- **`fix`**: Soluciona un error en el código.  
- **`perf`**: Optimiza el rendimiento sin modificar la funcionalidad.  
- **`refactor`**: Mejora la estructura del código sin cambiar su comportamiento.  
- **`style`**: Cambios que no afectan la lógica del código (formato, espacios, etc.).  
- **`test`**: Agrega o mejora pruebas automatizadas.  
- **`chore`**: Actualizaciones de herramientas, dependencias o configuraciones.  

### 📝 Formato del mensaje  

Cada commit debe seguir la estructura:  

```bash
tipo(scope): descripción corta
```

Ejemplo:  

```bash
feat(auth): agrega autenticación con OAuth2  
fix(ui): corrige el desbordamiento de texto en botones  
```

## 🔄 Vault Streams: Flujo de Versionado  

### 📂 ¿Qué son los Vault Streams?  

Vault Streams es una estrategia de control de versiones que permite organizar y gestionar diferentes estados del código en paralelo. Esto facilita:  

- **Manejo de versiones en desarrollo, pruebas y producción.**  
- **Integración de nuevas funcionalidades sin afectar la estabilidad.**  
- **Reversión rápida en caso de errores críticos.**  

### 🚀 Estrategia de Branching  

- **`main`**: Contiene la versión estable del proyecto.  
- **`dev`**: Branch principal para desarrollo activo.  
- **`feature/{nombre}`** *(Colaboradores externos)*: Para nuevas funcionalidades propuestas por colaboradores fuera de la organización.  
- **`feature/JIRA-{ticket}`** *(Miembros de NextGen)*: Para nuevas funcionalidades siguiendo la nomenclatura del ticket en Jira.  
- **`release/{nombre}`** *(Colaboradores externos)*: Para preparar una versión estable.  
- **`release/JIRA-{ticket}`** *(Miembros de NextGen)*: Para versiones gestionadas dentro de la organización.  
- **`hotfix/{nombre}`** *(Colaboradores externos)*: Para correcciones urgentes.  
- **`hotfix/JIRA-{ticket}`** *(Miembros de NextGen)*: Para correcciones urgentes gestionadas internamente.  

### 🔄 Flujo de Integración  

1. **Desarrollo de funcionalidades:**  
   - **Colaboradores externos** crean una rama `feature/{nombre}` desde `dev`.  
   - **Miembros de NextGen** crean una rama `feature/JIRA-{ticket}` desde `dev`.  
   - Se siguen los estándares de Conventional Commits.  
   - Se realiza un Pull Request a `dev` para revisión.  

2. **Preparación de una versión estable:**  
   - **Colaboradores externos** crean `release/{nombre}` desde `dev`.  
   - **Miembros de NextGen** crean `release/JIRA-{ticket}` desde `dev`.  
   - Se realizan pruebas y ajustes finales.  
   - Tras validación, se fusiona en `main` y se etiqueta la versión.  

3. **Correcciones urgentes en producción:**  
   - **Colaboradores externos** crean `hotfix/{nombre}` desde `main`.  
   - **Miembros de NextGen** crean `hotfix/JIRA-{ticket}` desde `main`.  
   - Se implementa la corrección y se sigue el proceso de revisión.  
   - Una vez validado, se fusiona en `main` y `dev` para mantener la consistencia.  

Este enfoque mantiene la organización y asegura que cada cambio pase por un flujo controlado antes de llegar a producción. 🚀