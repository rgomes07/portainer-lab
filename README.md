# 🚢 Portainer CE - Gestão de Containers SEDUC

Este projeto documenta e gerencia a stack do **Portainer Community Edition (CE)**, utilizada para a orquestração e gerenciamento visual do ambiente de containers da Secretaria de Estado de Educação (SEDUC).

## 🎯 Finalidade

O Portainer foi implementado para servir como a interface central de gerenciamento da nossa infraestrutura de containers. Ele permite que a equipe de TI visualize, monitore e gerencie recursos do Docker sem a necessidade exclusiva de interação via linha de comando (CLI), democratizando o acesso técnico e agilizando operações.

## 🏗️ Arquitetura: Docker Swarm

Diferente de uma instalação standalone, o Portainer da SEDUC está rodando sobre um **Cluster Docker Swarm**. 

* **Alta Disponibilidade:** O Portainer gerencia todos os 5 nós do cluster (`dck01` a `dck05`).
* **Agentes Globais:** Utilizamos o `portainer-agent` em modo global, garantindo que o Portainer consiga orquestrar containers em qualquer servidor do parque.
* **Persistência:** As configurações estão armazenadas no nosso storage centralizado (**NFS** em `/storage`), permitindo que o serviço seja recuperado em qualquer nó do cluster.



## 🚀 Vantagens do Portainer para a SEDUC

A adoção do Portainer traz benefícios estratégicos para a nossa infraestrutura:

* **✅ Visualização em Tempo Real:** Dashboard completo para monitorar o uso de CPU, Memória e status dos serviços em todo o cluster Swarm.
* **✅ Gestão de Stacks:** Facilidade para implantar e atualizar arquivos `docker-compose.yml` diretamente pela interface web.
* **✅ Console Integrado:** Acesso rápido ao terminal dos containers e logs diretamente pelo navegador, agilizando o troubleshoot.
* **✅ Controle de Acesso (RBAC):** Permite definir quem pode gerenciar cada projeto, aumentando a segurança operacional.
* **✅ Gestão de Imagens e Volumes:** Limpeza de recursos não utilizados e inspeção de volumes no storage NFS de forma gráfica.

## ⚙️ Acesso ao Serviço

O serviço está exposto através do nosso Proxy Reverso (Nginx) centralizado:

* **URL:** `http://portainer.seduc.pa.gov.br`
* **Segurança:** Acesso restrito à rede interna da secretaria.

---
*Mantido pela equipe de Infraestrutura e Redes - SEDUC-PA*
