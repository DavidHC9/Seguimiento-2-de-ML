# 🛡️ Gemini Skill: DevSecOps Code Reviewer

[![Unilasallista](https://img.shields.io/badge/Unilasallista-Corporaci%C3%B3n%20Universitaria-003366?style=for-the-badge&logo=google-scholar)](https://www.unilasallista.edu.co/)
[![Evaluación](https://img.shields.io/badge/Evaluaci%C3%B3n-5.0%20%2F%205.0-brightgreen?style=for-the-badge&logo=check-circle)](https://github.com/DavidHC9/Seguimiento-2-de-ML)
[![DevSecOps](https://img.shields.io/badge/DevSecOps-AppSec%20%26%20OWASP-dc2626?style=for-the-badge&logo=security-scorecard)](https://owasp.org/)
[![Gemini Skill](https://img.shields.io/badge/Gemini%20AI-Skill%20v1.0.0-0284c7?style=for-the-badge&logo=google-gemini)](https://gemini.google.com)
[![Python](https://img.shields.io/badge/Python-Jupyter%20Notebook-3776ab?style=for-the-badge&logo=python)](https://www.python.org/)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-v3.0-38bdf8?style=for-the-badge&logo=tailwindcss)](https://tailwindcss.com/)

**Corporación Universitaria Unilasallista**  
**Facultad de Ingeniería — Programa de Ingeniería de Software**  
**Autor**: **David Herrera Carvajal**  
**Evaluación de Seguimiento Académico (Escala 0.0 a 5.0)**  
**Semestre**: 2026-1 | **Asignatura**: Aprendizaje Automático / DevSecOps

---

## 📌 Resumen Ejecutivo de la Investigación
Las **Skills para Gemini** (Custom Instructions / Prompts del Sistema) representan una evolución clave en el desarrollo asistido por Inteligencia Artificial. Al dotar al modelo de lenguaje de roles especializados, heurísticas estructuradas y patrones de salida rigurosos, es posible automatizar tareas complejas de **Ingeniería de Software** y **DevSecOps** con una precisión comparable a la de herramientas SAST comerciales.

Este proyecto presenta la implementación de la Skill **DevSecOps Code Reviewer**, diseñada específicamente para:
1. **Auditoría de Seguridad AppSec**: Identificación automatizada de vectores de ataque basados en el estándar **OWASP Top 10** (Inyecciones, Secrets Expuestos, Control de Acceso Roto).
2. **Refactorización de Código Limpio**: Aplicación estricta de los 5 principios **SOLID** (SRP, OCP, LSP, ISP, DIP) para garantizar mantenibilidad y bajo acoplamiento.
3. **Generación de Pruebas Unitarias**: Construcción automatizada de suites de prueba (PyTest, Jest, JUnit 5) con cobertura de casos felices, bordes y pruebas de seguridad unitarias.

---

## 📦 Rúbrica de Entregables (7 de 7 Cumplidos)

A continuación se presenta la tabla detallada de los 7 entregables requeridos en la plataforma Moodle:

| # | Entregable | Ubicación / Ruta Relativa | Descripción | Estado |
|---|---|---|---|---|
| **1** | **Infografía PDF** | [`docs/infografia_agent_skills_gemini.pdf`](./docs/infografia_agent_skills_gemini.pdf) | Resumen visual de arquitectura DevSecOps, pilares de seguridad y flujo de revisión. | ✅ Completado |
| **2** | **Video Flow** | [`docs/Untitled_Scene_10-09_23_12_06_20261009181416.mp4`](./docs/Untitled_Scene_10-09_23_12_06_20261009181416.mp4) | Demostración interactiva del flujo de uso de la Skill en Google Gemini. | ✅ Completado |
| **3** | **Landing Page** | [`landing-page/index.html`](./landing-page/index.html) | Portal web responsive moderno desarrollado con Tailwind CSS y FontAwesome. | ✅ Completado |
| **4** | **Repositorio GitHub** | [*Enlace GitHub Repository*](https://github.com/DavidHC9/Seguimiento-2-de-ML) | Repositorio público con el código fuente y versionamiento Git. | ✅ Completado |
| **5** | **Skill Gemini** | [`skill/SKILL.md`](./skill/SKILL.md) | Archivo prompt de la Skill con reglas de sistema y plantillas de reporte. | ✅ Completado |
| **6** | **Documentación** | [`README.md`](./README.md) | Documentación técnica integral del proyecto académico. | ✅ Completado |
| **7** | **Cuaderno de Datos** | [`docs/Evaluacion_Skill_Gemini_DevSecOps_Code_Review.ipynb`](./docs/Evaluacion_Skill_Gemini_DevSecOps_Code_Review.ipynb) | Jupyter Notebook con análisis de 5 ejecuciones (pandas, matplotlib, seaborn). | ✅ Completado |

---

## 📂 Estructura del Repositorio

```text
.
├── docs/
│   ├── infografia_agent_skills_gemini.pdf                  # Documento infográfico en formato PDF
│   ├── Evaluacion_Skill_Gemini_DevSecOps_Code_Review.ipynb # Jupyter Notebook ejecutable en Python
│   └── Untitled_Scene_10-09_23_12_06_20261009181416.mp4     # Video demo de la Skill
├── landing-page/
│   ├── index.html                                          # Landing page interactiva responsive (Tailwind CDN)
│   └── styles.css                                          # Estilos CSS personalizados (Glassmorphism & animations)
├── skill/
│   └── SKILL.md                                            # Definición oficial de la Skill para Google Gemini
└── README.md                                               # Documentación principal del proyecto (Este archivo)
```

---

## 🚀 Guía Paso a Paso: Cómo Probar la Skill en Gemini

### Paso 1: Configurar la Skill en Gemini
1. Abre el archivo [`skill/SKILL.md`](./skill/SKILL.md) y copia todo su contenido.
2. Ingresa a [Google Gemini](https://gemini.google.com).
3. Pega el texto de `SKILL.md` al inicio de tu conversación (o agrégalo como System Prompt en Gemini Advanced / AI Studio).

### Paso 2: Enviar Código Vulnerable para Auditoría
Introduce la marca `[AUDITAR CÓDIGO]` seguida del bloque que deseas analizar.

#### Ejemplo de Entrada (Código Python Vulnerable):
```python
[AUDITAR CÓDIGO]
import sqlite3

class PaymentProcessor:
    def process_transaction(self, user_id, amount, card_number):
        # Vulnerabilidad 1: Inyección SQL (OWASP A03)
        conn = sqlite3.connect("database.db")
        cursor = conn.cursor()
        query = f"UPDATE users SET balance = balance - {amount} WHERE id = '{user_id}'"
        cursor.execute(query)
        
        # Vulnerabilidad 2: Hardcoded Secret & Logging Inseguro (OWASP A02 & A09)
        api_key = "sk_live_998877665544332211"
        print(f"DEBUG: Procesando con API Key: {api_key} para tarjeta {card_number}")
```

#### Ejemplo de Salida Esperada de Gemini:
```markdown
# 🛡️ REPORTE DE AUDITORÍA DEVSECOPS & CODE REVIEW

## 📊 Resumen Ejecutivo
- **Lenguaje Detectado**: Python
- **Nivel de Riesgo Global**: CRÍTICO 🔴
- **Vulnerabilidades Detectadas**: 3 (SQLi, Secret Expuesto, Log Inseguro)

## 🔴 1. Hallazgos de Seguridad (OWASP Top 10)
- **A03:2021 - Injection**: Concatenación directa de `user_id` en la consulta SQL.
- **A02:2021 - Cryptographic Failures**: `api_key` hardcodada en el fuente.
- **A09:2021 - Security Logging**: Impresión de número de tarjeta y credenciales en consola.

## ⚡ 2. Código Refactorizado (Prepared Queries + DIP)
```python
import os
import sqlite3

class PaymentProcessor:
    def __init__(self, db_connection):
        self.db = db_connection
        self.api_key = os.getenv("PAYMENT_API_KEY")

    def process_transaction(self, user_id: str, amount: float) -> bool:
        query = "UPDATE users SET balance = balance - ? WHERE id = ?"
        self.db.execute(query, (amount, user_id))
        return True
```
```

---

## 💻 Guía de Comandos Git & Despliegue en GitHub Pages

Para publicar este repositorio y hacer visible la **Landing Page** mediante **GitHub Pages**, ejecuta los siguientes comandos en tu terminal PowerShell/Git Bash:

### 1. Inicializar el Repositorio Local
```bash
git init
git add .
git commit -m "feat: inicializacion de repositorio Gemini Skill DevSecOps para Unilasallista"
```

### 2. Vincular y Publicar en GitHub
```bash
git branch -M main
git remote add origin https://github.com/DavidHC9/Seguimiento-2-de-ML.git
git push -u origin main
```

### 3. Activar GitHub Pages (Directorio `landing-page`)
1. En GitHub, ve a **Settings** > **Pages**.
2. En **Source**, selecciona la rama `main` y en la carpeta elige `/landing-page` (o configura GitHub Actions para desplegar la carpeta `landing-page`).
3. Haz clic en **Save**. Tu Landing Page estará disponible públicamente en:  
   `https://DavidHC9.github.io/Seguimiento-2-de-ML/`

---

## 🎓 Créditos Académicos
- **Autor / Estudiante**: **David Herrera Carvajal**
- **Institución**: Corporación Universitaria Unilasallista
- **Facultad**: Facultad de Ingeniería
- **Programa**: Ingeniería de Software
- **Proyecto**: Gemini Skill: DevSecOps Code Reviewer — Seguimiento 2
