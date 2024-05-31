# Criando-o-seu-Blog-com-Ruby-on-Rails

Criando um blog com Ruby on Rails focado na temática dos livros que você leu este ano. Vamos dividir o processo em módulos para manter o código organizado e fácil de manter.

### Módulo 1: Configuração Inicial
Primeiro, você precisa instalar o Ruby on Rails no seu sistema. Após a instalação, você pode criar um novo projeto Rails com o comando:

```ruby
rails new blog_livros
```

### Módulo 2: Estrutura do Banco de Dados
Defina as entidades do seu blog. Provavelmente você terá pelo menos duas: `Livros` e `Posts`. Use migrations para criar essas tabelas.

```ruby
rails generate model Livro titulo:string autor:string ano:integer
rails generate model Post titulo:string conteudo:text livro:references
```

Não esqueça de rodar `rails db:migrate` para aplicar as mudanças no banco de dados.

### Módulo 3: Rotas e Controladores
Configure as rotas no arquivo `config/routes.rb` e crie os controladores correspondentes.

```ruby
resources :livros
resources :posts
```

### Módulo 4: Views
Crie views para listar, mostrar, criar, editar e deletar livros e posts. Use o `form_with` para criar formulários dinâmicos.

```erb
<%= form_with(model: @livro, local: true) do |form| %>
  <%= form.label :titulo %>
  <%= form.text_field :titulo %>

  <%= form.label :autor %>
  <%= form.text_field :autor %>

  <%= form.label :ano %>
  <%= form.number_field :ano %>

  <%= form.submit %>
<% end %>
```

### Módulo 5: Estilização
Adicione CSS para melhorar a aparência do seu blog. Você pode usar frameworks como Bootstrap para acelerar esse processo.

### Módulo 6: Deploy
Por fim, faça o deploy do seu blog. Existem várias opções como Heroku, AWS e DigitalOcean.

Lembre-se de testar todas as funcionalidades antes de colocar o blog no ar. Espero que essas dicas te ajudem a criar um blog incrível sobre os livros que você leu!
