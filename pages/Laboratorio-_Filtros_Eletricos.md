# Laboratório: Filtros Elétricos

## Objetivos

Verificar o de funcionamento dos **filtros elétricos RC e RL**.

## Procedimentos Práticos

### Filtro RC passa baixa

1.  Monte no **SimulIDE** o circuito do **filtro RC passa baixa** da figura abaixo, usando o **resistor** de 68Ω e o **capacitor** de 22uF:

<a href="Arquivo:FiltroRC_PassaBaixa.png" class="wikilink" title="Arquivo:FiltroRC_PassaBaixa.png">Arquivo:FiltroRC_PassaBaixa.png</a>

1.  Utilize como entrada do filtro um **gerador de funções**, configurado para gerar uma **onda senoidal** com **frequência** de 10 Hz e **tensão** variando de 0 V a 5 V.
2.  Utilize o **canal 1** osciloscópio para observar a **forma de onda** gerada pelo **gerador de funções** (v<sub>in</sub>) e o **canal 2** para observar a forma de onda sobre o **capacitor** (v<sub>out</sub>).
3.  Gradualmente aumente a **frequência** da **onda senoidal** até 1000 Hz e observe no **canal 2** a redução da amplitude da forma de onda sobre o capacitor.
4.  Ajuste a frequência da **onda senoidal** no **canal 1** até que a amplitude da onda no **canal B** seja 3,5 V, ou seja, 70,7% da amplitude da entrada (5 . 0,707 ≈ 3,5).

### Filtro RC passa alta

1.  Monte no **SimulIDE** o circuito do **filtro RC passa alta** da figura abaixo, usando o **resistor** de 68Ω e o **capacitor** de 10uF. Observe que o **resistor** está conectado a tensão de 2,5 V e não ao terra. Verifique se a frequência ajustada corresponde a **frequência de corte** teórica.

<a href="Arquivo:FiltroRC_PassaAlta.png" class="wikilink" title="Arquivo:FiltroRC_PassaAlta.png">Arquivo:FiltroRC_PassaAlta.png</a>

1.  Utilize como entrada do filtro um **gerador de funções**, configurado para gerar uma **onda senoidal** com **frequência** de 10 Hz e **tensão** variando de 0 V a 5 V.
2.  Utilize o **canal 1** osciloscópio para observar a **forma de onda** gerada pelo **gerador de funções** (v<sub>in</sub>) e o **canal 2** para observar a forma de onda sobre o **resistor** (v<sub>out</sub>).
3.  Gradualmente aumente a **frequência** da **onda senoidal** até 1000 Hz e observe no **canal 2** o aumento da amplitude da forma de onda sobre o resistor.
4.  Ajuste a frequência da **onda senoidal** no **canal 1** até que a amplitude da onda no **canal B** seja 3,5 V, ou seja, 70,7% da amplitude da entrada (5 . 0,707 ≈ 3,5). Verifique se a frequência ajustada corresponde a **frequência de corte** teórica.

Análise do circuito  
É importante notar que o **resistor** no **filtro passa alta** está conectado a uma referência de tensão de 2,5 V e não ao terra. Isto é necessário pois o **filtro passa alta** não permite a passagem de **corrente contínua** (CC), podendo ser visto como um circuito que remove a componente de corrente contínua do sinal. O nível tensão CC (2,5 V) do outro lado do resistor ajusta a componente CC da saída do filtro para o valor médio da excursão do sinal de saída, uma vez que não há componente contínua no sinal de saída. Se o resistor fosse referenciado ao terra, a saída alternada oscilaria com valores positivos e negativos em torno da referência zero.

### Filtro RL passa baixa

1.  Monte no **SimulIDE** o circuito do **filtro RL passa baixa** da figura abaixo, usando o **resistor** de 68Ω e o **indutor** de 100mH:

<a href="Arquivo:FiltroRL_PassaBaixa.png" class="wikilink" title="Arquivo:FiltroRL_PassaBaixa.png">Arquivo:FiltroRL_PassaBaixa.png</a>

1.  Utilize como entrada do filtro um **gerador de funções**, configurado para gerar uma **onda senoidal** com **frequência** de 10 Hz e **tensão** variando de 0 V a 5 V.
2.  Utilize o **canal 1** osciloscópio para observar a **forma de onda** gerada pelo **gerador de funções** (v<sub>in</sub>) e o **canal 2** para observar a forma de onda sobre o **resistor** (v<sub>out</sub>).
3.  Gradualmente aumente a **frequência** da **onda senoidal** até 1000 Hz e observe no **canal 2** a redução da amplitude da forma de onda sobre o resistor.
4.  Ajuste a frequência da **onda senoidal** no **canal 1** até que a amplitude da onda no **canal B** seja 3,5 V, ou seja, 70,7% da amplitude da entrada (5 . 0,707 ≈ 3,5). Verifique se a frequência ajustada corresponde a **frequência de corte** teórica.

## Observações e Conclusões

- **Filtros elétricos** são circuitos que permitem a passagem de terminadas **frequências** e limitam outras.
- Filtros simples podem ser construídos com componentes passivos, como os **filtros RC** e **filtros RL**.
- Na **frequência de corte** dos filtros a tensão da saída atinge 70,7% da tensão da entrada.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 12h23min de 1 de outubro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
