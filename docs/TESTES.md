# Testes manuais — Hefesius AI

## Evidência histórica (ambiente original)

Esses testes foram realizados manualmente durante o desenvolvimento e conferidos por capturas de tela, não por testes automatizados. Os resultados abaixo dizem respeito ao workflow original, antes da preparação do pacote público.

| Cenário | Entrada | Resultado observado |
|---|---|---|
| Pedido disponível | iPhone 13, 2 un.; estoque 3; preço unitário 2200 | `disponivel`, `valor_total: 4400` e mensagem `R$ 4.400,00` |
| Estoque insuficiente | iPhone 13, 5 un.; estoque 3 | `estoque_insuficiente` e mensagem dinâmica |
| Produto não cadastrado | iPhone 17, 1 un. | `produto_nao_cadastrado`, modelo e quantidade preservados |
| Zero unidades | iPhone 13, 0 un. | `quantidade_invalida` e `Get row(s)` não executado |
| Valor negativo | iPhone 13, -3 un. | Caminho de quantidade inválida |
| Valor fracionário | iPhone 13, 1.5 un. | Caminho de quantidade inválida |
| Regressão após conversão segura | iPhone 13, 2 un. | Caminho de pedido disponível executado |
| Regressão após conversão segura | iPhone 13, 0 un. | Caminho de quantidade inválida executado |

## Testes a repetir após importar os JSONs públicos

- [ ] Criar tabela com `dados/produtos_exemplo.csv` e religar `Get row(s)`.
- [ ] Executar manualmente o Workflow 01 e conferir a comparação.
- [ ] Enviar iPhone 13 com quantidade 2 e conferir resultado 4400.
- [ ] Enviar iPhone 13 com quantidade 5 e conferir indisponibilidade.
- [ ] Enviar iPhone 17 com quantidade 1 e conferir produto não cadastrado.
- [ ] Enviar zero, negativo e fracionário, conferindo bloqueio antes de consultar tabela.
- [ ] Testar entradas vazias/malformadas e confirmar comportamento do formulário.
- [ ] Verificar duplicação de nomes no catálogo e comportamento do limite 1.
- [ ] Confirmar que o formulário não está publicamente acessível antes de configurar controles adequados.

> Não marcar esses testes de reinstalação como concluídos sem efetivamente realizá-los.
