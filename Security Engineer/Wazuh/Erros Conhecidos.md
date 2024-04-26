
### wazuh+i java consumindo muita memória
Ir para "*/etc/wazuh-indexer/jvm.options*" e editar "*Xmx*" e "*Xms*"

---

### Agentes desconectados

Para servidores Windows (Executar os comandos como administrador no Powershell):
- Start-Service WazuhSvc
- Set-Service -Name 'WazuhSvc' -StartupType Automatic

Para servidores Linux:
- sudo systemctl restart wazuh-agent
- sudo systemctl enable wazuh-agent

---

