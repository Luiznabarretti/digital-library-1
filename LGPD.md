# Conformidade com a LGPD (Lei Geral de Proteção de Dados)

## 1. Mapeamento de Dados Pessoais

| Dado Pessoal Coletado | Finalidade Específica | Base Legal | Retenção | Observação |
|-----------------------|----------------------|------------|----------|------------|
| **Nome** | Identificação do usuário na interface do sistema e personalização da experiência. | Consentimento (Art. 7, I) ou Execução de contrato (Art. 7, IX) | Enquanto a conta estiver ativa ou até a solicitação de exclusão pelo usuário. | Não armazenado em texto puro.
| **E‑mail** | Identificador único de login, comunicação de segurança, recuperação de senha e notificações. | Consentimento (Art. 7, I) ou Execução de contrato (Art. 7, IX) | Enquanto a conta estiver ativa ou até a solicitação de exclusão pelo usuário. | Utilizado para envio de e‑mails transacionais.
| **Senha** | Autenticação e garantia de acesso seguro. | Execução de contrato (Art. 7, IX) | Enquanto a conta estiver ativa ou até a solicitação de exclusão pelo usuário. | Armazenada como hash BCrypt com salt único.
| **Endereço IP (opcional)** | Registro de acesso para segurança, detecção de tentativas de acesso indevido e auditoria. | Legítimo interesse (Art. 7, IX) | 30 dias ou até a solicitação de exclusão pelo usuário. | Não associado a identidade sem a combinação com outros dados.
| **Dados de Navegação (user‑agent, timestamps)** | Monitoramento de desempenho, análise de uso e detecção de falhas. | Legítimo interesse (Art. 7, IX) | 90 dias ou até a solicitação de exclusão pelo usuário. | Não contém informações sensíveis.

## 2. Finalidade e Necessidade

O sistema coleta **apenas** os dados acima descritos, estritamente necessários para:
- Permitir o cadastro e autenticação de usuários.
- Garantir a segurança da conta (login, recuperação de senha, detecção de tentativas suspeitas).
- Fornecer a funcionalidade principal da plataforma de pesquisa de livros digitais.

## 3. Retenção e Eliminação

- **Dados de conta (Nome, E‑mail, Senha):** Mantidos enquanto a conta permanecer ativa. O usuário pode solicitar a exclusão a qualquer momento, o que aciona a remoção completa dos registros.
- **Logs de acesso (IP, user‑agent, timestamps):** Mantidos por **30 dias** para segurança e por **90 dias** para análise de uso, conforme a necessidade operacional.

## 4. Direitos dos Titulares

Conforme a LGPD, os titulares têm o direito de:
- **Acesso:** receber cópia dos seus dados pessoais armazenados.
- **Retificação:** corrigir informações incompletas, inexatas ou desatualizadas.
- **Excluir:** solicitar a exclusão definitiva dos seus dados.
- **Portabilidade:** obter os dados em formato estruturado, de uso comum e leitura automática.
- **Revogar consentimento:** retirar o consentimento a qualquer momento, sem prejuízo da legitimidade do tratamento anterior.
- **Informação:** ser informado sobre como seus dados são tratados.

**Procedimento:** O usuário deve enviar solicitação ao e‑mail `privacy@digital-library.com.br`. A equipe responderá em até 15 dias úteis, cumprindo a ação solicitada.

## 5. Medidas de Segurança

- **Comunicação segura (TLS 1.2+):** Todas as requisições entre cliente e API são criptografadas.
- **Armazenamento de senhas:** Utiliza algoritmo **bcrypt** (custo ≥ 12) com salt aleatório por usuário.
- **Dados em repouso:** O banco Supabase (PostgreSQL) possui criptografia AES‑256 por padrão.
- **Controle de acesso:** Privilégios de leitura/escrita são restritos por papéis (role‑based access control).
- **Logs de auditoria:** Operações críticas (login, alteração de senha, exclusão de conta) são registradas com data/hora e IP.
- **Proteção contra vazamento:** Dados sensíveis não são expostos em logs ou mensagens de erro.

## 6. Contrato com Terceiros (Supabase)

O projeto utiliza o serviço **Supabase** como provedor de banco de dados e autenticação. Foi firmado **Acordo de Tratamento de Dados (Data Processing Agreement)** que inclui:
- Compromisso de tratamento de dados conforme LGPD.
- Garantia de segurança, confidencialidade e sub‑processamento apenas com parceiros aprovados.
- Direito de auditoria e notificação de incidentes de segurança.

## 7. Plano de Resposta a Incidentes

1. **Detecção:** Monitoramento contínuo de logs de acesso e alertas de atividades suspeitas.
2. **Notificação interna:** Equipe de segurança é informada imediatamente.
3. **Comunicação ao titular:** Caso haja risco à privacidade, o titular será notificado em até **72 horas**.
4. **Comunicação à Autoridade:** Se o incidente representar risco significativo, a Autoridade Nacional de Proteção de Dados (ANPD) será informada conforme Art. 48 da LGPD.
5. **Mitigação:** Contenção da vulnerabilidade, análise de causa raiz e aplicação de correções.
6. **Documentação:** Registro completo do incidente, medidas adotadas e lições aprendidas.

## 8. Privacidade por Design e por Default

- **Minimização:** Apenas os dados listados são coletados; nenhum dado sensível adicional é solicitado.
- **Configurações padrão:** As opções de compartilhamento ou uso de dados para marketing estão desativadas por padrão.
- **Arquitetura em camadas:** Separação clara entre camada de apresentação (frontend) e camada de persistência (Supabase), reduzindo exposição direta dos dados ao cliente.
- **Revisões de código:** Analises de segurança são realizadas antes de cada release.

---

**Contato para questões de privacidade:**
- E‑mail: `no-email-yet@digital-library.com.br`
- Telefone: `+55 11 99999‑9999`

*Este documento reflete o compromisso do projeto **digital‑library** com a proteção de dados pessoais, atendendo aos requisitos da LGPD.*
