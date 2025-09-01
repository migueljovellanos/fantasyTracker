# 🏆 La Liga de los Fantásticos

Aplicación web para gestionar la liga fantasy de tu grupo de amigos, desarrollada con Astro.

## 🚀 Características

- **Tabla de puntuaciones**: Visualiza los puntos por jornada y totales de cada jugador
- **Cálculo automático de dinero**: Calcula automáticamente cuánto debe pagar cada jugador según las reglas
- **Diseño responsive**: Funciona perfectamente en móviles y escritorio
- **Fácil actualización**: Sistema simple para actualizar puntos sin necesidad de base de datos

## 💰 Reglas de la Liga

- **Último de la jornada**: Paga 2.5€
- **Penúltimo de la jornada**: Paga 1.5€
- **Antepenúltimo de la jornada**: Paga 1€

## 🛠️ Instalación y Uso

### Prerrequisitos
- Node.js (versión 18 o superior)
- npm

### Instalación
```bash
# Las dependencias ya están instaladas, pero si necesitas reinstalar:
npm install
```

### Ejecutar la aplicación
```bash
npm run dev
```

La aplicación estará disponible en `http://localhost:4321/`

## 📝 Cómo Actualizar los Puntos

### Método 1: Archivo JSON (Recomendado)
1. Abre el archivo `src/data/liga.json`
2. Modifica los datos según necesites:
   - **Cambiar nombres**: Edita el campo `nombre` de cada jugador
   - **Añadir jornada**: Agrega un nuevo número al final del array `jornadas`
   - **Actualizar total**: Suma todos los puntos y actualiza el campo `total`
   - **Cambiar reglas**: Modifica los valores en la sección `reglas`

### Método 2: Archivo CSV (Alternativo)
1. Abre el archivo `src/data/liga.csv` en Excel o cualquier editor de texto
2. Cada fila representa un jugador
3. Las columnas j1-j38 representan las jornadas
4. Actualiza la columna `total` con la suma de todas las jornadas
5. **Nota**: Actualmente solo funciona el método JSON, el CSV es para referencia

### Ejemplo de actualización (JSON)
```json
// ANTES (jornada 10):
{
  "nombre": "Jugador 1",
  "jornadas": [85, 92, 78, 88, 95, 87, 91, 83, 89, 94],
  "total": 882
}

// DESPUÉS (añadiendo jornada 11 con 76 puntos):
{
  "nombre": "Jugador 1",
  "jornadas": [85, 92, 78, 88, 95, 87, 91, 83, 89, 94, 76],
  "total": 958
}
```

### Liga de 38 jornadas
La aplicación lee toda la configuración desde `liga.json`:
- **Total de jornadas**: Configurable en `totalJornadas`
- **Jornadas a mostrar**: Configurable en `jornadasAMostrar`
- **Reglas de pago**: Configurables en la sección `reglas`
- **Nombre de la liga**: Configurable en `nombre`

## 🔒 Seguridad

- **Solo lectura para usuarios**: Los visitantes solo pueden ver los datos, no modificarlos
- **Administración simple**: Solo quien tenga acceso al código puede modificar los puntos
- **Sin login necesario**: Los usuarios pueden consultar sin registrarse

## 📱 Páginas Disponibles

- `/` - Página principal con la tabla de la liga

## 🎨 Personalización

Puedes personalizar fácilmente:
- Nombres de jugadores
- Número de jornadas
- Reglas de penalización (modificando la función `calcularDinero`)
- Estilos y colores en el CSS

## 📦 Despliegue

Para desplegar en producción:

```bash
npm run build
```

Esto generará los archivos estáticos en la carpeta `dist/` que puedes subir a cualquier hosting.

## 🤝 Soporte

Si necesitas ayuda o tienes alguna pregunta, revisa:
1. Este README para instrucciones detalladas
2. Los archivos de datos en `src/data/` para ejemplos
3. La documentación de [Astro](https://docs.astro.build/)

---

¡Disfruta de tu liga fantasy! 🏆⚽
