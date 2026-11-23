## 3. Requisitos do Software.
### 3.1 Requisitos Funcionais

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
---

### 3.2 Requisitos Não Funcionais

* O sistema deve garantir compatibilidade em computadores com o firmware UEFI com Secure Boot Ativado, sem exigir a desativação manual da proteção na BIOS/UEFI da máquina cliente.
Link: https://github.com/ventoy/Ventoy/blob/master/SecureBoot.md
* O sistema deve estruturar e alinhar as estruturas de partições de USB em blocos de 4KB por padrão, para garantir otimização na instalação dos dispositivos. 
Link:https://github.com/ventoy/Ventoy/releases/tag/v1.0.36
* O sistema deve possuir um tutorial de como instalar e usar o Ventoy para usuários novos, leigos, etc.
Link: https://www.ventoy.net/en/doc_start.html
* A interface gráfica do Ventoy deve ser compatível com os sistemas operacionais e ambientes gráficos Linux suportados pelo projeto, permitindo sua execução adequada.
Link: https://github.com/ventoy/Ventoy/issues/3406
---

## 3.3 Histórias de Usuário

### História de Usuário 1 — Inicialização de imagens ISO

**Como** técnico de suporte,  
**quero** selecionar uma imagem ISO (Debian ou Windows) na lista exibida pela interface de inicialização do Ventoy,  
**para** carregar o respectivo ambiente de instalação e realizar instalações ou manutenções em computadores.

**Cenário 1 — Inicialização da ISO do Debian**

- **Dado que** o técnico de suporte possui um pen drive com o Ventoy instalado em sua versão mais recente e com as imagens ISO mais recentes do Debian e do Windows;
- **Quando** conectar o dispositivo USB a um computador, inicializá-lo por meio desse dispositivo e selecionar a ISO do Debian;
- **Então** o sistema deverá carregar o ambiente de instalação do Debian, permitindo que o técnico prossiga com a instalação no disco do computador.

**Cenário 2 — Inicialização da ISO do Windows**

- **Dado que** o técnico de suporte possui um pen drive com o Ventoy instalado em sua versão mais recente e com as imagens ISO mais recentes do Debian e do Windows;
- **Quando** conectar o dispositivo USB a um computador, inicializá-lo por meio desse dispositivo e selecionar a ISO do Windows;
- **Então** o sistema deverá carregar o ambiente de instalação do Windows, permitindo que o técnico prossiga com a instalação no disco do computador.

---

### História de Usuário 2 — Alternância entre estilos de partição

**Como** estudante de Tecnologia da Informação,  
**quero** alternar entre os estilos de partição MBR e GPT,  
**para** compreender e avaliar, na prática, as diferenças entre esses dois formatos.

**Cenário 1 — Alteração de GPT para MBR**

- **Dado que** o Ventoy está configurado para utilizar o estilo de partição GPT;
- **Quando** o usuário acessar o menu "Opções", selecionar "Estilo da Partição" e escolher a opção MBR;
- **Então** o software deverá atualizar a indicação do estilo de partição selecionado, exibindo MBR no lugar de GPT.

**Cenário 2 — Alteração de MBR para GPT**

- **Dado que** o Ventoy está configurado para utilizar o estilo de partição MBR;
- **Quando** o usuário acessar o menu "Opções", selecionar "Estilo da Partição" e escolher a opção GPT;
- **Então** o software deverá atualizar a indicação do estilo de partição selecionado, exibindo GPT no lugar de MBR.

---

### História de Usuário 3 — Alteração do idioma

**Como** usuário do Ventoy,  
**quero** alterar o idioma da interface para português brasileiro,  
**para** facilitar a compreensão e a utilização das funcionalidades do software.

**Cenário 1 — Alteração do idioma para português brasileiro**

- **Dado que** o software está configurado com o idioma padrão (inglês);
- **Quando** o usuário acessar a opção "Language" e selecionar "Portuguese Brazilian (Português Brasileiro)";
- **Então** todos os elementos da interface que possuem tradução disponível deverão ser exibidos em português brasileiro.

**Cenário 2 — Persistência do idioma selecionado**

- **Dado que** o software está configurado no idioma português brasileiro;
- **Quando** o usuário fechar e abrir novamente o programa;
- **Então** o idioma selecionado anteriormente deverá ser mantido.

---

### História de Usuário 4 — Atualização do Ventoy

**Como** usuário do Ventoy,  
**quero** atualizar a versão instalada no meu pen drive diretamente pelo software,  
**para** manter o dispositivo atualizado sem precisar realizar uma nova instalação e perder os arquivos armazenados.

**Cenário 1 — Confirmação da atualização**

- **Dado que** o Ventoy está instalado no pen drive em uma versão anterior e o dispositivo está conectado ao computador;
- **Quando** o usuário selecionar a opção "Atualizar", o software deverá exibir uma mensagem solicitando a confirmação da operação, informando que a atualização é segura e que os arquivos ISO não serão modificados;
- **E** quando o usuário confirmar a operação selecionando "Sim";
- **Então** o software deverá iniciar o processo de atualização, exibindo o indicador de carregamento, e atualizar o Ventoy para a versão mais recente disponível.

**Cenário 2 — Cancelamento da atualização**

- **Dado que** o Ventoy está instalado no pen drive em uma versão anterior e o dispositivo está conectado ao computador;
- **Quando** o usuário selecionar a opção "Atualizar", o software deverá exibir uma mensagem solicitando a confirmação da operação, informando que os arquivos ISO não serão modificados;
- **E** quando o usuário selecionar "Não";
- **Então** a operação deverá ser cancelada, o dispositivo deverá permanecer inalterado e o software deverá retornar à tela inicial.
