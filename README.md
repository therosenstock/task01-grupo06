# Comandos Git
<h2> Git Rebase </h2> 
Serve para integrar alterações de uma branch para outra.
Processe de mover ou combinar uma sequência de commits para um novo commit base.
O rebase muda a base do seu branch de um commit para outro, fazendo parecer que o seu branch foi criado a partir de um commit diferente.
Importante entender que apesar de parecer o mesmo branch, ele é composto de commits novos.
<h3>Uso</h3>
Usado para manter um histórico de projeto de maneira linear. Exemplo: se você está trabalhando em um branch alternativo, e o seu branch principal progrediu; então você deseja obter informações mais recentes da principal em sua branch, desejando manter o histórico de sua ramificação limpo, parecendo que está trabalhando na principal. Oferece o benefício posterior de uma mesclagem mais limpa na sua branch. Manter essa "história limpa" tem como benefício de tornar tangível ao executar operações do Git para investigar a introdução de uma regressão.
 <h3>Git rebase Standard e Git Rebase Interactive</h3>
 Git rebase interativo é quando o git rebase aceita argumentos. Sem nenhum argumento é executado no modo padrão.

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

Aplique as alterações introduzidas por alguns commits existentes

* ### Uso
Esse comando é usado quando mais de uma pessoa está trabalhando em branchs
que possuem relações, caso um encontre um problema e a corrija porém sua task
ainda entá em andamento, podemos buscar na branch do colega por meio do git log
o id do commit necessário e aplicalo com cherry pie.

>git cherry-pick <*id do commit necessário*>