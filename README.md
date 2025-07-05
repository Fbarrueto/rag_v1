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

## Licencia

Este proyecto se distribuye bajo la licencia MIT.

> ⚠️ Nota: N8N no es completamente open-source bajo MIT. Su uso en contextos comerciales puede requerir una licencia enterprise. Consulta más detalles en su [licencia oficial](https://github.com/n8n-io/n8n/blob/master/LICENSE.md).

---

¿Tienes dudas o quieres colaborar?  
Puedes abrir un issue o enviar un Pull Request directamente.
