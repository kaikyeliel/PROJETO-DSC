Task Management System

🛠️ Tecnologias utilizadas
Java 17
Spring Boot 3.4.3
Spring Security + JWT
Spring Data JPA (Hibernate)
PostgreSQL
Docker / Docker Compose
Gradle

🚀 Como rodar o projeto
1. Subir pelo Docker
docker-compose up --build

Têm a opção alternativa de subir pelo Gradle localmente (não usei)
./gradlew clean build
./gradlew bootRun

A aplicação estará disponível em:
 👉 http://localhost:8080

🎨 Front-end
Professor, desenvolvi também um front-end para consumir a API.
 No front-end o senhor pode:
Criar uma conta.

Obs: Pode aparecer um erro de rede. Esse erro não significa falha no cadastro, é só uma limitação do front-end.

O usuário é criado corretamente no banco, e é possível fazer login logo em seguida.

Fazer login com usuário e senha criados.

Após logar, o senhor vai notar que a parte de criação de quadros interativos ainda não está finalizada.
 A autenticação funciona, mas a interação visual ficou com essa limitação.


🔎 Como verificar que a API funciona pelo Front-end
Mesmo com esses problemas do front-end, é possível confirmar que a API está funcionando normalmente:
Acesse o front-end.


Pressione F12 → aba “Network” (Inspecionar).


Ao criar conta, logar ou interagir, o senhor vai ver as requisições reais sendo feitas para o back-end:


POST /api/auth/signup


POST /api/auth/signin


GET /api/users


POST /api/boards


etc.


Essas requisições provam que o front-end está consumindo diretamente a API que desenvolvi no back-end.

🔑 Endpoints principais
Autenticação
POST /api/auth/signup → Criar novo usuário


POST /api/auth/signin → Login e retorno de token JWT


Usuários
GET /api/users → Lista usuários (necessário token)


Tarefas / Boards
POST /api/boards → Criar novo board


POST /api/tasks → Criar nova tarefa


GET /api/boards/{id}/tasks → Listar tarefas de um board



Obs
Professor, usei Spring Boot 3.5, que recentemente quebrou compatibilidade com springdoc.
 Por isso mantive a versão 3.4.3, mas ainda tive dificuldades com cache no Docker.
 Infelizmente a documentação automática (Swagger) não carregou e não consegui resolver.
