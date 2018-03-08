# jquery-shopkart
This little plugin controls basic actions of a shoping cart display widget.

## Iniciar com as configurações padrões
```$.shopkart();```

### Estrutura básica contendo os atributos data necessário para utilização padrão do plugin
- ```data-kart="display"```: Indica o display que exibirá as informaçes do carrinho
- ```data-kart-total-item```: Indica a quantidade total de itens no carrinho
- ```data-kart-total-price```: Indica o valor total do carrinho
    
    
    
> Para exibir o display que contém a quantidade e o preço total do carrinho, deve ser criado um elemento com o atributo ```data-kart``` com o valor display:
```html
<div data-kart="display">
    <!-- Display do conteúdo do carrinho -->
</div>
```

> Para exibir o total de items do carrinho deve ser criado um elemento dentro do elemento ```data-kart="display"``` com o atributo ```data-kart-total-item```:
```html
<div data-kart="display">
    <div data-kart-total-item="0">
        <!-- Total de items -->
    </div>
</div>
```

> Para exibir o preço total do carrinho deve ser criado um elemento dentro do elemento ```data-kart="display"``` com o atributo ```data-kart-total-price```:
```html
<div data-kart="display">
    <div data-kart-total-item="0">
        <!-- Total de items -->
    </div>
    <div data-kart-total-price="0">
        <!-- Preço total -->
    </div>
</div>
```

> Para manipular o display do carrinho ao adicionar ou remover items, deve-se criar um elemento com três atributos data.
1. Para identificar o botão de cada item: ```data-kart="item-button"```
2. Para identificar o status de cada item: ```data-kart-item-status="[add-item|remove-item]"```
4. Deverá ser um objeto (json) de chave valor contendo os dados do item:. ```data-kart-item='{"key":"value"}'```
```html
<button
    data-kart="item-button"
    data-kart-item-status="add-item"
    data-kart-item='{"id": 1, "descricao": "Item 01", "valor": 100}'>
    Comprar
</button>
```

### Opções para configurações customizadas
> Customizar o valor da ação dos botões de Adicionar e Remover items:
```javascript
kartItemButtonStatus: {
     add: "foo",
     remove: "bar"
}
```
> Customizar os textos dos botões Adicionar e Remover items:
```javascript
kartItemButtonText: {
    add: 'Adicionar texto customizado',
    remove: 'Remover texto customizado'
}
```

> Customizar o total de items no carrinho:
```javascript
formatTotalItem: function (preco) {
    return total_item_customizado;
}
```

> Customizar o preço total do carrinho:
```javascript
formatTotalPrice: function (preco) {
    return total_preco_customizado;
}
```

> Customizar o estilo do botão Adicionar:
```javascript
styleButtonAddItem: function ($button) {
    // adicione seu próprio estilo. Ex.: $button.css('background-color': "black")
}
```

> Customizar o estilo do botão Remover:
```javascript
styleButtonRemoveItem: function ($button) {
    // adicione seu próprio estilo. Ex.: $button.css('background-color': "grey")
}
```
