# KEITHLEY OTA — DMM 2100

Software de aquisição de dados para o multímetro digital **Keithley 2100 DMM**, desenvolvido para medições laboratoriais via comunicação **USB/VISA**.

O programa foi estruturado para operar o Keithley 2100 como instrumento de aquisição, sem aplicação de tensão ou corrente pelo software. A comunicação foi validada usando comandos SCPI com o método `write_raw + read_bytes`, adequado ao comportamento observado durante os testes com o equipamento.

## Versão

**v1.0**

Primeira versão estável do programa.

## Principais recursos

- Comunicação USBTMC/VISA com Keithley 2100 DMM.
- Interface gráfica no padrão visual LayTech.
- Aquisição em tempo real.
- Salvamento automático em arquivo TXT ponto a ponto.
- Seleção de pasta de salvamento.
- Gráficos em tempo real.
- Eixo X padrão por número da amostra.
- Verificação de drivers VISA.
- Links de suporte para instalação de drivers.
- Organização por abas independentes para cada modo de medição.

## Modos de medição disponíveis

- Tensão DC
- Tensão AC
- Corrente DC
- Corrente AC
- Resistência 2 fios
- Resistência 4 fios
- Frequência
- Período
- Continuidade
- Diodo
- Temperatura RTD

## Comunicação

A comunicação com o Keithley 2100 é feita por USB/VISA. Durante os testes, o método padrão `query()` apresentou instabilidade em algumas leituras. Por isso, a comunicação do programa foi baseada em:

```python
write_raw + read_bytes
