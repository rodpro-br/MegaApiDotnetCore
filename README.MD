# Megaman API

## 🔧 Sobre o Projeto
Este projeto consiste em uma API desenvolvida em .NET Core 3.1 para listar os dados dos bosses do jogo Megaman. O principal objetivo é fornecer um backend que disponibilize os dados dos robôs em formato JSON.

Exemplo de resposta JSON fornecida pela API:
```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

---

## 📊 Estrutura de Pastas
```
.vs/
.vscode/
bin/
Controllers/
    RobotsController.cs
Database/
middlewares/
Models/
obj/
Properties/
Services/
appsettings.Development.json
appsettings.json  
global.json
MegamanApi.csproj  
MegamanApi.sln
Program.cs
Startup.cs
```

---

## 🔧 Tecnologias Utilizadas
- **ASP.NET Core 3.1**: Framework para criação de APIs RESTful.
- **Entity Framework Core**: ORM para manipulação de dados.
- **SQL Server**: Banco de dados relacional para armazenamento dos robôs.
- **Newtonsoft.Json**: Biblioteca para serialização e desserialização de objetos JSON.

---

## 📈 Endpoints
### **Base URL**
```
/api/v1/robots
```

### **GET /api/v1/robots**
Retorna a lista de todos os robôs cadastrados.

**Exemplo de Resposta:**
```json
[
  {
    "Id": 1,
    "Code": "DLN/DRN-003",
    "Name": "Cutman",
    "HP": 150,
    "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
  }
]
```

### **GET /api/v1/robots/{id}**
Retorna os detalhes de um robô específico pelo `id`.

**Exemplo de Resposta de Sucesso (Status 200):**
```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

**Exemplo de Resposta de Erro (Status 404):**
```json
{
  "message": "Nenhum robo encontrado"
}
```

### **POST /api/v1/robots**
Endpoint para criação de novos robôs.

**Exemplo de Resposta de Sucesso (Status 200):**
```json
{
  "message": "Robo criado com sucesso"
}
```

---

## 📊 Dependências
As principais dependências do projeto estão descritas na tabela abaixo:

| Dependência | Versão | Descrição |
|--------------|---------|-------------|
| [ASP.NET Core](https://dotnet.microsoft.com/download/dotnet/3.1) | 3.1 | Framework para criação de APIs RESTful. |
| [Entity Framework Core](https://learn.microsoft.com/pt-br/ef/core/) | 3.1.8 | ORM para acesso a bancos de dados. |
| [Microsoft.EntityFrameworkCore.SqlServer](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.SqlServer/3.1.8) | 3.1.8 | Provider do SQL Server para o Entity Framework Core. |
| [Microsoft.EntityFrameworkCore.Design](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.Design/3.1.8) | 3.1.8 | Ferramentas de design do Entity Framework Core. |
| [Newtonsoft.Json](https://www.newtonsoft.com/json) | 12.0.2 | Biblioteca para serialização e desserialização de objetos JSON. |

---

## 📚 Configuração do Projeto
Para executar o projeto, siga os seguintes passos:

1. **Clone o Repositório**
   ```bash
   git clone https://github.com/seu-usuario/megaman-api.git
   cd megaman-api
   ```

2. **Configure o Banco de Dados**
   - Certifique-se de que o SQL Server esteja em execução.
   - Ajuste a string de conexão em `appsettings.Development.json`.

3. **Execute as Migrações do Banco de Dados**
   ```bash
   dotnet ef database update
   ```

4. **Execute o Projeto**
   ```bash
   dotnet run
   ```

O projeto estará disponível em: [http://localhost:5000](http://localhost:5000)

---

## 📊 Estrutura do Código
A estrutura dos arquivos é descrita a seguir:

- **Controllers/**: Contém os controladores que lidam com as requisições HTTP.
  - **RobotsController.cs**: Controlador responsável pelos endpoints relacionados aos robôs.

- **Database/**: Contém os arquivos de configuração e migrações do banco de dados.

- **middlewares/**: Pasta reservada para futuros middlewares de tratamento de requisições e respostas.

- **Models/**: Contém as classes de modelo que representam os objetos da aplicação.

- **Services/**: Contém os serviços que encapsulam as regras de negócio e a lógica de acesso ao banco de dados.

- **appsettings.json**: Arquivo de configurações gerais da aplicação.

- **Startup.cs**: Configuração dos serviços, middlewares e pipeline de requisição HTTP.

- **Program.cs**: Classe principal que inicializa e executa o servidor web.

---

## 📚 Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues e pull requests para melhorias e correções.

---

## ⚙️ Licença
Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

