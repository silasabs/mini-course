# Guia de Configuração

- [OptiCommPy](#opticommpy)
- [Prepando o seu ambiente](#prepando-o-seu-ambiente)
	- [Verificando e Instalando o Python](#verificando-e-instalando-o-python)
	    - [Instruções para o Windows](#instruções-para-o-windows)
	    - [Instruções para o Linux](#instruções-para-o-linux)
	- [Criando Ambientes Virtuais com o MiniConda](#criando-ambientes-virtuais-com-o-miniconda)
	    - [Instalando o MiniConda no Windows](#instalando-o-miniconda-no-windows)
	    - [Instalando o MiniConda no Linux](#instalando-o-miniconda-no-linux)
	    - [Manipulando ambientes com o MiniConda](#manipulando-ambientes-com-o-miniconda)
	- [Instalando o OptiCommPy](#instalando-o-opticommpy)
- [Dicas](#dicas)
    - [Instalação customizada](#instalação-customizada-opcional)
    - [Integração com Jupyter Notebooks](#integração-com-jupyter-notebook)

## OptiCommPy

 O [OptiCommPy](https://github.com/edsonportosilva/OptiCommPy) e uma estrutura baseada em Python para simular sistemas, subsistemas e componentes de sistemas de comunicação de fibra óptica. O pacote conta com os principais algoritmos utilizados em processamento digital de sinais:

- Filtragem FIR (CPU / GPU)
- Upsample / Decimate
- Resample
- Filtro de Média Móvel
- Normalização

E dentre outros. Além disso diversos algoritmos são acelerados a partir do Numba e diversas implementações baseadas em GPU estão disponíveis. para mais informações consulte a documentação oficial [aqui](https://opticommpy.readthedocs.io/en/latest/index.html).

## Prepando o seu ambiente

### Verificando e Instalando o Python

Será necessário ter o Python instalado para utilizarmos o OptiCommPy, permitindo a execução dos algoritmos que serão explorados durante o mini curso.

#### Instruções para o Windows

1. Verifique se você possui o python instalado em sua máquina.

    Abra o Prompt de Comando ou o PowerShell e execulte o seguinte comando:

    ```
    $ python --version
    ```

    Se o Python estiver instalado, o comando retornará algo como: Python 3.x.x. Se o comando não funcionar, pode ser que o Python não esteja instalado ou o caminho do Python não esteja no PATH.

2. Instalando o Python.

    Acesse o [site oficial](https://www.python.org/downloads/) e baixe o instalador para a versão mais recente do Python 3. Execute o instalador baixado. 

    **Importante**: Marque a opção "*Add Python to PATH*" antes de clicar em *"Install Now"*. Isso adicionará o Python ao seu PATH, permitindo que você o execute em qualquer lugar do PowerShell.

3. Verificando a instalação.
    
    Após a instalação, abra o Prompt de Comando ou PowerShell e execute:

    ```
    $ python --version
    ```
    
    Para instalar o pip, normalmente já vem incluído no instalador do Python. Verifique com o comando:

    ```
    $ pip --version
    ```
    
    Caso o pip não esteja instalado, você pode instalá-lo manualmente:
    
    ```
    $ python -m ensurepip --upgrade
    ```

#### Instruções para o Linux

Na maioria das distribuições Linux, como Ubuntu e Fedora, o Python geralmente já vem pré-instalado. Caso não esteja, você pode instalar facilmente.

1. Para distribuições baseadas em Debian

    Abra o terminal e execute o comando para atualizar o gerenciador de pacotes:

    ```
    $ sudo apt update
    ```

2. Para instalar a versão mais recente do Python 3 faça:

    ```
    $ sudo apt install python3
    ```

3. Verifique a instalação

    ```
    $ python3 --version
    ```

4. Para instalar o pip (gerenciador de pacotes Python)

    ```
    $ sudo apt install python3-pip
    ```

O processo e semelhante para as demais distribuições !

### Criando Ambientes Virtuais com o MiniConda

Criar e gerenciar diferentes ambientes com MiniConda permite que você mantenha projetos independentes com versões específicas de pacotes e do Python.

MiniConda é uma versão leve do Anaconda, que contém apenas o essencial: o Conda (o gerenciador de pacotes e ambientes) e Python. Ele é útil para criar ambientes isolados e gerenciar pacotes sem precisar baixar o Anaconda completo. Com ele, você pode criar diferentes ambientes para cada projeto com diferentes dependências e versões de Python.

#### Instalando o MiniConda no Windows
    
1. Acesse o [site oficial](https://docs.anaconda.com/miniconda/) do MiniConda e baixe a versão para Windows "Miniconda3 Windows 64-bit".
    
2. Execute o instalador e siga os passos. Marque a opção para adicionar o Conda ao PATH, permitindo seu uso no prompt de comando.
    
3. Após a instalação, abra o Prompt de Comando do Conda e digite: 
        
    ```
    $ conda --version
    ```

#### Instalando o MiniConda no Linux

1. Siga os passos descritos [aqui](https://docs.anaconda.com/miniconda/#miniconda-latest-installer-links). Vá até "Quick command line install" e selecione a opção "Linux" as mesmas instruções se encontram abaixo:
        
    Esses quatro comandos baixam a versão mais recente de 64 bits do instalador do Linux, renomeiam-no para um nome de arquivo mais curto, instalam silenciosamente e, em seguida, excluem o instalador:

    ```
    $ mkdir -p ~/miniconda3
    $ wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64 sh -O ~/miniconda3/miniconda.sh
    $ bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
    $ rm ~/miniconda3/miniconda.sh
    ```

#### Manipulando ambientes com o MiniConda

Agora com o MiniConda devidamente instalado podemos criar diferentes ambientes para diferentes projetos, podemos criar um ambiente como:

```
$ conda create -n nome_do_ambiente_virtual python=3.11.4
```

Onde o nome_do_ambiente_virtual pode ser substituido por qualquer nome que você desejar, como por exemplo "mini_curso_pds", você também pode especificar qualquer versão do Python, como 3.9, 3.7, etc.

Lembre-se que quando utilizamos o conda o ambiente virtual padrão é definido como "base" é será necessário realizar a troca para o ambiente que acabamos de criar, para fazer isso digite no seu terminal:

```
$ conda activate mini_curso_pds
```

Caso queira retornar para o ambiente "base" faça:

```
$ conda deactivate
```

Com o ambiente selecionado podemos começar a instalação dos pacotes que serão necessários durante o mini curso. Caso você queira aprender mais sobre MiniConda e como manipular diferentes ambientes virtuais acesse este [link](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) que levará você para documentação oficial do MiniConda.

### Instalando o OptiCommPy

Agora que você possui um ambiente devidamente configurado podemos instalar o OptiCommPy na env "mini_curso_pds", para isso faça:

```
$ pip install OptiCommPy
```

Automaticamente as demais dependências também serão instaladas como o NumPy, SciPy, Matplotlib ... 

Se você deseja utilizar os algoritmos baseados em GPU certifique-se de possuir uma GPU Nvidia além de instalar a versão mais recente do CUDA e possuir o pacote CuPy em seu ambiente virtual "mini_curso_pds". Você também pode optar por utilizar o ambiente do Google Colab.

**Importante**: Caso você utilize algum editor de código como o Visual Studio Code, certifique-se de que o ambiente virtual que acabamos de criar está selecionado.

## Dicas

### Instalação customizada (opcional)

O modo desenvolvedor permite que você faça alterações no código-fonte do projeto enquanto testa e usa a versão mais recente do pacote sem precisar reinstalar ou recompilar constantemente. Ele é útil para quem está contribuindo com o desenvolvimento de um pacote ou para necessidades específicas.

Para realizar estas etapas e importante que você possua o Git instalado em sua máquina, caso contrário você pode instalar seguindo os passos descritos [aqui](https://git-scm.com/downloads). Em "Downloads" selecione sua plataforma e siga as instruções necessárias.

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

### Integração com Jupyter Notebook

Utilizar os cadernos jupyter ".ipynb" nos permite testar o código em pequenos blocos, alternar entre explicações teóricas e práticas no mesmo ambiente, obter a visualização de gráficos diretamente nas células e diversas outras funcionalidades que nos ajudam na compreensão de conceitos mais complexos. 

Aqui iremos fornecer instruções para integrar o seu ambiente criado anteriormente para aproveitar os benefícios que os cadernos jupyter fornecem através do ambiente do Jupyter Notebook. O Jupyter Notebook é um ambiente de desenvolvimento interativo, onde o código é executado através do navegador da web porém funcionando localmente. 

Agora que criamos e ativamos um ambiente conda "mini_curso_pds", vamos ver como podemos usá-lo no Jupyter Notebook.

**Importante**: Siga as instruções abaixo com a env "mini_curso_pds" selecionada.

1. Instalando a interface clássica do Jupyter Notebook

    Primeiro, certifique-se de ter o pip mais recente; versões mais antigas podem ter problemas com algumas dependências:
    
    ```
    $ pip3 install --upgrade pip
    ```

2. Em seguida, instale o Jupyter Notebook usando:

    ```
    $ pip3 install jupyter
    ```

3. Instale o pacote ipykernel utilizando o repositório do conda-forge:

    ```
    $ conda install ipykernel
    ```
    
    Este pacote permite que você crie um kernel para o ambiente conda que pode ser usado no Jupyter Notebook.

4. Crie um kernel para o seu ambiente:

    ```
    $ python -m ipykernel install --user --name=mini_curso_pds
    ```
    
    Isso criará um novo kernel para o ambiente “mini_curso_pds” que pode ser usado no Jupyter Notebook.

5. Inicie o Jupyter Notebook:

    ```
    $ jupyter notebook
    ```
    
    O Jupyter Notebook irá inicializar um servidor local. Você deverá ver o ambiente aberto no seu navegador.

Agora no Jupyter Notebook, crie ou abra um notebook, e no canto superior direito selecione “mini_curso_pds” como o kernel. Agora você deve conseguir usar os pacotes instalados no ambiente “mini_curso_pds” no seu Jupyter Notebook.