Recentemente começo meus estudos com o python, confesso que tentativas anteriores fracassaram mas agora estou usando uma ferramenta chamada <a target="_blank" href="http://www.alura.com.br">Alura</a> e seus cursos maravilhosos. Aqui deixo algumas notações. 

## Python - parte 1

#### Afinal o que é Python?

É uma linguagem de programação de alto nível, interpretada, de script, imperativa, orientada a objetos, funcional, de tipagem dinâmica e forte. Foi lançada por Guido van Rossum em 1991. Atualmente possui um modelo de desenvolvimento comunitário, aberto e gerenciado pela organização sem fins lucrativos Python Software Foundation. Apesar de várias partes da linguagem possuírem padrões e especificações formais, a linguagem como um todo não é formalmente especificada. O padrão de facto é a implementação CPython. [<a target="_blank" href="https://pt.wikipedia.org/wiki/Python">Wikipedia</a>]

#### Como instalar?

Obviamente que grandes sistemas operacionais já com o Python instalado.

<img src="/assets/python/entendi_a_referencia.jpg" width="400" height="250"/>

Calma jovem, você pode seguir dois caminhos.
1º Instalar um sistema operacional na sua maquina.
2º Instalar o <a target="_blank" href="http://docs.python-guide.org/en/latest/starting/install/win/">python</a> para windows.

#### Filosofia Python

Tim Peters um usuário do python de longa data escreveu 'The Zen of Python'. Para ve-lo no terminal digite:

```
import this

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!

```

Translate:

```
Belo é melhor que feio.
Explícito é melhor que implícito.
Simples é melhor que complexo.
Complexo é melhor que complicado.
Plano é melhor que aninhado.
Esparso é melhor que denso.
Legibilidade conta.
Casos especiais não são especiais o suficiente para violar as regras.
Embora praticidade vença pureza.
Erros não devem passar silenciosamente.
A não ser que sejam explicitamente silenciados.
Em caso de ambiguidade, resista à tentação de adivinhar.
Deve haver um - e somente um - jeito óbvio de fazer.
Embora tal jeito não seja tão óbvio no à primeira vista a não ser que você seja holandês.
Agora é melhor que nunca.
Embora nunca é frequentemente melhor que exatamente agora.
Se a implementação é difícil de explicar, a ideia é ruim.
Se a implementação é fácil de explicar, talvez a ideia seja boa.
Espaços de nomes são uma ideia estupenda - vamos fazer mais deles!
```

### A linguagem

A primeira impressão que tive é uma linguagem facil, onde indentação realmente importa. <s>Quero ver aqueles cabeções não indentar a porcaria do código agora...</s>

Por conversão é usado o underscore para nome de variavel ou funções, exemplo:

```
nome_da_variavel

def nome_da_funcao():
```

#### Declaracao de Variáveis

A declaração é simples. Simplesmente podemos nomear a variavel atribindo o valor. Ele "automaticamente" reconhe o tipo de variável a ser atribuida. Veja:

```
nome_do_inteiro = 10
nome_da_string = 'Gabriel'
```

Mas e se eu quiser um long? Ou numero mais complexo?

Para usar um Long atribua o caracter 'l' na frente do valor, exemplo:

```
variavel_long = 1000l
```

Para usar um valor complexo atibua o caracter 'j', veja:

```
variavel_complex = 12121212j
```

<!-- COMPARTILHAMENTO DE POST -->
<table width="100%" align="center">
        <tr>
                <td><p>Compartilhe</p></td>
        </tr>
        <tr>
                <td align="center" title="Facebook">
                        <a onclick="window.open(this.href, 'facebook-share','width=580,height=296');return false;" href="https://www.facebook.com/sharer/sharer.php?u=http://gpanassol.github.io/notes/nosql/" class="icon-facebook">
                                <img src="/assets/network/fc.png" width="50" height="50"/>
                        </a>
                </td>
                <td align="center" title="Twitter">
                        <a onclick="window.open(this.href, 'twitter-share', 'width=550,height=235');return false;" href="http://twitter.com/share?text=NoSQL&amp;url=http://gpanassol.github.io/notes/nosql/" class="icon-twitter">
                                <img src="/assets/network/twitter.png" width="50" height="50"/>
                        </a>
                </td>
                <td align="center" title="LinkedIn">
                        <a onclick="window.open(this.href, 'google-plus-share', 'width=490,height=530');return false;" href="https://plus.google.com/share?url=http://gpanassol.github.io/notes/nosql/" class="icon-google-plus">
                                <img src="/assets/network/google-plus.png" width="50" height="50"/>
                        </a>

                </td>
        </tr>
</table>
