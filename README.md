
# Introdução
Este é um simples projeto final para a matéria de Álgebra Linear Algorítmica no ano de 2022.1, ministrada pelo professor João Antônio Recio da Paixão, no curso de Ciência da Computacão da UFRJ.

O intuito deste projeto é desenvolver uma **ferramenta que borre o rosto de uma pessoa em uma foto ou vídeo** e **explorar como aplicar blur em uma imagem usando álgebra linear usando o** ***Filtro Gaussiano(GaussianBlur)***

# Funcionamento

O código desse projeto também está disponível para ser usado em um [notebook no Google Colaboratory](https://colab.research.google.com/drive/1sIAmw0SzXdhPXB8pVGIm2pLdSdVUxRhq?usp=sharing), sendo necessário o uso da GPU para o funcionamento da biblioteca *dlib* no Colab, necessário para a IA.

Para o reconhecimento dos rostos, foi usada a IA conhecida como [face_recognition](https://github.com/ageitgey/face_recognition), feita por [ageitgey](https://github.com/ageitgey), pois é uma API bem simples e documentada de Python.

No notebook há 4 funções principais:
  - ***censura_rosto***
    >Esta função possui como entrada (filename, top, right, bottom, left), sendo o filename o nome/caminho do arquivo a ser alterado e o "top, right, bottom, left" a posição, em pixels, do rosto encontrado pela IA.
    
    >Possui como especificação aplicar um filtro gaussiano apenas na região do rosto especificado.
  - ***censura_foto***
    >Esta função possui como entrada (filename, number_of_times_to_upsample = 2), sendo o filename o nome/caminho da foto a ser alterada e um parâmetro opcional "number_of_times_to_upsample", que comanda a precisão para encontar os rostos mais distantes na imagem, porém quanto mais alto é o valor, mais lento fica. Definido como 2 por padrão.
    
    >Possui como especificação aplicar um filtro gaussiano apenas nos rostos encontrados pela IA na imagem.
  - ***extrai_video***
    >Esta função possui como entrada (filename), sendo o filename o nome/caminho do vídeo a ser extraído em todos os seus frames e seu audio.
    
    >Possui como especificação colocar todos os frames inalterados do vídeo no formato .png e seu áudio no formato .mp3 na pasta "./video"
  - ***censura_video***
    >Esta função possui como entrada (filename, number_of_times_to_upsample = 1), sendo o filename o nome/caminho do vídeo a ser alterado e um parâmetro opcional "number_of_times_to_upsample", que comanda a precisão para encontar os rostos mais distantes em cada frame, porém quanto mais alto é o valor, mais lento fica. Definido como 1 por padrão.

    >Possui como especificação aplicar um filtro gaussiano apenas nos rostos encontrados pela IA em cada frame e ser rápido o suficiente para retornar um vídeo curto com seus frames alterados e seu áudio.

***Para saber mais sobre essas funções e o funcionamento do Filtro Gaussiano, veja a Wiki***

# Exemplo de Uso

## Em Imagens 
 - Foto original: 
    >![test](https://user-images.githubusercontent.com/69607669/177061094-5fc257af-2be2-4198-98aa-e08eb92b700a.jpg)

 - Resultado:
    >![test (1)](https://user-images.githubusercontent.com/69607669/177061163-27d59317-2c48-4641-ae32-44b9a4f02c9b.jpg)

## Em Vídeos
 - Vídeo original
    >![Nautica_SS18_Campaign_Video_15_Sec_AdobeExpress](https://user-images.githubusercontent.com/69607669/177062452-df7865fa-1bda-4c2a-b3d3-5357ccb29303.gif)

 - Resultado
   >![finished_video__1__AdobeExpress](https://user-images.githubusercontent.com/69607669/177062454-6f0d9b4c-f316-4860-bf20-74bf35f47b76.gif)
   
# Limitações
  - A IA não consegue identificar um rosto se há alguma obstrução na face, isso pode causar erros frequentes nos vídeos
  - A IA não consegue indentificar uma face em que não esteja olhando diretamente para a câmera, isso pode causar erros frequentes em fotos e vídeos
  - A IA não consegue encontrar um rosto muito distante sem um alto custo computacional e com precisão, o que causa erros frequentes em algumas fotos e vídeos.
  - [A IA reconhece com menor taxa de sucesso rostos em um arquivo .jpg, logo o ideal seria no formato .png](https://github.com/ageitgey/face_recognition/issues/1421)
  - Imagens com baixa iluminação possuem uma baixa taxa de reconhecimento
  - Vídeos muito grandes demoram muito para serem analisados
# Agradecimentos 
  - Ao professor João Paixão pelas aulas
  - Ao [face_recognition](https://github.com/ageitgey/face_recognition) pela IA
  - Ao Google pela GPU usada no Colab
  - Ao [OpenCV](https://docs.opencv.org/4.x/index.html) pela útil biblioteca em python 
# Autor
  - Manoel Marcelo da Silva [@manoelmms](https://github.com/manoelmms)
