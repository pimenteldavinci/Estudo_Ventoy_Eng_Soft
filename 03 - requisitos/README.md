**3. Requisitos do Software.**

**3.1 Requisitos Funcionais**

* O sistema deve permitir que o usuário instale vários arquivos de imagem para o SO em um disco USB.
<img src="../screen_uefi_en.png" alt="Tela UEFI" width="500">


* O sistema deve permitir que o usuário instale o Ventoy em diversos drivers USB.
Link: https://www.ventoy.net/en/index.html?utm_source=chatgpt.com
* O sistema deve permitir que seja possível realizar instalação automática de distribuições Ubuntu Server na versão 20.x ou superiores por meio de arquivos de configuração baseados em cloud-init.
Link da issue: https://github.com/ventoy/Ventoy/issues/1351 
* O sistema deve permitir que o usuário escolha entre usar o estilo GPT ou MBR para partição.
Link: https://www.ventoy.net/en/index.html
* Na versão 1.0.11 do Ventoy foi adicionada a funcionalidade de persistência para distribuições como Ubuntu, MX Linux, Linux Mint e Elementary. A funcionalidade permite que alterações feitas durante o modo Live sejam armazenadas em um arquivo de persistência e recuperadas em futuras atualizações. 
Link das notas: https://www.ventoy.net/en/plugin_persistence.html 

**3.2 Requisitos Não Funcionais**

* O sistema deve garantir compatibilidade em computadores com o firmware UEFI com Secure Boot Ativado, sem exigir a desativação manual da proteção na BIOS/UEFI da máquina cliente.
Link: https://github.com/ventoy/Ventoy/blob/master/SecureBoot.md
* O sistema deve estruturar e alinhar as estruturas de partições de USB em blocos de 4KB por padrão, para garantir otimização na instalação dos dispositivos. 
Link:https://github.com/ventoy/Ventoy/releases/tag/v1.0.36
* O sistema deve possuir um tutorial de como instalar e usar o Ventoy para usuários novos, leigos, etc.
Link: https://www.ventoy.net/en/doc_start.html
* A interface gráfica do Ventoy deve ser compatível com os sistemas operacionais e ambientes gráficos Linux suportados pelo projeto, permitindo sua execução adequada.
Link: https://github.com/ventoy/Ventoy/issues/3406

**3.3 Histórias de Usuário**

Como técnico de suporte, eu gostaria de selecionar uma imagem ISO (Debian ou Windows) na lista exibida na interface de boot do Ventoy, para que eu possa carregar o respectivo instalador e realizar a instalação ou manutenção offline em qualquer computador. 

**Cenário 1**: **Dado** que o técnico de suporte possui um pen drive com armazenamento suficiente para ter a versão mais recente do Ventoy e as duas ISOs com suas respectivas versões mais recentes.

**Quando** o técnico conectar o pen drive em um computador e inicializar via dispositivo USB e selecionar a ISO do Debian.

**Então** o sistema deve carregar o ambiente de instalação do Debian, permitindo prosseguir com a instalação no disco da máquina. 
