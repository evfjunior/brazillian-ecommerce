# brazillian-ecommerce
A data analysis project about brazillian e-commerce.<br>
Um projeto de análise de dados sobre o comércio online brasileiro.


## Introdução
<p>Este projeto se baseia em dados públicos divulgados pela Olist ( https://olist.com/ ), um dos maiores marketplaces do comércio online no Brasil. Os dados foram coletados no Kaggle ( https://kaggle.com/ ).</p>
<p>Os datasets contém mais de 100 mil registros de compra, no período de setembro de 2016 a setembro de 2018, com informações sobre produtos, compras, clientes, opinião de satisfação, entre outros.</p>

## Os Dados
<p>A seguir, teremos uma descrição dos datasets e seus conteúdos  (Versão 4).</p>

<p><b><i>geolocation_olist_public_dataset.csv</i></b>:<br>
Este dataset inclui latitudes e longitudes aleatórias a partir de um dado prefixo de CEP.</p>

<ul>
  <li><b>zip_code_prefix</b>:
    São os três primeiros dígitos de um CEP;</li>
  <li><b>city</b>:
    Cidade associada ao CEP.</li>
</ul>

<p><b><i>olist_classified_public_dataset.csv</i></b>:<br>
Este dataset inclui 3584 linhas, as mesmas 21 características do dataset não classificado e mais alguns dados de classificação.<br>
Ele foi classificado por três analistas independentes. Cada analista votou em qual classe ele julgava que um comentário deveria pertencer. Assim, classificamos um comentário escolhendo a classe mais votada.</p>

<ul>
  <li><b>votes_before_estimate</b>:
    Votos recebidos por mensagens com indicação de recebimento do produto antes da data estimada;</li>
  <li><b>votes_delayed</b>:
    Votos recebidos por reclamação de atraso;</li>
  <li><b>votes_low_quality</b>:
    Votos recebidos por reclamação de baixa qualidade no produto;</li>
  <li><b>votes_return</b>:
    Votos recebidos por mensagens de clientes com desejo de devolução do produto ao vendedor;</li>
  <li><b>votes_not_as_anounced</b>:
    Votos recebidos por reclamação de produto diferente do anunciado;</li>
  <li><b>votes_partial_delivery</b>:
    Votos recebidos por reclamação de entrega parcial (nem todos os produtos foram entregues);</li>
  <li><b>votes_other_delivery</b>:
    Outros tipos de reclamação envolvendo a entrega;</li>
  <li><b>votes_other_order</b>:
    Outros tipos de reclamação envolvendo o pedido;</li>
  <li><b>votes_satisfied</b>:
    Votos recebidos por mensagens de clientes satisfeitos;</li>
  <li><b>most_voted_subclass</b>:
    Seleciona a sublclasse mais votada para o comentário;</li>
  <li><b>most_voted_class</b>:
    Agrega sublclasses em três classes (satisfeito, problemas com a entrega e problemas com a qualidade).</li>
</ul>

<p><b><i>olist_public_dataset_v2.csv</i></b>:<br>
Este dataset inclui 100 mil linhas e 21 características.<br>  
Observações:
<ul>
  <li>Note que um comentário talvez possa se repetir se uma compra tiver dois ou mais produtos diferentes;</li>
  <li>Uma compra pode ser realizada por mais de um vendedor se o cliente comprar mais de um produto;</li>
  <li>Alguns comentários de avaliação possuem dados pessoais como número de telefone, então foi feita uma busca <i>regex</i> para substituir cada grupo de 3 dígitos por '000'. Isso pode bagunçar também outros dados que não sejam números de telefone no meio dos comentários;</li>
  <li>Todos os textos identificando lojas e seus parceiros foram substituídos por nomes das grandes casas de Game of Thrones.</li>
</ul></p>

<ul>
  <li><b>order_id</b>:
    Identificador único da compra;</li>
  <li><b>order_status</b>:
    Referência do status da compra (entregue, enviado, etc);</li>
  <li><b>order_products_value</b>:
    Preço total de todos produtos da compra;</li>
  <li><b>order_freight_value</b>:
    Valor total do frete em uma compra;</li>
  <li><b>order_items_qty</b>:
    Quantidade total de produtos na compra;</li>
  <li><b>order_sellers_qty</b>:
    Total da quantidade de vendedores que realizaram a venda;</li>
  <li><b>order_purchase_timestamp</b>:
    Registro de data e hora da compra;</li>
  <li><b>order_aproved_at</b>:
    Data e hora da aprovação de pagamento;</li>
  <li><b>order_estimated_delivery_date</b>:
    Data estimada de entrega mostrada ao cliente no momento da compra;</li>
  <li><b>order_delivered_customer_date</b>:
    Data real de entrega ao cliente;</li>
  <li><b>customer_id</b>:
    Identificador do cliente. Cada compra tem um único cliente. Para encontrar o <i>customer_id</i> único, consulte o dataset <i>customers</i>;</li>
  <li><b>customer_city</b>:
    Cidade do cliente;</li>
  <li><b>customer_state</b>:
    Estado do cliente;</li>
  <li><b>customer_zip_code_prefix</b>:
    Os três primeiros dígitos do CEP do cliente;</li>
  <li><b>product_category_name</b>:
    A categoria raiz do produto comprado (em português);</li>
  <li><b>product_name_lenght</b>:
    Número de caracteres do nome do produto;</li>
  <li><b>product_description_lenght</b>:
    Número de caracteres da descrição do produto;</li>
  <li><b>product_photos_qty</b>:
    Número de fotos publicadas no anúncio do produto;</li>
  <li><b>product_id</b>:
    Identificador único do produto;</li>
  <li><b>review_id</b>:
    Identificador único da avaliação do produto;</li>
  <li><b>review_score</b>:
    Nota (entre 1 e 5) dada pelo cliente em uma pesquisa de satisfação;</li>
  <li><b>review_comment_title</b>:
    Título da avaliação deixada pelo cliente (em português);</li>
  <li><b>review_comment_message</b>:
    mensagem deixada pelo cliente na avaliação do produto (em português);</li>
  <li><b>review_creation_date</b>:
    Data na qual a pesquisa de avaliação foi enviada ao cliente;</li>
  <li><b>review_answer_timestamp</b>:
    Data e hora que a pesquisa de avaliação foi respondida.</li>             
</ul>

<p><b><i>olist_public_dataset_v2_customers.csv</i></b>:
Este dataset inclui identificadores únicos de clientes.</p>

<ul>
  <li><b>customer_id</b>:
    Chaves para o dataset <i>orders</i>. Cada compra possui um <i>customer_id</i> único;</li>
  <li><b>customer_unique_id</b>:
    Identificador único de um cliente .</li>
</ul>

<p><b><i>payments_olist_public_dataset.csv</i></b>:<br>
Este dataset inclui opções de pagamento das compras.</p>

<ul>
  <li><b>order_id</b>:
    Identificador único de uma compra;</li>
  <li><b>installments</b>:
    Quantidade de parcelas escolhida pelo cliente;</li>
  <li><b>sequential</b>:
    Um cliente pode utilizar mais de um método de pagamento. Neste caso, uma sequência será criada para acomodar todos os pagamentos;</li>
  <li><b>payment_type</b>:
    Método de pagamento escolhido pelo cliente;</li>
  <li><b>value</b>:
    Valor da transação.</li>
</ul>

<p><b><i>product_category_name.csv</i></b>:<br>
Traduz o dataset <i>product_category_name</i> para o inglês.</p>

<p><i>Este projeto está em andamento, recebendo atualizações e adições com frequência.</i></p>
