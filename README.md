<h1>Download</h1>
<p>Basta entrar no link, escolher sua plataforma e clicar em download.</p>
<a href="https://www.soapui.org/downloads/latest-release/" target="_blank">https://www.soapui.org/downloads/latest-release/</a>

<h1 style="margin-top: 15px;">Instalação</h1>
<p>Após executar o arquivo baixado continue clicando em next até finalizar a instalação.</p>

<h1 style="margin-top: 15px;">Importando o projeto</h1>
<ul>
    <li>Com o SoapUI aberto, clique em File -> Import Project.</li>
    <li>Navegue até a pasta onde está o arquivo Trabalho_S206.xml e selecione este arquivo.</li>
</ul>

<h1 style="margin-top: 15px;">Testando Endpoints</h1>
<p>Caso queira testar algum endpoint das APIs que já estão importadas, basta seguir o seguinte padrão:</p>
<p>Para enviar uma requisicao para o consultaCEP dos correios por exemplo, expanda a api com o nome AtendeClienteServiceSoapBinding, em seguida expanda consultaCEP, dê dois cliques em Request 1 e uma janela de requisição soap vai abrir. </p>
<p>Podemos alterar os parâmetros da requisição nas propriedades que possuem o comentário < !--Optional:-- >. Assim, basta inserir o CEP que se deseja fazer a consulta entre a tag < cep > e clicar no botão verde no canto superior esquerdo da janela.</p>

<h1 style="margin-top: 15px;">Importando diferentes APIs Soap com WSDL</h1>
<p>Para testar alguma outra API de sua preferencia, tenha em sua posse o arquivo wsdl desta api. Então clique com o botao direito no nome do projeto e depois em add WSDL, se tiver o endereço do arquivo wsdl basta colar na janela que vai abrir, caso tenha o arquivo, clique em Browse e navegue até este arquivo. Clique em ok e os metodos serão carregados e estarão prontos.</p>

<h1 style="margin-top: 15px;">Exportando relatorios HTML (necessario ter JDK instalado)</h1>
<h2>Instalando Apache Ant</h2>
<ol>
    <li>Precisamos primeiramente ter o JDK instalado e o JAVA_HOME configurada como variável de ambiente do sistema</li>
    <li>Entre no link https://ant.apache.org/bindownload.cgie baixe a versao release (no nosso caso utilizamos 1.9.16. Extraia o conteudo para a pasta root do seu disco principal. Ex: C:\apache-ant-1.9.16</li>
    <li>Adicionar variavel de ambiente ANT_HOME: Procure a opcao "editar variaveis de ambiente do sistema" no painel de controle, clique em Variáveis de ambiente, no bloco de baixo clique em new. No campo nome da variavel digite ANT_HOME e em valor da variavel informe o diretorio onde o apache ant foi extraído. No nosso caso esse valor ficou "C:\apache-ant-1.9.16"</li>
    <li>Atualizar PATH - Procure e selecione a variável Path nas Variáveis do sistema e clique em Editar, clique no botao NOVO e digite o mesmo valor do diretorio anterior com \bin no final. Exemplo: C:\apache-ant-1.9.16\bin</li>
    <li>Verificando a instalacao - Abra o prompt de comando e digite: ant -version</li>
</ol>

<h1 style="margin-top: 15px;">Criando um script Build</h1>
<p>Precisamos de um arquivo Build para informar ao ant as definicoes do nosso projeto para que ele construa o html dos nossos testes, para isso baixe o arquivo build.xml e também o arquivo Trabalho_S206 e salve na seguinte pasta: C:\SoapUIWorkspace.</p>
<p>Este arquivo Build possui alguns valores que precisam estar de acordo com o seu ambiente, altere os campos soapui.project, soapui.home e results.dir para ficar compatível com o seu ambiente.</p>

<h1 style="margin-top: 15px;">Gerando os testes em HTML</h1>
<p>Abra o prompt de comando e navegue até C:\SoapUIWorkspace, em seguida dê o seguinte comando: ant</p>
<p>O relatório será salvo na pasta especificada no arquivo build na propriedade reports.dir</p>