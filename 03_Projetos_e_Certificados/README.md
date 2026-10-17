# Projetos e Certificados

## Sobre esta seção

Aqui ficam os projetos que construí, na faculdade e por conta própria, e os cursos e certificações que registram minha formação em Tecnologia da Informação.

Meus projetos se dividem em duas frentes:

- **Aplicativos mobile** feitos com Flutter e Dart.
- **Automação de processos (RPA)** feita com Power Automate e SQL Server.

## Estrutura

- `Projetos/`: documentação e código dos projetos.
  - `Projetos_Mobile/`: aplicativos para dispositivos móveis.
  - `Projetos_RPA/`: automações de processos.
- `Certificacoes/`: cursos e certificações concluídos.

## Projetos em destaque

| Projeto | Área | O que faz |
|---|---|---|
| Diário de Treino | Mobile | Registra os dias de treino e monta fichas com aparelhos, séries e carga. |
| Estante de Jogos | Mobile | Estante pessoal de jogos com reviews, comunidade e dados da API da Twitch. |
| Gerador de Boletos | RPA | Robô que lê dados, grava em SQL Server e gera boletos automaticamente. |

---

## Projetos Mobile

### Diário de Treino (app de academia)

**Problema:** acompanhar a rotina de academia em planilhas ou anotações soltas dificulta ver a evolução.

**O que o app faz:**

- Registra os dias em que o usuário treinou.
- Monta o treino escolhendo aparelhos e exercícios.
- Define séries, repetições e carga para cada exercício.
- Mantém o histórico para acompanhar a evolução ao longo do tempo.

**Tecnologias:** Flutter e Dart, com armazenamento do histórico de treinos em banco de dados (Firebase Cloud Firestore).

**Como executar:**

1. Instale o [Flutter SDK](https://docs.flutter.dev/get-started/install) e confira com `flutter doctor`.
2. Clone o repositório e entre na pasta do app.
3. Baixe as dependências: `flutter pub get`
4. Conecte um celular ou abra um emulador e rode: `flutter run`

**Imagens:** adicione capturas de tela em uma pasta `imagens/` e referencie aqui.

### Estante de Jogos (rede social de games)

**Problema:** reunir em um só lugar os jogos que a pessoa tem, quer jogar ou já zerou, e conversar sobre eles com outras pessoas.

**O que o app faz:**

- Permite adicionar jogos à estante pessoal.
- Mostra capa, descrição e outras informações obtidas pela API da Twitch (IGDB).
- Permite escrever reviews, visíveis para a comunidade.
- Permite seguir outros usuários e acompanhar o que eles jogam e avaliam.

**Tecnologias:** Flutter e Dart, Firebase (Authentication e Cloud Firestore) para contas, reviews e seguidores, e API da Twitch (IGDB) para os dados dos jogos.

**Como executar:**

1. Instale o [Flutter SDK](https://docs.flutter.dev/get-started/install) e confira com `flutter doctor`.
2. Crie um aplicativo em [dev.twitch.tv](https://dev.twitch.tv/console) para obter o **Client ID** e o **Client Secret** da API.
3. Guarde essas chaves em um arquivo `.env` (que não vai para o GitHub) ou em variáveis de ambiente.
4. Baixe as dependências: `flutter pub get`
5. Rode o app: `flutter run`

**Imagens:** adicione capturas de tela em uma pasta `imagens/` e referencie aqui.

---

## Projetos RPA

### Gerador de Boletos

**Problema:** gerar boletos manualmente é repetitivo e sujeito a erro de digitação, principalmente quando o volume é grande.

**Como funciona:**

1. O robô lê uma planilha Excel com os dados de cada boleto.
2. Limpa e valida os campos (remoção de caracteres inválidos e validação de datas).
3. Grava os dados no banco SQL Server.
4. Cada boleto entra em uma **fila de processamento** com status, tentativas e data de inserção.
5. O robô processa a fila, gera o boleto no site e guarda o arquivo em **Base64** no banco.
6. O status de cada item é atualizado ao final, para acompanhar sucessos e erros.

**Ferramentas:** Power Automate Desktop, Power Automate Cloud, SQL Server, Excel, expressões regulares (regex).

**Estrutura do banco:**

- Tabela de dados do boleto.
- Tabela de fila de processamento.
- Tabela de armazenamento do boleto em Base64.

**Pontos que trabalhei:**

- Validação de datas dentro do próprio fluxo, enviando `NULL` ao banco quando a data é inválida.
- Limpeza padronizada de textos com regex antes da gravação.
- Controle de fila e tratamento de erros.

**Imagens:** adicione prints do fluxo e do banco, sempre com dados fictícios.

---

## Documentação dos projetos

Cada projeto traz, quando aplicável:

1. Descrição e objetivo.
2. Tecnologias utilizadas.
3. Estrutura dos arquivos.
4. Instruções de instalação ou execução.
5. Funcionalidades.
6. Evidências e resultados.
7. Melhorias futuras.

As alterações de código são registradas com commits claros e objetivos.

## Certificações

Os registros incluem nome do curso, instituição, data de conclusão, carga horária e link de validação, quando houver. Entram somente cursos concluídos, separados dos que estão em andamento.

## Boas práticas

Não incluir no repositório credenciais, senhas, chaves de API (como as da Twitch), tokens, strings de conexão reais ou dados pessoais de clientes. Use dados fictícios nos exemplos e nas imagens.
