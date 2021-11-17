# Dicas Git/Hub



[Tutorial feito por Letícia Santos](https://digitalinnovation.one/artigos/dicas-git-e-github)



Nesse pequeno tutorial vou colocar algumas dicas que super funcionam no Git quando você está usando o GitHub.

Lembrando que a intenção foi fazer em uma linguagem fácil e sem muito termo  técnico, além de é claro ser feito por uma iniciante e todas as  recomendações de alteração/melhoria são válidas e muito bem vindas!

Não esqueçam de criar o repositório no GitHub antes de seguir esse passo a passo hein!

Primeiro vou colocar os comandos úteis:

1. **git init** = iniciar o monitoramento git
2. **git remote add origin** = só diz para o repositório local o endereço do repositório remoto
3. **git add** = adiciona as alterações de arquivo no git uma por uma
4. **git add .** = adiciona todas as alterações que você fez
5. **git status** = mostra o status do arquivo que você está trabalhando
6. **git commit -m “[seu comentário]”** = faz o commit das alterações que você fez e possibilita colocar um comentário
7. **git push -u origin master** = você empurra as suas alterações para seu repositório remoto

Agora vamos ao passo a passo usando o git clone ao invés de git init:

1. **git clone [url do seu repositório]** = cria uma cópia local do seu repositório remoto já sendo monitorada pelo git
2. **git add** = adiciona as alterações de arquivo no git uma por uma
3. **git add .** = adiciona todas as alterações de arquivo no git
4. **git status** = mostra o status do arquivo que você está trabalhando
5. **git commit -m “[seu comentário]”** = faz o commit das alterações que você fez e possibilita colocar um comentário
6. **git push -u origin master** = você empurra as suas alterações para seu repositório remoto

A diferença entre o processo 1 e o processo 2 como vocês puderam perceber é que no processo 2 não precisamos dar o git init para iniciar o  monitoramento da pasta, o próprio git clone já faz isso.

Mas Letícia, eu quero parar o monitoramento local da minha pasta, como eu faço?

Bem simples, você vai usar o comando:

1. **rm -Rf .git**

Esse comando vai fazer com que a pasta .git seja apagada e o monitoramento seja parado

Letícia, fiz um commit errado e dei push, o que eu faço pra ele sair do meu GitHub?

Vamos lá:

1. **git reset HEAD^** = vai falar para o repositório que você quer apagar o último commit que você fez do GitHub
2. **git push -f** = faz o GitHub dar o push e forçar esse “apagão” do commit

Legal Letícia mas não é o último commit que eu quero apagar, e agora?

1. **git reset --hard [hash do commit]** = aqui você precisa ter o hash (ID) do commit que você deu errado para conseguir reverter aquele commit
2. **git push -f** = você força o push do commit que você quer excluir

“Lê, não quero apagar o commit do github só quero reverter para o anterior”

Tranquilo, só usar o:

1. **git revert [hash do commit]** = você não perde o histórico de commit no git e faz um novo commit voltando para as configurações anteriores

Letícia, deu fetch aqui, o que eu faço?

Relaxa que está tudo certo, você vai fazer o seguinte

1. **rm -Rf .git** = apaga sua pasta .git
2. **git clone [url do seu repositório]** = cria uma cópia local do seu repositório remoto já sendo monitorada pelo git
3. **git add .** = adiciona todas as alterações de arquivo no git
4. **git status** = mostra o status do arquivo que você está trabalhando
5. **git commit -m “[seu comentário]”** = faz o commit das alterações que você fez e possibilita colocar um comentário
6. **git pull origin master --rebase** = você junta as alterações em uma só
7. **git push -u origin master** = você empurra as suas alterações para seu repositório remoto

Letícia, muito obrigada, aqui funcionou mas me explica o que o rebase fez?

Claro!

O rebase junta o que está no seu computador com o que está no seu repositório.

Quando da esse erro, ele entendeu que a sua master do git está com alguma  coisa diferente da que ta na sua máquina e não consegue fazer o push.

É tipo quando você está comendo dois chocolates, você dá uma mordida em  um e dá uma mordida no outro depois quer juntar os dois porque com uma  barra só fica muito melhor de comer. Você usa o rebase e pronto, estão  juntos em um chocolate só