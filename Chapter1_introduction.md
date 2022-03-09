# Chapter 1

## VCS

- VCS(version controll system) ou sistema de controle de versão é um sistema que grava um arquivo ou uma serie de arquivos com a vantagem de você ter registrado todas as versões desse arquivo/projeto em um repositorio.

- A maior vantagem do uso de VCS no desenvolvimento de algum software é ter a segurança que sempre que uma novo bug é descoberto ou que uma nova versão defeituosa é lançada, nós poderemos dar um step-back e voltar para a versão funcional de um software

- Para muitas pessoas o metodo padrão de versionamento de codigo é fazer copias manualmente do sistema em versões diferentes em diretórios diferentes, porem esse método é pouco seguro, maçante e atrapalha no desempenho, a melhor alternativa é utilizar um software que faça todo esse processo de uma maneira que melhore a autonomia no trabalho
    - O primeiro desses softwares criados foi o RCS, ele funcionava mantendo conjunto de patchs em um formato especial no disco

### CVCS

- Com o tempo foi percebido outro problema do uso desses sistemas acima, a dificuldade de utilizar esse versionamento de codigo em colaboração com uma equipe de desenvolvimento que cada um trabalha-se de uma maquina, a primeira solução criada pra isso foi o CVCSs(Centralized Version Control System), esse sistema tinha um servidor que armazenava todos os arquivos versionados, e as maquinas(desenvolvedores) que faziam esse versionamento.

- O CVCSs foi a maneira oficial de versionamento de código de muitas empresas por um longo tempo, porem mesmo ele sendo muito consistente e importante ele ainda tinha uma grande desvantagem: Por ele funcionar em um servidor, quando esse servidor ficava offline por qualquer motivo, não era possivel fazer qualquer colaboração ou salvar qualquer mudanças versionadas, ademais, se por acaso o HD desse servidor fosse corrompido todos esse versionamento seria perdido pois na epoca não existia uma forma viavel de fazer um backup de tantos dados

## DVCS

- Para resolver o problemas do CVCS, foi desenvolvido um novo tipo de sistema de versionamento de codigo, o DVCS(Distributed Version Control Systems), a grande diferença desse sistemas para os centralizado é que cada colaborador do projeto tem o repositorio do projeto na sua maquina, e o versionamento é feito por commits e updates, diferentemente do sistema centralizado que, só existia um repositorio(servidor) e cada colaborador fazia commits e updates de suas maquinas para ele

- Por cada colaborador ter o repositorio direto em suas maquinas, mesmo com as possíveis quedas de energia do servidor principal ainda sim era possivel fazer atualizações nos arquivos, melhorando consideravelmente a produtividade e a segurança do projeto, pois aqui teríamos as versões do código no dispositivo de todos os colaboradores

## GIT

- O GIT é um sistema distribuído de versionamento de código que foi desenvolvido em 2005 pela comunidade de desenvolvimento do Linux com a ideia de se tornar um sistema padrão de versionamento de código

- Suas principais características são:
    - Velocidade
    - Design simples
    - Suporte para desenvolvimento não lineares
    - Completamente Distribuído
    - Capaz de cuidas de projetos de larga escala como o próprio Linux kernel com eficiência
    
- A principal diferença entre o GIT e os outros VCS é a maneira que o GIT “pensa” sobre os dados[e
- O GIT trabalha versionando os arquivos como series de snapshots, com GIT toda vez que você faz um commit ou salva os dados do seu projeto, o git “cria uma imagem” dos arquivos do seu commit, para aumentar a eficiência

- Os arquivos em um repositorio GIT possuem normalmente 3 estados:
    - Modified : Significa que você alterou um arquivo porem ele ainda não foi “commitado” ainda
    - Staged : Quando um arquivo esta `staged` significa que ele foi marcado para ser “commitado”, ou seja, ele já foi adicionado com o `git add` para ser commitado
    - Committed : Esse termo significa que o arquivo já foi commitado e esta seguramente armazenado no seu repositorio local, virando um novo snapshot
    
- Além desses estados citados acima, ainda existe o estado `untracked` que significa que um arquivo é novo ou alterado, porem ainda não foi adicionado ao repositorio anteriormente