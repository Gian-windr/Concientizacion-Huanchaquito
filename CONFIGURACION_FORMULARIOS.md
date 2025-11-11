# 📋 Configuración de Formularios - CuidemosHuanchaquito

## 🎯 Estado Actual

Actualmente el formulario de voluntarios en `participa.html`:
- ✅ Guarda los datos en **localStorage** del navegador como respaldo
- ✅ Muestra mensaje de confirmación al usuario
- ⚠️ **NO envía emails automáticamente** (requiere configuración adicional)

## 🔧 Opciones para Enviar Formularios

### **OPCIÓN 1: Formspree (RECOMENDADA - Gratis)**

Formspree es un servicio gratuito que convierte formularios HTML en emails.

**Pasos:**
1. Ve a https://formspree.io
2. Crea una cuenta gratis
3. Crea un nuevo formulario
4. Copia tu **Form ID** (ejemplo: `mzzbqpre`)
5. En `participa.html`, busca la línea 226 y descomenta:
   ```javascript
   const response = await fetch('https://formspree.io/f/TU_FORM_ID', {
       method: 'POST',
       body: formData,
       headers: {
           'Accept': 'application/json'
       }
   });
   ```
6. Reemplaza `TU_FORM_ID` con tu Form ID real

**Ventajas:**
- ✅ 50 envíos gratis al mes
- ✅ Fácil de configurar
- ✅ Recibe emails automáticamente
- ✅ Panel de administración web

---

### **OPCIÓN 2: Google Forms (Alternativa)**

Puedes crear un Google Form y embeber el formulario o usar su API.

**Pasos:**
1. Crea un Google Form en https://forms.google.com
2. Configura los campos igual que en tu HTML
3. Obtén el enlace de envío del formulario
4. Puedes redirigir o usar la API de Google Forms

---

### **OPCIÓN 3: Email Service (EmailJS)**

EmailJS permite enviar emails directamente desde JavaScript.

**Pasos:**
1. Regístrate en https://www.emailjs.com (200 emails gratis/mes)
2. Configura tu servicio de email
3. Obtén tu Service ID, Template ID y Public Key
4. Añade el SDK de EmailJS en tu HTML

---

### **OPCIÓN 4: Backend Propio (Avanzado)**

Si tienes un servidor propio (Node.js, PHP, Python):
- Crea un endpoint que reciba datos POST
- Configura un servicio de email (nodemailer, SendGrid, etc.)
- Actualiza la URL de envío en el JavaScript

---

## 📊 Ver Registros Guardados Localmente

Los datos se guardan temporalmente en el navegador. Para exportarlos:

1. Abre la **Consola del Navegador** (F12)
2. Escribe: `exportarVoluntarios()`
3. Se descargará un archivo JSON con todos los registros

**O manualmente:**
```javascript
// En la consola del navegador:
JSON.parse(localStorage.getItem('voluntarios'))
```

---

## 🔐 Seguridad y Privacidad

- Los datos en localStorage son temporales y solo locales
- Para producción, usa un servicio de backend seguro
- Considera implementar CAPTCHA para evitar spam
- Cumple con políticas de privacidad (GDPR, LFPDP Perú)

---

## 📧 Contacto del Proyecto

- **Email:** info@cuidemoshuanchaquito.pe
- **WhatsApp:** +51 999 999 999

---

## ✅ Configuración Recomendada para el Proyecto

Para este proyecto académico de Huanchaquito, recomiendo:
1. **Usar Formspree** (gratis, fácil, efectivo)
2. **Mantener el respaldo en localStorage**
3. **Exportar registros periódicamente**

¡Así tendrás un sistema funcional para recibir inscripciones de voluntarios!
