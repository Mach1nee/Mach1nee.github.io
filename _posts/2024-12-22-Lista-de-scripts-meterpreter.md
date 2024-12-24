---
title: "NASA ClickJacking"
date: 2024-12-07 13:00:00 -0300
categories: [Metasploit]
tags: [Lista]
---

![imagem](https://i.pinimg.com/736x/c4/12/3e/c4123ed77620f4d1a3b234986c79303b.jpg)

# Sobre
* Observe que novos scripts meterpreter estão sendo desenvolvidos todos os dias.
  Esta lista tenta fornecer a você uma lista completa de scripts no momento em que este texto foi escrito,
  logo com o passar do tempo os scripts na lista podem ter sido alterados

 * provavelmente você irá querer voltar aqui mais tarde para encontrar um script específico para um hack específico.

# Lista de scripts Meterpreter do msf
 arp_scanner.rb – Script para executar uma descoberta de varredura ARP. 
autoroute.rb – Sessão do Meterpreter sem precisar colocar a sessão atual em segundo plano. 
checkvm.rb – Script para detectar se o host de destino é uma máquina virtual. 
credcollect.rb – Script para coletar credenciais encontradas no host e armazená-las no banco de dados. 
domain_list_gen.rb – Script para extrair a lista de contas de administrador de domínio para uso. 
dumplinks.rb – Dumplinks analisa arquivos .lnk da pasta de documentos recentes de um usuário e da pasta de documentos recentes do Microsoft Office, se presente. Os arquivos .lnk contêm carimbos de data/hora, locais de arquivo, incluindo nomes de compartilhamento, números de série de volume e muito mais. Essas informações podem ajudar você a direcionar sistemas adicionais. 
duplicate.rb – Usa uma sessão meterpreter para gerar uma nova sessão meterpreter em um processo diferente. Um novo processo permite que a sessão tome ações “arriscadas” que podem fazer com que o processo seja morto pelo A/V, dando uma sessão meterpreter para outro controlador ou iniciando um keylogger em outro processo.
enum_chrome.rb – Script para extrair dados de uma instalação do Chrome.
enum_firefox.rb – Script para extrair dados do Firefox.enum_logged_on_users.rb – Script para enumerar usuários conectados no momento e usuários que efetuaram login no sistema.
enum_powershell_env.rb – Enumera configurações do PowerShell e WSH.
enum_putty.rb – Enumera conexões do Putty.
enum_shares.rb – Script para enumerar ações oferecidas e histórico de ações montadas.
enum_vmware.rb – Enumera configurações VMware para produtos VMware.
event_manager.rb – Mostra informações sobre Logs de Eventos no sistema de destino e sua configuração.
file_collector.rb – Script para pesquisar e baixar arquivos que correspondem a um padrão específico.
g et_application_list.rb – Script para extrair uma lista de aplicativos instalados e suas versões.
getcountermeasure.rb – Script para detectar AV, HIPS, Firewalls de Terceiros, Configuração DEP e configuração do Firewall do Windows. Também fornece a opção de matar os processos de produtos detectados e desabilitar o firewall integrado.
get_env.rb – Script para extrair uma lista de todas as variáveis ​​de ambiente do Sistema e do Usuário.
getfilezillacreds.rb – Script para extrair servidores e credenciais do Filezilla.
getgui.rb – Script para habilitar o Windows RDP.
get_local_subnets.rb – Obtenha uma lista de sub-redes locais com base nas rotas do host.
 get_pidgen_creds.rb – Script para extrair serviços configurados com nome de usuário e senhas.
gettelnet.rb – Verifica se o telnet está instalado.
get_valid_community.rb – Obtém uma string de comunidade válida do SNMP.
getvncpw.rb – Obtém a senha do VNC.
hashdump.rb – Obtém hashes de senha do SAM.
hostedit.rb – Script para adicionar entradas no arquivo Hosts do Windows.
keylogrecorder.rb – Script para executar o keylogger e salvar todas as teclas digitadas.
killav.rb – Encerra quase todos os softwares antivírus da vítima.
metsvc.rb – Exclui um serviço meterpreter e inicia outro.
migrar – Move o serviço meterpreter para outro processo.
multicommand.rb – Script para executar vários comandos em alvos Windows 2003, Windows Vista e Windows XP e Windows 2008.
multi_console_command.rb – Script para executar vários comandos de console em uma sessão meterpreter.
multi_meter_inject.rb – Script para injetar um Payload Meterpreter reverce tcp na memória de vários PIDs. Se nenhum for fornecido, um processo do bloco de notas será criado e um Payload Meterpreter será injetado em cada um.
multiscript.rb – Script para executar múltiplos scripts em uma sessão do Meterpreter.
netenum.rb – Script para varreduras de ping em alvos do Windows 2003, Windows Vista, Windows 2008 e Windows XP usando comandos nativos do Windows.
packetrecorder.rb – Script para capturar pacotes em um arquivo PCAP.
panda2007pavsrv51.rb – Este módulo explora uma vulnerabilidade de escalonamento de privilégios no Panda Antivirus 2007. Devido a problemas de permissão insegura, um invasor local pode obter privilégios elevados.
persistence.rb – Script para criar um backdoor persistente em um host de destino.
pml_driver_config.rb – Explora uma vulnerabilidade de escalonamento de privilégios no PML Driver HPZ12 da Hewlett-Packard. Devido a permissões inseguras do SERVICE_CHANGE_CONFIG DACL, um invasor local pode obter privilégios elevados.
powerdump.rb – Script Meterpreter para utilizar puramente o PowerShell para extrair hashes de nome de usuário e senha por meio de chaves de registro. Este script requer que você esteja executando como sistema para funcionar corretamente. Isso foi testado atualmente no Server 2008 e no Windows 7, que instalam o PowerShell por padrão.
prefetchtool.rb – Script para extrair informações da pasta prefetch do Windows.
process_memdump.rb – O script é baseado no artigo Neurosurgery With Meterpreter.
remotewinenum.rb – Este script enumerará hosts do Windows no ambiente de destino, dado um nome de usuário e senha ou usando a credencial sob a qual o Meterpeter está sendo executado usando a ferramenta nativa do Windows WMI wmic.
scheduleme.rb – Script para automatizar as tarefas de agendamento mais comuns durante um pentest. Este script funciona com Windows XP, Windows 2003, Windows Vista e Windows 2008.
schelevator.rb – Exploit para Escalação de Privilégios do Agendador de Tarefas 2.0 do Windows Vista/7/2008. Este script explora o Agendador de Tarefas 2.0 XML0day explorado pelo Stuxnet.
schtasksabuse.rb – Script Meterpreter para abusar do serviço do planejador no Windows, agendando e executando uma lista de comandos novamente em um ou mais alvos. Usando o comando schtasks para executá-los como sistema. Este script funciona com Windows XP, Windows 2003, Windows Vista e Windows 2008.
scraper.rb – O objetivo deste script é obter informações do sistema de uma vítima por meio de uma sessão existente do Meterpreter.
screenspy.rb – Este script abrirá uma visualização interativa de hosts remotos. Você precisará do Firefox instalado na sua máquina.
screen_unlock.rb – Script para desbloquear uma tela do Windows. Precisa de privilégios de sistema para executar e assinaturas conhecidas para o sistema alvo.
screen_dwld.rb – Script que pesquisa e baixa recursivamente arquivos que correspondem a um determinado padrão.
service_manager.rb – Script para gerenciar serviços do Windows.
service_permissions_escalate.rb  Este script tenta criar um serviço e, em seguida, pesquisa em uma lista de serviços existentes para encontrar permissões de arquivo ou configuração inseguras que permitirão que ele substitua o executável por um payload. Ele tentará reiniciar o serviço substituído para executar o payload. Se isso falhar, na próxima vez que o serviço for iniciado (como na reinicialização), o invasor obterá privilégios elevados.
sound_recorder.rb – Script para gravar em intervalos o som capturado por um microfone host alvo.
srt_webdrive_priv.rb – Explora uma vulnerabilidade de escalonamento de privilégios no South River Technologies WebDrive.
uploadexec.rb – Script para enviar arquivo executável para o host.
virtualbox_sysenter_dos – Script para DoS Virtual Box.
 virusscan_bypass.rb – Script que mata processos do Mcafee VirusScan Enterprise v8.7.0i+.
vnc.rb – Script Meterpreter para obter uma sessão VNC rápida.
webcam.rb – Script para habilitar e capturar imagens da webcam host.
win32-sshclient.rb – Script para implantar e executar o ssh-client de linha de comando “plink”. Suporta apenas hosts MS-Windows-2k/XP/Vista.
win32-sshserver.rb – Script para implantar e executar o OpenSSH na máquina de destino.
winbf.rb – Função para verificar a política de senha do sistema atual. Esta política pode assemelhar-se à política de outros servidores no ambiente de destino.
winenum.rb – Enumera o sistema Windows, incluindo variáveis ​​de ambiente, interfaces de rede, roteamento, contas de usuário, etc.
wmic.rb – Script para executar comandos WMIC em alvos Windows 2003, Windows Vista e Windows XP e Windows 2008.
