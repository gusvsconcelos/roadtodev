# Aula: Segurança Física, Lógica e Controle de Acesso

**Curso:** #ADS
**Semestre:** #ADS1
**Disciplina:** #IntroduçãoàSegurançadaInformação
**Data:** 11-07-2025
**Tags:** #ADS #SegurançaDaInformação #SegurançaFísicaeLógica #ControleDeAcesso #criptografia

## Resumo

### Segurança Física

A família de normas ABNT ISO/IEC 27000 divide a segurança física em dois aspectos: um relacionado aos equipamentos e outro ao ambiente.

Na [[Segurança da Informação]], as proteções são implementadas em camadas justapostas, semelhantes às camadas de uma cebola. Essa abordagem garante que a vulnerabilidade de uma camada seja compensada pela proteção de outra.

Além disso, é essencial considerar ameaças naturais, como enchentes, incêndios e desastres. Para isso, controles preventivos e de monitoramento devem ser instalados.

**Exemplos de medidas de segurança física:**

- Câmeras de vigilância;
- Controle de temperatura;
- Extintores de incêndio;
- Sprinklers (aspersores automáticos).

### Segurança Lógica

Complementando a segurança física, a segurança lógica consiste em medidas implementadas por meio de software, com o objetivo de proteger o acesso e o uso da [[Informação]].

**Exemplos de medidas de segurança lógica:**

- Senhas fortes;
- [[Criptografia]];
- [[Firewalls]];
- Listas de controle de acesso.

Assim como na segurança física, essas medidas atuam em camadas, reforçando-se mutuamente.

### [[Criptografia]]

A [[Criptografia]] compreende técnicas que embaralham [[Dado]]s por meio de chaves e algoritmos matemáticos, garantindo a [[Confidencialidade]] e, em alguns casos, o [[Não-repúdio]].

#### Criptografia simétrica

Utiliza uma única chave para cifrar e decifrar os [[Dado]]s. É mais rápida, porém menos segura em ambientes com múltiplos usuários.

**Exemplos de algoritmos:**

- Cifra de César;
- Blowfish;
- Twofish;
- Rijndael.

#### Criptografia assimétrica

Utiliza duas chaves distintas: uma pública (disponível em um servidor confiável) e uma privada (mantida pelo usuário). Essa abordagem permite garantir tanto a [[Confidencialidade]] quanto o [[Não-repúdio]].

**Exemplos de algoritmos:**

- Diffie-Hellman;
- El Gamal;
- Curvas Elípticas.

### Controles de segurança em redes

Para proteger os [[Dado]]s em trânsito e a infraestrutura de rede, destacam-se os seguintes controles:

- [[Firewalls]];
- Sistemas de detecção de intrusões (IDS);
- Redes privadas virtuais (VPNs).

## Conceitos abordados

- [[Criptografia]]
- [[Firewalls]]

## Conclusões

- Aprendi sobre a diferença entre segurança física e lógica;
    
- Compreendi a importância de investir em diversas técnicas de proteção, tanto na parte física quanto na lógica (software);
    
- Entendi como a redundância de mecanismos de segurança contribui para maior proteção da [[Informação]];
    
- Estudei os fundamentos da [[Criptografia]], incluindo seus dois principais tipos de algoritmos: simétricos e assimétricos.

> *Conhecer esses conceitos e princípios contribui para o desenvolvimento de um repertório sólido no cuidado com [[Dado]]s e [[Informação]], tanto para aplicá-los corretamente quanto para lidar com riscos e vulnerabilidades quando necessário.*