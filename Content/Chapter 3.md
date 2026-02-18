## Chapter 3

Section 3.4.1 - The R.S Latch

| S | R | STATES |
|--|--|--|
| 0 | 0 | Inválido, Ambas as saídas viram 1. Viola a lógica do circuito. |
| 0 | 1 | Set, Força a saída Q para 1. |
| 1 | 0 | Reset, Força a saída Q para 0. |
| 1 | 1 | Repouso, Memória. Mantém o último estado (Set ou Reset) indefinidamente. |

https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWc0BMYAcKAsBOAzDgGyQDskeWJeIWhISCk9ApgLRhgBQYCEKCdMMRB5C6cMKYp69brxD86KdONHjl4qTIScA7iLESma8DmmQ9B8WDMKBduhf0mNVh1Esv7i0+cs+baQCSR39vcKUSPwAZdzxILHAQkQSoNIAzAEMAGwBnZhkLWICsRLBksFK0piy8gqQLAFk3ISZS60kFaB1mlxUaLHV+qW7OAA9wBBxwFCksajAUakTsEHyAF3GaPGsdmntKiBXEgEUtypIFdD48PnRE45AAJ2YNrfn1Qjosb0JppVOnCAA

Section 3.4.2 - The Gated D Latch

* **WE = 0 (Memória):** O "portão" está fechado, forçando as entradas do RS Latch para o estado de repouso (1, 1) e mantendo o valor armazenado, independentemente do que aconteça em **D**.
* **WE = 1 (Escrita):** O "portão" está aberto, permitindo que o valor de **D** (e seu inverso) chegue ao RS Latch, tornando a saída  uma cópia direta da entrada.

Basicamente: **WE=0** congela a memória; **WE=1** deixa o dado passar.

https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWc0FwCwCY0HYEA4cEMElURTJyBTAWjDACgwEJiA2cNygZjb08qUMUckxYh2EvP178M0kcNIMA7iFkD1fcAE5hkVVv5g9EhB0kG1G+TO2XDN82Y4n9hyW5fhsHK98lA7HcAWSNNNDRjLkUUBjCbBUi5BSE4gA8QNG5jHKznMDQINAkSgEUGTOy5Ng40Zww2HRALcsMwGMKSz0iodpjuSG7nQZL-PEoOyijNcaEklP5-GdssuSw+tQnweRAabmEwXf99w93T9QxBMQhtrs17oXJRZlueIc1RxWeEBgBJTiXSjbA6CKAoUQAGT2Bx2-DoRzhIkoADMAIYAGwAzlRngZoR0JBshMSROjsbikAZMoSMIiihJmFlAQB1ACihguoMB3P8tI2K2JhhmUzWRLGlQkkGaYG42EZMrQ00BAGVJVd5QduIyZI1mYSAEoMIA

Section 3.5 - The Concept of Memory

Exemplo:
• Endereço: 2 bits -> 4 Linhas (Gaveta 00, 01, 10, 11).
• Endereçabilidade: 8 bits (1 Byte, padrão atual).
• Capacidade Total: 4×8=32 bits.

A endereçabilidade é decidida pelo arquiteto do computador independentemente do número de gavetas. Eu posso ter um hotel com apenas 4 quartos (endereço de 2 bits), mas cada quarto pode ser uma suíte presidencial gigante que guarda 64 bits de uma vez

| No Hotel de Gavetas | No Computador (Seção 3.5) | Explicação Técnica |
| --- | --- | --- |
| **O número pintado na porta** | **Endereço (Address)** | O identificador único de uma localização de memória. |
| **O número total de gavetas na parede** | **Espaço de Endereçamento (3.5.1)** | Se você usa 2 bits para o endereço, você tem 4 gavetas. Se usa 20 bits, tem 1 milhão. |
| **A largura da gaveta (quantas folhas cabem)** | **Endereçabilidade (3.5.2)** | Quantos bits vivem em *cada* endereço. Geralmente é 8 bits (1 byte), mas pode ser maior. |
| **O Gerente com as chaves** | **Decodificador (3.5.3)** | O circuito que recebe o endereço (ex: "11") e ativa apenas a linha correspondente. |
| **A linha que destranca a gaveta** | **Word Line** | O fio que sai do decodificador e "acorda" os bits daquela linha específica. |
| **O crachá "AUTORIZADO"** | **WE (Write Enable)** | O sinal elétrico que permite gravar novos dados. Se for 0, é só leitura. Se for 1, grava. |
