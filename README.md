<div align="center">

# 🖥️ MeshCentral: Acesso Remoto Open-Source, Seu Próprio "AnyDesk"

### Controle computadores, servidores e dispositivos de qualquer lugar, com a sua marca, nos seus servidores e sem mensalidade por dispositivo.

[![Licença](https://img.shields.io/badge/licen%C3%A7a-Apache%202.0-blue.svg)](https://github.com/Ylianst/MeshCentral/blob/master/license.txt)
[![Node.js](https://img.shields.io/badge/Node.js-%E2%89%A5%2016-green.svg)](https://nodejs.org/)
[![Docker](https://img.shields.io/badge/Docker-pronto-2496ED.svg)](#-instala%C3%A7%C3%A3o-com-docker)
[![Docs](https://img.shields.io/badge/docs-meshcentral-orange.svg)](https://docs.meshcentral.com/)
[![Self-Hosted](https://img.shields.io/badge/self--hosted-100%25-success.svg)](#)

[📚 Documentação Oficial](https://docs.meshcentral.com/) • [🚀 Início Rápido](#-in%C3%ADcio-r%C3%A1pido) • [🎨 Personalização](#-personaliza%C3%A7%C3%A3o-e-white-label) • [⚖️ Comparativo](#%EF%B8%8F-meshcentral-vs-anydesk) • [❓ FAQ](#-faq)

</div>

---

## 📖 Índice

- [O que é o MeshCentral?](#-o-que-%C3%A9-o-meshcentral)
- [Por que usar no lugar do AnyDesk?](#-por-que-usar-no-lugar-do-anydesk)
- [Principais recursos](#-principais-recursos)
- [Arquitetura](#%EF%B8%8F-arquitetura)
- [Início rápido](#-in%C3%ADcio-r%C3%A1pido)
- [Instalação com Docker](#-instala%C3%A7%C3%A3o-com-docker)
- [Configuração básica](#%EF%B8%8F-configura%C3%A7%C3%A3o-b%C3%A1sica-configjson)
- [Instalando o agente nos dispositivos](#-instalando-o-agente-nos-dispositivos)
- [Personalização e white-label](#-personaliza%C3%A7%C3%A3o-e-white-label)
- [Segurança](#-seguran%C3%A7a)
- [MeshCentral vs AnyDesk](#%EF%B8%8F-meshcentral-vs-anydesk)
- [Casos de uso](#-casos-de-uso)
- [Roadmap deste repositório](#%EF%B8%8F-roadmap-deste-reposit%C3%B3rio)
- [Como contribuir](#-como-contribuir)
- [FAQ](#-faq)
- [Licença e créditos](#-licen%C3%A7a-e-cr%C3%A9ditos)

---

## 🚀 O que é o MeshCentral?

O **[MeshCentral](https://docs.meshcentral.com/)** é uma plataforma **100% open-source** de **gerenciamento e acesso remoto de computadores**, criada por Ylian Saint-Hilaire e mantida por uma comunidade ativa. Com ele você instala um servidor próprio e passa a controlar máquinas **Windows, Linux, macOS e FreeBSD** direto pelo navegador, sem depender de serviços de terceiros.

Pense nele como a combinação de:

| Você conhece como...      | No MeshCentral é...                                   |
| ------------------------- | ----------------------------------------------------- |
| AnyDesk / TeamViewer      | Área de trabalho remota via navegador                 |
| SSH / PowerShell remoto   | Terminal remoto integrado                             |
| WinSCP / FileZilla        | Gerenciador de arquivos remoto                        |
| RMM (gestão de endpoints) | Inventário, monitoramento, grupos e scripts           |
| VPN / túnel               | MeshCentral Router (mapeia portas TCP/UDP)            |

> 💡 **Resumo:** é uma central de suporte remoto que **você hospeda, controla e personaliza**.

---

## 🎯 Por que usar no lugar do AnyDesk?

O AnyDesk é uma ótima ferramenta, mas é **proprietária**: você depende do plano do fornecedor, dos limites de licença e das regras dele. Com o MeshCentral, o jogo muda:

### 💰 1. Sem custo de licença por dispositivo ou por técnico
O software é gratuito. Seu custo é apenas a infraestrutura (uma VPS pequena já atende muita gente). Cresça de 10 para 10.000 máquinas sem renegociar contrato.

### 🔐 2. Seus dados ficam com você
As conexões passam **pelo seu servidor**, não por uma nuvem de terceiros. Ideal para empresas que precisam atender **LGPD**, políticas internas de compliance ou ambientes isolados (air-gapped / rede interna).

### 🎨 3. Customização total (a grande vantagem)
Por ser **open-source**, o código está aberto: você pode **trocar logos, cores, textos, domínios e até alterar o comportamento da plataforma**, entregando uma solução com a **sua marca** para clientes ou equipe (white-label).

### 🧩 4. Sem lock-in
Nada de ficar refém de um fornecedor. Os dados e a configuração são seus; você pode migrar, integrar via API ou até criar um *fork*.

### 🏢 5. Feito para equipes e multiempresa
Usuários, grupos de dispositivos, permissões granulares, múltiplos domínios e autenticação em dois fatores já vêm de fábrica.

---

## ✨ Principais recursos

### 🖱️ Acesso remoto
- **Desktop remoto** via navegador (sem instalar cliente no lado do técnico)
- **Terminal remoto** (Shell / PowerShell / bash)
- **Gerenciador de arquivos**: upload, download e edição remota
- **Compartilhamento de tela** e controle de mouse/teclado
- **Cópia e cola** entre máquinas, e suporte a vários monitores
- **Wake-on-LAN** para ligar máquinas remotamente
- **Chat** com o usuário final e **notificações**

### 🛠️ Gerenciamento de dispositivos
- Inventário de hardware e software
- Monitoramento de status (online/offline)
- Execução de **comandos e scripts** em um ou vários dispositivos
- Agrupamento de máquinas em **"Device Groups"**
- Reinício, desligamento e logoff remoto

### 👥 Usuários e permissões
- Contas de usuário, grupos e **permissões por dispositivo**
- **Autenticação em 2 fatores (2FA)**
- Integração com **LDAP / Active Directory** e **login único (SSO)**
- Suporte a **múltiplos domínios** (multi-tenant)

### 🔌 Extensibilidade
- **API e WebSocket** para automações
- **Plugins**
- Ferramentas de linha de comando (**MeshCtrl**)
- **MeshCentral Router** para encaminhar portas (RDP, SSH, VNC, HTTP, etc.)
- Suporte a **Intel® AMT** para gerenciamento fora de banda (BIOS, KVM por hardware)

### 🌐 Implantação
- Roda em **Windows, Linux, macOS** e **Docker**
- Suporte a **Raspberry Pi** e dispositivos ARM
- Bancos de dados: **NeDB** (padrão), **MongoDB**, **MySQL/MariaDB**, **PostgreSQL**
- Agentes leves, com **instalador personalizável**

---

## 🏗️ Arquitetura

```
        ┌───────────────────────┐
        │   Técnico / Usuário   │
        │  (Navegador ou App)   │
        └───────────┬───────────┘
                    │ HTTPS / WSS
                    ▼
        ┌───────────────────────┐
        │   Servidor MeshCentral│  ← você hospeda (VPS, on-premise, Docker)
        │   (Node.js + Banco)   │
        └───────────┬───────────┘
                    │ Conexão segura (agente → servidor)
        ┌───────────┼───────────┐
        ▼           ▼           ▼
   ┌─────────┐ ┌─────────┐ ┌─────────┐
   │ Agente  │ │ Agente  │ │ Agente  │
   │ Windows │ │  Linux  │ │  macOS  │
   └─────────┘ └─────────┘ └─────────┘
```

Os agentes **se conectam de dentro para fora** ao servidor, o que facilita o acesso a máquinas atrás de **NAT e firewalls**, sem precisar abrir portas em cada cliente.

---

## ⚡ Início rápido

### Pré-requisitos
- Servidor (Linux recomendado) ou máquina Windows
- **Node.js** (versão LTS) e **npm**
- Um **domínio** apontando para o servidor (recomendado, para usar HTTPS com certificado válido)

### Instalação via npm

```bash
# 1. Crie uma pasta para o servidor
mkdir meshcentral && cd meshcentral

# 2. Instale o MeshCentral
npm install meshcentral

# 3. Inicie o servidor
node node_modules/meshcentral
```

Na primeira execução, o MeshCentral gera certificados e a pasta `meshcentral-data`. Depois, acesse no navegador:

```
https://SEU_SERVIDOR
```

> ⚠️ **O primeiro usuário criado se torna o administrador do servidor.** Crie sua conta imediatamente após a instalação.

### Executando como serviço (Linux/systemd)

```ini
# /etc/systemd/system/meshcentral.service
[Unit]
Description=MeshCentral Server
After=network.target

[Service]
Type=simple
User=meshcentral
WorkingDirectory=/opt/meshcentral
ExecStart=/usr/bin/node /opt/meshcentral/node_modules/meshcentral
Restart=always
RestartSec=10

[Install]
WantedBy=multi-user.target
```

```bash
sudo systemctl daemon-reload
sudo systemctl enable --now meshcentral
```

> 📌 Consulte o [guia oficial de instalação](https://docs.meshcentral.com/) para opções específicas de cada sistema operacional.

---

## 🐳 Instalação com Docker

O projeto oficial disponibiliza imagem Docker. Exemplo de `docker-compose.yml`:

```yaml
services:
  meshcentral:
    image: ghcr.io/ylianst/meshcentral:latest
    container_name: meshcentral
    restart: unless-stopped
    ports:
      - "443:443"
    environment:
      - HOSTNAME=suporte.seudominio.com.br
      - USE_EXTERNAL_DNS=true
      - REVERSE_PROXY=false
    volumes:
      - ./meshcentral/data:/opt/meshcentral/meshcentral-data
      - ./meshcentral/user_files:/opt/meshcentral/meshcentral-files
      - ./meshcentral/backup:/opt/meshcentral/meshcentral-backups
      - ./meshcentral/web:/opt/meshcentral/meshcentral-web
```

```bash
docker compose up -d
```

> ✅ Os volumes garantem que **dados, arquivos, backups e personalizações visuais** sobrevivam a atualizações do contêiner.
> ⚠️ Confira as variáveis de ambiente e tags de imagem mais recentes na documentação oficial, pois podem mudar entre versões.

---

## ⚙️ Configuração básica (`config.json`)

O arquivo fica em `meshcentral-data/config.json`. Exemplo inicial:

```json
{
  "$schema": "https://raw.githubusercontent.com/Ylianst/MeshCentral/master/meshcentral-config-schema.json",
  "settings": {
    "cert": "suporte.seudominio.com.br",
    "port": 443,
    "redirPort": 80,
    "WANonly": true
  },
  "domains": {
    "": {
      "title": "Minha Empresa",
      "title2": "Suporte Remoto",
      "newAccounts": false,
      "userNameIsEmail": true
    }
  }
}
```

| Opção            | Função                                                              |
| ---------------- | ------------------------------------------------------------------- |
| `cert`           | Nome DNS do servidor (usado nos certificados e nos agentes)         |
| `port`           | Porta HTTPS principal                                               |
| `redirPort`      | Porta HTTP que redireciona para HTTPS                               |
| `WANonly`        | Servidor acessível pela internet                                    |
| `newAccounts`    | `false` impede que qualquer pessoa crie conta (recomendado)         |
| `title / title2` | Título e subtítulo exibidos na interface                            |

> 🔧 **Dica:** após editar o `config.json`, reinicie o serviço para aplicar as mudanças.

---

## 📥 Instalando o agente nos dispositivos

1. Faça login no painel do MeshCentral.
2. Crie um **Device Group** (ex.: "Clientes", "Servidores", "Matriz").
3. Clique em **Add Agent** e escolha o sistema operacional do dispositivo.
4. Baixe o instalador (ou copie o comando de instalação) e execute no computador alvo.
5. Pronto: o dispositivo aparece online no painel e já pode ser controlado.

### Modos de uso

| Modo                   | Quando usar                                                                 |
| ---------------------- | --------------------------------------------------------------------------- |
| **Agente instalado**   | Acesso permanente e não supervisionado (servidores, estações da empresa)    |
| **Agente temporário**  | Suporte pontual, com o usuário executando sem instalar (estilo AnyDesk)     |
| **Convite por link**   | Enviar um link ao usuário para iniciar uma sessão de suporte                |

---

## 🎨 Personalização e White-Label

> **Esta é a grande vantagem sobre soluções fechadas.** Como o MeshCentral é open-source, você pode transformá-lo em um produto com a **sua identidade visual**.

### O que você pode personalizar

| Item                          | Como                                                                          |
| ----------------------------- | ----------------------------------------------------------------------------- |
| 🏷️ **Nome e títulos**         | `title` e `title2` no `config.json`                                           |
| 🖼️ **Logotipo e imagens**     | Substituindo arquivos na pasta `meshcentral-web`                              |
| 🌈 **Cores e estilo (CSS)**   | Sobrescrevendo views e estilos em `meshcentral-web`                           |
| 📝 **Textos da tela de login**| Configurações de domínio e views personalizadas                               |
| 🌐 **Idioma**                 | Suporte a vários idiomas, incluindo **português**                             |
| 🌍 **Domínio próprio**        | `suporte.suaempresa.com.br`                                                   |
| 📦 **Instalador do agente**   | Nome, ícone e descrição do agente podem ser personalizados                    |
| 🏢 **Multi-domínio**          | Uma instalação, várias marcas/clientes                                        |
| 🧬 **Código-fonte**           | Faça *fork* e altere qualquer comportamento                                   |

### Como aplicar sua marca (visão geral)

```text
meshcentral-web/
├── views/          # Cópias das telas (HTML/Handlebars) que você deseja alterar
└── public/         # Imagens, CSS, JS e logotipos próprios
```

1. Copie as views que deseja modificar do código original para `meshcentral-web/views`.
2. Edite o HTML/CSS com sua identidade visual.
3. Coloque logotipos e imagens em `meshcentral-web/public`.
4. Reinicie o servidor.

> 📚 **Passo a passo oficial:** consulte a seção de personalização/branding na [documentação do MeshCentral](https://docs.meshcentral.com/), pois os nomes de arquivos e opções podem variar entre versões.

### 💼 Ideias de customização para este projeto

- [ ] Tema visual completo (cores, logo, favicon)
- [ ] Tela de login com a identidade da empresa
- [ ] Textos e mensagens 100% em **português (BR)**
- [ ] Instalador do agente com nome e ícone da marca
- [ ] Página de "Suporte rápido" com botão de download (estilo AnyDesk)
- [ ] Termo de consentimento personalizado antes da sessão remota
- [ ] Integração com sistema de chamados (GLPI, Zammad, Freshdesk, etc.)
- [ ] Notificações via Telegram / WhatsApp / e-mail
- [ ] Painel com relatórios próprios via API

---

## 🔒 Segurança

O MeshCentral foi pensado com segurança em mente, mas **a segurança final depende da sua configuração**. Boas práticas:

- ✅ Use **HTTPS** com certificado válido (Let's Encrypt)
- ✅ Ative **2FA** para todos os administradores
- ✅ Defina `"newAccounts": false` para bloquear cadastros abertos
- ✅ Mantenha o **MeshCentral, Node.js e o sistema operacional atualizados**
- ✅ Faça **backups periódicos** da pasta `meshcentral-data`
- ✅ Use **permissões mínimas** por usuário e por grupo de dispositivos
- ✅ Habilite **notificação/consentimento do usuário** em sessões de suporte
- ✅ Considere um **proxy reverso** (Nginx / Traefik / Caddy) e firewall
- ✅ Restrinja acessos administrativos por IP quando possível
- ✅ Ative logs e revise eventos regularmente

---

## ⚖️ MeshCentral vs AnyDesk

> Comparativo de **modelo e filosofia**. Recursos e preços de produtos comerciais mudam; confirme sempre nos sites oficiais.

| Critério                      | 🟢 MeshCentral                         | 🔴 AnyDesk (proprietário)              |
| ----------------------------- | -------------------------------------- | -------------------------------------- |
| **Código-fonte**              | Aberto (Apache 2.0)                    | Fechado                                |
| **Custo de licença**          | Gratuito                               | Planos pagos por licença/recursos      |
| **Hospedagem**                | Você escolhe (self-hosted)             | Infraestrutura do fornecedor           |
| **Controle dos dados**        | Total                                  | Dependente do fornecedor               |
| **White-label / marca própria** | Sim, livre e sem restrição           | Limitado / sujeito a plano e contrato  |
| **Customização do código**    | Ilimitada (fork)                       | Não é possível                         |
| **Limite de dispositivos**    | Limitado pelo seu servidor             | Limitado pelo plano contratado         |
| **Acesso via navegador**      | Sim                                    | Parcial                                |
| **Terminal e arquivos**       | Integrados                             | Variável conforme o plano              |
| **Gerenciamento (RMM)**       | Inventário, scripts, grupos            | Variável conforme o plano              |
| **Integração por API**        | Aberta                                 | Conforme o plano                       |
| **Intel AMT / fora de banda** | Suportado                              | Não é o foco                           |
| **Suporte**                   | Comunidade + documentação + você       | Suporte comercial                      |
| **Facilidade inicial**        | Exige configurar o servidor            | Pronto para usar                       |

### 🧭 Quando o MeshCentral é a melhor escolha?
- Você quer **reduzir custos** com licenças recorrentes.
- Precisa de **privacidade e controle** sobre as conexões.
- Quer oferecer suporte remoto **com a sua marca**.
- Precisa **integrar** o acesso remoto a outros sistemas.
- Gerencia **muitos dispositivos** ou **vários clientes**.

### ⚠️ Quando considerar com cuidado?
- Você não tem ninguém para **administrar o servidor**.
- Precisa de **suporte comercial 24/7 com SLA** do fornecedor.
- Não quer lidar com **atualizações e manutenção**.

---

## 💼 Casos de uso

| Perfil                         | Como o MeshCentral ajuda                                              |
| ------------------------------ | --------------------------------------------------------------------- |
| 🧑‍💻 **Empresas de TI / MSPs**    | Atender vários clientes com marca própria e sem custo por máquina     |
| 🏢 **Empresas (TI interna)**    | Suporte a colaboradores e gestão de parque de máquinas                |
| 🏫 **Escolas e universidades** | Gerenciar laboratórios e computadores de forma centralizada           |
| 🏥 **Saúde e setor regulado**  | Manter dados e sessões em infraestrutura própria                      |
| 🏭 **Indústria / IoT**         | Acesso a máquinas e equipamentos em redes remotas                     |
| 🏠 **Home lab / entusiastas**  | Acessar PCs, servidores e Raspberry Pi de qualquer lugar              |
| 👨‍👩‍👧 **Suporte familiar**      | Ajudar parentes à distância, sem pagar por isso                       |

---

## 🗺️ Roadmap deste repositório

- [ ] Documentar a instalação passo a passo em português
- [ ] Publicar tema/branding personalizado
- [ ] Criar `docker-compose` pronto para produção (com proxy reverso e HTTPS automático)
- [ ] Scripts de backup e restauração automatizados
- [ ] Guia de integração com sistema de chamados
- [ ] Tutorial em vídeo
- [ ] Página de download rápido para usuários finais

> 💬 Tem uma ideia? Abra uma *issue*!

---

## 🤝 Como contribuir

Contribuições são muito bem-vindas!

1. Faça um **fork** deste repositório
2. Crie uma branch: `git checkout -b minha-melhoria`
3. Faça seus commits: `git commit -m "Adiciona minha melhoria"`
4. Envie para o seu fork: `git push origin minha-melhoria`
5. Abra um **Pull Request**

Você também pode ajudar **reportando bugs**, **melhorando a documentação**, **traduzindo** ou **compartilhando o projeto**.

---

## ❓ FAQ

<details>
<summary><b>O MeshCentral é realmente gratuito?</b></summary>

Sim. É open-source sob a licença Apache 2.0. Você paga apenas pela infraestrutura onde hospeda (VPS, energia, domínio etc.).
</details>

<details>
<summary><b>Posso usar comercialmente e cobrar de clientes?</b></summary>

A licença Apache 2.0 permite uso comercial e modificações. Leia a licença para entender as obrigações (como manter os avisos de copyright e de licença).
</details>

<details>
<summary><b>Preciso de IP fixo ou abrir portas nos clientes?</b></summary>

Não nos clientes: os agentes se conectam ao servidor. Apenas o **servidor** precisa estar acessível (IP público ou domínio, e portas liberadas).
</details>

<details>
<summary><b>Funciona atrás de NAT/CGNAT?</b></summary>

Os dispositivos com agente normalmente funcionam, pois iniciam a conexão com o servidor. Já o **servidor** deve ter endereço acessível, ou você pode usar uma VPS na nuvem.
</details>

<details>
<summary><b>Funciona em celular?</b></summary>

O painel é acessível pelo navegador do celular e há suporte a dispositivos móveis dentro do ecossistema. Verifique na documentação oficial os recursos disponíveis para cada plataforma.
</details>

<details>
<summary><b>Posso trocar o logotipo e o nome?</b></summary>

Sim, essa é uma das maiores vantagens. Veja a seção [Personalização e White-Label](#-personaliza%C3%A7%C3%A3o-e-white-label).
</details>

<details>
<summary><b>Como faço backup?</b></summary>

Faça backup da pasta `meshcentral-data` (configuração, certificados e banco de dados) e dos diretórios de arquivos e personalização. O MeshCentral também oferece rotinas de backup automáticas configuráveis.
</details>

<details>
<summary><b>Onde encontro ajuda?</b></summary>

Na [documentação oficial](https://docs.meshcentral.com/), no repositório oficial no GitHub e nas comunidades de usuários.
</details>

---

## 📄 Licença e créditos

- **MeshCentral** é um projeto de **Ylian Saint-Hilaire** e colaboradores, distribuído sob a licença **Apache 2.0**.
- Repositório oficial: <https://github.com/Ylianst/MeshCentral>
- Documentação oficial: <https://docs.meshcentral.com/>

> Este repositório **não é afiliado oficialmente** ao projeto MeshCentral. *AnyDesk* e demais nomes citados são marcas de seus respectivos proprietários e aparecem aqui apenas para fins de comparação.

---

<div align="center">

### ⭐ Gostou? Deixe uma estrela no repositório!

**Feito com ❤️ e código aberto.**

</div>
