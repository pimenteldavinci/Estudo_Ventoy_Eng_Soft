O Ventoy é um software livre que permite a criação de unidades USB para arquivos ISO/WIM/IMG/VHD(x)/EFI. Com o Ventoy, você não precisa formatar o disco repetidamente; basta arrastar e soltar os arquivos na unidade USB e inicializá-los diretamente, podendo copiar vários arquivos para pastas diferentes e o software irá exibir um menu de inicialização para selecioná-los. O software é direcionado para o uso de estudantes, profissionais da área de T.I e usuários que necessitam formatar a sua máquina ou que formatam regularmente. O software é indicado para pessoas que realizam reparos regularmente, que possam necessitar o teste de diferentes sistemas operacionais, como Linux, Windows, etc.
Suas principais funcionalidades são: 
* a criação de unidades de imagem, como ISO/WIM/IMG/VHD(x)/EFI;
* suporte a instalação automatizada para Linux e Windows;
* criar um dispositivo multiboot.
As tecnologias utilizadas no Ventoy são, principalmente, em C. Também é utilizado Shell, HTML, Java Script, C++. Essas tecnologias são utilizadas para interface gráfica.
Por ser um software livre, o Ventoy utiliza a licença GPLv3 (GNU General Public License v.3.0).
A versão que estaremos analisando é a 1.1.18 (versão mais recente até o presente momento).

Personas e JTBD
Persona 1: Karthikgone 
O usuário Karthikgone é uma pessoa que instala windows 10 e 11 para computadores antigos e modernos. Enquanto ele faz a instalação, é necessário procurar o local em que será instalado o SO, seja HD ou SSD e em algumas situações, depois de instalar e reiniciar a máquina, não apareceu o pendrive com o Ventoy e foi direto para o carregamento de drivers.
Job to be done (JTBD) - Quando estou instalando Windows em computadores com diferentes configurações de hardware, quero conseguir acessar facilmente meus drivers de armazenamento pelo Ventoy, para realizar as instalações sem precisar procurar arquivos manualmente em outros dispositivos.
Link persona 1: https://github.com/ventoy/Ventoy/discussions/3722

Persona 2: wlatendresse
wlatendresse é um usuário que está experimentando outras distribuições de Linux, seja para estar mais informado a respeito do estado atual dos SO ou para servir como inspiração, incluindo ideias para customizar o próprio desktop. O Ventoy é de grande ajuda para isso, entretanto, ele gostaria de que houvesse um simples texto que mostre qualquer arquivo de texto, pois muitas distribuições possuem nomes e senhas específicas. Para ele, é impossível lembrar de todas elas, então se tivesse um arquivo de texto que armazena todas essas informações junto com a imagem seria melhor.
Job to be done (JTBD) -  Quando estou experimentando diferentes distribuições Linux pelo Ventoy e preciso consultar informações específicas de cada sistema, como nomes de usuário e senhas, quero visualizar arquivos de texto armazenados no pendrive sem precisar inicializar a imagem ISO, para que eu consiga acessar essas informações rapidamente e facilitar a utilização de diferentes sistemas operacionais.
link persona 2: https://github.com/ventoy/Ventoy/discussions/3698.

Issue: Não é possível inicializar o arquivo de recuperação de imagem do Steam Deck pelo Ventoy.
Descrição do problema: Um usuário (https://github.com/ventoy/Ventoy/issues/2875) relatou que ao colocar o arquivo de recuperação de imagem do Steam Deck (SteamOS) no drive Ventoy, não carrega apropriadamente e gera um erro quando o drive é conectado e inicializado no console.
Posteriormente foi sugerido por um desenvolvedor a implementação de um suporte para inicialização de arquivos de recuperação de imagens do SteamOS Holo. 
Então, um responsável pelo Ventoy realizou algumas otimizações e implementou a mudança no software na versão 1.1.18, caracterizando essa ação como um Pull Request.

Commits da versão 1.1.18: Suporte de recuperação de imagens para SteamOS. Isso significa que a comunidade está trazendo o Ventoy para outras plataformas, como é o caso do console Steam Deck que utiliza SteamOS.
https://github.com/ventoy/Ventoy/commit/029a0a9d19eWJh8J6Mx9DrGXKEv3ojKmqw8Cv9pscK.

Mudança arquitetural na versão 1.0.15, agora era possível instalar o Ventoy usando o estilo de partição com GPT (GUID Partition Table). Isso serve para garantir compatibilidade com placas-mãe modernas que usam o firmware UEFI e recursos como o Secure Boot.
https://www.ventoy.net/en/doc_disk_layout_gpt.html

Na versão do Software 1.0.36, houve a introdução da interface gráfica (GUI) chamada VentoyWeb. A interface é baseada em um navegador web voltado para o Sistema Operacional Linux. Até o lançamento da versão 1.0.36, a instalação e gerenciamento do Ventoy no ambiente Linux era somente através da linha de comando Ventoy2Disk.sh. A partir dessa versão, foi disponibilizado o servidor HTTP local (VentoyWeb.sh), que permite o acesso para a interface gráfica pelo navegador, simplificando o processo de instalação e configuração de mídias bootáveis no Linux mais simplificado, semelhante ao utilizado no Windows Ventoy2Disk.exe.
https://www.ventoy.net/en/doc_linux_webui.html
