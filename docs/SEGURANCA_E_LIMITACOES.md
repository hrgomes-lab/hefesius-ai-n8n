# Segurança, publicação e limitações

## Tratamento realizado nesta versão pública

- Removidos identificadores no nível do workflow (`id`, `versionId`) e metadados da instância.
- Gerados novos IDs aleatórios para nodes, condições e atribuições.
- Substituído o identificador do formulário (`webhookId`) por um novo identificador aleatório de demonstração.
- Eliminada a URL interna em cache para Data Table e esvaziada a seleção original da tabela no node `Get row(s)`.
- Nenhuma credencial ou token foi identificado nos arquivos recebidos para a revisão estática; isso **não é garantia genérica** para futuras exportações.
- Removida uma atribuição vazia e sem nome do exercício introdutório.
- Mantidos nomes de nodes e expressões JavaScript que fazem parte da lógica.

## Passos obrigatórios antes do uso

1. Criar Data Table no n8n do ambiente receptor; abrir `Get row(s)` e selecionar a tabela nova.
2. Verificar funcionamento do Form Trigger e os novos links de teste/produção.
3. Conferir os quatro caminhos de resposta após a importação.
4. Não publicar formulários de demonstração ou links de produção antes de revisar autenticação, controle de acesso e proteção contra abuso.
5. Nunca substituir uma tabela de produção por preços ou estoques deste exemplo.

## Limitações de funcionalidade

- Não registra pedidos persistentes, não sincroniza estoques, não realiza pagamento ou entrega, não envia respostas ao cliente.
- Sem inteligência artificial generativa integrada neste estágio.
- `Get row(s)` limita a primeira linha correspondente; não resolve produtos duplicados.
- `.item` e `.first()` foram usadas em workflow demonstrativo de um pedido por vez; revisar para lotes.
- A conversão `Number.isFinite(...) ? Number(...) : 0` previne NaN, mas colapsa valores inválidos para zero e requer validação mais rigorosa para serviços externos.
- Testes de portabilidade (importar em outra instância) **não foram executados** neste pacote.

## O que não publicar

- Backups originais sem revisão; documentos reais de fornecedores; telefones de clientes; credenciais; links privados de webhook; configurações de produção.
- Capturas com dados pessoais, URLs privadas ou identificadores operacionais sem antes ocultá-los.

O repositório foi preparado para estudo e demonstração, não certificado como seguro para produção.
