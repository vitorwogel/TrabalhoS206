Importando o projeto
Com o SoapUI aberto, clique em File -> Import Project.
Navegue até a pasta onde está o arquivo Trabalho_S206.xml e selecione este arquivo.

Testando Endpoints
Caso queira testar algum endpoint das APIs que já estão importadas, basta seguir o seguinte padrão:
Para enviar uma requisicao para o consultaCEP dos correios por exemplo, expanda a api com o nome AtendeClienteServiceSoapBinding, em seguida expanda consultaCEP, dê dois cliques em Request 1 e uma janela de requisição soap vai abrir. 
Podemos alterar os parâmetros da requisição nas propriedades que possuem o comentário <!--Optional:-->. Assim, basta inserir o CEP que se deseja fazer a consulta entre a tag <cep> e clicar no botão verde no canto superior esquerdo da janela.

Importando diferentes APIs Soap com WSDL
Para testar alguma outra API de sua preferencia, tenha em sua posse o arquivo wsdl desta api. Então clique com o botao direito no nome do projeto e depois em add WSDL, se tiver o endereço do arquivo wsdl basta colar na janela que vai abrir, caso tenha o arquivo, clique em Browse e navegue até este arquivo. Clique em ok e os metodos serão carregados e estarão prontos.

Exportando relatorios HTML (necessario ter JDK instalado)
Instalando Apache Ant
1 - Precisamos primeiramente ter o JDK instalado e o JAVA_HOME configurada como variável de ambiente do sistema
2 - Entre no link https://ant.apache.org/bindownload.cgie baixe a versao release (no nosso caso utilizamos 1.9.16. Extraia o conteudo para a pasta root do seu disco principal. Ex: C:\apache-ant-1.9.16
3 - Adicionar variavel de ambiente ANT_HOME: Procure a opcao "editar variaveis de ambiente do sistema" no painel de controle, clique em Variáveis de ambiente, no bloco de baixo clique em new. No campo nome da variavel digite ANT_HOME e em valor da variavel informe o diretorio onde o apache ant foi extraído. No nosso caso esse valor ficou "C:\apache-ant-1.9.16"
4 - Atualizar PATH - Procure e selecione a variável Path nas Variáveis do sistema e clique em Editar, clique no botao NOVO e digite o mesmo valor do diretorio anterior com \bin no final. Exemplo: C:\apache-ant-1.9.16\bin
5 - Verificando a instalacao - Abra o prompt de comando e digite: ant -version

Criando um script Build
Precisamos de um arquivo Build para informar ao ant as definicoes do nosso projeto para que ele construa o html dos nossos testes, para isso baixe o arquivo build.xml e também o arquivo Trabalho_S206 e salve na seguinte pasta: C:\SoapUIWorkspace.
Este arquivo Build possui alguns valores que precisam estar de acordo com o seu ambiente, altere os campos soapui.project, soapui.home e results.dir para ficar compatível com o seu ambiente.

Gerando os testes em HTML
Abra o prompt de comando e navegue até C:\SoapUIWorkspace, em seguida dê o seguinte comando: ant
O relatório será salvo na pasta especificada no arquivo build na propriedade reports.dir