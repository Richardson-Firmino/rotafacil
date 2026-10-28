# RotaFácil — Plataforma de Mobilidade

> Projeto acadêmico de uma plataforma de mobilidade urbana que propõe conectar passageiros e motoristas.

## Sobre o projeto

O **RotaFácil** é uma proposta de plataforma de mobilidade urbana com o objetivo de aproximar passageiros e motoristas e contribuir para uma experiência de transporte mais simples, organizada e acessível.

Este repositório apresenta a proposta do projeto e documenta a arquitetura em nuvem planejada com serviços da Amazon Web Services (AWS). A documentação descreve a arquitetura apresentada pela equipe; não significa, por si só, que todos os serviços estejam implantados em um ambiente de produção.

## Objetivos

- Documentar a proposta da plataforma RotaFácil.
- Apresentar a arquitetura de infraestrutura planejada na AWS.
- Demonstrar conceitos de computação em nuvem, redes, disponibilidade, escalabilidade, monitoramento e segurança.
- Manter a documentação do projeto organizada para fins acadêmicos e de portfólio.

## Arquitetura AWS

A arquitetura apresentada prevê recursos distribuídos em duas zonas de disponibilidade, com separação de sub-redes públicas e privadas, balanceamento de carga, instâncias de aplicação, banco de dados e serviços complementares.

![Diagrama da arquitetura AWS do RotaFácil](docs/arquitetura-aws.png)

### Componentes apresentados no diagrama

| Serviço/componente | Papel previsto na arquitetura |
|---|---|
| Amazon Route 53 | Resolução DNS e direcionamento de usuários ao endpoint da aplicação. |
| Amazon VPC | Rede virtual que organiza os recursos da solução. |
| Sub-redes públicas e privadas | Segmentação da rede conforme a exposição e a função dos recursos. |
| Internet Gateway | Conectividade entre a VPC e a internet, conforme as rotas configuradas. |
| NAT Gateway | Permite que recursos em sub-redes privadas iniciem conexões de saída, conforme a configuração de rede. |
| Amazon EC2 — front-end | Hospedagem da camada de apresentação da aplicação. |
| Amazon EC2 — back-end | Processamento da aplicação e comunicação com os demais componentes. |
| Application Load Balancer (ALB) | Distribuição de tráfego para os destinos configurados. |
| Auto Scaling | Ajuste da quantidade de instâncias conforme políticas e métricas configuradas. |
| Grupos de segurança | Controle do tráfego de entrada e saída dos recursos associados. |
| Amazon RDS Multi-AZ | Banco de dados relacional com implantação em múltiplas zonas de disponibilidade, conforme configuração. |
| Amazon S3 e S3 Intelligent-Tiering | Armazenamento de objetos e possível otimização de custos por padrão de acesso. |
| AWS Lambda | Execução de funções sob demanda para tarefas definidas na solução. |
| Amazon CloudWatch | Coleta de métricas e logs e configuração de alarmes. |
| Amazon SNS | Distribuição de notificações para endpoints ou assinantes configurados. |
| AWS Key Management Service (KMS) | Gerenciamento de chaves de criptografia. |
| Amazon Macie | Identificação e proteção de dados sensíveis em fontes compatíveis, como o Amazon S3. |
| AWS Certificate Manager (ACM) | Gerenciamento de certificados TLS/SSL para serviços integrados compatíveis. |
| Serviço externo de pagamento | Integração externa prevista no diagrama; o fornecedor não está especificado nesta documentação. |

> **Observação:** a presença de um serviço no diagrama descreve o desenho proposto. A disponibilidade real, o nível de segurança, a redundância e os custos dependem da configuração e da implantação efetiva dos recursos.

## Fluxo geral da solução

1. Passageiros e motoristas acessam a plataforma pela internet.
2. O DNS e os componentes de entrada encaminham as requisições para a infraestrutura configurada.
3. O balanceador distribui o tráfego entre os destinos de aplicação definidos.
4. Os componentes de back-end se comunicam com o banco de dados e os serviços auxiliares autorizados.
5. Serviços de monitoramento, automação, armazenamento e notificação apoiam a operação, conforme configurados.

Este é um resumo conceitual do diagrama, não uma especificação de endpoints ou de funcionalidades já implementadas.

## Tecnologias e serviços

- Amazon Web Services (AWS)
- Amazon EC2
- Amazon VPC e sub-redes
- Application Load Balancer (ALB)
- Auto Scaling
- Amazon RDS Multi-AZ
- Amazon S3 e S3 Intelligent-Tiering
- AWS Lambda
- Amazon CloudWatch
- Amazon SNS
- AWS KMS
- Amazon Macie
- Amazon Route 53
- AWS Certificate Manager (ACM)
- Git e GitHub para versionamento e documentação

As linguagens de programação, frameworks, fornecedor de pagamento e tecnologia específica da aplicação não estão especificados neste README e devem ser adicionados quando forem confirmados.

## Estrutura do repositório

```text
rotafacil/
├── README.md
├── docs/
│   └── arquitetura-aws.png
└── assets/
    └── README.md
```

- `README.md`: apresentação e documentação principal do projeto.
- `docs/arquitetura-aws.png`: diagrama da arquitetura AWS.
- `assets/`: diretório reservado para identidade visual e outros materiais do projeto.

## Status do projeto

Projeto acadêmico. A documentação poderá ser atualizada conforme a implementação e a validação dos componentes.

## Equipe

Adicione aqui os integrantes da equipe e os links de seus perfis profissionais, se desejarem.

## Licença

A licença ainda não foi definida. Antes de adicionar uma licença, confirme com a equipe como o código e os materiais poderão ser reutilizados.
