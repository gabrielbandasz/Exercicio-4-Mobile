# Exercicio-4-Mobile
# Exercícios Android — Java

## Exercício 1 — Pedido de Lanche

```java
EditText etxtLanche = findViewById(R.id.etxtLanche);
EditText etxtBebida = findViewById(R.id.etxtBebida);
EditText etxtObservacao = findViewById(R.id.etxtObservacao);
Button btn_Pedir = findViewById(R.id.btn_Pedir);
TextView txtResultado = findViewById(R.id.txtResultado);

btn_Pedir.setOnClickListener(v -> {
    String lanche = etxtLanche.getText().toString();
    String bebida = etxtBebida.getText().toString();
    String obs = etxtObservacao.getText().toString();

    Log.d("PEDIDO", "Lanche: " + lanche);
    Log.d("PEDIDO", "Bebida: " + bebida);
    Log.d("PEDIDO", "Observação: " + obs);

    txtResultado.setText("Pedido: " + lanche + " + " + bebida + " (" + obs + ")");
});
```

## Exercício 2 — Cadastro de Pet

```java
EditText etxtNomePet = findViewById(R.id.etxtNomePet);
EditText etxtEspecie = findViewById(R.id.etxtEspecie);
EditText etxtIdadePet = findViewById(R.id.etxtIdadePet);
Button btn_CadastrarPet = findViewById(R.id.btn_CadastrarPet);
TextView txtResultado = findViewById(R.id.txtResultado);

btn_CadastrarPet.setOnClickListener(v -> {
    String nome = etxtNomePet.getText().toString();
    String especie = etxtEspecie.getText().toString();
    String idade = etxtIdadePet.getText().toString();

    Log.d("PET", "Nome: " + nome);
    Log.d("PET", "Espécie: " + especie);
    Log.d("PET", "Idade: " + idade + " anos");

    txtResultado.setText(nome + " (" + especie + "), " + idade + " anos, cadastrado com sucesso!");
});
```

## Exercício 3 — Reserva de Sala

```java
EditText etxtNome = findViewById(R.id.etxtNome);
EditText etxtSala = findViewById(R.id.etxtSala);
EditText etxtHorario = findViewById(R.id.etxtHorario);
Button btn_Reservar = findViewById(R.id.btn_Reservar);
TextView txtResultado = findViewById(R.id.txtResultado);

btn_Reservar.setOnClickListener(v -> {
    String nome = etxtNome.getText().toString();
    String sala = etxtSala.getText().toString();
    String horario = etxtHorario.getText().toString();

    Log.d("RESERVA", "Responsável: " + nome);
    Log.d("RESERVA", "Sala: " + sala);
    Log.d("RESERVA", "Horário: " + horario);

    txtResultado.setText(sala + " reservado para " + nome + " às " + horario);
});
```

## Exercício 4 — Tela de Login

XML da senha:

```xml
<com.google.android.material.textfield.TextInputLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:endIconMode="password_toggle">

    <com.google.android.material.textfield.TextInputEditText
        android:id="@+id/etxtSenha"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Senha"
        android:inputType="textPassword" />
</com.google.android.material.textfield.TextInputLayout>
```

Java:

```java
EditText etxtEmail = findViewById(R.id.etxtEmail);
EditText etxtSenha = findViewById(R.id.etxtSenha);
Button btn_Entrar = findViewById(R.id.btn_Entrar);
TextView txtResultado = findViewById(R.id.txtResultado);

btn_Entrar.setOnClickListener(v -> {
    String email = etxtEmail.getText().toString();
    String senha = etxtSenha.getText().toString();

    Log.d("LOGIN", "E-mail digitado: " + email);
    Log.d("LOGIN", "Senha com " + senha.length() + " caracteres");

    if (senha.length() < 6) {
        Log.d("LOGIN", "Senha muito curta! Mínimo 6 caracteres.");
        txtResultado.setText("Senha muito curta! Mínimo 6 caracteres.");
    } else {
        Log.d("LOGIN", "Login realizado: " + email);
        txtResultado.setText("Bem-vindo(a), " + email + "!");
    }
});
```

## Exercício 5 — Inscrição em Evento

```java
EditText etxtNome = findViewById(R.id.etxtNome);
EditText etxtEmail = findViewById(R.id.etxtEmail);
EditText etxtIdade = findViewById(R.id.etxtIdade);
Button btn_Inscrever = findViewById(R.id.btn_Inscrever);
TextView txtResultado = findViewById(R.id.txtResultado);

btn_Inscrever.setOnClickListener(v -> {
    String nome = etxtNome.getText().toString();
    String email = etxtEmail.getText().toString();
    int idade = Integer.parseInt(etxtIdade.getText().toString());

    Log.d("EVENTO", "Nome: " + nome);
    Log.d("EVENTO", "E-mail: " + email);
    Log.d("EVENTO", "Idade: " + idade);

    if (idade < 14 || idade > 99) {
        Log.d("EVENTO", "Idade inválida para o evento.");
        txtResultado.setText("Idade inválida para o evento.");
    } else {
        Log.d("EVENTO", "Inscrição confirmada!");
        txtResultado.setText(nome + ", sua inscrição foi confirmada!");
    }
});
```

## Exercício 6 — Cadastro de Produto

```java
EditText etxtProduto = findViewById(R.id.etxtProduto);
EditText etxtPreco = findViewById(R.id.etxtPreco);
EditText etxtQuantidade = findViewById(R.id.etxtQuantidade);
Button btn_Cadastrar = findViewById(R.id.btn_Cadastrar);
TextView txtResultado = findViewById(R.id.txtResultado);

btn_Cadastrar.setOnClickListener(v -> {
    String produto = etxtProduto.getText().toString();
    double preco = Double.parseDouble(etxtPreco.getText().toString());
    int quantidade = Integer.parseInt(etxtQuantidade.getText().toString());

    Log.d("PRODUTO", "Produto: " + produto);
    Log.d("PRODUTO", "Preço: R$ " + preco);
    Log.d("PRODUTO", "Quantidade: " + quantidade);

    if (preco <= 0) {
        Log.d("PRODUTO", "Preço inválido!");
        txtResultado.setText("Preço inválido!");
    } else {
        Log.d("PRODUTO", "Produto cadastrado!");
        txtResultado.setText(produto + " cadastrado! Valor em estoque: R$ " + (preco * quantidade));
    }
});
```

## Exercício 7 — Recuperar Senha

```java
EditText etxtEmail = findViewById(R.id.etxtEmail);
EditText etxtConfirmarEmail = findViewById(R.id.etxtConfirmarEmail);
Button btn_Recuperar = findViewById(R.id.btn_Recuperar);
TextView txtResultado = findViewById(R.id.txtResultado);

btn_Recuperar.setOnClickListener(v -> {
    String email = etxtEmail.getText().toString();
    String confirmacao = etxtConfirmarEmail.getText().toString();

    Log.d("RECUPERAR", "E-mail: " + email);
    Log.d("RECUPERAR", "Confirmação: " + confirmacao);

    String msg = email.equals(confirmacao)
            ? "Link enviado para " + email
            : "Os e-mails não conferem!";

    Log.d("RECUPERAR", msg);
    txtResultado.setText(msg);
});
```
