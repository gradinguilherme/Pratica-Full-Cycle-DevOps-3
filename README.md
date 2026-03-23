# Prática Full Cycle: DevOps - Atividade Nº3

## Visão Geral

Este repositório contém os resultados da atividade prática focada em **Garantia de Qualidade (QA) e DevOps**. O objetivo principal foi validar componentes isolados de uma aplicação Flask, garantindo que o software se comporte conforme o esperado sob diferentes condições, incluindo fluxos de sucesso e tratamento de exceções.

---

## Objetivos da Prática

- Implementar testes unitários para validar funções isoladas de uma API Flask
- Utilizar ferramentas de análise de cobertura para identificar lacunas nos testes
- Incrementar a cobertura de código de 64% até atingir a meta de 100%
- Aplicar a cultura de automação para aumentar a eficiência no ciclo de desenvolvimento

---

## Tecnologias e Ferramentas

| Ferramenta | Descrição |
|-----------|-----------|
| **Python** | 3.11+ |
| **Flask** | Framework Web para criar a API |
| **unittest (PyUnit)** | Framework de Testes |
| **coverage.py** | Análise de Cobertura de Código |
| **Visual Studio Code** | Editor de código |

---

## Evolução da Cobertura de Testes

O projeto foi desenvolvido em três etapas progressivas para garantir a qualidade total do arquivo `app.py`:

### **Etapa 1: Diagnóstico Inicial**
- **Status:** 64% de cobertura
- **Lacunas:** As rotas existiam, mas os fluxos internos de lógica (como validação de parâmetros) não eram exercitados pelos testes iniciais

### **Etapa 2: Expansão (Caso de Sucesso)**
- **Ação:** Implementação do método `test_print_hello_success` no arquivo `appTest.py`
- **Resultado:** A cobertura subiu para 91%

### **Etapa 3: Cobertura Total (Caso de Erro)**
- **Ação:** Implementação do método `test_print_hello_error` para validar o comportamento do sistema diante de entradas inválidas (ex: nome não informado)
- **Resultado Final:** Alcance de **100% de cobertura** em todos os arquivos do projeto

---

## Cobertura de Testes

A cobertura de testes, também conhecida como cobertura de código, consiste na razão entre o número de linhas executadas por ao menos um caso de teste e o número total de linhas existentes:

```
cobertura de teste = linhas de código executadas / número total de linhas
```

A cobertura do teste é frequentemente utilizada para avaliar a qualidade de um conjunto de testes. Se a cobertura for baixa (ex: 5%), é um indicador de que você não está testando o suficiente. Porém, 100% de cobertura não implica necessariamente em alta qualidade — é preciso avaliar os cenários individualmente.

---

## Como Executar o Projeto e os Testes

### **1. Instale as dependências:**

```bash
pip install flask coverage
```

### **2. Execute os testes e gere os dados de cobertura:**

```bash
python -m coverage run -m unittest -v tests/appTest.py
```

### **3. Gere o relatório no terminal:**

```bash
python -m coverage report
```

**Saída esperada:**
```
Name               Stmts   Miss  Cover
--------------------------------------
app/app.py            11      0   100%
tests/appTest.py      15      0   100%
--------------------------------------
TOTAL                 26      0   100%
```

### **4. Gere o relatório visual em HTML:**

```bash
python -m coverage html
```

O relatório detalhado poderá ser visualizado abrindo o arquivo `htmlcov/index.html`.

### **5. Execute a aplicação:**

```bash
python app/app.py
```

A aplicação responderá em duas rotas na web:

- **Health Check:** http://localhost:5000/health-check
- **Hello:** http://localhost:5000/hello?name=Guilherme

---

## Estrutura do Projeto

```
.
├── app/
│   └── app.py              # Aplicação Flask com as rotas
├── tests/
│   └── appTest.py          # Testes unitários (PyUnit)
├── htmlcov/                # Relatório de cobertura em HTML
├── README.md               # Este arquivo
└── assets/                 # Recursos visuais
```

---

## Casos de Teste Implementados

### **test_print_health_check()**
Valida o endpoint `/health-check`:
- Verifica se retorna status code `200`
- Verifica se o corpo da resposta é `<h1>Hello, I'm Alive!</h1>`

### **test_print_hello_success()**
Valida o endpoint `/hello` com parâmetro válido:
- Verifica se retorna status code `200`
- Verifica se a resposta é `Hello, Guilherme!` (quando enviado `?name=Guilherme`)

### **test_print_hello_error()**
Valida o endpoint `/hello` sem parâmetro:
- Verifica se retorna status code `400` (erro)
- Verifica se a resposta é `Nome não informado`

---

## Referências

- [Flask Documentation](https://flask.palletsprojects.com/)
- [Python unittest Documentation](https://docs.python.org/3/library/unittest.html)
- [coverage.py Documentation](https://coverage.readthedocs.io/)

---

## Instituição

**UNIVERSIDADE SENAI CIMATEC** 
**Componente curricular:** Práticas Integradas: Full Cycle  

