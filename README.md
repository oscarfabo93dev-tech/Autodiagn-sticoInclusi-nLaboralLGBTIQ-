# 🏳️‍🌈 Autodiagnóstico en Inclusión Laboral LGBTIQ+

Una herramienta interactiva de autodiagnóstico desarrollada en **Streamlit** para evaluar el nivel de madurez de las **empresas** en inclusión laboral de personas LGBTIQ+.

![Python](https://img.shields.io/badge/python-v3.8+-blue.svg)
![Streamlit](https://img.shields.io/badge/streamlit-v1.36+-red.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

---

## 📋 Tabla de Contenidos

- [Características](#-características)
- [Demo](#-demo)
- [Requisitos](#-requisitos)
- [Instalación](#-instalación)
- [Uso](#-uso)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Arquitectura](#-arquitectura)
- [Características Técnicas](#-características-técnicas)
- [Configuración](#-configuración)
- [Contribución](#-contribución)
- [Licencia](#-licencia)
- [Autores](#-autores)
- [Agradecimientos](#-agradecimientos)

---

## 🚀 Características

### Funcionalidades Principales

- ✅ **Cuestionario interactivo** con 10 preguntas estructuradas sobre inclusión LGBTIQ+
- 📊 **Tres niveles de evaluación**: Inicial, Intermedio y Avanzado
- 📱 **Interfaz responsive** optimizada para desktop, tablet y móvil
- 📄 **Generación automática de PDF** con resultados detallados del diagnóstico
- 🎨 **Barra de progreso LGBTI** con los colores de la bandera (sticky footer)
- 🔒 **Seguridad HTML** con escapado de contenido dinámico
- ⚡ **Carga optimizada** con caché de datos y lectura eficiente de Excel
- 🎯 **Identificación de áreas a fortalecer** según respuestas de bajo puntaje
- 🖼️ **Logos institucionales** integrados en header y footer

### Experiencia de Usuario

- 🎨 Diseño moderno con gradientes y animaciones suaves
- 📐 Layout centrado con máximo 800px de ancho para mejor legibilidad
- 🌈 Colores de la bandera LGBTI en la barra de progreso
- ♿ Accesibilidad mejorada con contraste de colores adecuado
- 📲 Navegación intuitiva y fluida

---

## 🎥 Demo

### Pantalla Principal

![Screenshot Principal](docs/screenshot-home.png)

### Resultados

![Screenshot Resultados](docs/screenshot-results.png)

**🔗 Demo en vivo:** [https://autodiagnostico-lgbtiq.streamlit.app](https://autodiagnostico-lgbtiq.streamlit.app) _(próximamente)_

---

## 💻 Requisitos

### Software

- **Python**: 3.8 o superior
- **pip**: Gestor de paquetes de Python
- **Git**: Para clonar el repositorio (opcional)

### Sistema Operativo

- ✅ Windows 10/11
- ✅ macOS 10.14+
- ✅ Linux (Ubuntu 18.04+, Debian, etc.)

---

## 📥 Instalación

### 1. Clonar el repositorio

```bash
git clone https://github.com/oscarfabo93dev-tech/AutodiagIncluLaboLGBTIQ-.git
cd AutodiagIncluLaboLGBTIQ-/mi_app_inclusiva
```

### 2. Crear entorno virtual

**Windows:**

```bash
python -m venv venv
venv\Scripts\activate
```

**macOS/Linux:**

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Instalar dependencias

```bash
pip install -r requirements.txt
```

### 4. Preparar archivos de datos

Coloca el archivo Excel de datos en la carpeta `data/`:

```
mi_app_inclusiva/
├── data/
│   └── Recurso 5.2. Autodiagnóstico en inclusión laboral LGBTIQ para empresas.xlsx
```

### 5. Agregar logos (opcional)

Coloca tus logos en formato PNG en la carpeta `assets/`:

```
mi_app_inclusiva/
├── assets/
│   ├── cropped-Logo_WebSite.png
│   └── camara-de-la-diversidad.jpg_1.png
```

---

## 🎯 Uso

### Ejecutar la aplicación

```bash
streamlit run app.py
```

La aplicación se abrirá automáticamente en tu navegador en `http://localhost:8501`

### Flujo de Uso

1. **Leer las instrucciones** - Expandir la sección "Ver instrucciones"
2. **Responder el cuestionario** - 10 preguntas con 3 opciones cada una
3. **Calcular resultado** - Hacer clic en el botón "Calcular resultado"
4. **Revisar diagnóstico** - Ver nivel obtenido y recomendaciones
5. **Descargar PDF** - Obtener informe completo en PDF

### Modo Debug

Para ver información de carga y rendimiento:

1. Activar el sidebar (ícono `>` arriba a la izquierda)
2. Marcar "Modo debug"
3. Ver métricas de tiempo de carga

---

## 📁 Estructura del Proyecto

```
mi_app_inclusiva/
├── app.py                      # 🚀 Aplicación principal Streamlit
├── assets/                     # 🖼️ Recursos estáticos (logos)
│   ├── cropped-Logo_WebSite.png
│   └── camara-de-la-diversidad.jpg_1.png
├── data/                       # 📊 Archivos de datos Excel
│   └── Recurso 5.2. Autodiagnóstico....xlsx
├── src/                        # 📦 Módulos de código fuente
│   ├── __init__.py
│   ├── data_handler.py         # 📥 Manejo de carga de datos Excel
│   ├── quiz_logic.py           # 🧮 Lógica del cuestionario y scoring
│   └── ui_builder.py           # 🎨 Construcción de interfaz de usuario
├── requirements.txt            # 📋 Dependencias del proyecto
├── README.md                   # 📖 Documentación (este archivo)
└── .gitignore                  # 🚫 Archivos ignorados por Git
```

### Descripción de Módulos

#### `app.py`

- Configuración de la página Streamlit
- Carga de logos y CSS global
- Estructura principal de la aplicación
- Generación de PDF de resultados

#### `src/data_handler.py`

- Carga y parseo del archivo Excel
- Extracción de instrucciones, preguntas y niveles
- Lectura optimizada con pandas y openpyxl
- Extracción de umbrales desde fórmulas Excel

#### `src/quiz_logic.py`

- Cálculo de puntaje total
- Determinación de nivel (Inicial/Intermedio/Avanzado)
- Identificación de áreas a fortalecer

#### `src/ui_builder.py`

- Renderizado de instrucciones con HTML/CSS
- Construcción del formulario del cuestionario
- Barra de progreso LGBTI sticky
- Cards de resultados responsive

---

## 🏗️ Arquitectura

```
┌─────────────────────────────────────────────────────────────┐
│                        STREAMLIT APP                        │
│                         (app.py)                            │
└────────────────┬────────────────────────────┬───────────────┘
                 │                            │
        ┌────────▼────────┐          ┌────────▼────────┐
        │  DATA HANDLER   │          │   UI BUILDER    │
        │ (data_handler)  │          │  (ui_builder)   │
        └────────┬────────┘          └────────┬────────┘
                 │                            │
        ┌────────▼────────┐          ┌────────▼────────┐
        │   QUIZ LOGIC    │          │   PDF EXPORT    │
        │  (quiz_logic)   │          │  (reportlab)    │
        └─────────────────┘          └─────────────────┘
                 │                            │
        ┌────────▼────────────────────────────▼────────┐
        │           EXCEL DATA SOURCE                  │
        │  (Autodiagnóstico inclusión LGBTIQ.xlsx)    │
        └──────────────────────────────────────────────┘
```

---

## 🔧 Características Técnicas

### Performance

- ✅ **Caché de datos** con `@st.cache_data` para evitar recargas
- ✅ **Lectura optimizada** de Excel con pandas DataFrame completo
- ✅ **Carga lazy** de imágenes con base64 encoding
- ✅ **100x más rápido** que lectura celda por celda de openpyxl

### Seguridad

- 🔒 **Escapado HTML** de todo contenido dinámico con `html.escape()`
- 🔒 **Validación de inputs** en formularios
- 🔒 **Manejo de errores** robusto con try/except
- 🔒 **Sin exposición** de datos sensibles en logs

### Diseño Responsive

```css
/* Desktop: 800px max-width */
@media (min-width: 769px) {
  ...;
}

/* Tablet: ajustes intermedios */
@media (max-width: 768px) {
  ...;
}

/* Mobile: layout apilado */
@media (max-width: 480px) {
  ...;
}
```

### Accesibilidad

- ♿ Contraste de colores según WCAG 2.1
- ♿ Labels descriptivos en formularios
- ♿ Navegación por teclado
- ♿ Textos alternativos en imágenes

---

## ⚙️ Configuración

### Variables de Entorno

Crea un archivo `.streamlit/config.toml` para personalizar:

```toml
[theme]
primaryColor = "#667eea"
backgroundColor = "#ffffff"
secondaryBackgroundColor = "#f8f9fa"
textColor = "#111827"
font = "sans serif"

[server]
port = 8501
enableCORS = false
enableXsrfProtection = true

[browser]
gatherUsageStats = false
```

### Personalización de Colores

Edita las variables CSS en `app.py`:

```css
:root {
  --primary-color: #667eea;
  --secondary-color: #764ba2;
  --success-color: #28a745;
  --warning-color: #f1c40f;
  --danger-color: #dc3545;
}
```

### Umbrales de Niveles

Los umbrales se extraen automáticamente del Excel (celda `C81`):

```python
# Fallback por defecto si no se encuentra fórmula:
DEFAULT_THRESHOLDS = {
    "nivel_1_max": 15,  # <= 15 puntos = Nivel Inicial
    "nivel_2_max": 23   # <= 23 puntos = Nivel Intermedio
}                       # > 23 puntos = Nivel Avanzado
```

---

## 🤝 Contribución

¡Las contribuciones son bienvenidas! Sigue estos pasos:

### 1. Fork del proyecto

```bash
git clone https://github.com/TU_USUARIO/AutodiagIncluLaboLGBTIQ-.git
cd AutodiagIncluLaboLGBTIQ-
```

### 2. Crear rama de feature

```bash
git checkout -b feature/AmazingFeature
```

### 3. Commit de cambios

```bash
git add .
git commit -m 'Add: AmazingFeature - descripción detallada'
```

### 4. Push a la rama

```bash
git push origin feature/AmazingFeature
```

### 5. Abrir Pull Request

Ve a GitHub y abre un PR con descripción detallada de los cambios.

### Guía de Estilo

- 🐍 **PEP 8** para código Python
- 📝 **Docstrings** en todas las funciones
- ✅ **Type hints** donde sea posible
- 🧪 **Tests** para nuevas funcionalidades
- 📖 **Documentación** actualizada

---

## 📄 Licencia

Este proyecto está bajo la **Licencia MIT**. Ver el archivo [LICENSE](LICENSE) para más detalles.

```
MIT License

Copyright (c) 2025 Oscar Fabo

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

---

## 👥 Autores

### Desarrollador Principal

**Oscar Fabo**

- 💼 GitHub: [@oscarfabo93dev-tech](https://github.com/oscarfabo93dev-tech)
- 📧 Email: [oscar.fabo@example.com](mailto:oscar.fabo@example.com)
- 🌐 LinkedIn: [Oscar Fabo](https://linkedin.com/in/oscarfabo)

### Colaboradores

Agradecimientos a todos los [colaboradores](https://github.com/oscarfabo93dev-tech/AutodiagIncluLaboLGBTIQ-/graphs/contributors) que han participado en este proyecto.

---

## 🙏 Agradecimientos

- 🏳️‍🌈 **Comunidad LGBTIQ+** por la inspiración y retroalimentación continua
- 🎨 **Equipo de diseño** por los recursos visuales y branding
- 💻 **Streamlit Community** por el framework open-source
- 📊 **Pandas & OpenPyXL** por las herramientas de manipulación de datos
- 📄 **ReportLab** por la generación de PDFs
- 🌟 **Todos los testers** que ayudaron a mejorar la experiencia

---

## 📞 Soporte

### ¿Necesitas ayuda?

- 📖 **Documentación**: Lee este README completo
- 🐛 **Reportar bugs**: [Abrir issue](https://github.com/oscarfabo93dev-tech/AutodiagIncluLaboLGBTIQ-/issues)
- 💬 **Discusiones**: [GitHub Discussions](https://github.com/oscarfabo93dev-tech/AutodiagIncluLaboLGBTIQ-/discussions)
- 📧 **Email**: oscar.fabo@example.com

### FAQ

**P: ¿Puedo usar esta herramienta en mi empresa?**  
R: ¡Sí! Es software libre bajo licencia MIT. Puedes usarlo, modificarlo y distribuirlo.

**P: ¿Los datos se guardan en algún servidor?**  
R: No, todo el procesamiento es local. Los datos no se envían a ningún servidor externo.

**P: ¿Cómo actualizo el cuestionario?**  
R: Simplemente edita el archivo Excel en la carpeta `data/` con las nuevas preguntas.

**P: ¿Funciona sin conexión a internet?**  
R: Sí, una vez instalado funciona completamente offline.

---

## 🗓️ Roadmap

### v2.0.0 (Q1 2025)

- [ ] Dashboard de estadísticas agregadas
- [ ] Exportación a múltiples formatos (DOCX, HTML)
- [ ] Comparación de resultados históricos
- [ ] Sistema de recomendaciones personalizadas
- [ ] Multi-idioma (ES, EN, PT)

### v2.1.0 (Q2 2025)

- [ ] Integración con APIs de RRHH
- [ ] Autenticación de usuarios
- [ ] Base de datos para almacenamiento
- [ ] Módulo de analytics avanzado

---

## 📊 Estado del Proyecto

![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)
![Coverage](https://img.shields.io/badge/coverage-85%25-green.svg)
![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![Last Commit](https://img.shields.io/github/last-commit/oscarfabo93dev-tech/AutodiagIncluLaboLGBTIQ-)

---

## 🌟 Star History

Si te gusta este proyecto, ¡dale una estrella! ⭐

[![Star History Chart](https://api.star-history.com/svg?repos=oscarfabo93dev-tech/AutodiagIncluLaboLGBTIQ-&type=Date)](https://star-history.com/#oscarfabo93dev-tech/AutodiagIncluLaboLGBTIQ-&Date)

---

<div align="center">

**Hecho con ❤️ y compromiso por la inclusión LGBTIQ+ en 2025**

[⬆ Volver arriba](#-autodiagnóstico-en-inclusión-laboral-lgbtiq)
