# Smart-City Emergency Dispatcher API (SPSKILLS / WorldSkills TP09)

> **PROJETO BASE**  
> **Esta API NÃO foi desenvolvida por mim.** Trata-se de um projeto base (*starter template*) fornecido oficialmente pela organização da competição (SPSKILLS / WorldSkills) para servir de servidor autoritativo em tempo real para a aplicação Desktop.

---

## Especificações Oficiais da API

Todas as especificações técnicas da API (rotas, verbos HTTP, contratos JSON, tempos de polling, regras de negócio e modelo de dados) estão detalhadas no arquivo PDF anexo:

- **Documento Oficial de Especificações:** `WSC2026_TP09_S3_API_actual_en_2.pdf`

---

## Como Rodar a API na sua Máquina

### Pré-requisitos
- **.NET SDK 8.0** (ou superior)
- **SQL Server / LocalDB**
- **Git**

---

### Passo a Passo de Execução

#### 1. Clonar o Repositório
```bash
git clone <URL_DO_SEU_REPOSITORIO>
cd <PASTA_DO_PROJETO>

```

#### 2. Configurar a String de Conexão

Abra o arquivo `appsettings.json` (ou `appsettings.Development.json`) e ajuste a propriedade `ConnectionString` para apontar para a sua instância local do SQL Server:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=SEU_SERVIDOR;Database=EmergencyApiDb;Trusted_Connection=True;TrustServerCertificate=True;"
  }
}

```

#### 3. Restaurar Dependências

```bash
dotnet restore

```

#### 4. Criar e Atualizar o Banco de Dados

Aplique as migrações do Entity Framework Core para estruturar o banco local:

```bash
dotnet ef database update

```

#### 5. Executar a API

```bash
dotnet run

```

#### 6. Verificar Conectividade

Acesse no navegador ou cliente HTTP:

```text
GET http://localhost:<PORTA>/api/health

```

**Resposta esperada (HTTP 200 OK):**

```json
{
  "status": "ok",
  "serverTime": "2026-10-22T16:27:00.000Z"
}
