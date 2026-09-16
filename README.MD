```mermaid
erDiagram
    PERFIL_ACESSO ||--o{ FUNCIONARIO : define
    CLIENTE o|--o{ VENDA : realiza
    FUNCIONARIO ||--o{ VENDA : registra
    VENDA ||--|{ ITEM_VENDA : possui
    PRODUTO ||--o{ ITEM_VENDA : compoe
    VENDA ||--o{ PAGAMENTO : recebe
    VENDA ||--o| ENTREGA : gera
    FORNECEDOR ||--o{ COMPRA : atende
    FUNCIONARIO ||--o{ COMPRA : registra
    COMPRA ||--|{ ITEM_COMPRA : possui
    PRODUTO ||--o{ ITEM_COMPRA : compoe
    CATEGORIA ||--o{ PRODUTO : classifica
    PRODUTO ||--o{ MOVIMENTACAO_ESTOQUE : possui
    FUNCIONARIO ||--o{ MOVIMENTACAO_ESTOQUE : executa
    ITEM_VENDA ||--o{ POS_VENDA : origina
    CLIENTE ||--o{ POS_VENDA : solicita
    FUNCIONARIO ||--o{ POS_VENDA : atende

    PERFIL_ACESSO {
        id_perfil
        nome
        descricao
    }
    FUNCIONARIO {
        id_funcionario
        nome
        cpf
        cargo
        login
        senha_hash
        status
    }
    CLIENTE {
        id_cliente 
        nome
        cpf
        telefone
        email
        data_cadastro
        status
    }
    CATEGORIA {
        id_categoria
        nome
        descricao
        status
    }
    PRODUTO {
        id_produto 
        sku
        nome
        marca
        condicao
        preco_venda
        estoque_minimo
        controla_serie
        status
    }
    FORNECEDOR {
        id_fornecedor 
        razao_social
        cnpj
        telefone
        email
        status
    }
    COMPRA {
        id_compra 
        data_compra
        numero_documento
        status
        valor_total
    }
    ITEM_COMPRA {
        id_item_compra 
        quantidade
        custo_unitario
        lote
        numero_serie
    }
    VENDA {
        id_venda 
        data_venda
        canal
        status
        subtotal
        desconto_total
        frete
        valor_total
    }
    ITEM_VENDA {
        id_item_venda 
        quantidade
        preco_unitario
        desconto
        numero_serie
    }
    PAGAMENTO {
        id_pagamento 
        forma
        valor
        data_pagamento
        status
        codigo_transacao
    }
    ENTREGA {
        id_entrega 
        modalidade
        destinatario
        endereco
        valor_frete
        codigo_rastreio
        status
    }
    MOVIMENTACAO_ESTOQUE {
        id_movimentacao 
        tipo
        quantidade
        data_hora
        motivo
        saldo_posterior
    }
    POS_VENDA {
        id_pos_venda 
        tipo
        data_solicitacao
        motivo
        status
        prazo
        resolucao
    }
```

---