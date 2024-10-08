# OptiCommPy 

- [O que é o OptiCommPy ?](#o-que-é-o-opticommpy-?)
- [Prepando o seu ambiente](#prepando-o-seu-ambiente)
	- [Verificando e Instalando o Python](#verificando-e-instalando-o-python)
	- [Adicionando Múltiplos Ambientes com o MiniConda](#adicionando-múltiplos-ambientes-com-o-miniconda)
	- [Instalando o OptiCommPy](#instalando-o-opticommpy)
- [Dicas](#dicas)
    - [Instalação customizada](#instalação-customizada)
    - [Integração com Jupyter Notebooks](#integração-com-jupyter-notebooks)

## O que é o OptiCommPy ?

 O OptiCommPy e uma estrutura baseada em Python para simular sistemas, subsistemas e componentes de sistemas de comunicação de fibra óptica. O pacote conta com os principais algoritmos utilizados em processamento digital de sinais:

- Filtragem FIR (CPU / GPU)
- Upsample / Decimate
- Resample
- Filtro de Média Móvel
- Normalização

E dentre outros. Além disso diversos algoritmos são acelerados a partir do Numba e diversas implementações baseadas em GPU estão disponíveis. para mais informações consulte a documentação oficial [aqui](https://opticommpy.readthedocs.io/en/latest/index.html).

## Prepando o seu ambiente

### Verificando e Instalando o Python

### Adicionando Múltiplos Ambientes com o MiniConda

### Instalando o OptiCommPy

## Dicas

### Instalação customizada

O modo desenvolvedor permite que você faça alterações no código-fonte do projeto enquanto testa e usa a versão mais recente do pacote sem precisar reinstalar ou recompilar constantemente. Ele é útil para quem está contribuindo com o desenvolvimento de um pacote ou para necessidades específicas.

1. Clonando o Repositório do OptiCommPy

    Com o Git instalado abra o terminal e use o comando abaixo para clonar o  repositório do OptiCommPy
    
    ```
    $ git clone https://github.com/edsonportosilva/OptiCommPy.git
    ```
    
    Isso vai criar uma cópia local do código-fonte do projeto.

2. Instalando o OptiCommPy em Modo Desenvolvedor
    
    Após clonar o repositório, entre na pasta do projeto:

    ```
    $ cd OptiCommPy
    ```
    
    Para instalar o pacote em modo desenvolvedor, execute o seguinte comando:

    ```
    $ pip install -e .
    ```
    
    O "-e" indica "*editable mode*", que é o modo desenvolvedor. Isso permite modificar o código diretamente e ver as mudanças sem precisar reinstalar o pacote. Agora, qualquer mudança feita no código-fonte será automaticamente refletida quando o pacote for executado.

### Integração com Jupyter Notebooks