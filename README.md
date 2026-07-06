# cybersecurity-portfolio
# Portfólio de Cibersegurança — Luan Basso


Portfólio com projetos práticos em cibersegurança defensiva, análise de logs, deteção de ataques, redes, Splunk, Wireshark, Linux e investigação de phishing.

## Sobre mim

Sou um profissional em transição para a área de Tecnologia e Cibersegurança, com formação prática de 300 horas em Cibersegurança pelo IEFP.

Tenho experiência laboratorial com análise de tráfego de rede, investigação de logs, deteção de atividades suspeitas, criação de regras de deteção, troubleshooting, fundamentos de redes e análise de emails suspeitos.

O meu objetivo é iniciar na área como **IT Support**, **Help Desk**, **NOC Analyst** ou **Cybersecurity Trainee**, aplicando conhecimentos práticos em suporte técnico, redes, monitorização e segurança defensiva.

---

## Competências Técnicas

- Troubleshooting técnico
- Linux e Windows
- Redes TCP/IP, DNS, DHCP, portas e protocolos
- Análise de logs e eventos de segurança
- Wireshark para análise de tráfego
- Splunk para investigação, correlação e alertas
- Nmap para reconhecimento em laboratório
- Análise de brute force, port scan, reverse shell e beaconing
- Análise de phishing, headers de email, SPF, DKIM e DMARC
- Conceitos de SOC, SIEM, NOC e resposta a incidentes

---

## Ferramentas Utilizadas

- Kali Linux
- Ubuntu Server
- Windows
- Splunk Enterprise
- Wireshark
- tcpdump
- Nmap
- Gobuster
- Netcat
- Metasploit Framework
- Hydra
- Python
- MXToolbox
- CyberChef

---

## Projetos Principais

| Projeto | Área | Ferramentas | Resultado / Evidência |
|---|---|---|---|
| SSH Brute-Force Detection with Splunk | SIEM / Detection Engineering | Splunk, OpenSSH, Nmap, Metasploit | Deteção de múltiplas tentativas falhadas de login SSH e criação de alerta no Splunk. |

| Port Scan Detection Engineering Lab | Reconhecimento / NOC / SOC | Nmap, Gobuster, tcpdump, Apache logs, Wireshark | Identificação de portas 22/SSH e 80/HTTP, enumeração web e lógica de deteção para comportamento de reconhecimento. |

| Reverse Shell Network Detection | Análise de Tráfego | Kali, Ubuntu, Netcat, Metasploit, Wireshark | Análise de comunicação suspeita na porta 4444 e identificação de indicadores de reverse shell. |

| Beaconing Traffic Detection | C2 / Análise Temporal | Kali, Ubuntu, Wireshark, Splunk | Deteção de 71 conexões HTTP periódicas com intervalo aproximado de 10 segundos. |

| FTP Brute Force Visibility Analysis | SIEM / Logs / Correlação | Splunk, vsftpd, Metasploit, Kali | Correlação de 273 falhas de login e 2 logins bem-sucedidos em 3 alertas agregados no Splunk. |

| Detection Rule Tuning & False Positive Reduction | Detection Engineering | Splunk, FTP logs, Hydra/Metasploit | Refinamento de regra para remover falsos positivos simulados sem perder a deteção do ataque real. |

| Phishing Email Header Forensics | Email Security / SOC | Python, MXToolbox, CyberChef, urlscan.io | Análise de 3 casos de email, incluindo phishing confirmado com falha de SPF/DMARC e domínio falso imitando PayPal. |

---

## Projetos em Destaque

### SSH Brute-Force Detection with Splunk

Projeto focado na deteção de tentativas repetidas de login SSH utilizando logs de autenticação e Splunk.

**O que foi feito:**

- Validação do serviço SSH exposto na porta 22.
- Geração controlada de falhas de autenticação em ambiente laboratorial.
- Ingestão de logs no Splunk.
- Extração de campos como IP de origem e utilizador.
- Criação de query SPL para identificar brute force.
- Configuração e validação de alerta no Splunk.

**Competências demonstradas:**

- Análise de logs SSH
- Criação de regra de deteção
- Uso de SPL
- Configuração de alerta
- Fluxo básico de trabalho SOC

---

### Port Scan Detection Engineering Lab

Projeto de deteção de atividade de reconhecimento contra um servidor Linux com SSH e Apache.

**O que foi feito:**

- Execução de diferentes tipos de scan com Nmap.
- Identificação dos serviços SSH e HTTP.
- Enumeração web com Gobuster e curl.
- Captura de tráfego com tcpdump.
- Análise de logs Apache.
- Criação de lógica de deteção para enumeração web e port scanning.

**Evidências observadas:**

- Porta 22/tcp aberta com OpenSSH.
- Porta 80/tcp aberta com Apache.
- Acessos a caminhos sensíveis como `.htaccess`, `.htpasswd` e `server-status`.
- Alto volume de respostas HTTP 404 geradas por enumeração.

**Competências demonstradas:**

- Reconhecimento defensivo
- Análise de Apache logs
- Deteção de web enumeration
- Análise de tráfego
- Criação de lógica SIEM

---

### Reverse Shell Network Detection

