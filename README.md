# Lançador do WhatsApp

Este projeto é uma página HTML simples que permite aos usuários gerar um link para o WhatsApp inserindo um número de telefone e aplicando transformações opcionais ao número. A interface é interativa, com campos de entrada, caixas de seleção e um botão para processar os dados.

## Funcionalidades

1. **Entrada de Número de Telefone**:
   - Um campo de texto onde o usuário pode inserir o número de telefone.
   - O número é automaticamente limpo para conter apenas caracteres numéricos.

2. **Remover Zeros à Esquerda**:
   - Uma caixa de seleção chamada "Remover zeros à esquerda".
   - Quando marcada, remove os zeros iniciais do número de telefone.

3. **Adicionar Código do País**:
   - Uma caixa de seleção chamada "Adicionar código do país".
   - Quando marcada, adiciona um código de país ao número de telefone.
   - O código do país pode ser personalizado em um campo de entrada adicional (máximo de 3 dígitos).

4. **Máscara de Número Internacional**:
   - O botão exibe o número de telefone formatado em um formato internacional amigável, como:
     - `+55 (XX) XXXX-XXXX` para números com 12 dígitos.
     - `+55 (XX) XXXXX-XXXX` para números com 13 dígitos.
     - Outros números são formatados como `+XX (XXX) XXX-XXXX`.

5. **Gerar Link do WhatsApp**:
   - Um botão chamado "Abrir Conversa".
   - Quando clicado, o número de telefone é processado com base nas opções selecionadas, e o link do WhatsApp é aberto em uma nova aba no formato:  
     `https://wa.me/<número_processado>`.

## Como Funciona

1. O usuário insere um número de telefone no campo de entrada.
2. O usuário pode opcionalmente:
   - Marcar a caixa "Remover zeros à esquerda" para remover zeros iniciais.
   - Marcar a caixa "Adicionar código do país" para adicionar um código de país.
   - Inserir um código de país personalizado no campo correspondente.
3. O botão exibe o número formatado dinamicamente.
4. Ao clicar no botão "Abrir Conversa", a função `launchWhatsApp` é executada:
   - O número é limpo para conter apenas números.
   - Se a opção "Remover zeros à esquerda" estiver marcada, os zeros iniciais são removidos.
   - Se a opção "Adicionar código do país" estiver marcada, o código do país é adicionado (padrão: `55`).
   - O link do WhatsApp é gerado e aberto em uma nova aba.

## Como Usar

1. Abra o arquivo HTML em um navegador.
2. Insira o número de telefone no campo de entrada.
3. Selecione as opções desejadas:
   - Remover zeros à esquerda.
   - Adicionar código do país (e insira um código personalizado, se necessário).
4. O botão exibirá o número formatado.
5. Clique no botão "Abrir Conversa" para abrir o link gerado.

## Exemplo

### Entrada:
- Número de telefone: `00123456789`
- Opções:
  - Remover zeros à esquerda: Marcado.
  - Adicionar código do país: Marcado.
  - Código do país personalizado: `1`.

### Saída:
- Botão: `Abrir Conversa com +1 (12) 3456-789`
- Link gerado: `https://wa.me/1123456789`

## Tecnologias Utilizadas

- **HTML**: Estrutura da página.
- **CSS**: Estilização da interface.
- **JavaScript**: Processamento do número de telefone, formatação e geração do link do WhatsApp.

## Personalização

- **Código do País Padrão**:  
  O código do país padrão é `55`. Para alterar, modifique o valor padrão no campo `customCountryCode`:
  ```html
  <input type="text" id="customCountryCode" value="55" ...>
  ```

- **Formatação de Números**:  
  A formatação dos números pode ser ajustada nas funções `formatPhoneNumber12`, `formatPhoneNumber13` e `formatI18nPhoneNumber`.

## Licença

Este projeto é de uso livre para fins pessoais ou educacionais.