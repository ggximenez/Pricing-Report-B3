# Automatização da Extração de Dados dos Boletins Pricing Reports da B3

<a target="_blank" href="https://colab.research.google.com/github/ggximenez/Princing-Report-B3/blob/main/pricing_reports_b3.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

Este projeto tem como objetivo automatizar a extração de dados dos boletins Pricing Reports da B3, através de um Jupyter Notebook. O notebook pode ser executado no Google Colaboratory, tornando a solução facilmente acessível e utilizável em qualquer lugar.

O script Python foi desenvolvido para:

1. Baixar automaticamente arquivos zip diários do site da B3 dentro de um intervalo de datas especificado.
2. Extrair arquivos XML dos arquivos zip e armazená-los para análise.
3. Processar arquivos XML para extrair dados úteis e formatá-los em um formato legível e útil.
4. Remover arquivos desnecessários para economizar espaço em disco.

## Pré-requisitos

Para executar este notebook, é necessário ter instalado Python 3.6 ou superior. Além disso, o script requer os seguintes pacotes Python: `os`, `zipfile`, `pandas`, `numpy`, `re`, `requests`, `glob` e `xml.etree.ElementTree`. O script tem uma função que verificará se esses módulos estão instalados e, se não, tentará instalá-los automaticamente.

## Como usar

1. Defina o intervalo de datas para os boletins que você deseja extrair.
2. Execute todas as células do notebook.

Os arquivos baixados serão salvos em uma pasta chamada 'downloads'. Os arquivos XML extraídos serão salvos em uma pasta chamada 'xmls'. Os arquivos com o sufixo mais alto para cada data serão mantidos e todos os outros serão removidos para economizar espaço em disco. Finalmente, os arquivos XML são processados para extrair a informação desejada.

## Funções

O script principal inclui várias funções para facilitar a reutilização e a organização do código:

- `install_and_import()`: Instala e importa os módulos necessários.
- `extract_zip()`: Extrai arquivos ZIP para um diretório especificado.
- `processar_arquivo()`: Processa os arquivos XML e extrai os dados necessários.

## Estrutura de Dados

O script foi projetado para lidar com a estrutura específica dos boletins Pricing Reports da B3. Isso inclui a extração de dados de várias tags XML, como `TradQty`, `PlcOfListg`, `OthrId`, `FinInstrmAttrbts` e outras. Os dados são então formatados e armazenados em dicionários Python para fácil manipulação e análise.

Os dados extraídos são salvos como uma lista de dicionários, onde cada dicionário representa uma única entrada de dados no boletim. As chaves do dicionário são as tags XML do boletim, e os valores são os dados associados a essas tags.

Ao fim, a lista de dicionários é convertida para um DataFrame Pandas armazenado na variável `df_total`.

## Nota

Este script foi desenvolvido para lidar com um formato de arquivo específico e pode não funcionar corretamente se o formato dos boletins Pricing Reports da B3 for alterado. Certifique-se de verificar regularmente se o script ainda está funcionando conforme o esperado e não hesite em modificar o código para atender às suas necessidades específicas.

## Contribuindo

Sinta-se à vontade para fazer fork e contribuir para este projeto. Se você encontrar qualquer problema ou tiver sugestões de melhorias, por favor, abra uma issue ou pull request.

## Licença

Este projeto é licenciado sob a MIT License - veja o arquivo LICENSE.md para mais detalhes.

