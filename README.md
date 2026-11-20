# Sistema de Registro e Gestão de Contas Bancárias

## Etapa 3 – INF101: Programação de Computadores I

Projeto desenvolvido como atividade acadêmica da disciplina **INF101 – Programação de Computadores I**, do Centro Universitário de Viçosa – UNIVIÇOSA.

**Professores:** Anderson R. Lamas e Vanderlea Queiroz.

**Aluno:** Leonardo Araújo - 27706

---

## 1. Sobre o projeto

O projeto consiste no desenvolvimento de um sistema bancário em linguagem C++, capaz de cadastrar e gerenciar contas bancárias, realizar movimentações financeiras e consultar o histórico de operações.

Na Etapa 3, o sistema foi aprimorado para armazenar permanentemente os dados utilizando arquivos de texto. Dessa forma, as contas cadastradas, os saldos e o histórico de movimentações continuam disponíveis mesmo após o encerramento do programa.

## 2. Funcionalidades

O sistema possui as seguintes funcionalidades:

1. **Cadastrar conta:** permite registrar uma nova conta bancária.
2. **Listar contas:** apresenta todas as contas cadastradas.
3. **Consultar conta:** pesquisa uma conta pelo número.
4. **Realizar depósito:** adiciona um valor ao saldo da conta.
5. **Realizar saque:** retira um valor, verificando se existe saldo suficiente.
6. **Realizar transferência:** transfere valores entre duas contas.
7. **Exibir extrato:** apresenta o histórico de movimentações de uma conta.
8. **Sair:** encerra o programa.

## 3. Armazenamento de dados

Para garantir a persistência das informações, o sistema utiliza dois arquivos de texto.

### contas.txt

Armazena os dados das contas cadastradas:

- Número da conta;
- Nome do cliente;
- CPF;
- Tipo da conta;
- Saldo;
- Situação da conta.

Exemplo:

```text
1001;Ana Silva;12345678900;1;700.00;1
1002;Bruno Souza;98765432100;2;800.00;1
```

Cada linha representa uma conta, com os campos separados por ponto e vírgula.

### movimentacoes.txt

Armazena o histórico das movimentações financeiras:

- Número da conta;
- Tipo da movimentação;
- Valor movimentado.

Os códigos utilizados são:

| Código | Movimentação |
|---|---|
| D | Depósito |
| S | Saque |

Exemplo:

```text
1001;D;500.00
1001;S;300.00
1002;D;300.00
```

Nas transferências, são registrados dois movimentos: uma saída (S) na conta de origem e uma entrada (D) na conta de destino.

## 4. Persistência dos dados

Ao iniciar o programa, o sistema realiza automaticamente a leitura dos arquivos `contas.txt` e `movimentacoes.txt`.

As informações são carregadas para os arrays utilizados pelo sistema.

Sempre que uma conta é cadastrada ou ocorre um depósito, saque ou transferência, os arquivos correspondentes são atualizados.

Assim, os dados permanecem armazenados mesmo depois que o programa é encerrado.

Caso os arquivos ainda não existam, o sistema inicia normalmente, sem contas ou movimentações cadastradas.

## 5. Tecnologias e recursos utilizados

- Linguagem C++;
- Biblioteca `iostream`;
- Biblioteca `string`;
- Biblioteca `iomanip`;
- Biblioteca `fstream`;
- Biblioteca `sstream`;
- Arrays;
- Estruturas condicionais;
- Estrutura de repetição `do while`;
- Estrutura de seleção `switch`;
- Funções próprias;
- Leitura e gravação de arquivos.

## 6. Organização dos arquivos

O projeto deve possuir a seguinte estrutura:

```text
sistema-bancario/
│
├── main.cpp
├── contas.txt
├── movimentacoes.txt
└── README.md
```

Os arquivos de dados são criados automaticamente pelo programa quando necessário.

## 7. Como executar

É necessário possuir um compilador C++ instalado.

### Compilação

No terminal, dentro da pasta do projeto, execute:

```bash
g++ main.cpp -o sistema_bancario
```

### Execução no Windows

```bash
sistema_bancario.exe
```

### Execução no Linux

```bash
./sistema_bancario
```

**Importante:** mantenha os arquivos `contas.txt` e `movimentacoes.txt` na mesma pasta em que o programa será executado, para que os dados sejam carregados e salvos corretamente.

## 8. Testes recomendados

Para verificar o funcionamento da persistência dos dados:

**Teste 1 – Cadastro e recuperação de contas**
1. Executar o programa.
2. Cadastrar três contas.
3. Encerrar o programa.
4. Executá-lo novamente.
5. Listar as contas cadastradas.

**Resultado esperado:** as contas devem continuar disponíveis com seus respectivos dados.

**Teste 2 – Persistência dos saldos**
1. Realizar um depósito.
2. Realizar um saque.
3. Encerrar o programa.
4. Executá-lo novamente.
5. Consultar os saldos.

**Resultado esperado:** os saldos devem permanecer atualizados.

**Teste 3 – Persistência das transferências**
1. Realizar uma transferência entre duas contas.
2. Encerrar o programa.
3. Executá-lo novamente.
4. Consultar as contas envolvidas.
5. Consultar os extratos.

**Resultado esperado:** os saldos devem permanecer atualizados e o histórico deve apresentar a saída e a entrada da transferência.

**Teste 4 – Histórico de movimentações**
1. Realizar depósitos, saques e transferências.
2. Encerrar o programa.
3. Executá-lo novamente.
4. Consultar o extrato de uma conta.

**Resultado esperado:** todas as movimentações anteriores devem continuar disponíveis.

---

## 9. Considerações finais

A Etapa 3 aprimora o sistema bancário desenvolvido nas etapas anteriores, acrescentando a utilização de arquivos para armazenamento permanente das informações.

Com isso, o programa consegue recuperar automaticamente as contas e movimentações registradas anteriormente, mantendo os dados disponíveis entre diferentes execuções.

**Centro Universitário de Viçosa – UNIVIÇOSA**

**Disciplina:** INF101 – Programação de Computadores I

**Etapa:** 3
