<p align="center">
	<img src="https://upload.wikimedia.org/wikipedia/en/thumb/c/c7/Dialogflow_logo.svg/694px-Dialogflow_logo.svg.png?20171011172202" />	
	</p>
Los chatbots son una parte esencial de cada plataforma de servicio al cliente.
</p>
Si tiene muchas conversaciones en curso en su cuenta, es posible que escalar el soporte humano no sea efectivo.
</p>
Puede implementar un chatbot que ayude a responder preguntas de trivia y entregárselo a un agente solo cuando sea necesario.
</p>
Dialogflow y Rasa.ai son las plataformas NLP mejor calificadas que le permiten construir un bot basado en su caso de uso.
</p>
En este artículo, veremos cómo puede configurar un chatbot de Dialogflow con Chattwoot.
</p>

</p>
<hr />
<p align="left">
	<img src="https://telegram.org/favicon.ico" alt="Telegram-logo" width="32" />
	<span>Grupo Telegram: </span>
	<a href="https://telinkei.com/gp-dialogflowbr-tg" target="_blank">Grupo</a>
</p>
<hr />
<p align="left">
	<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
	<span>Grupo WhatsaAPP: </span>
	<a href="https://telinkei.com/gp-dialogflowbr-" target="_blank">Grupo</a>
</p>
----------------------------------------------------------------------------
</p>

** ¿Te gustó el tutorial? Haz tu aporte**

<img src="https://github.com/EngagementoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="DialogFlow" width="200" />

</p>
-------------------------------------------------- --------------------------
</p>


**Configurando la integración de Dialogflow en Chatwoot**

**Crear un nuevo Agente**

</p>
Accede a la Consola de Dialogflow.
</p>
https://dialogflow.cloud.google.com
</p>
Usaremos Dialogflow Essentials para este artículo. Haga clic en "Crear nuevo agente". Mostraría opciones como se muestra a continuación.
</p>

<img src="https://www.chatwoot.com/docs/assets/images/create-new-agent-51f6b6bc6e6da84e81c18c0bbc06986a.png" alt="DialogFlow" width="1000" />

**Crear interacciones**

</p>
Deberá crear intenciones en función de cómo desea que responda su bot.
</p>
Habrá 2 intentos predeterminados en el proyecto llamados "Intento alternativo predeterminado" e "Intento de bienvenida predeterminado" como se muestra a continuación
</p>

<img src="https://www.chatwoot.com/docs/assets/images/default-intents-1159dded08111f981981ea9513cff68f.png" alt="DialogFlow" width="1000" />

</p>

**Ahora que la configuración básica del bot está lista, creemos una cuenta de servicio y conéctela a Chattwoot**

</p>
También puede crear intenciones adicionales para sus casos de uso específicos.
</p>
Chattwoot también admite intenciones avanzadas que permiten la transferencia de agentes, mensajería interactiva, etc.
</p>
ver: intenciones avanzadas
</p>

**Crear una cuenta**

</p>
Para conectar este bot a Chattwoot, debe crear una cuenta de servicio en su consola de Google Cloud.
</p>
Navegue a Google Cloud Project Console haciendo clic en el ID del proyecto en la Configuración del proyecto a continuación.
</p>

<img src="https://www.chatwoot.com/docs/assets/images/project-settings-7e5fb3d738a18ead8c0298b7af2b8276.png" alt="DialoFlow" width="1000" />

</p>
Vaya a IAM y administración -> Cuentas de servicio. Verá una vista previa como la siguiente. Haga clic en "Crear cuenta de servicio".
</p>

<img src="https://www.chatwoot.com/docs/assets/images/service-account-console-418be807b0449cb5e3a1ba539a106407.png" alt="DialoFlow" width="1000" />

Proporcione un nombre de cuenta de servicio y una descripción como se muestra a continuación.

<img src="https://www.chatwoot.com/docs/assets/images/service-account-details-4ab284d92f85ffca4f9f18702dcfc5b7.png" alt="DialoFlow" width="1000" />

Para proporcionar acceso, seleccione Dialogflow API Client en el menú desplegable.

<img src="https://www.chatwoot.com/docs/assets/images/service-access-88029531f5f8437b409ed22d1e7cab8f.png" alt="DialoFlow" width="1000" />

Continúe y haga clic en "Listo". Ahora podrá ver el servicio enumerado en el tablero. El siguiente paso es crear una clave para poder compartirla con Chattwoot. Haga clic en la cuenta de servicio y haga clic en la pestaña "Claves". Luego haga clic en "Agregar clave". Podrá ver una pantalla como la siguiente.

<img src="https://www.chatwoot.com/docs/assets/images/add-keys-885720919305b703fa3979807b445c7a.png" alt="DialoFlow" width="1000" />

</p>

**Haga clic en "JSON" y haga clic en "Crear". Generaría una clave para su cuenta de servicio, descargaría la clave y la guardaría para su uso posterior.**

</p>
Chattwoot tiene una integración nativa de Dialogflow.
</p>
Vaya a "Configuración -> Aplicaciones -> Dialogflow".
</p>
Haga clic en "Configurar", verá un botón para "Agregar un nuevo gancho".
</p>
Debe agregar "ID del proyecto", "Archivo de clave del proyecto" y un cuadro de entrada para crear un gancho.
</p>
(Copie el contenido del archivo clave previamente descargado y péguelo en el área de texto)
</p>

<img src="https://www.chatwoot.com/docs/assets/images/add-to-chatwoot-463fe037a8269b447e13e5f9c3d4c891.png" alt="Quepasa-logo" width="1000" />

</p>
¡Voila! La integración es completa.
</p>
Pruebe la bandeja de entrada del sitio para ver si el bot maneja la consulta inicial o no.
</p>

**Interacciones Avanzadas**

</p>
creando un
</p>
Después de que el usuario solicite hablar con el agente, Dialogflow debe informar a Chattwoot que un agente ahora puede hacerse cargo de la conversación.
</p>
Cree una intención llamada "Intención de transferencia" con frases de entrenamiento como "Hablar con un agente" o "Hablar con un agente", etc. para hacer frente a la
</p>
intento de transferencia, crearemos una respuesta de "Carga útil personalizada" como se muestra a continuación.
</p>

{
</p>
    "action": "handoff"
   </p>
}

</p>

<img src="https://www.chatwoot.com/docs/assets/images/handoff-intent-c24d32864b162046bd0ec929b0cc1be1.png" alt="Quepasa-logo" width="1000" />

</p>
Al activar una intención con la carga útil anterior, Chattwoot cambiará el estado de la conversación para abrirla y entregársela a un agente.
</p>

**Mensajes interactivos**

</p>
Nota: Por el momento, los mensajes interactivos solo se admiten en el canal del sitio web.
</p>
La integración de chatwoot de dialogflow también es compatible con la mensajería interactiva. Se admiten los siguientes tipos de mensajes interactivos:
</p>
Opciones: soporte soporte
</p>
tarjetas
</p>
Artículos
