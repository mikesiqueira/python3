#Autor: Robson Vaamonde<br>
#Procedimentos em TI: http://procedimentosemti.com.br<br>
#Bora para Prática: http://boraparapratica.com.br<br>
#Robson Vaamonde: http://vaamonde.com.br<br>
#Facebook Procedimentos em TI: https://www.facebook.com/ProcedimentosEmTi<br>
#Facebook Bora para Prática: https://www.facebook.com/BoraParaPratica<br>
#Instagram Procedimentos em TI: https://www.instagram.com/procedimentoem<br>
#YouTUBE Bora Para Prática: https://www.youtube.com/boraparapratica<br>
#Data de criação: 16/07/2024<br>
#Data de atualização: 29/07/2024<br>
#Versão: 0.04<br>

Conteúdo estudado nessa aula:<br>
#01_ Trabalhando com Condições de Estrutura de Decisão IF (SE) do Python 3 no Linux Mint<br>
#02_ Trabalhando com Condições de Estrutura de Decisão e Blocos IF (SE) do Python 3 no Linux Mint<br>

#01_ Trabalhando com Condições de Estrutura de Decisão IF (SE) do Python 3 no Linux Mint<br>
Link de apoio: https://www.w3schools.com/python/gloss_python_if_statement.asp
```python
#CENÁRIO 01: estrutura de decisão simples com IF (SE)

#Salvar o arquivo de script com o nome: 30-ifbasic01.py no diretório: ScriptsPython
#Executar o script com a opção: F5 ou Ctrl+F5 ou clicar o ícone: Run Python File

#Atribuindo os valores inteiros a duas variáveis dinâmicas
valor01=int(input("Digite o primeiro valor: "))
valor02=int(input("Digite o segundo valor.: "))
print()

#Bloco de teste lógico de condição verdadeira utilizando o IF
if valor01 > valor02:
    #Imprimir na tela se o resultado for verdadeiro, se for falso não
    print("Primeiro valor é MAIOR que o Segundo valor!")
if valor02 > valor01:
    #Imprimir na tela se o resultado for verdadeiro, se for falso não
    print("Segundo valor é MAIOR que o Primeiro valor!")
```
```python
#CENÁRIO 02: estrutura de decisão simples com IF (SE)

#Salvar o arquivo de script com o nome: 31-ifbasic02.py no diretório: ScriptsPython
#Executar o script com a opção: F5 ou Ctrl+F5 ou clicar o ícone: Run Python File

#Atribuindo o valor inteiro a variável constante
#Link: https://www.autoindustria.com.br/2024/04/24/frota-brasileira-envelhece-e-idade-media-dos-carros-supera-11-anos/
media_idade = int(11)

#Atribuindo valor inteiro a variável dinâmica
idade_carro = int(input("Digite a idade do seu carro: "))
print()

#Bloco de teste lógico de condição verdadeira utilizando o IF
if idade_carro <= media_idade:
    #Imprimir na tela se o resultado for verdadeiro, se for falso não
    print("Seu carro é MAIS NOVO que a média de idade dos carros dos Brasileiro!")
if idade_carro > media_idade:
    #Imprimir na tela se o resultado for verdadeiro, se for falso não
    print("Seu carro é MAIS VELHO que a média de idade dos carros dos Brasileiro!")
```

#02_ Trabalhando com Condições de Estrutura de Decisão e Blocos IF (SE) do Python 3 no Linux Mint<br>
Link de apoio: https://www.w3schools.com/python/gloss_python_if_statement.asp
```python
#CENÁRIO 03: trabalhando com IF para uma nova versão do IRPF (modo simples)
#Link dos valores: https://www.gov.br/receitafederal/pt-br/assuntos/meu-imposto-de-renda/tabelas/2024
#Link dos valores: https://www.gov.br/inss/pt-br/noticias/confira-as-aliquotas-de-contribuicao-ao-inss-com-o-aumento-do-salario-minimo

#Salvar o arquivo de script com o nome: 32-irpfv2.py no diretório: ScriptsPython
#Executar o script com a opção: F5 ou Ctrl+F5 ou clicar o ícone: Run Python File

#!/usr/bin/python3
#Instalando o módulo: Tabulate (Tabulador) do Python: pip install tabulate
#Importando a Função Tabulate do Módulo Tabulate para o projeto do Python
from tabulate import tabulate

#Criando a Tabela de Alíquotas do IRPF 2024 utilizando o Módulo Tabulate
tabela_irpf2024 = [ 
	["Base de Cálculo", "Alíquota", "Dedução"],
	["Até 2.259,20", "0%", "0,00"],
	["De 2.259,21 até 2.826,65", "7,5%", "169,44"],
	["De 2.826,66 até 3.751,05", "15.0%", "381,44"],
	["De 3.751,06 até 4.664,68", "22,5%", "662,77"],
	["Acima de 4.664,68", "27,5%", "896,00"],
]

#Bloco de digitação dos Valores para o Cálculo do IRPF 2024
print("Digite os valores para o Cálculo do IRPF 2024")
renda_bruta = float(input("Digite a sua Renda Bruta Mensal.: "))
salario = renda_bruta
imposto = 0.0
print()

#Bloco de teste lógico das condições verdadeiras utilizando o IF
#O código abaixo verifica a renda_bruta em faixas decrescentes, ajustando o valor do
#imposto de acordo com a alíquota correspondente, o ajuste da faixa da variável da
#renda_bruta garante que cada faixa de renda seja tributada corretamente, sem sobreposição.
if renda_bruta > 4664.68:
    imposto = imposto + (renda_bruta - 4664.68) * 0.275
    renda_bruta = 4664.68
if renda_bruta > 3751.06:
    imposto = imposto + (renda_bruta - 3751.06) * 0.225
    renda_bruta = 3751.06
if renda_bruta > 2826.66:
    imposto = imposto + (renda_bruta - 2826.66) * 0.15
    renda_bruta = 2826.66
if renda_bruta > 2259.21:
    imposto = imposto + (renda_bruta - 2259.21) * 0.075
    renda_bruta = 2259.21
print(f"Renda Bruta Mensal: R$:{salario:6.2f} - Imposto a Pagar: R$:{imposto:6.2f}")

#Imprimindo na Tela a Tabela do IRPF 2024 utilizando a Função Tabulate
#A Função TABULATE() chama os valores da variável: tabela_irpf2024 e passa os parâmetros
#de: headers="firstrow" que usa a primeira linha como cabeçalho, tablefmt="grid"
#que formata a tabela com bordas e stralign="center" que centraliza o Texto.
print(tabulate(tabela_irpf2024, headers="firstrow", tablefmt="grid", stralign="center"))
```