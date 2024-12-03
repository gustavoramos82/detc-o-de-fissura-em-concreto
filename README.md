# Utilizando redes neurais para classificação de fissura em concreto e pavimento

Aqui neste repositório, será disponibilido os códigos que foi utilizado para criar a rede e fazer calssficaçãos euma determinada estrutura de concreto ou pavimento tem fissura ou não.

Para isso, foram testadas as seguiente redes citadas a seguir (sendo que foi utilizado a blibiotecas keras e tensorflow para construir a rede e pegar as redes pré-treinadas disponibilizadas):
- VGG16
- ResNet50
- DenseNet121
- MobileNet

Os dados utilizados estão disponiveis no [kaggle](https://www.kaggle.com/datasets/oluwaseunad/concrete-and-pavement-crack-images) caso queira consultar os dados e construir a sua própria rede

## Sobre as redes utilizadas

**Tabela1**: Caracteristicas das redes utilizadas
|  | Total de parâmetros | Parametros treinaveis | Parametros não treinaveis | Tamanho Total |
| --- | --- | --- | --- | --- |
| VGG16 |  14.723.906  |   14.723.906  | 0    |  56,17 MB   |
| ResNet50 |   23.624.578 |   23.571.458  |  53.120   |   90,12 MB  |
| DenseNet121 |  7.055.938  |  6.972.290    |   83.648  |  26,92 MB   |
| MobileNet | 3.247.298   |   3.225.410  |  21.888   |   12.39 MB |



O intuito de escolher essas rede foi de escolher com diferentes parametros para analisar e verificar qual tem o melhor desempenho, levando em consideração o seu custo computacional

