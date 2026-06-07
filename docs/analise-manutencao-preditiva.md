# Trabalho Final - Cenario 1: Manutencao Preditiva

## Integrantes

- Alexandre Rezende Silva - RA 5127545
- Raul Fernandes Silva Melo - RA 5170007
- Bruna Duarte Bueno - RA 5161875
- Matheus Lemes Carneiro - RA 5161892

## Problema escolhido

Uma fabrica possui motores eletricos nas linhas de producao. Com o tempo, esses motores podem apresentar desgaste mecanico, desalinhamento, aquecimento ou falha em rolamentos. Esses problemas costumam aparecer primeiro como aumento de vibracao e aumento de temperatura.

A solucao proposta monitora os sensores MQTT em tempo real para identificar sinais de falha antes que o equipamento pare a producao.

## Arquitetura

```mermaid
flowchart TD
    A["Sensores IoT das linhas de producao"] --> B["Broker MQTT<br/>76.13.175.168:1883"]
    B --> C["Node-RED<br/>Topico: sensores/#"]
    C --> D["Tratamento JSON e regras de alerta"]
    D --> E["Dashboard<br/>6 indicadores + 3 graficos + alerta"]
    E --> F["Tomada de decisao<br/>manutencao preventiva"]
```

## Regras de manutencao preditiva

- Temperatura normal: ate 35 graus Celsius.
- Temperatura em alerta: acima de 35 graus Celsius.
- Vibracao normal: ate 4 g.
- Vibracao em alerta: acima de 4 g.
- Se temperatura ou vibracao ultrapassar o limite, o dashboard mostra alerta de manutencao.

## Indicadores do dashboard

- Temperatura em graus Celsius.
- Umidade em porcentagem.
- Radiacao solar em W/m2.
- Pressao em bar.
- Vazao em L/min.
- Vibracao em g.

## Graficos historicos

- Historico de temperatura por linha.
- Historico de vibracao por linha.
- Historico de vazao por linha.

## Como importar o fluxo no Node-RED

1. Instale o Node.js.
2. Instale o Node-RED:

```bash
npm install -g --unsafe-perm node-red
```

3. Execute:

```bash
node-red
```

4. Acesse:

```text
http://localhost:1880
```

5. Instale o dashboard:

```text
Menu -> Manage palette -> Install -> node-red-dashboard
```

6. Importe o arquivo:

```text
node-red/fluxo-manutencao-preditiva.json
```

7. Clique em `Deploy`.
8. Abra o dashboard:

```text
http://localhost:1880/ui
```

## Analise esperada dos dados

O dashboard permite acompanhar se os motores estao operando dentro de uma faixa segura. Quando a temperatura sobe acima de 35 graus Celsius, pode existir sobrecarga, atrito, falha de refrigeracao ou operacao fora da condicao ideal. Quando a vibracao passa de 4 g, pode existir desalinhamento, desgaste, folga mecanica ou problema em rolamentos.

Com essas informacoes, a empresa pode agir antes da falha total, programando uma manutencao preventiva. Isso reduz paradas inesperadas, evita perda de producao, aumenta a vida util dos equipamentos e melhora a seguranca operacional.

## Beneficio economico

A principal economia vem da reducao de parada nao planejada. Em vez de esperar o motor quebrar e interromper a linha de producao, a empresa recebe um alerta antecipado e pode planejar a manutencao em um horario de menor impacto. Isso reduz custo de emergencia, desperdicio de materia-prima, horas extras e perda de produtividade.
