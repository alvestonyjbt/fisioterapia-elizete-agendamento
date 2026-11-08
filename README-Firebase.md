# Versão com Firebase - Fisioterapia Elizete Conceição

Esta versão usa o Firebase Realtime Database para que os agendamentos sejam compartilhados automaticamente entre qualquer navegador ou dispositivo.

## Como configurar (passo a passo)

1. Acesse https://console.firebase.google.com e faça login com sua conta Google.
2. Clique em **Adicionar projeto** e crie um projeto (ex: `elizete-fisioterapia`).
3. No menu lateral, vá em **Build → Realtime Database**.
4. Clique em **Criar banco de dados** e escolha o modo de teste (ou configure as regras depois).
5. Vá em **Configurações do projeto** (ícone de engrenagem) → aba **Geral**.
6. Em **Seus apps**, clique no ícone da Web (`</>`) e registre um app.
7. Copie o objeto `firebaseConfig` que aparece.
8. Abra o arquivo `agendamento-firebase.html` e substitua o bloco `firebaseConfig` pelos seus dados.

### Regras de segurança recomendadas (opcional, mas importante)

No Realtime Database → Regras, use algo assim para começar (permite leitura e escrita pública — mude depois se quiser mais segurança):

```json
{
  "rules": {
    "agendamentos": {
      ".read": true,
      ".write": true
    }
  }
}
```

## Como usar

- Abra o arquivo `agendamento-firebase.html` em qualquer navegador.
- Todos os agendamentos feitos em qualquer dispositivo aparecerão automaticamente para todos.
- O botão **Ver Agendamentos** mostra a lista em tempo real.
- O botão **Enviar lista para WhatsApp** continua funcionando.

## Observações

- É necessário internet para funcionar.
- Se aparecer erro de conexão, verifique se a `databaseURL` e as chaves estão corretas.
- Para hospedar online, você pode usar Firebase Hosting, Netlify, Vercel ou qualquer serviço de hospedagem estática.
