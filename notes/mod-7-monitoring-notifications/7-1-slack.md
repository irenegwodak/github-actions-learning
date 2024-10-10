Podemos usar aplicaciones de terceros para recibir notificaciones de Github Actions.

Para Slack hace falta crear un webhook:
Click en nombre del servidor/herramientas y ajustes/gestionar aplicaciones
Se abre el navegador, buscar "webhooks" y seleccionar "WebHooks entrantes"
[https://testgagrupo.slack.com/marketplace/A0F7XDUAZ-webhooks-entrantes]

Click en Add to Slack, elegir el canal
Copiar la URL y crear un nuevo secreto en Github Actions.

En el workflow añadimos la acción:

<!-- 
- name: slack notification
  uses: rtCamp/action-slack-notify@v2
  env:
    SLACK_WEBHOOK: ${{ secrets.SLACK_WEBHOOK_URL }}
  with:
      author_name: Github Actions
      fields: repo, message, commit, author, action, eventName
 -->