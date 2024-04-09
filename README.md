# Máquina de Estados Finitos para Controle Remoto de TV.
Este repositório contém código Python que implementa uma Máquina de Estados Finitos (MEF) modelando o comportamento de um controle remoto de TV. A MEF é construída usando a biblioteca automathon para definir e trabalhar com autômatos finitos determinísticos (DFA), e a biblioteca visual_automata para visualizar DFAs.

Instalação
Certifique-se de ter de usar o GoogleColab ou o instalar o Jupyter Notebook [tutorial](https://jupyter.org/install) e, em seguida, instale as bibliotecas necessárias:

```bash
!pip install automathon --upgrade
!pip install visual_automata --upgrade
```

# Descrição da Máquina de Estados Finitos
A MEF representa o comportamento de um controle remoto de TV com os seguintes estados e transições:

Estados (Q):

q0: TV desligada

q1: TV ligada

q2: Selecionar usuário no aplicativo Netflix

q3: Selecionar filme no aplicativo Netflix

q4: Selecionar filme no aplicativo Globo Play (não requer autenticação)

q5: Selecionar usuário no aplicativo Prime Video

q6: Selecionar filme no aplicativo Prime Video

Alfabeto (Σ):

L: Botão de energia

K: Enter/OK

+: Aumentar volume

-: Diminuir volume

N: Netflix

P: Prime Video

G: Globo Play

Transições (δ):

As transições são definidas como um dicionário que mapeia cada estado e símbolo de entrada para o próximo estado.
Estado Inicial:

q0: TV desligada

Estados Finais (F):

q3: Filme selecionado no Netflix

q4: Filme selecionado no Globo Play

q6: Filme selecionado no Prime Video

Uso
Instancie o objeto DFA representando a MEF do controle remoto de TV:

```bash
from automathon import DFA
from visual_automata.fa.dfa import VisualDFA

# Defina estados, alfabeto, transições, estado inicial e estados finais
```
```bash
automata = DFA(Q, sigma, delta, initial_state, F)
Verifique se o autômato é válido:
```
```bash
#Verificando se o autômato é valido
automata.is_valid()
```
Visualize o DFA:

```bash
#convertendo o objeto DFA para VisualDFA
dfa = VisualDFA(states = automata.q, input_symbols = automata.sigma,transitions=automata.delta,initial_state = automata.initial_state,final_states=automata.f)

```
Acesse a tabela de transições:


```bash
#Criando a tabela usando a propriedade do objeto VisualDFA.
dfa.table
```
**Referências**

[Repositório do automathon no GitHub](https://github.com/rohaquinlop/automathon)

[Documentação do automathon](https://rohaquinlop.github.io/automathon/)

[visual_automata no PyPI](https://pypi.org/project/visual-automata/)
[Código para visualização funcionando na integra](https://colab.research.google.com/drive/1dzYm548UzZMZOgMde33kMYTxzAqxGOyQ?usp=sharing)

Para mais detalhes, consulte os links e documentação fornecidos.
