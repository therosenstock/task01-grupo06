# Comandos Git
<h2> Git Rebase </h2> 
Serve para integrar alterações de uma branch para outra, no processo de mover ou combinar uma sequência de commits para um novo commit base.
O rebase muda a base do seu branch de um commit para outro, fazendo parecer que o seu branch foi criado a partir de um commit diferente.
Importante entender que apesar de parecer o mesmo branch, ele é composto de commits novos.

<h3>Uso</h3>

Usado para manter um histórico de projeto de maneira linear. Exemplo: se você está trabalhando em um branch alternativo, e o seu branch principal progrediu, então você deseja obter informações mais recentes da principal em sua branch, desejando manter o histórico de sua ramificação limpo, parecendo que está trabalhando na principal. Oferece o benefício posterior de uma mesclagem mais limpa na sua branch. Manter essa "história limpa" tem como benefício de tornar tangível ao executar operações do Git para investigar a introdução de uma regressão.
 <h3>Git Rebase Standard e Git Rebase Interactive</h3>
 Git rebase interativo é quando o git rebase aceita argumentos. Sem nenhum argumento é executado no modo padrão.
 <p>

 > git checkout -b new_feature
 > git commit -am "add new feature"

Git rebase padrão automaticamente pegará os commits em seu branch atual e os aplicará ao head do branch passado.
> git rebase <base>

Isso rebaseia automaticamente o branch atual para < base >, pode ser qualquer tipo de referência de confirmação ( por exemplo, um ID, um nome de brach, tag ou referência relativa a HEAD ).

>git rebase --interactive < base >
Isso rebaseia o branch atual, mas usa uma sessão de rebase interativa. Isso abre um editor onde você pode inserie comandos para cada commit a ser rebaseado. Isso determina como os commits individuais serão transferidos.

<h3>Comandos adicionais de rebase</h3>

* git rebase --d

* git rebase -- p

* git rebase -- x

## Git Cherry Pick

Aplica as alterações introduzidas por alguns commits existentes.

### Uso
Esse comando é usado quando mais de uma pessoa está trabalhando em branches relacionados. No caso, quando é encontrado um problema, corrigido e sua task ainda está em andamento, podemos buscar na branch do colega por meio do git log, o ID do commit neessário, para aplicá-lo com cherry pick.


>git cherry-pick <*id do commit necessário*>

## Git Revert

O comando git revert é usado no Git para desfazer um ou mais commits específicos. Ao contrário do git reset, que remove commits do histórico, o git revert cria um novo commit que reverte as alterações introduzidas pelos commits selecionados.

### Uso
Ao executar o comando git revert, o Git criará um novo commit que desfaz as alterações do commit selecionado. O novo commit terá a mensagem padrão informando que uma reversão foi aplicada.

>git revert <*commit*>

Aqui, <*commit*> representa o identificador do commit que você deseja reverter. Você também pode especificar vários commits separados por espaço para reverter vários commits em sequência.

Por exemplo, se você deseja reverter o commit com o identificador abc123, você pode executar o seguinte comando:

>git revert abc123

Após executar o comando, o Git criará um novo commit que desfaz as alterações introduzidas pelo commit abc123. Essa abordagem permite manter o histórico de commits intacto, enquanto registra a reversão das alterações.

## Git Squash

No Git, o termo squash é usado para compactar os commits anteriores em um só. Não é um comando, em vez disso, é uma palavra-chave. O squash é uma excelente técnica para mudanças específicas do grupo antes de encaminhá-las para os outros. Você pode mesclar vários commits em um único commit.

### Uso
* Uso o git log para ver os commits que tenho;

* Logo em seguida, uso: git rebase -i HEAD~2;

* Após isso será aberto um menu interativo para que eu decida o que irei fazer;

* Aperto a tecla i, apago o segundo pick e escrevo squash;

* aperto Esc e digito: ":wq";

* Escrevo a mensagem do novo commit.