# Repondendo-Perguntas-da-Vaga-Magazord

# Plano de Testes - Analista de Qualidade

## 1º Cenário: Integração com Marketplaces.

### 1. Documentação e Materiais de Apoio
- **Identificação da documentação:**
  - Documentação oficial das APIs dos marketplaces (Amazon, Mercado Livre)
  - Especificação técnica da integração
  - Requisitos funcionais do projeto
  - Mapas de processos da integração
  - Logs e histórico de transações
- **Análise da documentação:**
  - Identificação de endpoints da API relevantes
  - Verificação de fluxos de sincronização de estoque, faturamento, pedidos e preço
  - Validação de respostas e códigos de erro
- **Mapeamento dos requisitos:**
  - Associação de cada funcionalidade da integração com casos de teste
- **Ferramentas:**
  - Postman (testes de API)
  - JIRA/Trello (gerenciamento de requisitos)
  - Swagger (documentação de API)

### 2. Abrangência dos Testes
- **Funcionalidades:**
  - Integração de estoque, preço, faturamento, pedidos e anúncios
- **Casos de uso:**
  - Testes funcionais (envio de dados, sincronização, resposta do marketplace)
  - Testes de erro (respostas inválidas, falhas de autenticação)
  - Testes de carga (vários pedidos simultâneos)
- **Priorizção:**
  - Funcionalidades críticas primeiro (sincronização de estoque e pedidos)
  - Testes de impacto no negócio

### 3. Execução dos Testes
- **Ambiente:**
  - Ambiente de homologação
- **Dados de teste:**
  - Produtos fictícios cadastrados
  - Simulação de pedidos
- **Ferramentas de automação:**
  - Selenium para testes de interface
  - JMeter para testes de carga
- **Registro de resultados:**
  - Ferramenta de gerenciamento de testes (TestRail, Zephyr)

## 2º Cenário: Integração com Bling

### 1. Documentação e Materiais de Apoio
- **Identificação da documentação:**
  - Documentação oficial da API Bling
  - Especificações da integração
  - Requisitos do projeto
- **Mapeamento dos requisitos:**
  - Associação de endpoints aos fluxos de negócio
- **Ferramentas:**
  - Postman, Swagger, JIRA

### 2. Abrangência dos Testes
- **Funcionalidades:**
  - Sincronização de produtos
  - Atualização de estoque
  - Processamento de pedidos
- **Priorizção:**
  - Impacto no negócio
  - Críticos primeiro (estoque e pedidos)

### 3. Execução dos Testes
- **Dados de teste:**
  - Cadastro de produtos e estoque fictício
- **Ferramentas de automação:**
  - Selenium, JMeter
- **Registro de resultados:**
  - TestRail, Zephyr

## 3º Cenário: Erro no Status dos Anúncios no Mercado Livre

### 1. Passos para Análise do Problema
1. Revisar logs de sincronização de estoque
2. Verificar comportamento da API do ML ao receber estoque zerado
3. Consultar documentação da API do ML sobre status de anúncio
4. Testar envio manual de estoque zerado para analisar resposta
5. Validar se há delay na atualização do status do anúncio

### 2. Possíveis Hipóteses do Erro
- API do Magazord não está enviando estoque zerado corretamente
- Configuração incorreta na API do ML
- Problema no processamento do status "Pausado sem estoque"

## 4º Cenário: Testes de Validação de Cadastro de Usuários

### Casos de Teste para os Campos Modificados
- **Nome completo:**
  - Inserir caracteres especiais e verificar erro
  - Nome com menos de 2 caracteres
  - Nome com espaços extras
- **E-mail:**
  - Formatos inválidos (@ faltando, domínio errado)
  - E-mails duplicados no sistema
- **Telefone:**
  - Inserção de caracteres não numéricos
  - Formato inválido de telefone
- **Data de nascimento:**
  - Datas impossíveis (ex: 30/02/2000)
  - Idade menor que 18 anos
- **Endereço:**
  - CEP inválido
  - Endereço sem rua ou cidade preenchida

### Ferramentas Utilizadas
- Selenium para testes automatizados
- Banco de dados para validação de registros
- TestRail para registro dos testes

