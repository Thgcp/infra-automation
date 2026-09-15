# Infra Automator

![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)
![PowerShell](https://img.shields.io/badge/powershell-5.1+-green.svg)
![Windows](https://img.shields.io/badge/windows-10/11-orange.svg)
![License](https://img.shields.io/badge/license-Proprietary-red.svg)

> Ferramenta de automação voltada para a equipe de Infraestrutura com interface gráfica

---

## 📋 Índice

- [Sobre a Ferramenta](#sobre-a-ferramenta)
- [Funcionalidades](#funcionalidades)
- [Menu Principal](#menu-principal)
- [Requisitos](#requisitos)
- [Instalação](#instalação)
- [Como Usar](#como-usar)
- [Segurança](#segurança)
- [Logs e Histórico](#logs-e-histórico)
- [Demonstração](#demonstração)
- [Solução de Problemas](#solução-de-problemas)
- [Licença](#licença)
- [Status do Projeto](#status-do-projeto)
- [Tags](#tags)

---

## 🖥️ Sobre a Ferramenta

O **Infra Automator** é uma aplicação Windows com interface gráfica desenvolvida em PowerShell para a equipe de Infraestrutura do Hospital Nipo Brasileiro. A ferramenta centraliza diversas automações do dia a dia da equipe, integrando-se com Active Directory, Exchange, Interact e sistemas de arquivos.

### Objetivo

- **Automatizar** tarefas repetitivas de infraestrutura
- **Centralizar** ferramentas em um único lugar
- **Padronizar** processos da equipe
- **Reduzir** erros operacionais
- **Aumentar** a produtividade

---

## ✨ Funcionalidades

### Gestão de Acessos e Pastas
| Opção | Funcionalidade | Descrição |
|-------|----------------|-----------|
| 1 | Verificar membros de pastas | Consulta permissões de pastas de rede |
| 2 | Verificar membros de um grupo | Lista membros de grupos AD |
| 3 | Verificar grupos de um usuário | Lista grupos de um usuário AD |
| 4 | Criar grupos de delegação | Cria grupos para controle de pastas |
| 5 | Copiar grupos de delegação | Copia permissões entre usuários |
| 12 | Extrair estrutura de pastas | Mapeamento de diretórios |
| 14 | Atualizar responsáveis de pastas | Troca de responsáveis |
| 15 | Relatório de acessos de pastas para coordenadores | Envio por e-mail referente à estrutura de pastas |

### Criação de Usuários em Massa
| Opção | Funcionalidade | Descrição |
|-------|----------------|-----------|
| 6.1 | Criar usuários de rede | Criação em lote no Active Directory |
| 6.2 | Criar usuários de Interact | Criação em lote via API |
| 6.3 | Criar usuários de E-mail | Criação em lote no Exchange |

### Desativação e Manutenção
| Opção | Funcionalidade | Descrição |
|-------|----------------|-----------|
| 7 | Converter XLSM para CSV | Converte planilhas Excel |
| 8 | Desabilitar máquinas ociosas | Máquinas inativas há 90+ dias |
| 9 | Desabilitar usuários ociosos | Usuários inativos há 90+ dias |
| 11 | Desabilitar usuários desligados | Rede / Interact / E-mail |
| 13 | Excluir computadores em OU Disable | Limpeza de computadores antigos |

### Impressoras
| Opção | Funcionalidade | Descrição |
|-------|----------------|-----------|
| 10.1 | Adicionar fila de impressão | Cadastro de novas impressoras |
| 10.2 | Alterar mapeamento - JSON | Gerenciamento de mapeamento |
| 10.3 | Substituição de impressora | Troca de equipamentos |

### Exchange (Microsoft Graph)
| Opção | Funcionalidade | Descrição |
|-------|----------------|-----------|
| 16.1 | Instalar módulo Exchange | Instala Microsoft.Graph |
| 16.2 | Conectar módulo Exchange | Autenticação no Exchange |
| 16.3 | Consultar usuários de E-mail | Pesquisa de usuários |
| 16.4 | Consultar grupos de E-mail | Pesquisa de grupos |
| 16.5 | Consultar membros de grupos | Lista membros de grupos |
| 16.6 | Cópia de grupos | Copia grupos entre usuários |
| 16.7 | Relatório por licença para Governança | E-mails criados no mês anterior de todas as unidades |
| 16.8 | Relatório por data de criação para o treinamento | E-mails criados no mês anterior |
| 16.9 | Relatório geral para a unidade HLOB | E-mail, grupos e licenças |

---

## 📁 Menu Principal

```
+ - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +
                  DESENVOLVIDO PARA A EQUIPE DE INFRAESTRUTURA
+ - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +

1. Verificar membros de pastas
2. Verificar membros de um grupo
3. Verificar grupos de um usuário
4. Criar grupos de delegação
5. Copiar grupos de delegação
6. Criar usuários em massa
7. Converter XLSM para CSV
8. Desabilitar máquinas ociosas
9. Desabilitar usuários ociosos
10. Menu de impressoras
11. Desabilitar usuários desligados
12. Extrair a estrutura de pastas
13. Excluir computadores em OU Disable
14. Atualizar responsáveis de pastas
15. Extrair relatório de acessos às pastas para coordenadores
16. Acessar menu Exchange
```

---

## 🛠️ Requisitos

### Sistema Operacional
- Windows 10 ou superior
- Windows Server 2016 ou superior

### Permissões
- Usuário do domínio `nipo.local`
- Permissões administrativas em determinadas funções
- Acesso à rede interna

### Dependências
- PowerShell 5.1 ou superior
- .NET Framework 4.5+
- Active Directory PowerShell Module
- Microsoft Graph Module (para Exchange)
- MySQL Client (para Interact)

---

## 🚀 Instalação

### 1. Baixar os Arquivos

```powershell
# Estrutura de diretórios necessária
C:\HN_Automator\
├── HN_Automator.ps1          # Script principal
├── funcoes.psm1              # Módulo com funções
├── config/                   # Arquivos de configuração
│   └── ...
└── imgs/                     # Imagens do menu
    ├── nipo-logo.png
    ├── balao-ajuda.png
    ├── atencao.png
    └── ...
```

### 2. Configurar Execução de Scripts

```powershell
# Liberar execução de scripts
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### 3. Executar a Aplicação

```powershell
# Navegue até a pasta do script
cd C:\HN_Automator

# Execute
.\HN_Automator.ps1
```

### 4. Criar Atalho (Opcional)

```powershell
# Criar atalho na área de trabalho
$WshShell = New-Object -comObject WScript.Shell
$Shortcut = $WshShell.CreateShortcut("$Home\Desktop\HN Automator.lnk")
$Shortcut.TargetPath = "powershell.exe"
$Shortcut.Arguments = "-ExecutionPolicy Bypass -File `"C:\HN_Automator\HN_Automator.ps1`""
$Shortcut.IconLocation = "C:\HN_Automator\imgs\nipo-logo.ico"
$Shortcut.Save()
```

---

## 📖 Como Usar

### Navegação

1. **Menu Principal**: Lista todas as opções disponíveis
2. **Submenus**: Opções com numeração (ex: 6.1, 10.1)
3. **Botão "Voltar"**: Retorna ao menu principal
4. **Botão "OK"**: Executa a ação selecionada

### Ícones de Ajuda

| Ícone | Função | Descrição |
|-------|--------|-----------|
| 💬 | Ajuda | Exibe dicas sobre a opção |
| ⚠️ | Atenção | Alerta sobre ações críticas |
| 🗺️ | Mapa | Visualiza todas as opções |
| 📋 | Histórico | Mostra ações realizadas |
| ✉️ | Feedback | Envia sugestões e bugs |
| 📨 | Resposta | Responde solicitações |

### Exemplo de Uso

```powershell
# 1. Abrir o menu
.\HN_Automator.ps1

# 2. Selecionar opção (ex: 6.1 - Criar usuários de rede)
Digite o número da opção: 6.1

# 3. Selecionar subopção (ex: 1 - Criar usuários de rede)
Digite o número da opção: 1

# 4. Preencher os campos solicitados
Data de admissão: 15/07/2026

# 5. Validar dados e confirmar
Clique em "OK" para executar
```

---

## 🔒 Segurança

### Proteções Implementadas

| Medida | Descrição |
|--------|-----------|
| **Credenciais Seguras** | Uso de SecureString para senhas |
| **Sessão Temporária** | Desconexão automática após inatividade |
| **Logs de Ação** | Registro de todas as operações |
| **Validação de Inputs** | Sanitização de entradas do usuário |
| **Controle de Acesso** | Funções restritas por servidor |

### Timeout de Sessão

- A sessão expira automaticamente após **20 minutos** de inatividade
- O timer é reiniciado com qualquer interação do mouse

---

## 📝 Logs e Histórico

### Histórico de Ações

O sistema mantém um histórico das ações realizadas durante a sessão:

```powershell
# Exemplo de histórico
1. Verificar membros de pastas
--> 1 - Verificar acessos de uma única pasta
[OK]
[Return]
2. Verificar membros de um grupo
--> 2 - Verificar membros de um grupo
[OK]
```

### Feedback e Solicitações

- **Feedback**: Envie sugestões, melhorias e reporte bugs
- **Solicitações**: Acompanhe o status das suas solicitações
- **Respostas**: Responda a solicitações e feedbacks

---

## 🎬 Demonstração

**[Demonstração Infra Automation]**(https://github.com/Thgcp/infra-automation/releases/download/demonstration/Demonstration.gif)

---

## ❗ Solução de Problemas

### Erro: "File cannot be loaded"

```powershell
# Solução: Liberar execução
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Erro: "Cannot connect to Exchange"

```powershell
# Solução: Instalar módulo
Install-Module Microsoft.Graph -Scope CurrentUser
```

### Erro: "Cannot connect to Interact"

```powershell
# Solução: Verificar arquivos DLL
# Certifique-se de que msvcp120.dll e msvcr120.dll estão em C:\Windows\System32
```

### Erro: "Access Denied"

```powershell
# Solução: Executar como administrador
# Clique com botão direito no PowerShell -> Executar como administrador
```

---

## 📄 Licença

Esta ferramenta é **propriedade intelectual do Hospital Nipo Brasileiro**. Seu uso, cópia, modificação ou distribuição é restrito conforme acordo de confidencialidade.

---

## 📊 Status do Projeto

| Métrica | Status |
|---------|--------|
| **Versão** | 2.0.0 |
| **Ambiente** | Produção |
| **Última Atualização** | Julho 2026 |
| **Suporte** | Ativo |

---

## 🏷️ Tags

`powershell` `automation` `active-directory` `exchange` `windows` `infrastructure` `hospital` `sysadmin`

---

*Desenvolvido para a equipe de Infraestrutura - Hospital Nipo Brasileiro* 🏥