Projeto AR-Móveis: Visualização de Objetos em Realidade Aumentada
===================================================================
Este projeto demonstra uma aplicação de Realidade Aumentada (RA) desenvolvida com Unity e Vuforia Engine. Ela permite aos usuários visualizar modelos 3D de móveis no ambiente real através da câmera de um dispositivo móvel, utilizando Image Targets (imagens impressas) para a detecção dos objetos virtuais.

Visão Geral
-------------------------------------------------------------------
O objetivo principal é proporcionar uma experiência interativa onde modelos 3D de móveis podem ser "trazidos" para o espaço físico do usuário, usando um marcador impresso como âncora de RA. Isso é ideal para pré-visualização de ambientes ou demonstrações interativas.

Móveis Atualmente Incluídos:
Cadeira Simples: Modelo básico para visualização.
Mesa de Centro: Para testar ocupação de superfície.
Luminária de Chão: Para simular objetos verticais e finos.

Funcionalidades
-------------------------------------------------------------------
Detecção de Image Target: Reconhecimento de imagens pré-definidas (Image Targets) impressas.
Sobreposição de Modelos 3D: Renderização virtual de móveis 3D sobre o Image Target detectado.
Visualização em Tempo Real: Manutenção do alinhamento do modelo 3D com o alvo ao mover o dispositivo ou o marcador.
Organização de Assets: Estrutura de pastas clara para modelos 3D e texturas.

Tecnologias Utilizadas
-------------------------------------------------------------------
Unity 3D: Game Engine para desenvolvimento da aplicação.
Vuforia Engine: SDK para detecção e rastreamento de Image Targets.
Modelos 3D: Formatos .fbx com texturas.
C#: Linguagem de programação para scripts Unity.

Configuração do Projeto
===================================================================
Siga os passos abaixo para configurar e executar o projeto em seu ambiente de desenvolvimento:

1. Clone o Repositório:
   git clone https://github.com/matheus54861/RV-RA-2025.git
   cd RV-RA-2025

2. Abra o Projeto no Unity:
   Abra o Unity Hub.
   Clique em "Add" e selecione a pasta raiz RV-RA-2025 do projeto clonado.
   Abra o projeto.

3. Configurar a Chave de Licença do Vuforia:
   No Unity Editor, vá para Window > Vuforia Engine > Configuration.
   Na seção "Vuforia Engine", insira sua Chave de Licença de Desenvolvimento do Vuforia. (Se você não tiver uma, crie gratuitamente no Vuforia Developer Portal).

4. Verificar Image Targets:
   O banco de dados de Image Targets (Furnitures.xml e Furnitures.dat) deve estar importado em Assets/StreamingAssets/Vuforia/.
   Na cena Unity, verifique se os objetos ImageTargetCadeira, ImageTargetLuminaria e ImageTargetMesa estão corretamente configurados para usar os alvos correspondentes do banco de dados Furnitures.

5. Verificar Modelos 3D:
   Confirme se os modelos 3D dos móveis (Wood_chair_1_low.fbx, FloorLamp.fbx, DPAM0035.fbx ou similares) estão localizados em Assets/Models (ou na pasta que você utilizou).
   Assegure-se de que esses modelos estão definidos como filhos dos respectivos ImageTargets na hierarquia da cena e que suas transformações (Posição, Rotação e Escala) estão ajustadas para a sobreposição correta.
   Dica de Ajuste: Para um posicionamento eficaz, considere "Resetar" a Transform (Botão Direito no componente Transform > Reset) e ajustar incrementalmente Position Y (para elevação), Rotation (especialmente X para verticalizar e Y para giro) e Scale (comece com valores pequenos como 0.01 ou 0.1 e aumente gradualmente).

Como Rodar
===================================================================

1. No Unity Editor (para testes com Webcam)
   Certifique-se de que sua webcam esteja conectada e funcionando.
   No Unity, vá em Window > Vuforia Engine > Configuration.
   Na seção "Device Tracker", em "Play Mode Type", selecione "WEBCAM" e escolha sua webcam em "Camera Device".
   Pressione o botão "Play" no Unity Editor.
   Apresente as folhas impressas dos Image Targets (cadeira, luminária, mesa) individualmente à câmera do seu computador. O modelo 3D correspondente deve aparecer sobreposto à imagem.

2. Em um Dispositivo Móvel (Android/iOS)
   Certifique-se de que as configurações de build para a plataforma móvel desejada estão corretas (File > Build Settings).
   Conecte seu dispositivo móvel ao computador.
   Em File > Build Settings, clique em "Build And Run".
   O aplicativo será construído e instalado no seu dispositivo.
   Abra o aplicativo no dispositivo e aponte a câmera para as folhas impressas dos Image Targets. Os móveis virtuais devem aparecer em Realidade Aumentada.

Preparando os Image Targets (Folhas Impressas)
-------------------------------------------------------------------
Para que a aplicação funcione, você precisará ter as imagens configuradas como Image Targets no Vuforia Developer Portal impressas em folhas de papel.

1. Obtenha as Imagens: Baixe as imagens que você configurou como Image Targets no Vuforia Developer Portal.
2. Imprima em Sulfite: Imprima cada imagem em uma folha de sulfite separada. Garanta boa qualidade de impressão, contraste e evite amassados ou danos, pois isso pode dificultar o rastreamento.
3. Iluminação: Utilize os Image Targets em ambientes com boa iluminação para otimizar o rastreamento.

Próximos Passos e Melhorias
===================================================================
Adicionar mais modelos de móveis para expandir o catálogo.
Implementar uma Interface de Usuário (UI) para seleção de móveis, ajuste de escala e rotação em tempo de execução.
Explorar oclusão para que os móveis virtuais sejam corretamente escondidos por objetos reais.
Implementar persistência de posição e rotação dos móveis.
Otimização de desempenho para dispositivos móveis.
