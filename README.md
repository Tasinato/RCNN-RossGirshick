# R-CNN — Anotações de estudo

Material de estudo organizado por **Rafael Tasinato** sobre detecção de objetos e a evolução da família R-CNN, com base nos artigos originais citados abaixo.

**Status:** documentação conceitual. Este repositório não contém implementação própria, modelos treinados ou resultados experimentais. Os métodos e as contribuições científicas pertencem aos autores das referências.

## Objetivos

- Compreender a combinação de propostas de regiões com redes neurais convolucionais.
- Diferenciar R-CNN, Fast R-CNN, Faster R-CNN e Mask R-CNN.
- Distinguir classificação, detecção de objetos e segmentação de instâncias.

## Conceitos essenciais

- **Classificação:** atribui uma categoria à imagem ou a uma região.
- **Detecção de objetos:** identifica categorias e localiza objetos por caixas delimitadoras (*bounding boxes*).
- **Segmentação semântica:** atribui classes aos pixels, sem separar necessariamente objetos da mesma classe.
- **Segmentação de instâncias:** produz uma máscara para cada objeto individual.
- **Características convolucionais:** representações aprendidas por uma CNN, utilizadas para reconhecer padrões visuais.

## Evolução da família R-CNN

| Método | Ideia central | Distinção importante |
| --- | --- | --- |
| **R-CNN** | Combina propostas de regiões com características extraídas por uma CNN para detectar objetos. | Processa as regiões individualmente; não utiliza a RPN introduzida posteriormente. |
| **Fast R-CNN** | Compartilha o cálculo das características convolucionais da imagem e utiliza RoI pooling para as regiões propostas. | Ainda depende de propostas de regiões externas à rede. |
| **Faster R-CNN** | Introduz a Region Proposal Network (RPN), que compartilha características com o detector. | A geração de propostas passa a ser aprendida por uma rede. |
| **Mask R-CNN** | Estende Faster R-CNN com um ramo de predição de máscaras e utiliza RoIAlign. | Acrescenta segmentação de instâncias à detecção. |

Esses métodos são trabalhos distintos. A autoria de toda a família não deve ser atribuída somente a Ross Girshick; cada artigo tem sua própria equipe de autores.

## Roteiro de leitura

1. Ler o artigo de R-CNN e identificar o papel das propostas de regiões e da CNN.
2. Comparar o compartilhamento de características no Fast R-CNN.
3. Estudar como a RPN modifica a geração de propostas no Faster R-CNN.
4. Examinar a predição de máscaras e o RoIAlign no Mask R-CNN.

## Referências e atribuição

1. **Girshick, R.; Donahue, J.; Darrell, T.; Malik, J.** *Rich feature hierarchies for accurate object detection and semantic segmentation*. CVPR, 2014. Preprint disponibilizado em 2013. [Artigo original — arXiv:1311.2524](https://arxiv.org/abs/1311.2524).
2. **Girshick, R.** *Fast R-CNN*. ICCV, 2015. [Artigo original — arXiv:1504.08083](https://arxiv.org/abs/1504.08083).
3. **Ren, S.; He, K.; Girshick, R.; Sun, J.** *Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks*. NeurIPS, 2015. [Artigo original — arXiv:1506.01497](https://arxiv.org/abs/1506.01497).
4. **He, K.; Gkioxari, G.; Dollár, P.; Girshick, R.** *Mask R-CNN*. ICCV, 2017. [Artigo original — arXiv:1703.06870](https://arxiv.org/abs/1703.06870).

As explicações acima são sínteses para estudo e não substituem a leitura dos artigos. A organização destas notas não implica autoria dos algoritmos, vínculo com os autores ou reprodução experimental dos resultados.

## Possíveis próximos passos

- Adicionar um exemplo didático com uma implementação de biblioteca, citando sua origem e licença.
- Documentar ambiente, dados públicos utilizados e instruções de execução.
- Registrar resultados somente após executar e avaliar os experimentos.

Esses itens são propostas de continuidade e ainda não estão implementados.
