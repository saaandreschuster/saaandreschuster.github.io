# Inspetor / Validador CNAB 240

Ferramenta web para **inspecionar, validar e editar** arquivos CNAB 240 (remessa e retorno) direto no navegador. É um único arquivo `index.html` (HTML + CSS + JavaScript inline, sem bibliotecas externas e sem build).

> **Privacidade:** todo o processamento acontece **no seu navegador**. Nenhum arquivo é enviado a servidores — os dados de remessa/retorno não saem da sua máquina.

## Recursos

- **Detecção automática de banco** pelas posições 1–3 da primeira linha.
- **Bancos com leiaute e validação próprios:**
  - Sicredi (748) — Pagamento a Fornecedor
  - Itaú (341) — SISPAG
  - Banco do Brasil (001)
- **Modo genérico FEBRABAN** para bancos sem plugin dedicado: exibe os campos pelo leiaute padrão (pagamentos e cobrança — segmentos P, Q, R, S, T, U, Y) sem aplicar regras específicas, com opção de validar pelo FEBRABAN.
- **Segmentos "fora do manual"** são sinalizados e exibidos pelo leiaute genérico, sem validação específica.
- **Inspeção de remessa** com validação campo a campo (tamanho de 240 bytes, numérico/data/código de barras, regras do banco) e destaque dos erros.
- **Inspeção de retorno** com decodificação das ocorrências e status por registro (Efetivado / Aceito-Agendado / Informativo / Rejeitado) para os três bancos, com resumo por classe e valor confirmado.
- **Editor de campos:** botão **Editar** abre uma tela com todos os registros e seus campos editáveis (respeitando tamanho e tipo de cada posição), com busca, aplicação com reanálise e download do `.REM` editado.
- **Ferramenta de código de barras:** decodifica código de barras (44 díg.) e linha digitável de boleto (47) e de convênio/arrecadação (48), com round-trip barras ↔ linha.
- **Exportação de relatório em PDF** (offline, sem bibliotecas).
- Arrastar-e-soltar arquivo, colar conteúdo e leitura via seletor de arquivo.

## Como usar

Acesse a página publicada ou abra o `index.html` localmente (basta abrir o arquivo no navegador). Em seguida:

1. Cole o conteúdo de um arquivo `.REM`/`.RET` (240 colunas por linha), arraste o arquivo para a área de entrada ou use **Abrir arquivo…**.
2. Clique em **Analisar**.
3. Use o menu lateral para alternar entre **Inspecionar CNAB 240**, **Inspecionar Retorno** e a ferramenta de **Código de Barras**.
4. Para alterar campos, clique em **Editar**, ajuste os valores e use **Aplicar e reanalisar** ou **Baixar .REM**.

## Publicação no GitHub Pages

O projeto é totalmente estático. Para publicar:

1. Coloque o `index.html` na raiz do repositório (ou na pasta `/docs`).
2. Em **Settings → Pages**, selecione a branch e a pasta correspondente.
3. A página fica disponível em `https://<usuario>.github.io/<repositorio>/`.

O GitHub Pages serve via HTTPS, necessário para o funcionamento pleno da leitura de arquivos e do download do `.REM`.

## Aviso

Ferramenta de apoio à conferência de arquivos CNAB 240. As tabelas de leiautes e ocorrências seguem os manuais dos bancos e o padrão FEBRABAN, mas podem existir variações por versão/convênio. Confira sempre com o manual vigente do seu banco antes de usar em produção.
