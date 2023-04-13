# Menu_Terminal_Select

Esse menu de seleção para terminal foi criado para suprir a necessidade de fluidez dentro de um sistema feito para o terminal, onde a entrada de dados e seleção de opções torna-se complicada e pouquíssimo atrativo para o usuário.


**Descrição técnica:**

Este programa contém duas funções e uma classe. A função cls() é responsável por limpar a tela do terminal. A função getch() captura a tecla pressionada pelo usuário sem exibir o caractere digitado no terminal. A classe Menu_seleção é responsável por criar um menu de seleção de opções no terminal, permitindo que o usuário navegue pelas opções usando as setas de direção e selecione uma opção pressionando a tecla Enter.

A classe Menu_seleção possui um construtor __init__() que define as opções de formatação de texto para o cabeçalho e as opções de menu, além de outras configurações. A classe tem também o método Set_Paleta() que permite definir um conjunto personalizado de opções de formatação de texto para o menu.

O método options() da classe Menu_seleção é responsável por exibir o menu e permitir que o usuário navegue pelas opções e selecione uma delas. Esse método recebe como parâmetros o cabeçalho, a descrição e as opções de menu a serem exibidas. O método usa a função cls() para limpar a tela e, em seguida, exibe o cabeçalho, a descrição e as opções de menu no terminal. O método permite que o usuário navegue pelas opções de menu usando as teclas de seta para cima e para baixo. Quando o usuário seleciona uma opção, pressionando a tecla Enter, o método retorna o índice da opção selecionada.
