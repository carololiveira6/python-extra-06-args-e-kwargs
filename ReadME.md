## **Table of Contents**
- [Extra - Args e Kwargs](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_03_args-e-kwargs.html&ref=master#mcetoc_1esj4slvm0)
  - [Objetivo](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_03_args-e-kwargs.html&ref=master#mcetoc_1f33pqfa47)
  - [Preparativos](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_03_args-e-kwargs.html&ref=master#mcetoc_1f33pqfa48)
- [Exercícios](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_03_args-e-kwargs.html&ref=master#mcetoc_1egvsckqv3)
- [Entregáveis](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_03_args-e-kwargs.html&ref=master#mcetoc_1egvoav555j)
  - [Repositório](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_03_args-e-kwargs.html&ref=master#mcetoc_1egvrpv6k1l4)
- [Critérios de aceitação](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_03_args-e-kwargs.html&ref=master#mcetoc_1esj6ecle3)
# **Extra - Args e Kwargs**
Nessa entrega você exercitará seus conhecimentos sobre **packing e unpacking** desenvolvendo operações lógicas básicas no estilo *kata*.
## **Objetivo**
Exercitar a distribuição de argumentos no formato args e kwargs.
## **Preparativos**
Você deverá criar um arquivo chamado main.py. Todas as funções devem estar com a assinatura no formato especificado.
# **Exercícios**
- **sum\_numbers(\*args)**
  - **Parâmetros:**
    - args: quantidade indefinida de parâmetros numéricos inteiros.
  - **Procedimento:** Somar cada um dos valores recebidos em args
  - **Retorno:** A soma de cada um dos valores recebidos em args

numbers = [1, 2, 3, 4, 5, 6]

result = sum\_numbers(\*numbers)

print(resut)

\> 21

- **get\_multiplied\_amount(multiplier, \*args)**
  - **Parâmetros:**
    - multiplier: número inteiro utilizado como multiplicador.
    - args: quantidade indefinida de parâmetros numéricos inteiros.
  - **Procedimento:**
    - Somar cada um dos valores recebidos em args
    - Multiplicar o resultado das somas pelo multiplier.
  - **Retorno:** O resultado das operações como valor numérico.

numbers = [1, 2, 3]

multiplier = 2

result = get\_multiplied\_amount(multiplier, \*numbers)

print(result)

\> 12

- **word\_concatenator(\*args)**
  - **Parâmetros:**
    - args: quantidade indefinida de palavras.
  - **Procedimento:**
    - Concatenar cada uma das palavras recebidas em args aplicando um espaço como separador. Não pode haver espaço após a última palavra.
  - **Retorno:** Uma string contendo todas as palavras concatenadas.

words = ["Tá", "pegando", "fogo", "bicho!!!"]

concatenated\_words = word\_concatenator(\*words)

print(concatenated\_words)

\> "Tá pegando fogo bicho!!!"

- **inverted\_word\_factory(\*args)**
  - **Parâmetros:**
    - args: quantidade indefinida de palavras.
  - **Procedimento:**
    - Concatenar numa string cada uma das palavras em args, porém cada palavra deve estar invertida, assim como a ordem das palavras.
  - **Retorno:** Uma string contendo todas as palavras concatenadas, porém, cada uma delas devem estar invertidas, inclusive a ordem das palavras.

words = ["eae", "amigão", "belezinha?"]

inverted\_words = inverted\_word\_factory(\*words)

print(inverted\_words)

\> "?ahnizeleb oãgima eae"

- **dictionary\_separator(\*\*kwargs)**
  - **Parâmetros:**
    - kwargs: dicionário contendo uma quantidade indefinida de itens.
  - **Procedimento:** 
    - Agrupar em uma lista todas as chaves do dicionário kwargs
    - Agrupar em uma lista todos os valores do dicionário kwargs
  - **Retorno:** Retornar uma **tupla** de duas posições, na primeira posição a lista de chaves do dicionário kwargs, na segunda posição uma lista de valores do dicionário kwargs

user = {

`    `"name": "Naruto",

`    `"age": 16,

`    `"favorite word": "Ichiraku Ramen"

}

items = dictionary\_separator(\*\*user)

print(items)

\> (

`    `["name", "age", "favorite word"],

`    `["Naruto", 16, "Ichiraku Ramen"]

)

- **dictionary\_creator(\*args, \*\*kwargs)**
  - **Parâmetros:**
    - args: quantidade indefinida de valores (podem ser inteiros ou string)
    - kwargs: dicionário contendo uma quantidade indefinida de itens
  - **Procedimento:**
    - Substituir cada uma das chaves do dicionário kwargs pelos valores recebidos da tupla args
      - Uma chave que se encontra na posição 2 do dicionário, deve ser substituída pelo valor de posição 2 dentro da tupla args, essa ordem deve ser seguida de forma respectiva
      - Caso a quantidade de valores dentro da tupla args, seja maior que a quantidade de itens no dicionário, ignorar os valores excedentes em args
  - **Retorno:**
    - Retornar **None**, caso a quantidade de valores dentro da tupla **args** seja **menor** **que** a quantidade **de itens em kwargs**
    - Retornar **dicionário**, caso a quantidade de valores dentro da tupla **args** seja **igual ou maior** a quantidade **de itens em kwargs**

change\_keys = ["username", "password", "address"]

user = {

`    `"name": "Williams",

`    `"key": "1234"

}

modified\_user = dictionary\_creator(\*change\_keys, \*\*user)

print(modified\_user)

\>  {

`    `"username": "Williams",

`    `"password": "1234"

}

- **purchase\_logger(\*\*kwargs)**
  - **Parâmetros:**
    - kwargs: dicionário representando um produto.
  - **Procedimento:**
    - Formar uma string contendo as informações do produto.
  - **Retorno**:
    - String formada com o nome do produto, seu preço e quantidade.

purchase = {"name": "washing powder", "price": 6.7, "quantity": 4}

purchase\_log = purchase\_logger(\*\*purchase)

print(purchase\_log)

\> "Product washing powder costs 6.7 and was bought 4"

- **world\_cup\_logger(country, \*args)**
  - **Parâmetros:**
    - country: uma string representando um país.
    - args: anos das copas do mundo em que o país foi campeão (lista de números inteiros)
  - **Procedimento:**
    - Formar uma string com o nome do país e os anos em que foi campeão, em ordem crescente:
  - **Retorno:**
    - String formada com o nome do país e os anos em que foi campeão, exatamente como mostrado acima

country = 'Alemanha'

year\_list = [2014, 1990, 1974, 1954]

log = world\_cup\_logger(country, \*year\_list)

print(log)

\> "Alemanha - 1954, 1974, 1990 e 2014"
### -----
# **Entregáveis**
## **Repositório**
- Link do **repositório** do **GitLab**
- **Código-fonte:**
  - Arquivo **main.py**.
- **Privacidade**
  - Incluir **ka-br-out-2020-correcoes** como **reporter**.
# **Critérios de aceitação**

|**pts**|**Dado**|**Quando**|**É esperado**|
| :-: | :-: | :-: | :-: |
|0.5|sum\_numbers |Executada com seus devidos parâmetros|O resultado da soma de todos os números passados em args seja retornado|
|0.5|get\_multiplied\_amount|Executada com seus devidos parâmetros|O resultado das operações seja retornado|
|0.5|word\_concatenator|Executada com seus devidos parâmetros|Uma string resultado da concatenação de cada um dos parâmetros recebidos|
|0.5|inverted\_word\_factory|Executada com seus devidos parâmetros|Cada uma das strings recebidas como parâmetros invertidas e concatenadas em uma string única|
|0.5|dictionary\_separator|Executada com seus devidos parâmetros|Uma tupla com duas posições, em cada uma das duas posições seus devidos valores conforme especificado|
|1|dictionary\_creator|Executada com seus devidos parâmetros|Um dicionário seja retornado|
|0.5|purchase\_logger|Executada com seus devidos parâmetros|Uma string formatada conforme especificado seja retornada|
|1|world\_cup\_logger|Executada com seus devidos parâmetros|Uma string formatada conforme especificado seja retornada|

**Boa diversão dev! 😁** 

