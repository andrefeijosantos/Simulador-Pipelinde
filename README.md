# Simulador Pipeline
Contribuidores: André Feijó, Natascha Palhares, Rafael Crevelari, Ricardo ferreira e Pedro Fioro.

## **Bem-vindo(a) ao Simulador Pipeline!** 

Este é um simulador de pipeline desenvolvido para fins acadêmicos. Para utilizá-lo, siga os passos abaixo:</br>

**Passo 1:** Executar as Células de Dependências e Imports.</br>
Na primeira etapa, você precisará executar as células de "Dependências" e "Imports e Definições Globais". Essas células garantem que todas as bibliotecas necessárias estejam carregadas e as definições globais estejam configuradas corretamente.</br></br>

**Passo 2:** Escolher uma Instância de Teste</br>
Em seguida, você precisa escolher a instância de teste que deseja utilizar. Você tem duas opções: Simulador ou Corretor. Essas instâncias estão numeradas de 1 a 8 e são pré-definidas. Se você deseja usar uma instância de teste personalizada, também pode carregar seu próprio arquivo de teste em formato .txt.

Para carregar sua própria instância de teste, clique em "Arquivo de Teste" e selecione o arquivo .txt no seu computador. Em seguida, escolha a opção "NOVO" para indicar que é uma instância personalizada. Para fazer upload de uma instância de teste, é importante que cada linha do arquivo .txt atenda à seguinte formatação:</br>
</br>
$instr$ $reg_d$ $reg_{src1}$ $reg_{src2}$ $reg_{src3}$ </br>
</br>
onde $instr$ é o nome da instrução e $reg_d$ e $reg_{src_i}$ são os *ids* (valor numérico) dos registradores de destino e fonte, respectivamente, que deseja utilizar (*e.g.:* "addf 3 4 5"). As instruções suportadas são *addf*, *addi*, *mulf*, *ld* e *sd*.
Também é importante que o código respeite a sintaxe. Esta versão **NÃO** verifica a validade da sintaxe inserida.

Por fim, selecione o número de ciclos que deseja executar.</br></br>

**Passo 3:** Verificar seu código</br>
Depois, você precisa executar a célula "Instância de Teste". Essa célula irá mostrar o código que será executado com base nas suas escolhas anteriores. Você pode revisar o código gerado para entender como o simulador de pipeline irá processar as instruções.
</br></br>
Após ter concluído os passos anteriores, você está pronto(a) para executar o Simulador de Pipeline! Você pode apenas simular uma tabela ou corrigir uma que tenha feito. Após os resultados, é possível assistir uma animação do caso de teste inserido executando a célula "Animação", no final do Colab.
</br></br>

### **O Simulador**
Para simular uma tabela, execute a Célula "Simulador". O simulador irá processar as instruções da instância de teste selecionada. Após a execução do Simulador, você verá uma tabela com os resultados na saída da célula. Essa tabela irá mostrar informações detalhadas sobre as instruções processadas pelo pipeline, incluindo os ciclos de clock, os estágios do pipeline e os registros envolvidos. Você pode revisar os resultados na tabela para analisar o desempenho do pipeline e entender como as instruções foram executadas.

Lembre-se de que o Colab pode cortar a tabela se forem executados mais do que 19 ciclos. No entanto, você pode fazer o download da tabela em formato CSV para análises mais detalhadas (Opcional). Para isso, vá em "Arquivos" na barra de menu do Colab e clique em "result.csv". Em seguida, selecione "Fazer Download" para salvar a tabela em seu computador.
</br></br>

### **O Corretor**
O Corretor é uma ferramenta que permite comparar a tabela de resultados gerada pelo Simulador com uma tabela fornecida pelo usuário em formato .txt. Ao executar a célula "Arquivo da Tabela", você pode carregar o arquivo com a tabela que deseja comparar. Certifique-se de que o arquivo esteja no formato .txt e contenha a tabela de resultados no formato adequado, o qual cada instrução é representada em uma única linha e os estágios do pipeline são separados por espaços. Se houver uma coluna em branco, preencha-a com o caractere "*". Por exemplo, a instância de teste 1 ficaria:</br>
</br>
F D A0 A1 A2 W</br>
\* F D D D M0 M1 M2 M3 M4 W</br>
</br>
Após carregar o arquivo com a tabela, o Corretor irá solicitar que você selecione a organização das colunas da tabela. Você pode escolher entre "por ciclos" ou "por estágios", dependendo de como os resultados estão organizados no arquivo.</br>
Por fim, o Corretor irá comparar a tabela do arquivo CSV com os resultados gerados pelo Simulador. Se as tabelas forem idênticas, você receberá a mensagem "TABELAS IGUAIS!!!" indicando que não há diferenças entre elas. Caso contrário, o Corretor irá mostrar as duas tabelas, destacando as diferenças para que você possa identificá-las.</br>
Lembre-se de que o Colab pode cortar a tabela se forem executados mais do que 19 ciclos. No entanto, você pode fazer o download da tabela em formato CSV para análises mais detalhadas (Opcional). Para isso, vá em "Arquivos" na barra de menu do Colab e clique em "result.csv". Em seguida, selecione "Fazer Download" para salvar a tabela em seu computador.
</br></br>
### **Notas dos Desenvolvedores**
Ao final, há uma célula de texto com algumas notas de como o simulador foi desenvolvido.
