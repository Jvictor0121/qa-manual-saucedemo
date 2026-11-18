# 📝 Casos de Teste (BDD)

Abaixo estão os cenários testados manualmente na aplicação SauceDemo.

---

### CT-01: Login com sucesso (Cenário Positivo)
* **Dado** que o usuário está na página de login do SauceDemo
* **Quando** preenche o campo usuário com `standard_user` e senha com `secret_sauce`
* **E** clica no botão "Login"
* **Então** o sistema deve redirecionar para a página de catálogo de produtos (`/inventory.html`).

---

### CT-02: Login com senha inválida (Cenário Negativo)
* **Dado** que o usuário está na página de login
* **Quando** preenche o usuário com `standard_user` e a senha com `senha_errada`
* **E** clica no botão "Login"
* **Então** o sistema deve bloquear o acesso e exibir a mensagem: *"Epic sadface: Username and password do not match any user in this service"*.

---

### CT-03: Login com usuário bloqueado (Cenário Negativo)
* **Dado** que o usuário está na página de login
* **Quando** preenche o usuário com `locked_out_user` e a senha com `secret_sauce`
* **E** clica no botão "Login"
* **Então** o sistema deve exibir a mensagem: *"Epic sadface: Sorry, this user has been locked out."*.

---

### CT-04: Tentativa de login com campos em branco (Cenário Negativo)
* **Dado** que o usuário está na página de login
* **Quando** deixa os campos de usuário e senha vazios
* **E** clica no botão "Login"
* **Então** o sistema deve exibir a mensagem de obrigatoriedade: *"Epic sadface: Username is required"*.

---

### CT-05: Adicionar produto ao carrinho (Cenário Positivo)
* **Dado** que o usuário está logado na página de produtos
* **Quando** clica no botão "Add to cart" do item "Sauce Labs Backpack"
* **Então** o botão deve mudar para "Remove" e o ícone do carrinho no topo deve exibir o número `1`.

---

### CT-06: Finalizar compra com campos de entrega vazios (Cenário Negativo)
* **Dado** que o usuário possui um item no carrinho e avançou para a tela de Checkout
* **Quando** clica em "Continue" sem preencher Nome, Sobrenome ou CEP
* **Então** o sistema deve impedir o avanço e exibir: *"Error: First Name is required"*.
