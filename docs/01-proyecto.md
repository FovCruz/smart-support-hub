# Smart Support Hub

## 01 - Finalidad y Arquitectura General del Sistema

### **1. Objetivo del Proyecto**

El proyecto **Smart Support Hub** tiene como objetivo desarrollar un sistema web inteligente que permite la **gestión automatizada de consultas o tickets de soporte**, integrando tecnologías de desarrollo fullstack, automatización de procesos e inteligencia artificial.  

El objetivo central es ofrecer una plataforma que facilite la atención y resolución de solicitudes mediante un **asistente inteligente** capaz de comprender el contexto y generar respuestas precisas, utilizando información propia de la organización.

---

### **2. Alcance del Proyecto**

El sistema permitirá que los usuarios registren consultas a través de una interfaz web y obtengan respuestas automáticas generadas por un asistente virtual.  
Para ello, se integran diferentes componentes tecnológicos que abarcan todo el flujo de procesamiento, desde la creación del ticket hasta la generación de la respuesta.

**Ámbitos cubiertos:**

- Desarrollo **Fullstack**: frontend, backend y base de datos.  
- **Automatización de procesos** mediante *n8n*.  
- **Inteligencia Artificial aplicada** con *LangChain* y *RAG (Retrieval Augmented Generation)*.  
- **Infraestructura cloud** desplegada en *Docker* sobre una *VPS (Linode)*.  

---

### **3. Arquitectura General del Sistema**

El sistema se compone de cinco módulos principales que trabajan de manera integrada para procesar las solicitudes de los usuarios.

---

#### **3.1. Frontend**

El **frontend** se implementa con **React** y **Tailwind CSS**, ofreciendo una interfaz moderna, adaptable y orientada a la experiencia del usuario.  

**Funciones principales:**

- Permitir el registro de consultas o tickets.  
- Mostrar el estado de las solicitudes realizadas.  
- Visualizar las respuestas automáticas generadas por el sistema.  

El frontend se comunica con el backend a través de una API **REST** o **GraphQL**, garantizando un flujo de información ágil y seguro.

---

#### **3.2. Backend**

El **backend** está desarrollado en **Node.js** utilizando el framework **Express**, encargado de manejar la lógica central del sistema y la comunicación entre servicios.

**Responsabilidades del backend:**

- Gestionar el registro y almacenamiento de las consultas.  
- Exponer endpoints de comunicación para el frontend.  
- Interactuar con la base de datos **PostgreSQL**.  
- Enviar eventos a **n8n** mediante webhooks.  
- Recibir y retornar las respuestas procesadas por el flujo de automatización e IA.  

---

#### **3.3. Base de Datos (PostgreSQL)**

El sistema utiliza **PostgreSQL** como motor de base de datos para el almacenamiento estructurado y persistente de la información.

**Datos gestionados:**

- Usuarios registrados.  
- Consultas y tickets creados.  
- Respuestas generadas por el asistente.  
- Documentos vectorizados utilizados por el componente RAG.  

Esta base de datos asegura integridad, rendimiento y escalabilidad, siendo el punto central de persistencia del sistema.

---

#### **3.4. Automatización con n8n**

El servicio **n8n** actúa como el motor de automatización encargado de coordinar la comunicación entre los distintos módulos del sistema.

**Flujo funcional de n8n:**

1. El backend envía un evento a *n8n* mediante un webhook al recibir una nueva consulta.  
2. *n8n* procesa el evento y ejecuta un flujo que:  
   - Envía la solicitud al modelo de lenguaje a través de **LangChain**.  
   - Consulta la base de conocimiento vectorizada (**RAG**) para obtener información contextual.  
3. La respuesta generada es devuelta al backend para su almacenamiento y posterior visualización en el frontend.  

Este componente permite la automatización de procesos complejos, reduciendo la intervención manual y mejorando los tiempos de respuesta.

---

#### **3.5. Inteligencia Artificial (LangChain + RAG)**

La inteligencia artificial se implementa utilizando **LangChain** junto con el enfoque **RAG (Retrieval Augmented Generation)**.  
Este módulo permite generar respuestas personalizadas y precisas basadas en la información interna de la organización.

**Funciones del módulo de IA:**

- Analizar las consultas ingresadas por el usuario.  
- Recuperar información relevante desde fuentes internas como PDFs, FAQs o manuales corporativos.  
- Generar respuestas coherentes y fundamentadas en el conocimiento existente.  

Este proceso combina recuperación de información semántica con generación de texto, logrando una interacción más natural y útil para el usuario final.

---

#### **3.6. Infraestructura y Despliegue**

El sistema se desplegará mediante contenedores **Docker**, permitiendo la ejecución independiente y controlada de cada servicio.  

**Servicios contenedorizados:**

- Frontend (React + Tailwind).  
- Backend (Node.js / Express).  
- Base de datos (PostgreSQL).  
- n8n (motor de automatización).  

El entorno de ejecución se implementará en una **VPS Linode**, configurada para garantizar conectividad segura, estabilidad y escalabilidad.  

El uso de contenedores facilita la portabilidad entre entornos de desarrollo, pruebas y producción, además de permitir una fácil replicación del sistema.

---

### **4. Objetivos Específicos**

- Construir un sistema web funcional para la gestión automatizada de consultas.  
- Implementar flujos de comunicación y automatización con n8n.  
- Incorporar un módulo de IA capaz de generar respuestas contextuales mediante LangChain y RAG.  
- Desplegar la solución completa en infraestructura cloud utilizando Docker.  
- Documentar cada componente y flujo para asegurar su mantenibilidad y escalabilidad futura.  

---

### **5. Aplicaciones Potenciales**

El sistema **Smart Support Hub** puede adaptarse a distintos contextos empresariales o institucionales, entre ellos:

- Plataformas de atención al cliente con respuestas automáticas.  
- Chatbots internos para soporte técnico o gestión documental.  
- Asistentes corporativos para recursos humanos o capacitación interna.  
- Sistemas de consulta inteligente basados en información propia de la organización.  

Debido al diseño modular, la solución puede evolucionar y escalar según los requerimientos específicos de cada implementación.  

---
