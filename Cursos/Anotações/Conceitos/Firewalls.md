# Firewalls

**Relacionado a:** #IntroduçãoàSegurançadaInformação
**Curso(s):** #ADS
**Tags:** #conceito #firewalls

## Definição

Um firewall é um dispositivo de segurança que monitora o tráfego de rede de entrada e saída, decidindo permitir ou bloquear esse tráfego com base em um conjunto de regras de segurança predefinidas.

Firewalls têm sido a linha de frente na segurança de redes e da internet há mais de 25 anos. Eles criam uma barreira entre redes internas protegidas e redes externas — confiáveis ou não — como a internet.

Um firewall pode ser implementado por meio de hardware, software ou ambos.

**As regras de um firewall podem adotar duas políticas principais:**

- **Negar por padrão:** Todo tráfego é bloqueado, e apenas os servidores e protocolos autorizados explicitamente (ex: R1) são permitidos.
    
- **Aceitar por padrão:** Todo tráfego é inicialmente permitido, e regras específicas (ex: R1, R2) definem quais tipos de tráfego devem ser bloqueados.

## Exemplos

- **Firewall de software (host-based):** O Windows Defender Firewall bloqueia um programa recém-instalado até que o usuário o autorize.
    
- **Firewall de hardware (network-based):** Um firewall da Cisco bloqueia todo o tráfego de entrada, exceto conexões HTTPS (porta 443) e HTTP (porta 80).
    
- **Firewall em roteador doméstico:** O roteador impede acessos externos a câmeras ou impressoras conectadas à rede Wi-Fi.
    
- **Política “negar por padrão”:** Uma empresa permite acesso apenas a sites corporativos, bloqueando todo o restante da internet.
    
- **Política “aceitar por padrão”:** Uma escola permite acesso geral à internet, mas bloqueia o YouTube e sites de jogos durante o horário de aula.
    
- **Firewall na nuvem:** Em um servidor AWS, apenas o IP da empresa pode acessar a porta 22 (SSH).

## Onde aparece

- [[2. Segurança Física, Lógica e Controle de Acesso|Segurança Física, Lógica e Controle de Acesso]]