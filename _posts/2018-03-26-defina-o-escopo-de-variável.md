## Java Básico - Defina o escopo de variável

### Defina o escopo de variável

O escopo de uma variável é a parte do programa onde a variável está acessível. Uma variável pode ser determinado no tempo do compilador e independente da pilha de chamadas da função. As regras do escopo Java podem ser cobertas nas seguintes categorias.

#### Variáveis estáticas 

São criadas quando a classe é carregada, sobrevivendo enquanto a classe continuar carregada na JVM.

```
public class Test
{
    static int a; //variavel estática
}
```

As variáveis ​​de membro podem ser acessadas fora de uma classe com as seguintes regras:

#### Variáveis de instância 

São criadas quando uma nova instância é criada, e duram até essa instância ser removida.

```
public class Test
{
    int a; //variavel de instancia
}
```

#### Variáveis locais 

Que permanecem enquanto o método que as contém estiver sendo executado.

```
public class Test
{
    public void local(){
        int a;  //variavel local
    }
}
```

#### Variáveis de bloco 

Que permanecem enquanto o bloco estiver sendo executado. 

```
public class Test
{
    public void local(String[] args){
        for(String a : args){
            a; //variavel de bloco
        }
    }
}
```
