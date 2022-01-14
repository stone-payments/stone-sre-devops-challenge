# Stone DevOps | SRE Challenge

Bem vindo(a)! Esse é o STech Challenge DevOps | SRE!

# Antes de começar....

- [Keep it simple](https://pt.wikipedia.org/wiki/Princ%C3%ADpio_KISS), entendemos que você possui suas prioridades e nossa proposta é com esse desafio é ter uma idéia geral de como você faz seus códigos, toma suas decisões arquiteturais e o seu conhecimento geral sobre os assuntos abordados.
- Seu desafio precisa estar versionado no Github, em um repositório público ou privado (vamos te passar usuários do Github para compartilhar a solução se for a sua preferência).
- Documentação é primordial e vamos nos guiar por ela ;)
- A aplicação deve ser fácil de ser executada localmente, então abuse de scripts em Makefiles e o que for necessário. 
- Não tem problema se você não conseguir finalizar tudo! Não deixe de enviar seu desafio por isso!

# O desafio

Temos alguns entregáveis que vão nos ajudar a entender em que ponto você está tecnicamente. Você não precisa se preocupar de ir até o final, queremos ver o seu código e a sua linha de raciocínio.
O mínimo que esperamos é o entregável 1 e ele pode ser incrementado até chegarmos no entregável 4, sendo que a solução do mundo perfeito integra todas os entregáveis, inclusive subindo a app desenvolvida no primeiro entregável no cluster final ;)

# O prazo

Gostaríamos de entender até onde você consegue ir dentro do prazo de uma semana desde o momento em que o desafio é enviado. 

## Entregável 1

- Desenvolver uma API na linguagem de sua preferência (detalhes abaixo), sem se preocupar com camada de persistência (pode ser utilizado sqlite, persistência em memória...)
- Um Dockerfile para essa API para conseguirmos subí-la localmente.
- Uma pipeline de integração contínua para essa API utilizando tecnologias como Azure DevOps, TravisCI, Github Actions ou algum outro de sua preferência.
- Subir a aplicação em algum PaaS como o Heroku ou qualquer outro cloud provider (provavelmente você terá que assinar uma conta free tier ou se aproveitar de limites gratuitos oferecidos por cloud providers).

**Atenção**: Apesar de sua simplicidade, trate a aplicação como algo que fosse ser usado de fato no mundo real. Não deve haver duplicidade de dados, por exemplo. A API deve retornar os dados de forma correta e consistente. Mesmo as coisas simples precisam de atenção e qualidade. 

### Informações da API

#### Entidade Usuário

- Nome
- Sobrenome
- CPF
- E-mail
- Data de Nascimento

#### Rotas necessárias

- Uma rota para retornar todos os usuários cadastrados
- Uma rota para inserir um usuário
- Uma rota para buscar um usuário através de CPF

### Plus
- Escrever testes unitários, executados pela pipe de CI
- Utilizar um banco de dados (ex: PostgreSQL, MariaDB) para guardar os dados da API.
- Utilizar um docker-compose que sobe a API + banco de dados localmente.
- Escrever um teste funcional, executado pela pipe de CI


## Entregável 2

- Criar os manifestos Kubernetes para deploy da aplicação.
- Subir um cluster de Kubernetes em algum cloud provider utilizando IaC (queremos ver o código!) (PS: Cuidado com o billing da plataforma de cloud, tente utilizar free tiers, máquinas preemptíveis, etc :P)
- Adaptar os comandos do seu Makefile para subir a aplicação na cloud e para ser testada localmente utilizando K8S (Minikube, Microk8s).

### Plus
- Adaptar a pipeline de CD para deployar no seu novo cluster.

## Entregável 3

- Criar testes de carga para avaliar gargalos da aplicação e prover um resumo do que foi descoberto (gargalos de performance, como melhorar, etc).
- Pensar em uma estratégia de deploy que fizesse rollout da aplicação de forma a diminuir a quantidade de possíveis erros de uma nova release.

### Plus
- Melhorar a pipeline de CI para garantir melhores práticas (qualidade de código, etc)

## Entregável 4

- Monitorar o cluster de Kubernetes, definindo alertas importantes.
- Monitorar a aplicação dentro do cluster de Kubernetes.
- Criar dashboards que mostrem o estado da aplicação e do cluster.
