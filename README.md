# 🛠️ Portal de Serviços Locais

Seja bem-vindo ao repositório oficial do projeto **Portal de Serviços Locais**. Este documento apresenta uma visão geral do sistema, explicando a sua proposta, a arquitetura adotada, as regras de negócio e a organização do desenvolvimento.

O projeto foi idealizado e desenvolvido no âmbito acadêmico do **Instituto Federal de Goiás (IFG) - Câmpus Formosa**, com o objetivo de construir uma solução tecnológica eficiente para conectar prestadores de serviços autônomos aos clientes da região.

---

## 📌 1. Visão Geral do Projeto

A proposta do **Portal de Serviços Locais** é funcionar como uma plataforma web/mobile interativa (marketplace) voltada para a contratação de serviços diversos. 

Muitas vezes, profissionais autônomos (como encanadores, eletricistas, pintores, entre outros) encontram dificuldades para divulgar o seu trabalho, enquanto clientes têm dificuldades para encontrar profissionais qualificados e confiáveis perto de casa. A nossa plataforma resolve esse problema centralizando a busca, o agendamento, o pagamento e as avaliações num único ambiente digital simples e seguro.

---

## 👤 2. Atores do Sistema e Perfis de Acesso

O sistema foi modelado para atender a três tipos de usuários bem definidos, cada um com responsabilidades e funcionalidades específicas:

1. **Cliente:**
   * Busca profissionais por nome ou palavra-chave.
   * Aplica filtros de pesquisa (como categoria do serviço e localização).
   * Visualiza o perfil do profissional e entra em contato via mensagem/chat.
   * Realiza pagamentos de serviços pela própria plataforma.
   * Deixa avaliações e notas (feedbacks) sobre os serviços contratados.

2. **Profissional:**
   * Cria e gerencia o seu perfil público (descrição, endereço, telefone de contato).
   * Cadastra os serviços oferecidos e define os seus respectivos valores base.
   * Registra e atualiza a sua disponibilidade de dias e horários de atendimento.
   * Responde às mensagens recebidas dos clientes.
   * Acompanha estatísticas sobre os atendimentos e avaliações recebidas.

3. **Administrador:**
   * Atua na moderação e gestão global da plataforma.
   * Modera e valida novos cadastros de usuários.
   * Cadastra, edita e gerencia as categorias de serviços do sistema.
   * Acompanha denúncias de má conduta e gerencia conteúdos inadequados.
   * Visualiza relatórios gerais do sistema e responde a chamados do suporte técnico.

---

## 🧩 3. Arquitetura e Estrutura de Classes (UML)

A estrutura orientada a objetos do sistema foi desenhada priorizando o reaproveitamento de código, a organização e a facilidade de manutenção.

### 🧬 Superclasse e Heranças
* **Usuário (Superclasse):** Armazena os dados comuns a todos os usuários da plataforma (`id_usuario`, `nome`, `email`, `cpf_cnpj`, `senha`, `dataCadastro`, `fotoPerfil`). Contém os métodos fundamentais de acesso: `realizarLogin()`, `fazerLogout()` e `editarPerfil()`.
* **Subclasses Herdeiras:** As classes `Cliente`, `Profissional` e `Administrador` herdam os atributos e métodos da classe `Usuário` (`extends`), adicionando apenas os atributos e funções específicos do seu perfil.

### 🔗 Classes de Apoio e Relacionamentos
* **Categoria:** Organiza a busca por segmentos (ex.: Construção, Tecnologia, Beleza).
* **Serviço:** Define o trabalho oferecido pelo profissional (`tituloServico`, `descricaoDetalhada`, `valorBase`). Um profissional pode cadastrar vários serviços ($1 \rightarrow 1*$).
* **HorarioAtendimento:** Controla os dias da semana (`diaSemana`) e horários (`horaInicio`, `horaFim`) em que o profissional atua.
* **Avaliação:** Registra a nota em estrelas (de 1 a 5), um comentário de texto e a data da avaliação feita pelo cliente ao profissional.
* **Pagamento:** Gerencia as transações financeiras (`valor`, `formaPagamento`, `dataTransacao`). O atributo `statusPagamento` utiliza um tipo enumerado (`Enum`: *Pendente*, *Aprovado*, *Recusado*), prevenindo erros de digitação e otimizando o processamento.

---

## 📱 4. Interfaces e Fluxos de Usuário (Wireframes)

Para garantir que a utilização do app seja fluida e simples para qualquer pessoa, a equipe desenhou os protótipos das telas principais:

* **Telas de Acesso (Login e Cadastro):** Formulários objetivos com opção de alternar entre o perfil de *Cliente* e *Profissional*, solicitando dados essenciais de identificação e segurança.
* **Tela de Perfil do Profissional:** Apresenta a foto de perfil, dados de contato, áreas de atuação e serviços disponíveis.
* **Tela de Avaliações:** Interface intuitiva onde o cliente pode avaliar a experiência do serviço prestado com notas e comentários simples.

---

## 📊 5. Organização do Projeto

A gestão das tarefas e prazos do projeto é acompanhada utilizando a metodologia Kanban por meio do **Trello** (*Projeto Portal de Serviços Locais*). 

As etapas de documentação técnica, modelagem UML (diagramas de caso de uso, classes e MER), definição de requisitos e criação de protótipos de tela foram distribuídas e concluídas de forma organizada, garantindo a rastreabilidade do progresso de cada membro da equipe.

---

## 🎓 6. Créditos e Instituição

* **Instituição:** Instituto Federal de Goiás (IFG) — Câmpus Formosa
* **Autor/Desenvolvedor:** Miguel Guilherme de Carvalho Alacoque
* **Projeto:** Portal de Serviços Locais
