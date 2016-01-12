Title: Simples Flask App
Date: 2016-01-11 21:57
Tags: python, flask, dev
Category: developing
Slug: simples-flask-app
Author: Henrique Lopes


Já sentiu vontade de criar uma simples aplicação web, mais se sentiu preso? Pois quando você via o número de
configurações que eram necessárias para fazer a sua aplicação apenas dar um Hello World, você ja sentia que ia
demorar? Pois bem o python não é uma bala de prata, mais ele possui n [frameworks](https://pt.wikipedia.org/wiki/Framework) e [microframeworks](https://en.wikipedia.org/wiki/Microframework) que vão fazer você sentir prazer em gerar um simples Hello World.

Hoje eu quero apresentar um microframework muito conhecimento e já difundido na comunidade python, o [Flask](http://flask.pocoo.org/) que pela sua simplicidade e robustez, merece ser o meu primeiro post hands on.
E para adicionar mais baterias ao nosso App, vamos falar um pouco de [virtualenv](https://virtualenv.readthedocs.org/en/latest/).

##### Primeiro Passo - Montar o ambiente:
Se você usa [Linux](https://pt.wikipedia.org/wiki/Linux) ou [Macosx](https://pt.wikipedia.org/wiki/OS_X) seguir esse post será muito tranquilo. Se você usa [Windows](https://pt.wikipedia.org/wiki/Microsoft_Windows), eu vou escrever um outro post só para ajudar você.

Abra o terminal e siga os passos abaixo:
```bash
pip install virtualenv
```

Porque não instalar logo o flask, e partir para o que realmente interessa? Se você teve a curiosidade de abrir o link do [virtualenv](https://virtualenv.readthedocs.org/en/latest/) e dar uma lida, você já sabe o porque e para que eu iniciei esse app instalando essa lib. O que eu quero fixar na sua mente de uma forma bem simples, é que no mundo real em uma empresa web ou de qualquer ramo da tecnologia, você vai ter a necessidade de trabalhar com várias versões de python no seu dia a dia. Cada app ou projeto que você for trabalhar, vão possuir características que irão exigir que você possua várias versões de python na sua máquina. O [virturalenv](https://virtualenv.readthedocs.org/en/latest/) vai permitir que possua para cada projeto uma versão de python diferente, sem precisar instalar nada no python nativo do seu sistema. E sem deixar passar despercebido eu estou usando o gerenciador de pacote do python o [pip](https://docs.python.org/3.6/installing/index.html), com ele você irá instalar todos pacotes de python que o seu app precisa.

```bash
virtualenv /tmp/hello_world
source /tmp/hello_world/bin/activate

pip install flask
```

Eu não vou entrar no mérito dos comandos executados com o virtualenv, até porque a documentação explica muito bem isso. Mais logo logo eu escrevo um post, para te deixar a par.


#### Segundo passo - Escrever o app:

Após criar o nosso ambiente, vamos criar o nosso app. Geralmente eu crio uma pasta, então se quiser fa

```bash
mkdir hello-world
cd hello-world
touch app.py
atom app.py
```

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "HelloWorld"

if __name__ == "__main__":
    app.run()
```


```bash
python app.py
```