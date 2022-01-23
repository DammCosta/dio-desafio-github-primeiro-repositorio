# Entenda o que é Git e sua importância
Sempre que estou aprendendo uma tecnologia nova eu respondo um questionamento!
Por quê?
Porque estou aprendendo sobre essa tecnologia e porque ela é relevante na minha carreira.



> Vamos aprender:
>
> - Controle de Versão 
> - Armazenamento em nuvem
> - Trabalho em equipe
> - Melhorar seu código
> - Reconhecimento

> O que vamos aprender?
>
> - Mudar de pastas
> - Listar as pastas
> - Criar pastas/arquivos
> - Deletar pastas/arquivos



### Entenda como o GIT funciona por baixo dos panos

- SHA1: A sigla SHA significa Secure Hash Algorithm (Algoritmo de Hash Seguro), é um conjunto de funções hash criptográficas 
  projetadas pela NSA (Agência de Segurança Nacional dos EUA).
  A encriptação gera conjunto de caracteres identificador de 40 dígitos.
- Objetos fundamentais
  BLOBS
- TREES
  A Trees armazenam bloobs e aponta para tipos de bloobs diferentes
  O Bloob não guarda o nome do arquivo, ele guarda o sha1 e só, enquanto o tree é responsável por montar toda a estrutura de 
  onde então os arquivos, ela pode apontar tanto para os bloobs quanto outras trees.
  As trees também possuem um sha1 deste metadado
- COMMITS
  Commit é o objeto que vai juntar tudo, vai dar sentido para a alteração que está sendo feita
  O commit aposta para uma árvore ela aponta para “parente”, ou seja, aponta para o último commit realizado antes dele, 
  o commit aponta para um autor e aponta para uma mensagem também
  Os commits também possuem um sha1
- sistema distribuído e seguro
  Todos que possuem o código, possuem um "cópia" do commit / arquivo. Ou seja, caso a rede do Git caia, vão existir 
  diversas cópias idênticas a do servidor que possuem um alto nível de segurança. 
- Chaves SSH e Tokens
  Chaves SSH - é uma forma estabelecer uma forma segura e encriptada entre duas máquinas. Vamos conectar nossa máquina 
  ao GITHUB e demonstrar que minha máquina é segura


Passa a passo no ciclo de vida



Untracked - Git não tem ciência dos arquivos
Tracked - Git tem conhecimento dos arquivos

- Unmodifed - arquivo não foi modificado ainda
- Modified - arquivo modificado
- Staged - está trabalhando por trás das cortinas ou que estão se preparando para poder fazer parte de outro tipo de agrupamento
  - Os arquivos que estão em Staged, eles estão se preparando para fazer parte de um commit, ou seja, envelopa todas as 
    modificações com significância. Esse commit carrega um autor, uma data. Assim eles deixam de ser um Staged e passam a ser commit.

* Depois de dar um commit no arquivo staged, o commit retorna esse arquivo para Unmodified. Pq ele retorna para Unmodified? 
  Pq ele fala que acabou de fazer as alterações no arquivo e vai salvá-los e criar um snapshot (uma foto do momento, para saber como ele está naquele ponto). 
  O ciclo sempre se repete entre Unmodifed, Modified, Staged - commit e volta para Unmodifed.

Git init


_Quando faço o commit as alterações passam a fazer parte do repository. Do local posso mandar para o repository no servidor_.

O repositório local só é composto por commit, caso contrário não é possível enviar para o ambiente remoto.



Eu adicionei o arquivo, e depois commitei e olhei o status por último. 

### Como resolvemos conflitos
Quando  estiver trabalhando em um arquivo e tentar empurrar (enviar) para o GITHUB e o mesmo for rejeitado por ter uma 
alteração no github que não tem no arquivo q estou trabalhando. Quando houver essa divergência, o git vai apresentar a seguinte mensagem:



#### Quando isso acontecer eu tenho que integrar os dois arquivos para depois tentar enviar novamente para o github.

1. _Puxar o arquivo_ que está no _github e diverge do arquivo que possuo_ em máquina __git pull origin master__ 

2. Depois de baixar o arquivo, vou abrir ele no Typora (pq é um arquivo .md) para ver o que está de diferente do arquivo no 
   github para o que está na minha máquina. Para uma melhor visualização vou copiar o conteúdo do arquivo do Typora e vou colar em um novo arquivo no bloco de notas.
   No bloco de notas eu consigo ver mais detalhado as alteração. O <<<< HEAD mostra a última alteração que eu fiz, 
   as linhas (== =) mostram a divisão do que eu alterei para o arquivo que outra pessoa alterou, ou seja, o que está abaixo das linhas foi alterado por outra pessoa.

3. Após verificar as divergências, vou fazer as devidas alterações e salvar o arquivo.

4. Após salvar o arquivo, volto no GIT, vou dar o comando __git status__, o git vai mostrar que o arquivo foi alterado e 
   depois vamos commitar o arquivo novamente com os seguintes comandos: __git add *__ para adicionar o arquivo para a área 
   de staged depois __git commit -m “resolve conflitos”__ para dar o commit e por último vou empurrar para o github com o comando __git push oringin master__ 

Baixar uma cópia de um repositório que está no github para o meu repositório local.
Vou entrar em um repositório, vou em “code” e copiar a URL “https:// …”


Vou para o git em workspace e vou passar o seguinte comando __git clone https:// …(restante do caminho)__. Logo após este comando eu clonei o arquivo para minha pasta.
