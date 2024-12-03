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

### Análise do treinamento das redes

Observando a função perda e acurácia durante o treinamento, podemos observar, segundo os graficos abaixo que:

![função perd](https://github.com/user-attachments/assets/4b72d879-f51f-4886-a843-355a49e20b39)

![acurácia](https://github.com/user-attachments/assets/0ca9fa59-0f5c-47a6-9446-4c9616b8bd23)

![tempo de treinamento](https://github.com/user-attachments/assets/2ec2dd29-49a3-4bd1-b11e-252d95cf7103)


- O Densenet121 teve uma boa convergencia
- VGG 16 foi o que teve o menor entre todos durante o treinamento
- Resnet50 e MobileNet tiveram um bom durante a epoca 4 e no quinto começaram a divergir
- Apesar de o DenseNet121 ter menos paramentro quanto o VGG16 e o ResNet 50 seu tempo de trinamento foi maior

### Resultados

**Tabela2**: Desempenho dos modelos
|  | Acurácia | Precisão | Recall | Tempo de inferencia do conjunto teste | 
| --- | --- | --- | --- | --- |
| VGG16 |   0,9794444441795349  |    0,9794444441795349 |  0,9794444441795349   |  5s | 
| ResNet50 |  0,9872221946716309 |   0,9872221946716309  |  0,9872221946716309  | 11s | 
| DenseNet121 |  0,9931111335754395 |  0,9931111335754395    |   0,9931111335754395 |  21s |
| MobileNet | 0,9506666660308838   |   0,9506666660308838 |  0,9506666660308838   |  5s

#### Conclusões e possibilidades de trabalhos futuros

- Todos os modelos tiveram um bom desempenho (acima de 95% nas métricas)
- O modelo que teve o melhor desempenho foi DenseNet121, mais foi o que demorou mais para o treino e fazer a inferências dos resultados no conjunto teste
- O MobileNet foi o mais rápido dentre todos, mas foi o que teve o menor desempenho, mas podemos melhorar seus parametros para melhorar o seu desempenho, tornando um modelo que seja eficiente e com uma boa perfomace

A partir disso, aplicação do modelo depende do cenário que queremos aplicar, inbclusive utilizar esses modelos como base de outros modeo mais robustos de segmentação semântica , por exemplo

- Se for pela acurácia, o DenseNet121 seria o melhor caso
- Se for para da reposta mais rápida, o Mobilenet ou o VGG16 seria a melhor opção
- Se for o meio termo o ResNet50 seria a melhor opção


