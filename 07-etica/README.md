## 6. Ética e Responsabilidade

### 6.1 Segurança - Utilização do *Secure Boot*

O *Secure Boot* é um recurso de segurança presente no firmware UEFI (*Unified Extensible Firmware Interface*) dos computadores, responsável por verificar a autenticidade dos componentes executados durante o processo de inicialização do sistema. O principal objetivo desse mecanismo é impedir que softwares não autorizados ou maliciosos sejam carregados antes do sistema operacional.

O Ventoy é um software de código aberto cujos componentes de inicialização precisam ser autorizados para funcionar com o Secure Boot. Para isso, o sistema oferece suporte ao Secure Boot por meio da chave MOK (Machine Owner Key) permitindo que o próprio usuário autorize esses componentes sem que seja necessário desativar o recurso de segurança. Na primeira utilização do computador com o Secure Boot habilitado, o usuário pode registrar a chave por meio do MOKManager, ferramenta responsável por gerenciar essas autorizações. Após a confirmação do registro da chave, o Ventoy pode ser inicializado normalmente.

Além disso, o Ventoy disponibiliza duas políticas de segurança sobre esse recurso de segurança. A primeira opção, utilizada como padrão, permite ignorar as verificações do Secure Boot para os arquivos UEFI executados, o que proporciona maior compatibilidade, mas reduz a segurança contra componentes maliciosos. Já a segunda opção mantém as verificações oficiais do UEFI, permitindo apenas a execução de arquivos com assinaturas reconhecidas, porém apresenta dificuldade de compatibilidade de funcionalidades do sistema.

**Problema Ético:** Existe um dilema entre facilitar a utilização do software e garantir a segurança dos usuários. Embora a configuração padrão aumente a compatibilidade do Ventoy, também pode permitir a execução de arquivos UEFI maliciosos. Além disso, é importante reconhecer que usuários sem conhecimento técnico sobre podem não compreender os reais riscos envolvidos nessa configuração.

**Responsabilidade do Engenheiro de Software:** Os profissionais devem avaliar os riscos associados com as decisões de implementação do sistema, informar claramente quais podem ser as consequências das políticas disponíveis e orientar os usuários sobre configurações de segurança mais seguras. Para além disso, devem buscar um equilíbrio entre compatibilidade, proteção dos usuários e simplicidade na utilização, garantindo que os usuários tenham informações para que possam tomar uma decisão mais segura.

---

### 6.2 Licenciamento - Licenças do Software Livre

O Ventoy é um software de código aberto que utiliza a licença GNU General Public License (GPL), versão 3 ou posteriores (GPLv3 +). Além de possuir códigos pelo próprio projeto, ele também incorpora componentes de outros projetos de código aberto, em que bibliotecas e ferramentas são utilizadas ou modificadas.

A licença GPL estabelece exigências para a utilização, modificação e redistribuição do software, permitindo que outros desenvolvedores tenham acesso ao código-fonte e possam modificá-lo de acordo com as suas necessidades. No entanto, a liberdade de utilizar, modificar e compartilhar o software devem respeitar determinações pré-definidas, como preservar os direitos autorais e disponibilizar o código-fonte quando exigido pelo próprio projeto.

No caso do Ventoy, essas condições também envolvem componentes desenvolvidos por terceiros. Como o projeto utiliza ferramentas e bibliotecas de diferentes origens, que possuem licenças específicas que também devem ser respeitadas.

**Problema ético:** Utilizar, modificar e redistribuir componentes desenvolvidos por terceiros sem respeitar as condições exigidas pelas suas respectivas licenças. Tal prática pode violar o direito dos desenvolvedores originais, comprometer a transparência do projeto e prejudicar a colaboração entre a comunidade de software livre.

**Responsabilidade do Engenheiro de Software:** Os profissionais devem verificar as licenças dos componentes utilizados no projeto, preservar os créditos e avisos de direitos autorais, documentar quais modificações foram realizadas e garantir que a utilização e distribuição do software sejam efetuadas de acordo com as condições estabelecidas pelas licenças.
