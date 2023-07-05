# Automação de Processos

## Objetivo

Este projeto foi feito como um exercício de um intensivão de Python. O objetivo é automatizar o um processo de entrar em um sistema, baixar uma base de dados, tratar os dados e enviar um relatório por email.

## Como funciona

O código utiliza a ferramenta de automação PyAutoGUI para controlar o mouse e o teclado do computador, permitindo a realização automática de tarefas. O código realiza os seguintes passos:

1. O script abre uma nova aba do navegador utilizando as funcionalidades do PyAutoGUI. Em seguida, direciona essa aba para o link de um sistema fictício.
2. O código faz o login do usuário no sistema, inserindo o nome de usuário e senha nos campos apropriados.
3. Após a autenticação, o script é redirecionado para um drive onde a base de dados está disponível. Utilizando o PyAutoGUI, o código localiza o botão de download e clica nele para iniciar o download da base de dados.
4. O próximo passo é abrir o cliente de e-mail utilizando o PyAutoGUI. Uma vez aberto, o código preenche os campos necessários, como o destinatário e o assunto, utilizando funções específicas do PyAutoGUI. Em seguida, o código redige um relatório com base nos dados da base de dados baixada e envia-o para o destino desejado.

Esse fluxo de automação oferece uma solução eficiente para realizar uma sequência de tarefas, desde a abertura de uma nova aba no navegador, autenticação em um sistema, download de dados e envio de um relatório por e-mail. O PyAutoGUI é uma ferramenta versátil que permite a automação de tarefas repetitivas, economizando tempo e esforço manual.

## Bibliotecas usadas

Foram utilizadas as bibliotecas: **PyAutoGUI, Pyperclip, Time,** e o **Pandas**

## Detalhes

- O código foi feito com base na resolução do meu computador, para rodar no seu, é necessário alterar as coordenadas nas linhas do código que possuem a função de clicar, como por exemplo:

```python
pyt.click(x=757, y=407)  # Alterar
pyt.write("Meu Login")

pyt.click(x=634, y=492)  # Alterar
pyt.write("Minha senha")
```

Para saber quais as coordenadas que deve colocar, execute esta seguinte célula do código, ela mostra as coordenados do seu cursor 5 segundos após executada, aí é só posicionar o mouse aonde deseja saber as coordenadas.

```python
# Esta ferramenta indica as coordenadas do seu mouse no momento em que você executa ela, vai servir para sabermos as coordenadas
# de onde a automação vai executar o click

# Aqui vamos rodar o código e temos 5 segundos para posicionar o mouse onde queremos descobrir as coordenadas
time.sleep(5)
print(pyt.position())
```

- Você também vai precisar alterar as linhas de código que definem o email do destinatário e o local de onde você baixou a base de dados:

```python
tabela = pd.read_csv(r"endereço da pasta onde baixou o arquivo", sep = ';')
display(tabela)

pyt.write("seuemailaqui@gmail.com")
pyt.press("tab") # escolher o destinatário
```
