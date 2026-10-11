|[&larr; Pagina-anterior](./pagina-21.md) | [Proxima-pagina &rarr;](./pagina23.md)|
|:---------:----------:|

# CAPITULO—02 Pagina 22
# O ARQUITETO


Para compreender fisicamente como o Sol poderia estar ativo desde o princípio sem atuar como um referencial astronômico nitidamente identificável na superfície terrestre, modelaremos a atmosfera como um filtro óptico de processamento de sinais. Na física computacional de atmosferas, a propagação da luz não é descrita apenas pela atenuação direta, representada pela Lei de Beer-Lambert, mas também pela Equação Integro-Diferencial de Transferência Radiativa (RTE), que permite considerar a absorção e o espalhamento da radiação.

Considerando um modelo plano-paralelo, a variação da intensidade específica da radiação \(I\) ao longo da profundidade óptica vertical \(\tau\) pode ser expressa, para um meio sem emissão térmica significativa na faixa espectral considerada, pela equação:

\[
\mu\frac{\partial I(\tau,\mu,\phi)}{\partial\tau}
=
I(\tau,\mu,\phi)
-
\frac{\omega_0}{4\pi}
\int_0^{2\pi}\int_{-1}^{1}
I(\tau,\mu',\phi')
P(\mu,\phi,\mu',\phi')
\,d\mu'\,d\phi'
\]

Nessa convenção, a profundidade óptica aumenta para dentro da atmosfera, e \(\mu\) é o cosseno do ângulo zenital medido em relação à direção vertical. A convenção angular e o sinal da equação devem ser mantidos consistentes com a definição da direção de propagação da radiação.

Nesta modelagem:

- \(\mu\) é o cosseno do ângulo zenital;
- \(\phi\) é o ângulo azimutal;
- \(\omega_0\) é o albedo de espalhamento simples, isto é, a razão entre o coeficiente de espalhamento e o coeficiente de extinção total;
- \(P\) é a função de fase, que descreve a distribuição angular da radiação espalhada;
- \(\tau\) é a profundidade óptica, que quantifica a extinção acumulada ao longo do caminho considerado.

Para resolver esse sistema em simulações computacionais, podemos aplicar o Método das Ordenadas Discretas (DOM), que transforma a dependência angular contínua em um sistema de equações diferenciais acopladas para um conjunto finito de direções de propagação.

Uma forma geral da equação discretizada é:

\[
\mu_i\frac{dI_i(\tau)}{d\tau}
=
I_i(\tau)
-
\frac{\omega_0}{4\pi}
\sum_{j=1}^{N}
W_j I_j(\tau)P_{ij}
\]

em que \(W_j\) representa os pesos da quadratura angular, incluindo a integração azimutal conforme a discretização adotada. Para uma quadratura unidimensional com simetria azimutal, a expressão pode ser reduzida a uma soma ponderada sobre as direções representadas pelos nós angulares. Os fatores numéricos dependem da normalização da função de fase e da quadratura escolhida.

A solução completa exige condições de contorno no topo e na base da atmosfera, além de parâmetros que representem sua composição, absorção, espalhamento e geometria de iluminação.

A partir desse modelo, podemos investigar dois estados ópticos hipotéticos: um em que a atmosfera apresenta profundidade óptica elevada, reduzindo fortemente a transmissão direta da radiação, e outro em que a profundidade óptica é menor, permitindo maior transmissão do feixe solar.

Esses estados serão utilizados como modelos físicos para examinar a hipótese interpretativa que relaciona a luz do primeiro dia aos luminares apresentados no quarto dia de Gênesis. Eles não constituem, por si mesmos, uma demonstração de que a atmosfera terrestre tenha passado historicamente por essa transição na sequência narrada.

## Diagrama de transferência radiativa: transição óptica atmosférica

```text
================================================================================
DIAGRAMA DE TRANSFERÊNCIA RADIATIVA: DOIS ESTADOS ÓPTICOS HIPOTÉTICOS
================================================================================

ESTADO 1: PRIMEIRO DIA — DOMÍNIO DO ESPALHAMENTO MÚLTIPLO
Referência narrativa: Gênesis 1:2-4

[FONTE: SOL]
       |
       v
[TOPO DA ATMOSFERA PRIMITIVA]
       |
       |  Meio opticamente espesso
       |  τ >> 1
       |  ω₀ próximo de 1, caso predomine o espalhamento
       |
       |  *  *  *  *  *  *  *
       |   *  *  *  *  *  *
       |  Interações sucessivas entre radiação e partículas
       |  Atenuação do feixe direto e redistribuição angular
       v
[SUPERFÍCIE TERRESTRE]
       |
       +--> Feixe direto: muito reduzido
       |
       +--> Luz difusa: depende das propriedades do meio
       |
       +--> Visibilidade do disco solar: depende da radiância
            difusa e da distribuição angular do espalhamento

--------------------------------------------------------------------------------

ESTADO 2: QUARTO DIA — MAIOR TRANSMISSÃO DIRETA
Referência narrativa: Gênesis 1:14-19

[FONTE: SOL]
       |
       v
[TOPO DA ATMOSFERA]
       |
       |  Meio opticamente menos espesso
       |  τ << 1
       |  Menor extinção ao longo do caminho óptico
       |
       |  Feixe direto mais intenso
       |  Menor contribuição relativa do espalhamento
       v
[SUPERFÍCIE TERRESTRE]
       |
       +--> Feixe direto: maior transmissão
       |
       +--> Luz difusa: ainda presente, dependendo do meio
       |
       +--> Maior possibilidade de identificar os luminares
            e utilizá-los como referências astronômicas

================================================================================
Observação: os estados representam cenários físicos hipotéticos, não uma
reconstrução comprovada da atmosfera terrestre em cada dia de Gênesis.
================================================================================
```

|[&larr; Pagina-anterior](./pagina-21.md) | [Proxima-pagina &rarr;](./pagina23.md)|
|:---------:----------:|


