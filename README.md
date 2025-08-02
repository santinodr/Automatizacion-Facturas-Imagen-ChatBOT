# Automatizacion-Facturas-Imagen-ChatBOT
Bot inteligente multiplataforma capaz de recibir facturas en formato de imagen vía chat (WhatsApp, Telegram, ect), extraer la información relevante mediante OCR, organizar datos financieros (ingresos, gastos, compras, ventas), y generar respuestas sobre el historial del usuario. Además, permite consultas por chat sobre movimientos pasados

---

📘 **Documentación completa del sistema**

### 🧠 Funcionalidad general
- Recepción de imagen desde apps de mensajería.
- Extracción de texto mediante OCR.
- Clasificación automática de datos (fecha, proveedor, productos, montos).
- Registro en base de datos (ganancias, pérdidas, detalles por ítem).
- Guarda toda la info importante ordenadamente en Google Sheet. 
- Motor conversacional para responder preguntas como:
  - “¿Qué compré en abril?”
  - “¿Cuánto gasté este mes?”
  - “¿Cuáles fueron mis ventas totales?”
  - “¿Qué tendría que comprar menos?”
  - “¿Qué piensas sobre mis compras?”
- Sistema de alertas y recordatorios (vía chat).

---

### 🏗️ Arquitectura Técnica
- **Frontend (opcional)**: Panel para visualización y carga manual.
- **Backend**:
  - **OCR**: Tesseract / Google Vision / Azure Form Recognizer
  - **Base de datos**: PostgreSQL / Supabase
  - **IA conversacional**: OpenAI API con RAG para contexto
  - **Orquestador**: n8n o Make para gestionar flujo completo
- **Seguridad**:
  - Autenticación de usuario por número/ID
  - Acceso por token para consulta segura
  - Encriptación de datos sensibles

---

### 📈 Flujos principales

**1. Recepción & extracción**
```plaintext
Usuario envía imagen → Bot detecta archivo → OCR extrae texto → Se clasifican campos → Se guarda en DB
```

**2. Conversación inteligente**
```plaintext
Usuario: “¿Qué gasté en julio?”
Bot: “Registraste 3 facturas por un total de $X. Proveedor principal: MercadoTech.”
```

**3. Recordatorios**
```plaintext
Bot analiza frecuencia de compras → Sugiere reabastecimiento o alerta de gasto
```

---

### 🎯 Casos de uso
- Freelancers que quieren gestionar gastos desde el móvil.
- Comercios que reciben muchas facturas y necesitan resumen automático.
- Usuarios que prefieren consultar su historial por chat en vez de planillas.
