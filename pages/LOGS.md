### Vasco Log

09/08

\- acertei o \#define Z_PROBE_OFFSET_FROM_EXTRUDER -2.0 // --\> é preciso ainda mexer neste valor para ajustar certinho

\- O bed leveling está como bilinear com 9 pontos. NOTA: é preciso retirar o G28 do startup dos gcodes, senão ele tira o bed_levelling sempre que inicia uma impressão!!!

O startup manual recomendado (que depois pode passara para o GCODE ou para o startup do pronterface é o seguinte:

G28 (home xyz) G29 (bed levelling) G28 (home xyz) M420s1 (para ligar o bed leveling M420v1 (para ver se deu certo)

Uma outra opção no futuro é passar para o EEPROM da placa de forma a não ter que fazer G29 sempre que se inicia (e se faz reset) a impressora

13/08

\- Foi colocada a mesa de Aluminio. Persiste o problema do aquecimento da mesa. **É necessário colocar cola na mesa para já**.

\- A alimentação do filamento não está fiável. É preciso ver uma forma do motor não encravar lá em cima. Pode ser preciso apertar/desapertar o parafuso de aperto e talvez também o parafuso do rolamento.

\- No código, mudei o Z_PROBE_OFFSET_FROM_EXTRUDER de -1.9 para -1.5 devido a mudança de material detetado pelo sensor (alumínio). Caso seja necessário diminuir 0.05 para -1.45 ou para 1.40.

\- É necessário ainda passar a calibração da mesa para o EEPROM!

\- **Falta nivelar a mesa!**.

16/08

\- Foi ajustado o Z_PROBE_OFFSET_FROM_EXTRUDER para -1.45. Este parece ser o valor correto, na atual calibração.

\- Os problemas de fiabilidade da alimentação do filamento continuam. No entanto a impressora está funcionando normalmente agora. Foi impresso mais um cubo, desta vez com brim, no que resultou um objeto sem alargamento nas primeiras camadas.

\- Aproveitamos também para ajustar o apoio da mesa aquecida e colocar o sensor da mesa no lugar.

\- Falta furar a mesa.
