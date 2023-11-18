# portatreko_v2
Sistema web simples de compartilhamento e guarda de arquivos - Versão 2

PortaTreko: um sistema simples de compartilhamento e armazenamento de arquivos diversos.
Notas da Versão 2 - PortaTreko

Notas de Atualização para a versão 2

O sistema foi atualizado com dois recursos que podem ser úteis:
Compartilhamento de arquivos para uma área pública e comum
Listagem de todos os arquivos do usuário logado e/ou da área comum/compartilhada

Os diretórios adicionados para a área compartilhada está dentro do raiz do sistema:
portatreko_publico/uploads/compartilhados

As configurações dos diretórios para compatilhamentos estão no arquivo config.php
Acesse e ajuste conforme seu ambiente.
Um detalhe sobre a questão de compartilhamento dos arquivos é sobre o uso 
de caminhos absolutos dos diretórios. Talvez funcione com caminhos relativos,
mas não termineis os testes. Talvez numa futura versão.

O diretório portatreko_publico/uploads/compartilhados deve ter permissão de escrita de todos, sendo 777.
Isso deve ser o suficiente para permitir qualquer usuário logado a compartilhar seus arquivos para esse local

Foi adicionado também uma listagem de todos os arquivos do usuário e da área pública.

Autor: Mario Medeiros
Site: https://www.mariomedeiros.eti.br
GitHub: https://github.com/lowcypher
Data: 2023-11-15
Versão: 2.0

Pode ser alterado e redistribuído. Mencione os devidos créditos.
Licença: GPL V3 e Creative Commons V4 CC-BY

#################################################
Notas da primeira versão  - versão 0.2

Este sistema tem como premissa a simples organização, armazenamento e compartilhamento de arquivos em uma pequena rede local.
Não pretende substituir nenhum sistema robusto como um Owncloud ou um sistema baseado em SMB ou SAMBA.

Serve como uma solução rápida e ágil de repositório de arquivos para distribuir entre usuários da rede.

Esclarecido isso, vamos às descrições básicas do sistema.

Escrito em PHP (backend), HTML5 e Bootstrap (frontend) esse sistema não utiliza bancos de dados para armazenar arquivos.
Necessário um webserver configurado para rodar PHP. Utilizei o Apache Server version: Apache/2.4.56 (Debian) e PHP 7.4 em Debian.

O sistema grava os arquivos em diretórios do webserver.
Descompacte o pacote sistema_portatreko_v2.zip num diretório do seu webserver. Dê as permissões necessárias aos diretórios.
No meu caso, utilizo user_dir do Apache e atribuí aos diretórios permissões 755. Para que possa ter acesso de gravação
no diretório uploads, no meu caso eu atribui permissão 777. Talvez seja somente isso, que no meu caso funcionaou bem.

Esse sistema é divido em duas partes, por assim dizer.
Primeira é que pode ter área de usuário com login e senha. 
Não existe nenhum usuário cadastrado no sistema. Registre um. 

Ao registrar um usuário, o script cria um diretório exclusivo desse novo usuário e faz uma cópia do sistema completo do PortaTreko.
Toda vez que o usuário se logar, será redirecionado para seu espaço. Será criado um espaço para cada usuário.

Os logins e senhas estarão gravados no arquivo padrão CSV. É o arquivo .users e este arquivo como pode ver, é oculto e sem extensão.
Um mínimo de segurança, que sim é vulnerável, mas como eu disse, é um sistema simples para soluções rápidas para pequenos ambientes.
Lembre-se disso. Se isso não lhe atende, não o use. Simples assim.

Existe a segunda parte do sistema que é a parte de arquivos públicos. Aqui não é necessário ter login no sistema. Se precisar compartilhar 
arquivos, é só adicionar e pronto. Ficarão todos num mesmo local. Para acesso aberto na rede.

Fiz alguns ajustes nos arquivos PHP utilizando session para poder limitar o acesso somente com usuário logado.
Pode não funcionar perfeitamente, uma vez que não tem os usuários registrados em banco de dados e não está implementado ainda formas mais agressivas de segurançs.

Isto é o que o sistema se propõe. 

Autor: Mario Medeiros
Site: https://www.mariomedeiros.eti.br
Data: 2023-11-03
Versão: 0.2

Pode ser alterado e redistribuído. Mencione os devidos créditos.
Licença: GPL V3 e Creative Commons V4 CC-BY
