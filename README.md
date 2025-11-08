# 🐑 Rebanho Hive - Gerenciamento de Ovelhas (Desafio EAD)

Este projeto implementa um aplicativo Flutter para gerenciar dados de ovelhas, utilizando o banco de dados local **Hive** para persistência, focando na implementação manual dos requisitos.

## 🚀 Requisitos e Execução

### Versão Utilizada
* **Flutter SDK:** 3.x (Versão compatível com Dart >= 3.0.0)

### Como Rodar o Projeto
1.  **Instalar Dependências:** Na raiz do projeto, execute:
    ```bash
    flutter pub get
    ```
2.  **Executar o App:** Inicie um emulador/dispositivo e rode o aplicativo:
    ```bash
    flutter run
    ```

## 💾 Estrutura de Camadas e Hive

O projeto segue uma arquitetura baseada em camadas (`DataSource`, `Repository`) e utiliza a persistência Hive para armazenamento local.

| Camada / Arquivo | Foco do Requisito | Localização no Código |
| :--- | :--- | :--- |
| **Modelo Hive** | **Classe `Ovelha` e Adapter Manual** (`TypeAdapter` sem `build_runner`). | `lib/model/ovelha.dart` |
| **Inicialização** | Configuração do Hive (`init`, `registerAdapter`, `openBox`). | `lib/main.dart` |
| **DataSource** | Acesso à `Box<Ovelha>` e lógica de **Upsert** (`box.put(rfid, ovelha)`). | `lib/data/ovelha_datasource.dart` |
| **Repository** | Lógica de negócios e fornecimento da lista **Reativa** e **Ordenada por RFID**. | `lib/repository/ovelha_repository.dart` |
| **Máscara RFID** | Implementação do `TextInputFormatter` **próprio** (`999-000000000000`). | `lib/utils/rfid_formatter.dart` |
