# Importação de documentos de fauna doméstica do SEI

Use este fluxo para manter originais e versões rastreáveis na cópia local do projeto.

## Organização

- `dados/sei/<processo>/originais/<protocolo>__<nome-original>`: cópia integral de cada documento.
- `dados/sei/<processo>/extraidos/<protocolo>/`: conteúdo extraído dos ZIPs e, posteriormente, texto por página e tabelas.
- `dados/sei/<processo>/manifesto.csv`: protocolo, nome no SEI, nome original, caminho e SHA-256.
- `dados/sei/<processo>/revisoes/`: conferências humanas.
- `dados/sei/<processo>/consolidado/`: resultados após revisão.

Os arquivos reais permanecem na cópia local, conforme o `.gitignore` existente. O script de organização não faz upload nem altera os arquivos originais em Downloads.

## Executar a organização

Depois de atualizar sua cópia do projeto, abra o PowerShell na pasta do projeto e execute:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\scripts\organizar-sei-fauna.ps1
```

O script usa Downloads como origem e a raiz do próprio projeto como destino. Se necessário, informe `-Origem "D:\OutraPasta"` ou `-Projeto "D:\Projetos\pedrohugo"`. Confirme o resumo de arquivos copiados e ausentes. Ausência ou falha não significa importação concluída.

## Preparação da consolidação

1. Preserve o PDF ou ZIP original e seu protocolo. Extraia ZIPs em pastas próprias, sem misturar versões.
2. Produza texto com identificação da página física de cada PDF; registre se foi necessário OCR.
3. Mantenha a relação entre cada tabela, mapa ou arquivo extraído e o ZIP de origem.
4. Separe inventário, evacuação, resgate, atendimento veterinário e dessedentação. Associe mapas, ART, fichas e cartilhas aos planos.
5. Identifique versões pelo protocolo e pelo conteúdo. Um protocolo mais recente, isoladamente, não comprova substituição integral do anterior.
6. Para cada valor consolidado, registre documento, página ou aba/célula, trecho e situação de revisão.
7. Não some inventários de versões diferentes. Registre divergências e estabeleça a versão de referência antes de calcular totais.

Este fluxo organiza arquivos; não executa OCR, não extrai automaticamente tabelas de PDFs e não aprova dados para consolidação.
