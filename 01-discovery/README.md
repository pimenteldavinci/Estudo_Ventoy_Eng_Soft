## 3.1 Caracterização do Software

O **Ventoy** é um software livre que permite criar unidades USB inicializáveis a partir de arquivos nos formatos ISO, WIM, IMG, VHD(x) e EFI. Uma de suas principais vantagens é dispensar a necessidade de formatar o dispositivo USB repetidamente para adicionar novos sistemas operacionais. Basta copiar os arquivos desejados para o dispositivo, organizá-los em diferentes pastas e inicializar o computador por meio dele. Durante a inicialização, o Ventoy apresenta um menu com os arquivos disponíveis, permitindo que o usuário selecione qual deseja executar.

O software é direcionado principalmente a estudantes e profissionais da área de Tecnologia da Informação, técnicos de suporte e usuários que realizam instalações, formatações e manutenções de computadores com frequência. Também é útil para pessoas que desejam testar diferentes sistemas operacionais, como distribuições Linux e versões do Windows.

Entre suas principais funcionalidades, destacam-se:

- Criação de unidades USB inicializáveis a partir de arquivos ISO, WIM, IMG, VHD(x) e EFI;
- Suporte à instalação automatizada de sistemas operacionais Linux e Windows;
- Criação de dispositivos multiboot, permitindo armazenar e inicializar diferentes sistemas operacionais em um único dispositivo USB.

Em relação às tecnologias utilizadas, o Ventoy é desenvolvido principalmente em **C**, mas também utiliza outras linguagens e tecnologias, como Shell Script, HTML, JavaScript e C++. Esses recursos são empregados em diferentes componentes do software, incluindo funcionalidades de inicialização, scripts de gerenciamento e interfaces gráficas.

Por se tratar de um software livre e de código aberto, o Ventoy é distribuído sob a licença **GPLv3 (GNU General Public License, versão 3)**.

A versão utilizada como referência nesta análise é a **1.1.18**, considerada a versão mais recente no período de elaboração deste trabalho.

---

## 3.2 Personas e Jobs to Be Done (JTBD)

### Persona 1 — Karthikgone

O usuário Karthikgone realiza instalações dos sistemas operacionais Windows 10 e Windows 11 em computadores com diferentes configurações de hardware, tanto antigos quanto modernos.

Durante o processo de instalação, ele precisa localizar os dispositivos de armazenamento, como HDs e SSDs, para selecionar o local adequado onde o sistema operacional será instalado. Entretanto, em determinadas situações, após a instalação e a reinicialização do computador, o dispositivo USB com o Ventoy não é reconhecido corretamente, fazendo com que a máquina inicialize diretamente no carregamento de drivers.

**Job to Be Done (JTBD):**

Quando estou instalando o Windows em computadores com diferentes configurações de hardware, quero conseguir acessar facilmente os drivers de armazenamento pelo Ventoy, para realizar as instalações sem precisar procurar arquivos manualmente em outros dispositivos.

