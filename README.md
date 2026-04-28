O AutiNet é um sistema de tecnologia assistiva de código aberto projetado para prever crises comportamentais no Transtorno do Espectro Autista (TEA) antes que elas ocorram.
Diferente de sistemas reativos que detectam a crise quando ela já começou, o AutiNet utiliza uma arquitetura de fluxo duplo para identificar:

    Instabilidade Neurofisiológica: Sinais internos de sobrecarga sensorial.
    Intenção Motora: Micro-ajustes posturais que precedem o ato de levantar ou movimentos impulsivos.

A convergência desses dois sinais permite criar uma Janela de Intervenção (em segundos), permitindo que cuidadores ajam de forma preventiva e ética.
🧠 Arquitetura Técnica
O sistema executa dois modelos de Deep Learning de forma síncrona, otimizados para hardware Intel:

    Modelo A (Neuro-State): Processa 23 canais de sinais temporais. Identifica a trajetória de perda de organização temporal e aumento de estresse.
    Modelo B (Motor-Intent): Processa 3 canais (IMU/Acelerômetro). Detecta a intenção motora de levantar "por baixo do radar".

Otimizações Intel®

    Quantização INT8: Modelos comprimidos via Intel® Neural Compressor, reduzindo a latência e o consumo de memória em dispositivos de borda.
    Inferência Local: Executado via Intel® OpenVINO™ Toolkit, garantindo que nenhum dado sensível saia do dispositivo (Privacy by Design).

🚀 Como Rodar o Projeto
1. Requisitos

    Python 3.10+
    Processador Intel® (CPU, iGPU ou NPU)

2. Instalação
bash

# Clone o repositório
git clone https://github.com
cd AutiNet

# Instale as dependências
pip install -r requirements.txt

Use o código com cuidado.
3. Estrutura de Pastas
Certifique-se de que os modelos estão na pasta correta:
text

AutiNet/
├── dashboard.py
├── models/
│   ├── neural_state.xml  <-- Modelo de 23 canais
│   ├── neural_state.bin
│   ├── motor_intent.xml  <-- Modelo de 3 canais
│   └── motor_intent.bin
└── requirements.txt

Use o código com cuidado.
4. Execução
bash

streamlit run dashboard.py

Use o código com cuidado.
📊 Casos de Uso Monitorados
O dashboard simula e monitora 10 cenários críticos, incluindo:

    Fuga (Elopement): Alta intenção motora + Stress interno elevado.
    Crise Silenciosa: Corpo estático, mas mente em sobrecarga severa.
    Movimento Funcional: Redução de falsos positivos quando o usuário levanta sem estar em estresse.

⚖️ Ética e Transparência (XAI)
O AutiNet utiliza Inteligência Artificial Explicável. Cada alerta é acompanhado de uma justificativa técnica e uma sugestão de política de ação (ex: Intervenção suave vs. Ajuste ambiental), garantindo que o cuidador tome a decisão final baseada em evidências de sinais.
📄 Licença
Este projeto é distribuído sob a licença Apache 2.0. Sinta-se à vontade para contribuir e adaptar para diferentes contextos clínicos e de pesquisa.
Disclaimer: Este sistema é uma ferramenta de suporte e pesquisa. Não constitui diagnóstico médico autônomo.
