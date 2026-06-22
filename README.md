# QUALIDADE E TESTES DE SOFTWARE — ATIVIDADES

---

## AULA 01

# 1. O que é qualidade?
- Qualidade é algo atender bem ao seu propósito e às expectativas de quem usa.
- Qualidade é o software fazer o que promete, do jeito que o usuário espera, atendendo os requisitos e sendo confiável, seguro e fácil de usar.

---

## AULA 02

# 1. QUAIS CARACTERISTICAS DE UM TESTER ÁGIL
- Participam da fase de requisitos
- Trabalham em conjunto com os desenvolvedor
- Fazem lançamentos frequentes para os testes ocorrerem a cada iteração
- Enfatizam a melhoria contínua e o feedback rápido
- Focam na entrega de valor ao usuário final

# 2. QUANDO TER OU QUANDO NÃO  TER CODE REVIEW
- Quando o code review envolve comprometimento de toda a equipe em analisar os PR's e TESTÁ-LOS e não apenas olhar o código em 30 segundos para voltar a resolver a bucha que estava anteriormente, aí assim faz sentido ter o code review. Por exemplo, a equipe de desenvolvimento do BitCoin utiliza até mesmo nomenclaturas para demonstrar honestidade na revisão do PR, como se concorda com o conceito do PR, não olhou o código, não testou, aprova.

fontes: 
- https://agiletest.app/agile-testing-vs-waterfall-testing/
- (Comentário do usuário *SafeCaramel9999*) https://www.reddit.com/r/brdev/comments/1432hpm/pra_que_realmente_serve_um_code_review/

# 3. QUANDO O CODE REVIEW FAZ SENTIDO E QUANDO DEIXA DE FAZER
Faz sentido quando:
- A equipe se compromete de verdade a olhar o PR, entender e testar e não dar aquele aprovado em 30 segundos só pra completar pra release e voltar pra bucha que estava resolvendo antes
- É parte crítica do sistema, onde uma segunda validação reduz o risco de cair em produção e gerar prejuízo financeiro ou de segurança
- Serve pra manter o padrão de código e espalhar conhecimento entre o time

Deixa de fazer sentido quando:
- Vira burocracia, só pra cumprir obrigação
- Usam o review pra crítica pessoal em vez de melhorar o código
- Atrasa a entrega sem agregar nada ou quando já existe revisão em tempo real (pair) e o review formal só duplica o trabalho.

---

## AULA 03

# 4. BDD DAS ROTINAS DO SISTEMA (CRUD + LOGIN)
Padrão Gherkin (Dado / Quando / Então):

**Login — sucesso**
- Dado que estou na tela de login
- Quando preencho email e senha corretos e clico em Entrar
- Então sou redirecionado para o painel principal

**Login — falha**
- Dado que estou na tela de login
- Quando preencho email ou senha incorretos e clico em Entrar
- Então vejo a mensagem "Login ou Senha inválidas"

**Create — cadastrar usuário**
- Dado que estou na tela de cadastro
- Quando preencho nome, email e senha e clico em Salvar
- Então o usuário é cadastrado e aparece na listagem

**Create — campo obrigatório em branco**
- Dado que estou na tela de cadastro
- Quando deixo o email em branco e clico em Salvar
- Então vejo a mensagem "Preencha todos os campos obrigatórios"

**Read — listar usuários**
- Dado que estou autenticado
- Quando acesso a listagem de usuários
- Então vejo todos os usuários cadastrados

**Update — editar usuário**
- Dado que estou na tela de edição de um usuário
- Quando altero o nome ou o email e clico em Salvar
- Então as informações são atualizadas na listagem

**Delete — remover usuário**
- Dado que estou na listagem de usuários
- Quando clico em Remover e confirmo a ação
- Então o usuário é removido da listagem

# 5. ISO 9126 — CARACTERÍSTICAS DE QUALIDADE (PORTABILIDADE)
A ISO 9126 define características de qualidade de software, cada uma com suas subcaracterísticas. Foco na **Portabilidade** (capacidade de levar o software de um ambiente pra outro):
- **Adaptabilidade** — se ajusta a ambientes diferentes sem perder qualidade
- **Instalabilidade** — instala fácil, rápido e sem erro
- **Coexistência** — roda junto com outros sistemas sem dar conflito
- **Substituibilidade** — dá pra trocar componentes sem mudar o comportamento do sistema
- **Conformidade** — está de acordo com normas, padrões e requisitos legais

---

## AULA 04

# 6. PRINCÍPIOS, NÍVEIS, TIPOS E TÉCNICAS DE TESTE

**Os 7 princípios de teste**
1. O teste mostra a presença de defeitos, não a ausência deles
2. Teste exaustivo é impossível
3. Testar cedo economiza tempo e dinheiro
4. Os defeitos se agrupam (poucos módulos concentram a maioria)
5. Cuidado com o paradoxo do pesticida, repetir sempre o mesmo teste para de achar bug novo
6. O teste depende do contexto
7. Ausência de erros é ilusão, software sem bug ainda pode ser inútil se não atende a necessidade

**Níveis de teste**
- **Componente** — testar uma função isolada, ex.: a que calcula desconto
- **Integração** — ver se o login conversa certo com o banco
- **Sistema** — fluxo completo: login → carrinho → pagamento
- **Aceite** — o cliente valida se o relatório saiu correto

