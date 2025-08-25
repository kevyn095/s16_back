O projeto SecureFlow cria um esquema de segurança essencial para uma API dedicada à gestão de pedidos, construída em Node.js utilizando Express. O objetivo é proteger os dados e restringir o acesso apenas ao front-end oficial da empresa.

Em primeiro lugar, o CORS foi ajustado para aceitar somente o domínio http://frontend.secureflow.com. Com isso, garante-se que apenas o site autorizado possa interagir com a API, bloqueando acessos provenientes de outras fontes.

A autenticação via token foi estabelecida para salvaguardar os endpoints sensíveis. Para visualizar os pedidos, o cliente deve inserir o token correto no cabeçalho Authorization. Isso faz a distinção entre autenticação (verificar a identidade do usuário) e autorização (definir o que o usuário pode acessar). Assim, somente usuários autenticados podem consultar os dados.

Um sistema simples de monitoramento também foi implementado, que registra todas as requisições recebidas em logs. São gravadas as tentativas de acesso não autorizado, permitindo a detecção de ações suspeitas e possíveis ataques. Durante os testes, acessos sem token ou com token inválido foram negados com um erro 401, enquanto acessos com token válido foram aceitos normalmente.

Com essas camadas de segurança — CORS restrito, autenticação/autorização e monitoramento — a API se torna mais sólida e capaz de reconhecer e reduzir os riscos.