Laboratório para simular e analisar comportamento semelhante a reverse shell em ambiente controlado.

**O que foi feito:**

- Criação de ambiente com Kali Linux, Ubuntu Server e máquina de análise.
- Geração controlada de reverse shell em laboratório.
- Captura do tráfego com tcpdump/Wireshark.
- Análise de conexão TCP na porta 4444.
- Identificação de indicadores como IP de origem, IP de destino, porta e comportamento da sessão.

**Competências demonstradas:**

- Análise de tráfego de rede
- Identificação de comunicação suspeita
- Uso de Wireshark
- Interpretação de conexões TCP
- Fundamentos de deteção em ambiente SOC

---

### Beaconing Traffic Detection

Projeto focado na identificação de comunicação periódica semelhante a tráfego de Command & Control.

**O que foi feito:**

- Simulação de tráfego HTTP periódico em laboratório.
- Captura de tráfego com Wireshark/tcpdump.
- Análise temporal das conexões.
- Investigação no Splunk.
- Identificação de padrão repetitivo com intervalo aproximado de 10 segundos.

**Resultado observado:**

- 71 conexões HTTP para o mesmo destino.
- Mesmo IP de origem.
- Mesma porta de destino.
- URI repetida `/beacon`.
- Regularidade temporal compatível com comportamento de beaconing.

**Competências demonstradas:**

- Análise temporal de eventos
- Deteção de padrões repetitivos
- Investigação com Splunk
- Análise de tráfego HTTP
- Conceitos de C2 e beaconing

---

### FTP Brute Force Visibility Analysis

Projeto de comparação entre logs brutos e deteção SIEM durante um brute force FTP em ambiente controlado.

**O que foi feito:**

- Identificação do serviço FTP na porta 21.
- Geração controlada de tentativas de login.
- Análise do log bruto do vsftpd.
- Ingestão e correlação dos eventos no Splunk.
- Criação de lógica para classificar brute force e login bem-sucedido.

**Resultado observado:**

- 273 falhas de login.
- 2 logins bem-sucedidos.
- 275 eventos brutos analisados.
- Agregação dos eventos em 3 alertas no Splunk.

**Competências demonstradas:**

- Análise de logs FTP
- Correlação de eventos
- Criação de alerta
- Comparação entre log bruto e SIEM
- Visibilidade de ataque em ambiente monitorizado

---

### Detection Rule Tuning & False Positive Reduction

Projeto focado no refinamento de regras de deteção para reduzir falsos positivos.

**O que foi feito:**

- Criação de uma regra inicial com threshold simples.
- Simulação de atividade maliciosa e ruído benigno.
- Identificação de falsos positivos.
- Refinamento da regra com janela temporal e threshold mais adequado.
- Validação da deteção final no Splunk.

**Resultado observado:**

- A regra inicial detetava o ataque real, mas também gerava falso positivo.
- A regra refinada removeu os falsos positivos simulados.
- A deteção do ataque real foi mantida.

**Competências demonstradas:**

- Detection engineering
- Redução de falsos positivos
- Tuning de regras SIEM
- Correlação temporal
- Análise crítica de alertas

---

### Phishing Email Header Forensics

Projeto de investigação de emails suspeitos utilizando análise de headers, autenticação e indicadores de phishing.

**O que foi feito:**

- Análise de amostras `.eml`.
- Extração de headers e URLs.
- Verificação de SPF, DKIM e DMARC.
- Análise de domínios suspeitos.
- Identificação de tracking, spoofing e possível phishing.
- Criação de relatórios de incidente e lista de IOCs.

**Resultado observado:**

- 3 casos analisados.
- 2 casos classificados como suspeitos/marketing agressivo.
- 1 caso classificado como phishing confirmado.
- Identificação de domínio falso imitando PayPal.
- SPF e DMARC falharam no caso de phishing confirmado.

**Competências demonstradas:**

- Análise de phishing
- Email authentication
- Extração de IOCs
- Investigação de headers
- Criação de relatório de incidente

---

## Projeto em Desenvolvimento

### Duplicate File Detector & Quarantine Tool

Ferramenta em Python para deteção de ficheiros duplicados através de hash SHA-256, com interface gráfica, autenticação e movimentação dos duplicados para uma pasta de quarentena.

**Funcionalidades atuais:**

- Interface gráfica com Tkinter.
- Autenticação com password.
- Hashing seguro com Argon2id.
- Cálculo de hash SHA-256 dos ficheiros.
- Deteção de ficheiros duplicados.
- Movimentação de duplicados para quarentena.
- Criação de log dos ficheiros movidos.

**Estado:** Em desenvolvimento.

---

## Ambiente de Laboratório

Os projetos foram realizados em ambiente controlado e isolado, com máquinas virtuais e serviços próprios para fins educativos e defensivos.

Exemplo de ambiente utilizado:


Kali Linux        →        Ubuntu Server        →        Splunk / Wireshark
Testes controlados         Alvo laboratorial              Análise e monitorização
## Contacto

Email: luanbasso04@gmail.com  
GitHub: github.com/luanbasso04-ops  



Este portfólio está em desenvolvimento ativo. Novos projetos são adicionados regularmente.
