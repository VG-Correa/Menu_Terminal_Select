# Menu_Terminal_Select

Esse menu de seleção para terminal foi criado para suprir a necessidade de fluidez dentro de um sistema feito para o terminal, onde a entrada de dados e seleção de opções torna-se complicada e pouquíssimo atrativo para o usuário.


**Descrição técnica:**

Este programa contém duas funções e uma classe. A função **cls()** é responsável por limpar a tela do terminal. A função **getch()** captura a tecla pressionada pelo usuário sem exibir o caractere digitado no terminal. A classe **Menu_seleção** é responsável por criar um menu de seleção de opções no terminal, permitindo que o usuário navegue pelas opções usando as setas de direção e selecione uma opção pressionando a tecla Enter.

A classe **Menu_seleção** possui um construtor **__init__()** que define as opções de formatação de texto para o cabeçalho e as opções de menu, além de outras configurações. A classe tem também o método **Set_Paleta()** que permite definir um conjunto personalizado de opções de formatação de texto para o menu.

O método **options()** da classe **Menu_seleção** é responsável por exibir o menu e permitir que o usuário navegue pelas opções e selecione uma delas. Esse método recebe como parâmetros o **cabeçalho**, a **descrição** e as **opções** de menu a serem exibidas. O método usa a função **cls()** para limpar a tela e, em seguida, exibe o **cabeçalho**, a **descrição** e as **opções** de menu no terminal. O método permite que o usuário navegue pelas opções de menu usando as teclas de seta para cima e para baixo. Quando o usuário seleciona uma opção, pressionando a tecla **Enter**, o método retorna o **índice** da opção selecionada.

Para utilizar em seu código, coloque o arquivo "Menu_seleção.py" na pasta de seu projeto de forma que consiga importa-lo.
Importe o menu de seleção, aconselho colocar o apelido como **ms**

```python
from Menu_seleção import Menu_seleção as ms
```

Defina um cabeçalho que sempre irá aparecer nas telas de navegação:
```python
cabecalho = "B.R.A.I.N.S"
```

Instancie um objeto do tipo Menu_seleção que receberá todas as configurações básicas para seu menu funcionar.

```python
menu = ms(cabeçalho=cabecalho)
```
Apenas com o cabeçalho já é possível utiliza-lo, pois ele vem com configurações default!
As configurações que podem ser definidas ao instanciar o menu são:

**1 - Cabeçalho:** Como no exemplo acima, ideal que tenha um tamanho legal para caber dentro do terminal e ainda conseguir mostrar as opções. Ele também pode ser vazio caso não queira cabeçalho, Basta apenas não especifica-lo.

**2 - limite_opçoes:** É o limite de opções que aparecerão por vez na tela. Em casos onde as opções passariam da tela e ficaria inviável visualizar de forma confortável. Ele por padrão vem como 10 itens, mas pode ser alterado da seguinte maneira:
```python
menu = ms(cabeçalho=cabeçalho,limite_opçoes=5)
```
Dessa forma ele vai imprimir na tela apenas cinco opções, e terá o rolamento deles caso o usuário tente selecionar o item 6.

**3 - texto_seleção:** É a configuração do estilo de texto, cor do texto e cor de fundo. Por padrão, o texto selecionado será em negrito, texto vermelho e fundo cinza.
Para alterar essa opção, basta informar uma lista com três strings respectivamente: 
```python
texto = ["negrito","vermelho","cinza"] # ["Estilo","Cor do texto","Cor de fundo"]
```

**As opções para alteração do estilo do texto são:**

**"negrito":** Deixa o texto mais grosso, no estilo bold;

**"sublinhado:"** Deixa o texto com uma linha abaixo;

**"normal":** Volta a formatação original do estilo;

**"negativo** Inverte a cor de texto com a cor de fundo;

**As opções para as cores de texto e cores de fundo são:**

**"branco","vermelho","verde","amarelo","azul","roxo","ciano","cinza","normal"**

Para editar essa formatação ao instanciar o menu, você pode fazer:

```python
menu = ms(texto_seleção=["normal","vermelho","verde"])
```

**texto_padrão:** É outro argumento parecido com o texto_seleção, tem as mesmas configurações e a sua edição é da mesma maneira, porém, ele vai editar as cores das opções que não estão selecionadas.

Caso queira editar as cores do terminal após instanciar o menu, você possui duas maneiras:

1 - Editando diretamente a variável interna **"texto_seleção** ou **"texto_padrao"**:
```python
menu.texto_seleção = ['normal','verde','branco']
menu.texto_padrao = ['negrito','ciano','cinza']
```
2 - Utilizando a função **Set_Paleta(texto_seleção,texto_padrão)**
```python
menu.Set_Paleta(['normal','verde','branco'],['negrito','ciano','cinza'])
```

**E por fim, temos a função que mostra as opções de navegação do usuário.**

Função **options**
**cabeçalho:** Ela por padrão utiliza o **cabeçalho** informado anteriormente, mas que pode ser informado nesse momento caso queira utilizar outro para essa tela específica (Não precisa ser especificado na função, por padrão, utilizará o cabeçalho informado anteriormente); 

**descrição:** É um argumento que pode mudar em toda tela, onde pode mostrar orientações ao usuário, descrição da tela,  mostrar alguns dados, etc. É um argumento String (Não precisa ser especificado na função, por padrão apenas não vai printar nenhuma descrição;

**opções:** É o argumento obrigatório para funcionar! Você informa uma lista de Strings que serão printadas na mesma ordem como opções para o usuário. Não há limite para a quantidade de opções. As únicas teclas reconhecidas nesse momento são as teclas para cima, baixo e enter.

O método vai retornar o index da lista informada de opções.