**Tipos de teste**
- **Funcional** — login válido leva pro painel
- **Não funcional** — sistema responde em menos de 2s com 1000 usuários
- **Caixa-branca** — garantir que todos os if/else rodem
- **Relacionado à mudança** — depois do deploy, conferir se nada quebrou (regressão)

**Técnicas de teste**

Caixa-preta:
- **Particionamento de equivalência** — campo de 1 a 100: testo um abaixo, um dentro e um acima
- **Análise de valor limite** — campo de 1 a 100: testo 1, 2, 99 e 100
- **Tabela de decisão** — empréstimo: maior de 18 E renda > R$1000 → aprovado
- **Transição de estado** — pedido: Novo → Confirmado → Enviado → Entregue
- **Caso de uso** — login: sucesso, senha errada, campo vazio

Caixa-branca:
- **Cobertura de instruções** — cada linha de código executada pelo menos uma vez
- **Cobertura de decisão** — testar cada if/else como verdadeiro e como falso

Baseadas na experiência:
- **Suposição de erro** — antecipar falhas com base no que já deu errado antes
- **Exploratório** — navegar pelo sistema sem roteiro, no feeling
- **Lista de verificação** — seguir um checklist pra não esquecer teste importante

**Erro x Defeito x Falha**
- **Erro** — engano humano que gera resultado incorreto
- **Defeito (bug)** — algo implementado errado no código
- **Falha** — o comportamento inesperado que o software apresenta

---

## AULA 05

# 7. PLANO DE TESTE DO REPOSITÓRIO
 - Equipe: Natália, Diego e Matheus.
 - Planilha de testes: https://senacsc754-my.sharepoint.com/:x:/g/personal/natalia_rodrigues3_alunos_sc_senac_br/IQDmgImQg1D1QYytY2a35gW-Acdj_7AnnraTX6TCLAkjv20?e=vTTsjF
 - Apresentação: [Gamma](https://gamma.app/docs/Avaliacao-de-Qualidade-de-Software-jn6o5q5am00icdy)

---

## AULA 06

# 8. AVALIAÇÃO EM EQUIPE (CASOS DE TESTE, EXECUÇÃO E APRESENTAÇÃO)

Parte 1 — criação dos casos de teste:
- Fork e clone do repositório da avaliação
- Li o código pra identificar as funcionalidades
- Montei os casos de teste na planilha e o banco de dados

Parte 2 — execução, correção e apresentação:
- Registrei os bugs na planilha com prioridade
- Corrigi os bugs e retestei (se voltasse a dar bug, registrava de novo)
- Montei a apresentação com: resumo dos testes com gráficos, os 5 bugs mais impactantes e 5 sugestões de melhoria (justificativa e como corrigir)

---

## AULA 07

# 9. ANÁLISE DE RISCO DOS CENÁRIOS
Para cada cenário, identifiquei probabilidade (A–E), impacto (1–5), a posição na matriz, os testes, a mitigação e os tipos de risco.

**Cenário 1 — Manutenção programada (serviço fora do ar)**
- Probabilidade B / Impacto 1 → **B1 — Muito Baixo**
- Testes: smoke test e regressão
- Mitigação: avisar os usuários antes, agendar em horário de baixo uso e rodar smoke test ao voltar
- Tipos: operacional e negócio

**Cenário 2 — Vulnerabilidade em dependência de terceiros**
- Probabilidade C / Impacto 5 → **C5 — Muito Alto**
- Testes: pentest, SAST/DAST e varredura de dependências
- Mitigação: atualizar a lib na hora, checar se houve exploração e notificar usuários se precisar
- Tipos: técnico, negócio (LGPD/reputação) e operacional

**Cenário 3 — Erro de interface confunde o usuário**
- Probabilidade C / Impacto 2 → **C2 — Médio**
- Testes: usabilidade, funcional e exploratório
- Mitigação: corrigir no próximo sprint e monitorar os tickets de suporte pra medir o impacto
- Tipos: técnico, humano e negócio

**Cenário 4 — Falha no backup de dados**
- Probabilidade B / Impacto 5 → **B5 — Alto**
- Testes: teste de recuperação de desastre (DR) e validação do restore
- Mitigação: alertas automáticos de falha de backup, testar o restore com frequência e manter redundância
- Tipos: operacional e negócio (perda irreversível de dados)

**Cenário 5 — Ataque de phishing aos usuários**
- Probabilidade D / Impacto 4 → **D4 — Muito Alto**
- Testes: pentest e teste de segurança
- Mitigação: ativar MFA, treinar o usuário pra identificar phishing e monitorar acessos suspeitos
- Tipos: técnico, humano e negócio

---

## AULA 09

# 10. CALCULADORA API + TESTES UNITÁRIOS (JEST)
- Tratei os erros base, principalmente o `isNaN`, pra não deixar passar entrada que não é número.
- Escrevi os testes unitários da planilha de teste usando Jest: `describe` pra agrupar, `it` pra cada teste, e `expect(...).toBe(...)` pra comparar resultado real com o esperado.
- Rodei com `npm test`.

---

## AULA 10 (12/06)

# 11. DEBUG DA CALCULADORA
- Usei o Debug do VS Code (Run and Debug → Node.js → breakpoints) pra acompanhar a execução e validar as mensagens.
- [Repositório](https://github.com/diegosilveira94/base-aulas-teste-debug-pt)
- [PR](https://github.com/renanponick/base-aulas-teste-debug-pt/pull/12)
