# Roteiro do pitch - 5 minutos

## Integrantes

- Alexandre Rezende Silva - RA 5127545
- Raul Fernandes Silva Melo - RA 5170007
- Bruna Duarte Bueno - RA 5161875
- Matheus Lemes Carneiro - RA 5161892
- Luciano Roberto Monteiro Araújo - RA 5160512

## 1. Abertura

Nosso projeto resolve um problema comum na industria: falhas inesperadas em motores eletricos das linhas de producao.

Quando um motor apresenta desgaste, normalmente os primeiros sinais aparecem nos sensores de vibracao e temperatura. Por isso, criamos uma solucao de manutencao preditiva com MQTT, Node-RED e dashboard em tempo real.

## 2. Problema

Uma parada inesperada de motor pode interromper a producao, gerar prejuizo, atrasar entregas e aumentar o custo de manutencao. O objetivo e identificar sinais de falha antes que o equipamento pare.

## 3. Solucao

Os sensores das cinco linhas enviam dados para o broker MQTT no topico `sensores/#`. O Node-RED recebe essas mensagens, converte o JSON, separa os sensores e aplica regras de alerta.

As regras principais sao:

- Temperatura acima de 35 graus Celsius indica risco de aquecimento.
- Vibracao acima de 4 g indica risco de desgaste mecanico.

## 4. Dashboard

O dashboard apresenta seis indicadores em tempo real: temperatura, umidade, radiacao solar, pressao, vazao e vibracao.

Tambem temos tres graficos historicos: temperatura, vibracao e vazao. Esses graficos ajudam a perceber tendencia, variacao por linha e comportamento anormal ao longo do tempo.

Quando algum limite e ultrapassado, o sistema exibe um alerta de manutencao.

## 5. Tomada de decisao

Com esse alerta, a empresa pode verificar o motor, programar manutencao preventiva e evitar uma parada nao planejada.

## 6. Beneficio economico

O beneficio economico esta na reducao de paradas inesperadas, menor custo com manutencao emergencial, maior vida util dos equipamentos e aumento da disponibilidade da linha de producao.

## 7. Fechamento

Portanto, a solucao transforma dados de sensores IoT em informacao util para decisao. Ela mostra nao apenas o valor atual dos sensores, mas tambem quando o equipamento esta entrando em uma condicao de risco.
