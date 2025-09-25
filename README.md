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

### Instalação de Dependências
```bash
py -m pip install opencv-python pandas tqdm
```

### Dataset
Este projeto utiliza o dataset **20BN-Jester V1** para reconhecimento de gestos:
- [Download dos vídeos](https://20bn.com/datasets/jester)
- [Download das legendas](https://20bn.com/datasets/jester) (arquivos .csv separados)

Estrutura de arquivos esperada:
```
projeto/
├── 20bn-jester-v1/          # Vídeos do dataset
├── jester-v1-train.csv      # Legendas de treino
├── jester-v1-validation.csv # Legendas de validação
└── scripts/
    ├── process_jester.py    # Processamento de dados
    └── inspect_labels.py    # Diagnóstico de gestos
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

### 1. Processamento de Dados
Primeiro, execute o script de diagnóstico para identificar os gestos disponíveis:
```bash
py inspect_labels.py
```

Em seguida, processe o dataset:
```bash
py process_jester.py
```

### 2. Treinamento (Em desenvolvimento)
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

### Problema: Arquivos .csv não encontrados
**Solução**: Baixe os arquivos de legenda separadamente do site do dataset 20BN-Jester.

## 📊 Status Atual

### ✅ Concluído
- [x] Configuração do ambiente de desenvolvimento
- [x] Resolução de problemas de dependências
- [x] Script de processamento de dados funcional
- [x] Script de diagnóstico de rótulos

### 🔄 Em Progresso
- [ ] Identificação dos gestos corretos no dataset
- [ ] Processamento final dos frames de vídeo
- [ ] Atualização da lista `TARGET_GESTURES`

### ⏳ Próximos Passos
- [ ] Desenvolvimento do script de treinamento
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
