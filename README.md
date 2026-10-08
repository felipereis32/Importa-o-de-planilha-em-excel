# Excel Cadastro Automático

Projeto desenvolvido em Python para automatizar a leitura de dados de uma planilha Excel e o registro dessas informações em um banco de dados SQLite.

A proposta é facilitar o processo de transferência de dados de uma planilha para um banco de dados, mantendo o arquivo Excel original intacto.

## 🚀 Funcionalidades

* Leitura automática de arquivos `.xlsx`
* Identificação dos registros presentes na planilha
* Leitura das informações de cliente, produto, quantidade e categoria
* Criação automática do banco de dados SQLite
* Importação dos registros do Excel para o banco
* Atualização de registros existentes sem criar duplicidades
* Preservação do arquivo Excel original
* Exibição da quantidade de registros processados

## 🛠️ Tecnologias utilizadas

* Python
* OpenPyXL
* SQLite
* pathlib

## 📂 Estrutura do projeto

```text
Excel Cadastro Automático/
│
├── main.py
├── vendas_de_produtos.xlsx
├── vendas.db
└── README.md
```

### Arquivos

**`main.py`**
Responsável por ler a planilha, processar os registros e armazená-los no banco de dados.

**`vendas_de_produtos.xlsx`**
Arquivo utilizado como fonte dos dados.

**`vendas.db`**
Banco de dados SQLite criado pelo programa para armazenar os registros importados.

## 🔄 Funcionamento

O programa realiza o seguinte processo:

```text
Planilha Excel
      ↓
Leitura com Python
      ↓
Processamento dos registros
      ↓
Banco de dados SQLite
```

O arquivo Excel é utilizado apenas como fonte de dados e não é modificado durante a execução.

## 🗄️ Banco de dados

Os registros são armazenados em uma tabela chamada `vendas`, contendo as seguintes informações:

| Campo         | Descrição                               |
| ------------- | --------------------------------------- |
| `id`          | Identificador único do registro         |
| `linha_excel` | Número da linha correspondente no Excel |
| `cliente`     | Nome do cliente                         |
| `produto`     | Produto da venda                        |
| `quantidade`  | Quantidade registrada                   |
| `categoria`   | Categoria informada na planilha         |

O campo `linha_excel` é utilizado para evitar a criação de registros duplicados quando o programa é executado novamente.

## ▶️ Como executar

### 1. Instale o Python

É necessário ter o Python instalado no computador.

### 2. Instale a dependência

No terminal:

```bash
python -m pip install openpyxl
```

### 3. Coloque os arquivos na mesma pasta

Certifique-se de que `main.py` e `vendas_de_produtos.xlsx` estejam na mesma pasta.

### 4. Execute o programa

```bash
python main.py
```

Após a execução, o banco `vendas.db` será criado ou atualizado automaticamente.

## 📌 Exemplo de execução

```text
==================================================
        IMPORTAÇÃO DE VENDAS
==================================================
Registros encontrados no Excel: 100

Importação concluída!
100 registros processados.
Planilha importada para o banco de dados com sucesso!
```

## 🎯 Objetivo

O projeto foi desenvolvido como uma prática de automação com Python, utilizando uma situação comum em processos administrativos: utilizar dados existentes em uma planilha para alimentar um banco de dados de forma automática.

A ideia é reduzir a necessidade de transferência manual de informações e criar uma base que possa posteriormente ser utilizada por outros sistemas ou processos automatizados.

## 🔮 Possíveis melhorias futuras

O projeto pode ser expandido futuramente para:

* integração com sistemas web;
* automação de cadastros utilizando Selenium;
* geração de relatórios;
* registro de logs;
* tratamento de erros;
* validação dos dados;
* exportação dos dados processados.

## 👨‍💻 Autor

Felipe Reis Neris

Projeto desenvolvido para estudos e prática de automação com Python.
