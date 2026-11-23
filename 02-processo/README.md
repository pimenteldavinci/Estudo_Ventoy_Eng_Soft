# 2. Práticas e Modelos de Desenvolvimento Observados

### Práticas de Desenvolvimento

O Ventoy é um projeto de código aberto (*open source*), hospedado no GitHub e mantido principalmente por seu desenvolvedor principal, conhecido como **longpanda**, com contribuições da comunidade.

Entre as práticas de desenvolvimento observadas, destacam-se:

- **Controle de versão:** utilização do Git para gerenciar o histórico de alterações e a evolução do código-fonte.
- **Gerenciamento de problemas e sugestões:** utilização da ferramenta Issues do GitHub para registrar erros, relatar problemas de compatibilidade e sugerir novas funcionalidades ou suporte a imagens ISO.
- **Colaboração da comunidade:** recebimento de contribuições externas por meio de Pull Requests, incluindo traduções, correções e melhorias de compatibilidade.
- **Entregas contínuas:** disponibilização de novas versões (*releases*) com correções, melhorias e funcionalidades adicionais.

### Modelos de Desenvolvimento Identificados

O desenvolvimento do Ventoy apresenta características de diferentes abordagens da Engenharia de Software, principalmente:

**1. Desenvolvimento Incremental**

O Ventoy apresenta uma evolução gradual, na qual novas funcionalidades e melhorias são incorporadas ao longo de suas versões. Em vez de disponibilizar um produto com todas as funcionalidades desde o início, o projeto evolui por meio de incrementos sucessivos.

Entre os exemplos dessa evolução estão a ampliação do suporte a diferentes estilos de partição, a implementação de uma interface web para Linux e a compatibilidade com novos sistemas operacionais, como o SteamOS.

**2. Reutilização de Software**

Em vez de desenvolver todos os componentes de inicialização do zero, o Ventoy utiliza ferramentas e tecnologias já existentes, aproveitando soluções consolidadas para diferentes necessidades.

Entre os recursos utilizados, destacam-se:

- **GRUB2:** gerenciador de inicialização amplamente utilizado em distribuições Linux.
- **iPXE:** firmware de inicialização de rede que permite realizar operações de boot por meio de conexões de rede.
- **Memdisk Mode:** mecanismo que permite carregar uma imagem de disco diretamente na memória RAM, possibilitando sua inicialização a partir desse ambiente.

### Relação com os Princípios Ágeis

Embora seja mantido predominantemente por um único desenvolvedor, o Ventoy apresenta características compatíveis com alguns princípios do Manifesto Ágil, principalmente:

- **Software em funcionamento mais que documentação abrangente:** a evolução do projeto é demonstrada pela disponibilização de versões funcionais, que incorporam melhorias e novas funcionalidades.
- **Responder a mudanças mais que seguir um plano:** o projeto recebe sugestões, correções e solicitações da comunidade, permitindo que seu desenvolvimento acompanhe necessidades identificadas pelos usuários.

### Modelos e Frameworks Não Identificados

Apesar de apresentar características de desenvolvimento incremental e princípios associados às metodologias ágeis, não há evidências suficientes para afirmar que o Ventoy adota integralmente um modelo formal ou framework específico de desenvolvimento.

Por ser um projeto mantido majoritariamente por um único desenvolvedor, não são observadas publicamente estruturas organizacionais típicas de frameworks como o **Scrum**, que envolvem papéis definidos, como Product Owner e Scrum Master, além de eventos e ciclos de desenvolvimento estruturados.

O projeto também apresenta diferenças em relação ao Modelo Cascata e ao RUP (*Rational Unified Process*), pois sua evolução pública ocorre de maneira contínua, com atualizações e incorporações de funcionalidades ao longo das versões, sem evidências de uma divisão rígida e sequencial de todas as etapas de desenvolvimento.

Dessa forma, o Ventoy pode ser caracterizado como um projeto de desenvolvimento contínuo, com abordagem incremental, reutilização de componentes e participação colaborativa da comunidade.
