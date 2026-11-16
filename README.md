# Soma-dos-quadrados-com-memoria-distribuida
Demonstrar que processos diferentes possuem dados locais separados e cooperam para resolver um cálculo: a soma dos quadrados de 0 até N-1

## Como funciona

1. O rank 0 cria a lista `0..N-1` e a divide de forma cíclica.
2. `scatter` entrega uma sublista a cada processo.
3. Cada processo calcula sua soma parcial.
4. `gather` reúne os resultados no rank 0, que confere com o cálculo sequencial.

## Execução

    mpiexec -n 4 python pratica3_soma_quadrados.py --n 12

Saída esperada: soma distribuída `506` e `[CORRETO?] True`.
