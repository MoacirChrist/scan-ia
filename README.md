<p align="center">
  <img src="https://scan-ia.inovia.space/images/logo.png" alt="Scan-IA Logo" width="200"/>
</p>

<h1 align="center">Scan-IA</h1>

<p align="center">
  <strong>Sistema Inteligente de Automação para Farmácias e Laboratórios</strong>
</p>

<p align="center">
  <a href="#-sobre">Sobre</a> •
  <a href="#-funcionalidades">Funcionalidades</a> •
  <a href="#-arquitetura">Arquitetura</a> •
  <a href="#-instalação">Instalação</a> •
  <a href="#-uso">Uso</a> •
  <a href="#-licenciamento">Licenciamento</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/.NET-9.0-512BD4?style=flat-square&logo=dotnet" alt=".NET 9"/>
  <img src="https://img.shields.io/badge/WinForms-Windows-0078D6?style=flat-square&logo=windows" alt="WinForms"/>
  <img src="https://img.shields.io/badge/Google%20Cloud-Run-4285F4?style=flat-square&logo=googlecloud" alt="Cloud Run"/>
  <img src="https://img.shields.io/badge/PostgreSQL-15+-336791?style=flat-square&logo=postgresql" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/Gemini-AI-FF6F00?style=flat-square&logo=google" alt="Gemini AI"/>
</p>

---

## 📋 Sobre

O **Scan-IA** é um sistema integrado de automação desenvolvido especificamente para **farmácias de manipulação** e **laboratórios de análises clínicas**. Utilizando tecnologia de IA generativa (Google Gemini), o sistema automatiza a leitura e extração de informações de documentos como receitas médicas, laudos de exames e solicitações de orçamento.

### O Problema

Farmácias e laboratórios recebem diariamente dezenas de documentos via WhatsApp, e-mail e outros canais. A transcrição manual dessas informações é:

- ⏱️ **Demorada** - consome horas de trabalho especializado
- ❌ **Propensa a erros** - digitação incorreta de dosagens pode ser perigosa
- 💰 **Custosa** - requer mão de obra qualificada para interpretação

### A Solução

O Scan-IA automatiza esse processo:

1. **Detecta** automaticamente novos arquivos na pasta Downloads
2. **Processa** o documento usando IA generativa
3. **Extrai** informações estruturadas em JSON
4. **Apresenta** os dados de forma organizada para validação

---

## ✨ Funcionalidades

### 🖥️ Aplicativo Desktop

| Funcionalidade | Descrição |
|----------------|-----------|
| **Monitoramento Automático** | Observa pasta de downloads em tempo real |
| **Detecção Inteligente** | Identifica arquivos PDF e imagens automaticamente |
| **Múltiplos Modelos de IA** | 3 opções de processamento (básico, intermediário, avançado) |
| **Visualização Estruturada** | Exibe dados extraídos em grid interativo |
| **Reprocessamento** | Permite tentar outro modelo se necessário |
| **Gestão de Licença** | Controle de ativação e consumo |

### 🌐 API Web

| Funcionalidade | Descrição |
|----------------|-----------|
| **Processamento de Arquivos** | Recebe e processa documentos via API REST |
| **Integração Gemini** | Comunicação nativa com Google AI |
| **Prompts Especializados** | Modelos treinados por tipo de documento |
| **Controle de Licenças** | Geração e validação de chaves |
| **Gestão de Limites** | Controle de consumo por plano |
| **Webhooks de Pagamento** | Integração automática com Asaas |

### 📄 Tipos de Documentos Suportados

- **Orçamentos** - Extrai itens, quantidades e valores
- **Receitas Médicas** - Identifica medicamentos, dosagens e posologia
- **Laudos de Exames** - Estrutura resultados laboratoriais
- **Documentos Personalizados** - Prompts customizáveis

---

## 🏗️ Arquitetura

```
┌─────────────────────────────────────────────────────────────┐
│                     SCAN-IA DESKTOP                         │
│              (C# / .NET 9 / WinForms)                       │
│                    Windows 11                               │
└──────────────────┬──────────────────────────────────────────┘
                   │ HTTPS (REST API)
                   ↓
┌─────────────────────────────────────────────────────────────┐
│                    SCAN-IA WEB                              │
│              (.NET 8 / Cloud Run)                           │
│           scan-ia.inovia.space                              │
└──────────────┬─────────────────────┬───────────────────────┘
               │                     │
               ↓                     ↓
        ┌──────────────┐    ┌──────────────┐
        │  Gemini API  │    │  PostgreSQL  │
        │   (Google)   │    │  (Cloud SQL) │
        └──────────────┘    └──────────────┘
```

### Modelos de IA Disponíveis

| Nível | Modelo | Características |
|-------|--------|-----------------|
| 🟢 Básico | `gemini-2.0-flash-lite-001` | Rápido, ideal para documentos simples |
| 🟡 Intermediário | `gemini-2.5-flash-lite` | Equilíbrio entre velocidade e precisão |
| 🔴 Avançado | `gemini-2.5-pro` | Máxima precisão para documentos complexos |

---

## 💻 Stack Tecnológica

### Desktop (DKP)

| Tecnologia | Versão | Uso |
|------------|--------|-----|
| C# | 13+ | Linguagem principal |
| .NET | 9.0 | Framework |
| WinForms | - | Interface gráfica |
| Visual Studio | 2026 | IDE |

### Web (WEB)

| Tecnologia | Versão | Uso |
|------------|--------|-----|
| C# | 12 | Linguagem principal |
| .NET | 8.0 | Framework (requisito Cloud Run) |
| ASP.NET Core | 8.0 | Web API |
| Entity Framework | 8.0 | ORM |
| PostgreSQL | 15+ | Banco de dados |
| Google Cloud Run | - | Hospedagem |
| Google Cloud Storage | - | Armazenamento de arquivos |

