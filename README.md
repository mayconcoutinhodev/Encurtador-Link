# Encurtador-Link

1. Requisitos Funcionais
  Redirecionamento de URL: Aceitar uma URL longa como entrada e fornecer um link curto que redirecione para a URL original.
  Geração de Slug: Criar um código único (slug) para a URL curta. Pode ser alfanumérico, com um número limitado de caracteres (por exemplo, 6 a 8).
  Validação de URL: Verificar se a URL inserida é válida (uso de regex pode ajudar aqui).
  Expiração Opcional de Link: Permitir ao usuário definir uma data de expiração para a URL curta.

3. Requisitos de Armazenamento e Banco de Dados
  Banco de Dados: Tabela urls com os campos:
  id (chave primária)
  original_url (URL longa)
  short_url (slug da URL curta)
  created_at (data de criação)
  expires_at (data de expiração, opcional)
  Contador de Cliques: Campo para contar quantas vezes o link foi acessado.

4. Requisitos de Backend
  API para Criar Link Curto: Endpoint POST /shorten que aceita a URL longa e retorna a URL curta.
  API para Redirecionamento: Endpoint GET /:slug para redirecionar o usuário para a URL original com base no slug.
  Lógica de Redirecionamento e Expiração: Verificar, ao redirecionar, se o link expirou; caso sim, exibir uma mensagem de erro.

5. Requisitos de Segurança
  Proteção contra Abuso: Limitar a frequência de requisições por usuário/IP para evitar spam.
  Validação e Sanitização de Entrada: Evitar URLs maliciosas e SQL Injection (se usar SQL).

6. Extras (Funcionalidades Avançadas)
  Autenticação de Usuário: Opcional, para que usuários possam acessar suas URLs encurtadas e estatísticas.
  Análise de Cliques: Gráficos e relatórios sobre os acessos dos links (localização, horário, navegador, etc.).
  Integração com API: Permitir a criação de links curtos via API para outros serviços ou aplicações.
