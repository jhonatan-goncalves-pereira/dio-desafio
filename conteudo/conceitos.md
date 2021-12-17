## Teoria
# Conceitos
### -SHA1 (SECURE HASH ALGORITHM)
- ALGORITMO DE ENCRIPTAÇÃO
- CONJUNTO DE ALGORITMOS HASH
- GERAM  PELA ENCRIPTAÇÃO UM CONJUNTO DE CARACTERES  DE 40 DÍGITOS(É ÚNICO)

>> uma mínima alteração no arquivo também gera uma alteração na chave de 40 CARACTERES
- Ao desfazer a altteração se tem a mesma chave.
- Verifique se o arquivo sofreu ou não alterações

## OBJETOS FUNDAMENTAIS todos possuem um sha1
### bloobs blob 9\0(bloco que contém metadados (tamanhos, string, etc))
- são arquivos
- usa o git para ver a chave e o outro usa o openssl e sha1 do git

echo 'content' | git hash-object --stdin
echo 'blob 9\0content' | openssl sha1
    
### trees (aramzena blobs) + aramzena do nome do arquivo

- commints(junta tudo) apontaa para uma tree, parente, autor, mensagem e otimestamp
- monta uma linha do tempo

## -SISTEMA DISTRIBUÍDO
- = meu código no repositório estará distribuído
- = e seguro porque todos estão 
- SEGURANÇA


## CHAVE SSH
   - ESTABELECE UMA CONEXÃO SEGURA E ENCRIPTADA 
   - FAZEMOS ISSO E O GITHUB RECONHECE A NOSSA MÁQUINA
   - ENVIA CÓDIGO SEM NEM PRECISAR COLOCAR SENHA
    ### PARA ISSO
    - configure no github para reconhecer a máquina a partir de um título e uma chave pARA MÁQUINA,
    - no bash vc faz:
    
    - gera sua chave no computador
     ssh-keygen -t ed25519 -C seuemail@dominio.com
    - depois você entra no diretório
     cd  .ssh
    - copia o conteúdo da chave.pub
     cat id_ed25519.pub
    cola a saída no campo chave SSH lá no Github

    - volta no bash e inicializa o ssh e digita
        eval $(ssh-agent -s)    
    - sai o pid e indica que iniciou o processo

    - adiciona a chave privada para o agente
        ssh-add id_ed25519 

    - clone o projeto pelo SSH
        git clone git@github.com:user/repositorio.git 