---

## 📥 Instalação

### Desktop

#### Opção 1: Microsoft Store (Recomendado)
```
Pesquise por "Scan-IA" na Microsoft Store
```

#### Opção 2: Download Direto
1. Acesse [scan-ia.inovia.space](https://scan-ia.inovia.space)
2. Baixe o instalador para Windows
3. Execute o instalador e siga as instruções

### Requisitos Mínimos

| Requisito | Especificação |
|-----------|---------------|
| Sistema Operacional | Windows 10/11 (64-bit) |
| .NET Runtime | 9.0 ou superior |
| Memória RAM | 4 GB mínimo |
| Espaço em Disco | 100 MB |
| Conexão | Internet necessária |

---

## 🚀 Uso

### Primeiro Acesso

1. **Inicie o aplicativo** Scan-IA
2. **Obtenha uma licença** (FREE ou paga)
3. **Configure a pasta** de monitoramento (padrão: Downloads)
4. **Selecione o prompt** adequado para seu tipo de documento

### Fluxo de Trabalho

```
1. Receba documento via WhatsApp/Email
        ↓
2. Salve na pasta monitorada
        ↓
3. Scan-IA detecta automaticamente
        ↓
4. Processamento com IA Gemini
        ↓
5. Visualize dados estruturados
        ↓
6. Copie ou exporte conforme necessário
```

### Dicas de Uso

- 📁 Use pastas separadas para diferentes tipos de documentos
- 🔄 Se o resultado não for satisfatório, tente outro modelo de IA
- 📊 Documentos em boa qualidade geram melhores resultados
- ⚡ O modelo Básico é mais rápido, ideal para alto volume

---

## 🔐 Licenciamento

### Planos Disponíveis

| Plano | Usos/Mês | Dispositivos | Modelos | Preço |
|-------|----------|--------------|---------|-------|
| **FREE** | 20 | 1 | Básico | Grátis |
| **Básico** | 500 | 1 | Todos | R$ 49/mês |
| **Profissional** | 2.000 | 3 | Todos | R$ 149/mês |
| **Empresarial** | Ilimitado | 10 | Todos | R$ 399/mês |

### Ativação de Licença

1. Acesse **Configurações** no aplicativo
2. Clique em **Ativar Licença**
3. Insira sua chave de licença
4. A ativação é validada automaticamente

### Licença FREE

- Ideal para avaliação e uso ocasional
- 20 processamentos por mês
- Renovação automática mensal
- Sem necessidade de cadastro de cartão

---

## 🌐 API

### Endpoint Principal

```
POST https://scania-api-1004446787467.us-central1.run.app/api/files/process
```

### Exemplo de Requisição

```json
{
  "fileUrl": "gs://bucket/arquivo.pdf",
  "promptId": 1,
  "modeloId": 0,
  "licenseKey": "XXXX-XXXX-XXXX-XXXX"
}
```

### Exemplo de Resposta

```json
{
  "success": true,
  "data": {
    "tipo": "receita",
    "paciente": "João Silva",
    "medicamentos": [
      {
        "nome": "Paracetamol",
        "dosagem": "500mg",
        "posologia": "1 comprimido de 8/8h"
      }
    ]
  },
  "tokensUsados": 1250
}
```

---

## 🗄️ Banco de Dados

### Principais Tabelas

```sql
-- Licenças
CREATE TABLE "Licencas" (
    "Id" SERIAL PRIMARY KEY,
    "ChaveLicenca" VARCHAR(255) UNIQUE NOT NULL,
    "PlanoId" INTEGER REFERENCES "Planos"("Id"),
    "UsuarioId" INTEGER,
    "DataExpiracao" TIMESTAMP WITH TIME ZONE,
    "Ativo" BOOLEAN DEFAULT true
);

-- Planos
CREATE TABLE "Planos" (
    "Id" SERIAL PRIMARY KEY,
    "Nome" VARCHAR(50) NOT NULL,
    "DispositivosPermitidos" INTEGER,
    "ApiCallsLimite" INTEGER,
    "PrecoMensal" DECIMAL(10,2),
    "PrecoAnual" DECIMAL(10,2)
);

-- Prompts
CREATE TABLE "Prompts" (
    "Id" SERIAL PRIMARY KEY,
    "Nome" VARCHAR(100) NOT NULL,
    "Conteudo" TEXT NOT NULL,
    "Categoria" VARCHAR(50),
    "Ativo" BOOLEAN DEFAULT true
);
```

---

## 🔒 Segurança

- ✅ Comunicação HTTPS em todas as requisições
- ✅ Validação de licença antes de cada processamento
- ✅ Autenticação via Cloud IAM / Service Accounts
- ✅ Conexão segura com Cloud SQL via proxy
- ✅ Secrets gerenciados via Secret Manager (GCP)
- ✅ Arquivos processados são deletados após uso

---

## 📞 Suporte

| Canal | Contato |
|-------|---------|
| Website | [scan-ia.inovia.space](https://scan-ia.inovia.space) |
| E-mail | suporte@inovia.space |
| WhatsApp | Em breve |

---

## 📄 Licença

Copyright © 2025 Inovia. Todos os direitos reservados.

Este software é proprietário e protegido por leis de direitos autorais.
A distribuição, modificação ou uso não autorizado é estritamente proibido.

---

<p align="center">
  Desenvolvido com ❤️ por <a href="https://inovia.space">Inovia</a>
</p>

<p align="center">
  <sub>Versão 1.0.0 • Dezembro 2025</sub>
</p>
