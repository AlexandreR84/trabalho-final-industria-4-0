# Trabalho Final - Industria 4.0

Projeto academico para o componente **Industria 4.0**, com foco no cenario **Manutencao Preditiva**.

## Objetivo

Monitorar dados industriais recebidos via MQTT e apresentar um dashboard em tempo real no Node-RED para apoiar a tomada de decisao.

## Cenario escolhido

**Cenario 1 - Manutencao Preditiva**

O problema tratado e o desgaste em motores eletricos das linhas de producao. A solucao monitora temperatura e vibracao para identificar sinais de falha antes da parada do equipamento.

## Regras de alerta

- Temperatura acima de 35 graus Celsius.
- Vibracao acima de 4 g.

Quando uma dessas condicoes ocorre, o dashboard exibe um alerta de manutencao.

## Arquivos principais

- `node-red-fluxo-manutencao-preditiva.json`: fluxo pronto para importar no Node-RED.
- `README-manutencao-preditiva.md`: explicacao do problema, arquitetura, indicadores e beneficio economico.
- `roteiro-pitch-manutencao-preditiva.md`: roteiro para apresentacao de 5 minutos.
- `TrabalhoFinalInd_Ostria40.pdf`: enunciado original do trabalho.

## Como executar

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

5. Instale o dashboard pelo menu:

```text
Menu -> Manage palette -> Install -> node-red-dashboard
```

6. Importe o fluxo:

```text
node-red-fluxo-manutencao-preditiva.json
```

7. Clique em `Deploy`.
8. Abra o dashboard:

```text
http://localhost:1880/ui
```

## Broker MQTT

- Broker: `76.13.175.168`
- Porta: `1883`
- Topico usado: `sensores/#`