**Link da discussão:** [Persona 1 — Karthikgone](https://github.com/ventoy/Ventoy/discussions/3722)

### Persona 2 — wlatendresse

O usuário wlatendresse utiliza o Ventoy para experimentar diferentes distribuições Linux, seja para conhecer o estado atual dos sistemas operacionais ou para buscar inspiração para personalizar seu próprio ambiente de trabalho.

Apesar de considerar o Ventoy uma ferramenta útil para essa finalidade, o usuário gostaria de contar com uma funcionalidade que permitisse visualizar arquivos de texto diretamente pelo software. Isso seria especialmente útil porque algumas distribuições possuem nomes de usuário e senhas específicos, informações que podem ser difíceis de memorizar quando se utilizam diversos sistemas operacionais.

Dessa forma, a possibilidade de armazenar arquivos de texto no próprio dispositivo USB e consultá-los sem precisar inicializar uma imagem ISO facilitaria o acesso a essas informações.

**Job to Be Done (JTBD):**

Quando estou experimentando diferentes distribuições Linux pelo Ventoy e preciso consultar informações específicas de cada sistema, como nomes de usuário e senhas, quero visualizar arquivos de texto armazenados no pen drive sem precisar inicializar a imagem ISO, para acessar essas informações rapidamente e facilitar a utilização de diferentes sistemas operacionais.

**Link da discussão:** [Persona 2 — wlatendresse](https://github.com/ventoy/Ventoy/discussions/3698)

---

## 3.3 Análise de Issues, Pull Requests e Commits

### Issue — Suporte à inicialização da imagem de recuperação do Steam Deck

**Descrição do problema:**

Um usuário relatou que não conseguia inicializar corretamente o arquivo de recuperação do Steam Deck (SteamOS) utilizando o Ventoy. Ao adicionar a imagem de recuperação ao dispositivo USB e tentar inicializá-la no console, o processo apresentava erros e não carregava o ambiente de recuperação adequadamente.

Posteriormente, foi sugerida a implementação de suporte específico para a inicialização das imagens de recuperação do SteamOS Holo.

A partir dessa solicitação, foram realizadas otimizações e implementações no software para possibilitar a compatibilidade com esse tipo de imagem. A melhoria foi incorporada ao projeto e disponibilizada na versão 1.1.18.

Esse caso demonstra como a identificação de problemas pelos usuários e as sugestões da comunidade podem contribuir diretamente para a evolução e ampliação da compatibilidade do software.

**Link da Issue:** [Issue #2875 — Ventoy](https://github.com/ventoy/Ventoy/issues/2875)

### Commit — Suporte às imagens de recuperação do SteamOS

Na versão 1.1.18, foi incorporado suporte às imagens de recuperação do SteamOS, permitindo ampliar a compatibilidade do Ventoy com dispositivos como o Steam Deck.

Essa implementação demonstra a importância da participação da comunidade na evolução do projeto, uma vez que problemas identificados pelos usuários podem resultar em melhorias concretas no software.

**Link do Commit:** [Suporte às imagens de recuperação do SteamOS](https://github.com/ventoy/Ventoy/commit/029a0a9d19eWJh8J6Mx9DrGXKEv3ojKmqw8Cv9pscK)

### Mudança Arquitetural — Suporte ao estilo de partição GPT (versão 1.0.15)

Na versão 1.0.15, o Ventoy passou a oferecer suporte à instalação utilizando o estilo de partição GPT (*GUID Partition Table*).

Essa implementação ampliou a compatibilidade do software com computadores modernos que utilizam firmware UEFI. Além disso, possibilitou a utilização de recursos associados a esse ambiente de inicialização, como o Secure Boot, desde que atendidos os requisitos de configuração necessários.

Essa mudança representa uma evolução importante na arquitetura do software, pois ampliou as possibilidades de instalação e inicialização do Ventoy em diferentes configurações de hardware.

**Documentação:** [Ventoy — Disk Layout GPT](https://www.ventoy.net/en/doc_disk_layout_gpt.html)

### Evolução da Interface Gráfica — VentoyWeb (versão 1.0.36)

Na versão 1.0.36, foi introduzida a interface gráfica VentoyWeb, desenvolvida para facilitar a instalação e o gerenciamento do Ventoy em ambientes Linux.

Até então, essas operações eram realizadas principalmente por meio da linha de comando, utilizando o script `Ventoy2Disk.sh`. Com a introdução do VentoyWeb, passou a ser possível acessar uma interface gráfica por meio de um navegador, utilizando um servidor HTTP local iniciado pelo script `VentoyWeb.sh`.

Essa implementação simplificou o processo de instalação e configuração de dispositivos USB inicializáveis no Linux, aproximando a experiência de utilização daquela já oferecida pela ferramenta gráfica disponível para Windows, o `Ventoy2Disk.exe`.

**Documentação:** [Ventoy — Linux WebUI](https://www.ventoy.net/en/doc_linux_webui.html)
