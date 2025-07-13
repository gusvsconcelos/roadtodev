# Criptografia

**Relacionado a:** #IntroduçãoàSegurançadaInformação
**Curso(s):** #ADS
**Tags:** #conceito #criptografia

## Definição

Criptografia é o processo de transformar [[Dado|dados]] legíveis em um formato ilegível por meio de algoritmos baseados em funções matemáticas, com o objetivo de proteger sua [[Confidencialidade|confidencialidade]]. Isso garante que apenas as partes autorizadas, com a chave de descriptografia correta, possam decifrá-los e acessar as [[Informação|informações]] originais.

**Existem dois tipos principais de criptografia:**

- **Simétrica:** Utiliza apenas uma chave para criptografar e descriptografar os [[Dado|dados]]. É mais rápida e simples, mas menos indicada para ambientes com muitos usuários.
    
- **Assimétrica:** Utiliza duas chaves distintas — uma pública (geralmente armazenada em um servidor confiável) e uma privada (mantida em posse do usuário). Apesar de mais lenta, é mais segura em ambientes distribuídos e com múltiplos participantes.

## Exemplos

**Criptografia Simétrica:**

- **Wi-Fi com senha (WPA2 ou WPA3):** Utiliza criptografia simétrica para proteger os [[Dado|dados]] transmitidos entre o roteador e o dispositivo.
    
- **Arquivos ZIP protegidos por senha:** Ao compactar arquivos com senha, uma única chave é usada para criptografar e descriptografar os [[Dado|dados]].
    
- **Discos rígidos criptografados (BitLocker, VeraCrypt):** Empregam criptografia simétrica para proteger todo o conteúdo do HD com uma chave única.

**Criptografia Assimétrica:**

- **Certificados SSL/TLS em sites HTTPS:** Garantem comunicação segura entre navegador e servidor, usando uma chave pública para cifrar e uma chave privada para decifrar.
    
- **Assinatura digital de e-mails (ex: PGP, S/MIME):** Permite verificar a autoria e [[Integridade|integridade]] da mensagem; o remetente assina com sua chave privada, o destinatário verifica com a chave pública.
    
- **Transações em blockchain:** Cada usuário possui um par de chaves (pública e privada) para assinar digitalmente suas transações, garantindo [[Autenticidade|autenticidade]] e [[Não-repúdio|não-repúdio]].

## Onde aparece

- [[2. Segurança Física, Lógica e Controle de Acesso|Segurança Física, Lógica e Controle de Acesso]]