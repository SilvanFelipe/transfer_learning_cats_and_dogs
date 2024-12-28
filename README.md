# Projeto de Transfer Learning com VGG16

Este projeto utiliza Transfer Learning com o modelo pré-treinado VGG16 para realizar a classificação de imagens de gatos e cachorros.

## Estrutura do Projeto

### 1. **Download e Preparação do Dataset**
- O dataset `cats_and_dogs_filtered` é baixado automaticamente e extraído.
- O conjunto é dividido em pastas de treino e validação.

### 2. **Data Augmentation**
- Aplicação de técnicas de aumento de dados, como:
  - Flip horizontal.
  - Rotação aleatória.

### 3. **Modelo Pré-Treinado**
- O modelo VGG16 é utilizado com pesos pré-treinados no dataset ImageNet.
- Camadas superiores do modelo são descongeladas durante o fine-tuning.

### 4. **Treinamento**
- O modelo é treinado em duas etapas:
  1. Treinamento inicial com as camadas do VGG16 congeladas.
  2. Fine-tuning com as camadas descongeladas para ajustes finais.

### 5. **Salvamento e Carregamento do Modelo**
- O modelo treinado é salvo em um arquivo `.h5` para reutilização futura.

---

## Como Usar

### Pré-requisitos
- Python 3.7+
- Bibliotecas:
  - `tensorflow`
  - `numpy`
  - `matplotlib`

### Execução

1. Abra o Google Colab e carregue o notebook:
   - Faça o upload do arquivo `.ipynb` no Colab ou abra diretamente do Google Drive.

2. Execute as células na ordem para:
   - Baixar e preparar o dataset.
   - Treinar o modelo.
   - Salvar o modelo no arquivo `cats_dogs_model.h5`.

### Avaliação do Modelo

Para carregar o modelo salvo e avaliar novas imagens, adicione as seguintes células ao notebook:
```python
from tensorflow.keras.models import load_model
model = load_model("cats_dogs_model.h5")
# Avaliação de novas imagens...
```

---

## Resultados Esperados

O script gera gráficos de:
- Precisão de treino e validação.
- Loss de treino e validação.

Esses gráficos ajudam a monitorar o desempenho do modelo durante o treinamento e fine-tuning.

---

## Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.

---

## Licença
Este projeto é distribuído sob a licença MIT. Consulte o arquivo `LICENSE` para mais detalhes.
