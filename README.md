# RAG Viva

> Un sistema open-source de Recuperación Aumentada (RAG) que puedes personalizar, auto-hospedar e integrar con tus propios documentos para potenciar el conocimiento interno de tu organización.

Este repositorio contiene una implementación basada en el código original de InsightsLM, adaptada y extendida bajo el proyecto **RAG Viva**. Puedes importar y comenzar desde:  
👉 [https://github.com/Fbarrueto/rag_viva_v2](https://github.com/Fbarrueto/rag_viva_v2)

---

## ¿Qué es RAG Viva?

**RAG Viva** es una plataforma de *Retrieval-Augmented Generation* que te permite subir documentos y obtener respuestas precisas basadas exclusivamente en las fuentes que proporcionas. Ideal para organizaciones que desean mantener control total sobre su información, sin depender de plataformas cerradas.

Construido con tecnologías modernas como Supabase, N8N y una interfaz React personalizable, RAG Viva es ideal para crear asistentes de IA privados que razonan sobre el conocimiento propio de una empresa, organización o comunidad.

---

## Características principales

- 📄 **Chat con tus documentos:** Sube PDFs, Word u otros archivos y comienza a hacer preguntas sobre su contenido.
- 🔎 **Citas verificables:** Respuestas acompañadas de enlaces a las fuentes originales, para evitar alucinaciones.
- 🔒 **100% privado y auto-hospedado:** Controlas dónde se almacena tu información y cómo se procesa.
- 🎙️ **Generación de audio/podcasts:** Convierte resúmenes o documentos en contenido audible.
- 🧩 **Extensible y modular:** Puedes personalizar tanto el frontend como el backend según tus necesidades.

---

## ¿Cómo comenzar?

Puedes clonar este proyecto desde el repositorio original aquí:  
📦 [https://github.com/Fbarrueto/rag_viva_v2](https://github.com/Fbarrueto/rag_viva_v2)

Luego, sigue los pasos detallados en la guía `GETTING_STARTED.md` dentro del repositorio para:

1. Crear tu proyecto en Supabase
2. Clonar el repositorio y editar tu configuración
3. Conectar los flujos de trabajo en N8N
4. Personalizar tu frontend y backend
5. ¡Listo para probar!

---

## Tecnologías utilizadas

- **Frontend:**
  - Vite + React + TypeScript
  - Tailwind CSS + shadcn/ui
- **Backend:**
  - Supabase (auth, DB, funciones edge)
  - N8N (automatizaciones)
  - OpenAI / Gemini (modelos LLM)

---


# Comenzando: Guía para No-Coders para Probar y Personalizar

Esta guía proporciona la forma más rápida de poner en marcha **RAGVIVA** para que puedas probar, personalizar y experimentar.

Te recomiendo seguir el video a partir del minuto 17:53 para una guía paso a paso completa:  
🔗 [Ver video](https://youtu.be/IXJEGjfZRBE?t=1073)

> ⚠️ Necesitarás tener un archivo de notas (notepad) abierto para copiar y pegar distintas credenciales y detalles.

---

## 1. Crear cuenta y proyecto en Supabase

1. Ve a [Supabase.com](https://supabase.com) y crea una cuenta gratuita.
2. Crea un nuevo proyecto.
3. Copia la contraseña de la base de datos y pégala en tu archivo de notas, ya que la necesitarás más adelante.

---

## 2. Crear cuenta de GitHub y repositorio desde la plantilla

1. Si no tienes una, crea una cuenta gratuita en [GitHub.com](https://github.com).
2. Navega al repositorio plantilla de InsightsLM:  
   🔗 [https://github.com/Fbarrueto/rag_v1/tree/main](https://github.com/Fbarrueto/rag_v1/tree/main)
3. Haz clic en el botón **"Use this template"** para crear una copia del repositorio en tu cuenta.
4. Completa el formulario para crear el nuevo repositorio.

---

## 3. Importar en un editor de IA (Bolt.new)

1. Crea una cuenta en [Bolt.new](https://bolt.new), ya que tiene integración con Supabase.  
   _(El proyecto fue creado inicialmente en Loveable, pero actualmente es más difícil importar proyectos existentes de GitHub allí)_
2. Importa tu repositorio de GitHub recién creado en tu proyecto de Bolt.
   - Tendrás que vincular tu cuenta de GitHub con Bolt.
   - Selecciona el repositorio y haz la importación.
3. Haz clic en la pestaña **"Integrations"** y conecta tu proyecto de Supabase.
   - Tendrás que vincular tu cuenta de Supabase con Bolt.
4. Una vez conectado, las **Edge Functions** de Supabase se desplegarán automáticamente.
   - Tendrás que aprobar la ejecución del **script de migración** para crear las estructuras de datos en Supabase.

---

## 4. Importar y configurar los flujos de trabajo N8N

La carpeta `/n8n` de este repositorio contiene los archivos JSON necesarios para los flujos de trabajo en **n8n**. Existen dos enfoques:

### Opción 1: Usar el importador de flujos
- Importa el archivo `Import_Insights_LM_Workflows.json` en un nuevo flujo en n8n.
- Sigue los pasos del video.
- Configura la **API key de n8n**, que se usará para crear automáticamente todos los flujos necesarios.
- También deberás configurar diversas credenciales.

### Opción 2: Importar manualmente cada flujo
- Descarga e importa los 6 archivos JSON de la carpeta `/n8n`.
- Configura nodo por nodo los servicios requeridos:
  - Supabase
  - OpenAI
  - Gemini
  - Sub-flujos
  - Etc.
- Sigue los **TODOs** dentro de cada flujo.

---

## 5. Agregar Webhooks de N8N a los Secrets de Supabase

Los flujos de trabajo de N8N se activan mediante **webhooks** desde las **Edge Functions** de Supabase.

- Si usaste el importador de flujos, tendrás la lista completa de secretos para crear.
- Si no, deberás obtenerlos desde los distintos flujos.

### En el panel de tu proyecto Supabase:
1. Navega a: `Edge Functions -> Secrets`
2. Agrega los siguientes secretos (con sus respectivos valores):

```text
NOTEBOOK_CHAT_URL  
NOTEBOOK_GENERATION_URL  
AUDIO_GENERATION_WEBHOOK_URL  
DOCUMENT_PROCESSING_WEBHOOK_URL  
ADDITIONAL_SOURCES_WEBHOOK_URL  
NOTEBOOK_GENERATION_AUTH (contraseña de autenticación por header personalizada para los webhooks de n8n)  
OPENAI_API_KEY (usada en la función “Generate Note Title”)


## Licencia

Este proyecto se distribuye bajo la licencia MIT.

> ⚠️ Nota: N8N no es completamente open-source bajo MIT. Su uso en contextos comerciales puede requerir una licencia enterprise. Consulta más detalles en su [licencia oficial](https://github.com/n8n-io/n8n/blob/master/LICENSE.md).

---

¿Tienes dudas o quieres colaborar?  
Puedes abrir un issue o enviar un Pull Request directamente.
