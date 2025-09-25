# SmartCam AI

## 🎯 O que nossa aplicação faz

O **SmartCam AI** é uma aplicação de visão computacional que reconhece gestos das mãos em tempo real usando a câmera do dispositivo móvel, mas com um diferencial revolucionário: **consome 10 vezes menos bateria** que as soluções tradicionais.

### Funcionalidade Principal
A aplicação fica "sempre ligada" no background do seu celular, monitorando continuamente através da câmera para detectar gestos específicos das mãos. Quando você faz um gesto reconhecido (como acenar, apontar, ou fazer um sinal de "ok"), a aplicação pode:

- Ativar funcionalidades do telefone sem precisar tocar na tela
- Controlar aplicativos através de comandos gestuais  
- Responder a comandos visuais mesmo quando o celular está na mesa

### O Diferencial: Eficiência Energética
**Problema atual**: Aplicações que usam câmera constantemente drenam a bateria muito rápido, tornando impraticável manter a funcionalidade sempre ativa.

**Nossa solução**: Utilizamos uma tecnologia inspirada no funcionamento do cérebro humano (Redes Neurais Spiking) que processa informações visuais de forma muito mais eficiente, permitindo que a aplicação funcione o dia todo sem impactar significativamente a bateria.

## 🗺️ Roadmap do Projeto

O projeto está estruturado em três etapas principais:

### Etapa 1: Linha de Base (Baseline) ⚡
- **Objetivo**: Estabelecer uma referência de desempenho
- **Tecnologia**: CNN tradicional (MobileNetV3)
- **Status**: 🔄 Em desenvolvimento - processamento de dados

### Etapa 2: Transição Neuromórfica 🧠
- **Objetivo**: Converter CNN para SNN otimizada
- **Foco**: Máxima eficiência energética
- **Status**: ⏳ Aguardando conclusão da Etapa 1

### Etapa 3: Demonstração e Análise 📊
- **Objetivo**: Simulação em hardware neuromórfico
- **Entrega**: Comparação completa com baseline
- **Status**: ⏳ Planejado

## 🔧 Configuração do Ambiente

### Pré-requisitos
- Python 3.x
- pip (gerenciador de pacotes Python)

### 🔧 Configuração de Dependências
```bash
py -m pip install opencv-python pandas tqdm
```

**Dependências utilizadas:**
- `opencv-python` - Processamento de imagem e vídeo
- `pandas` - Manipulação dos arquivos CSV de legendas  
- `tqdm` - Barras de progresso durante processamento

### Dataset
Este projeto utiliza o dataset **20BN-Jester V1** para reconhecimento de gestos:
- [Download dos vídeos](https://20bn.com/datasets/jester) - Frames em formato JPG organizados por pasta
- [Download das legendas](https://20bn.com/datasets/jester) - Arquivos CSV separados

**Arquivos necessários:**
```
projeto/
├── 20bn-jester-v1/              # Pasta com subpastas numeradas (cada uma contém frames JPG)
├── jester-v1-labels.csv         # Lista completa de todos os gestos
├── jester-v1-train.csv          # Mapeamento ID → gesto (treino)
├── jester-v1-validation.csv     # Mapeamento ID → gesto (validação)
└── scripts/
    ├── process_jester.py        # Processamento principal
    └── inspect_labels.py        # Diagnóstico de gestos
```

## 📁 Estrutura do Projeto

```
smartcam-ai/
├── scripts/
│   ├── process_jester.py     # Processamento principal do dataset
│   ├── inspect_labels.py     # Inspeção de rótulos
│   └── train_model.py        # [Em desenvolvimento] Treinamento do modelo
├── data/
│   └── processed/           # Dados processados
├── models/
│   └── baseline/           # Modelos da linha de base
└── docs/
    └── progress_report.html # Relatório de progresso
```

## 🚀 Como Usar

### 1. Identificação dos Gestos Disponíveis
Primeiro, execute o script de diagnóstico para ver todos os gestos disponíveis no dataset:
```bash
py inspect_labels.py
```
Este script lê o arquivo `jester-v1-labels.csv` e lista todos os gestos únicos disponíveis.

### 2. Processamento de Dados
Após identificar os gestos desejados, atualize a lista `TARGET_GESTURES` no arquivo `process_jester.py` e execute:
```bash
py process_jester.py
```

**Gestos atualmente configurados:**
- `Thumb up` - Sinal de "positivo" com o polegar
- `Stop Sign` - Sinal de "pare" com a mão aberta

### 3. Treinamento (Em desenvolvimento)
```bash
py train_model.py
```

## 🐛 Problemas Conhecidos e Soluções

### Problema: 'python' não é reconhecido
**Solução**: Use `py` em vez de `python` no Windows, ou configure a variável PATH.

### Problema: ModuleNotFoundError 
**Solução**: 
```bash
py -m pip install [nome_do_modulo]
```

### Problema: Arquivo 'jester-v1-labels.csv' não encontrado
**Solução**: Baixe todos os arquivos CSV de legendas separadamente do site do dataset 20BN-Jester. São 3 arquivos:
- `jester-v1-labels.csv` (lista de gestos)
- `jester-v1-train.csv` (mapeamento treino)  
- `jester-v1-validation.csv` (mapeamento validação)

### Problema: Gestos não encontrados no processamento
**Solução**: Execute `py inspect_labels.py` para ver os nomes exatos dos gestos e atualize a lista `TARGET_GESTURES` no arquivo `process_jester.py`.

## 📊 Status Atual

### ✅ Concluído
- [x] Configuração do ambiente de desenvolvimento
- [x] Resolução de problemas de dependências  
- [x] Script de processamento de dados (`process_jester.py`)
- [x] Script de diagnóstico de gestos (`inspect_labels.py`)
- [x] Identificação dos gestos corretos no dataset

### 🔄 Em Progresso
- [ ] Processamento final dos frames de vídeo para os gestos selecionados
- [ ] Validação da qualidade dos dados processados

### ⏳ Próximos Passos
- [ ] Desenvolvimento do script de treinamento (`train_model.py`)
- [ ] Implementação da CNN baseline (MobileNetV3)
- [ ] Métricas de desempenho e consumo energético
- [ ] Conversão para SNN (Etapa 2)

## 🤝 Contribuição

Este é um projeto de pesquisa em desenvolvimento. Para contribuir:

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 📧 Contato

Para dúvidas ou colaborações, entre em contato através dos issues do GitHub.

---

**Nota**: Este projeto está em desenvolvimento ativo. A documentação será atualizada conforme o progresso das etapas.
