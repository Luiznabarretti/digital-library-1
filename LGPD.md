# Conformidade com a LGPD

Em cumprimento aos requisitos do projeto, este documento detalha a política de tratamento de dados do sistema.

## 1. Minimização e Finalidade dos Dados

O sistema coleta estritamente três informações essenciais para o seu funcionamento, garantindo a minimização e a privacidade do usuário:

| Dado Pessoal Coletado | Finalidade Específica | Justificativa de Minimização |
| :--- | :--- | :--- |
| **Nome** | Identificação do usuário na interface do sistema. | Necessário para personalizar a experiência e identificar o titular de forma legível. |
| **E-mail** | Identificador único de login, comunicação de segurança e recuperação de senha. | Essencial para a criação da conta e para garantir o acesso exclusivo do titular. |
| **Senha** | Autenticação e garantia de acesso seguro. | Essencial para proteção da conta. A senha não é armazenada em texto claro, sendo processada via hash criptográfico (bcrypt) e salt exclusivo gerenciado pelo Supabase. |
