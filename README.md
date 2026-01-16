# 💳 Simulador de Crédito & Risk Engine

> **Sistema de evaluación crediticia y cálculo de amortización diseñado bajo estándares de la industria Fintech.**

Este proyecto es un **Simulador de Crédito Financiero** que no solo calcula tablas de amortización, sino que integra un motor de evaluación de riesgo que consume datos transaccionales de fuentes externas para determinar la viabilidad crediticia.

---

## 🚀 Propósito del Proyecto

Demostrar habilidades avanzadas en:

- **Backend Development**: Arquitectura limpia y asíncrona con FastAPI
- **QA Engineering**: Estrategias de pruebas unitarias, de integración y validación de contratos
- **Data Quality**: Manejo de precisión financiera mediante tipos de datos exactos (`Decimal`)
- **Integración**: Consumo de APIs bancarias externas (Mocked via Postman)

---

## 🏗️ Arquitectura

El sistema sigue los principios de **Clean Architecture**, separando la lógica de negocio de los detalles de implementación:

```
simulador_credito_qa/
├── app/
│   ├── schemas/          # Validación estricta de datos (Data Contracts) con Pydantic
│   ├── services/         # Lógica pura de negocio (Cálculos y Risk Engine)
│   ├── routers/          # Endpoints de la API (Swagger auto-documentado)
│   └── main.py           # Punto de entrada de la aplicación
├── tests/                # Suite completa de pruebas automatizadas
├── requirements.txt      # Dependencias del proyecto
└── README.md
```

### Capas del Sistema

- **`app/schemas`**: Validación estricta de datos (Data Contracts) con Pydantic
- **`app/services`**: Lógica pura de negocio (Cálculos de amortización y Risk Engine)
- **`app/routers`**: Endpoints de la API documentados automáticamente por Swagger
- **`tests/`**: Suite completa de pruebas automatizadas con Pytest

---

## 🛠️ Stack Tecnológico

| Componente | Tecnología |
|-----------|------------|
| **Framework** | FastAPI (Asynchronous Web Framework) |
| **HTTP Client** | HTTPX (Soporte nativo para `async/await`) |
| **Validación** | Pydantic v2 |
| **Testing** | Pytest con plugins para asincronía |
| **Procesamiento** | Python Native (`Decimal`) & Pandas |

---

## 🧪 Estrategia de Calidad (QA Focus)

Este proyecto pone especial énfasis en la **fiabilidad de los datos financieros**:

### 1. Validación de Contratos
Los datos entrantes del banco (JSON) son validados contra esquemas estrictos para asegurar consistencia en `currency`, `status` y `amounts`.

### 2. Precisión de Punto Flotante
Se evita el uso de `float` en cálculos de dinero, utilizando la librería `decimal` para garantizar que no se pierdan centavos en las tablas de amortización.

### 3. Manejo de Edge Cases
Pruebas específicas para:
- Transacciones fallidas
- Saldos insuficientes
- Mezclas de divisas (COP/USD)

---

## 🚦 Instalación y Uso

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu-usuario/simulador_credito_qa.git
cd simulador_credito_qa
```

### 2. Configurar el entorno

```bash
# Crear entorno virtual
python -m venv venv

# Activar entorno virtual
# En Linux/Mac:
source venv/bin/activate
# En Windows:
venv\Scripts\activate

# Instalar dependencias
pip install -r requirements.txt
```

### 3. Ejecutar la API

```bash
uvicorn app.main:app --reload
```

### 4. Acceder a la documentación interactiva

- **Swagger UI**: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
- **ReDoc**: [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)

---

## 🧪 Ejecutar las Pruebas

```bash
# Ejecutar todos los tests
pytest

# Ejecutar con cobertura
pytest --cov=app tests/

# Ejecutar tests específicos
pytest tests/test_services.py -v
```

---

## 📊 Funcionalidades Principales

### Motor de Riesgo Crediticio
- ✅ Evaluación de historial transaccional
- ✅ Análisis de patrones de gasto
- ✅ Scoring de riesgo automatizado

### Calculadora de Amortización
- ✅ Múltiples sistemas de amortización (Francés, Alemán, Americano)
- ✅ Cálculos con precisión decimal
- ✅ Generación de tablas completas de pagos

### Integración Bancaria
- ✅ Consumo asíncrono de APIs externas
- ✅ Validación de contratos de datos
- ✅ Manejo robusto de errores

---

## 📈 Roadmap / Próximos Pasos

- [ ] Integración de procesamiento masivo con Pandas para carga de clientes vía Excel/CSV
- [ ] Implementación de un servicio de Currency Conversion para normalizar transacciones en diferentes divisas
- [ ] Generación automática de reportes de amortización en PDF
- [ ] Dashboard de visualización de métricas de riesgo
- [ ] Sistema de notificaciones para aprobaciones/rechazos

---

## 📋 Requisitos del Sistema

- Python 3.10 o superior
- FastAPI
- HTTPX
- Pydantic v2
- Pytest

---

## 🎯 Casos de Uso

Este simulador está diseñado para:

- Evaluación preliminar de solicitudes de crédito
- Análisis de riesgo basado en comportamiento transaccional
- Cálculo preciso de tablas de amortización
- Prototipado rápido de productos financieros
- Validación de lógica de negocio en entornos Fintech

---

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Por favor:

1. Haz fork del proyecto
2. Crea una rama para tu feature (`git checkout -b feature/NuevaFuncionalidad`)
3. Asegúrate de que todos los tests pasen (`pytest`)
4. Commit tus cambios (`git commit -m 'Add: Nueva funcionalidad'`)
5. Push a la rama (`git push origin feature/NuevaFuncionalidad`)
6. Abre un Pull Request

---

## 📝 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

---

## 👤 Autor

**Edwin Leonardo Quintero**

- Rol: QA Analyst | Banking & Fintech Specialist | SQL & Data Validation
- GitHub: [@tu-usuario](https://github.com/tu-usuario)
- LinkedIn: [Tu Perfil](https://linkedin.com/in/tu-perfil)

---

## 📧 Contacto

Si tienes preguntas o sugerencias sobre el proyecto, no dudes en:

- Abrir un [Issue](https://github.com/tu-usuario/simulador_credito_qa/issues)
- Enviar un Pull Request
- Contactarme directamente

---

## ⭐ Agradecimientos

Este proyecto fue desarrollado como demostración de capacidades técnicas en:
- Desarrollo backend con Python
- Arquitectura de software limpia
- Prácticas de QA Engineering
- Manejo de datos financieros críticos
