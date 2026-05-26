# Padrões e Melhorias Futuras

Backlog vivo de feedbacks coletados em uso real e melhorias planejadas para próximas revisões. Atualizar a cada ciclo de uso.

---

## Feedbacks coletados — PSW e padrões similares

Feedbacks observados em projetos anteriores da Mais Performance, a considerar em revisões futuras.

### Auto-teste exposto na UI

**Observação**: usuários finais se perdem com a seção de auto-testes visível. Botões e elementos técnicos confundem sobre "o que clicar".

**Origem**: PSW expõe `<details>` com testes da lógica de cálculo direto na página.

**Decisão para Armaduras v2.1**: não incluir auto-testes na UI (já omitidos).

**Recomendação para próxima revisão do PSW**: esconder por completo a seção de auto-testes do usuário final. Manter apenas como suite de teste fora da página principal (arquivo separado, ou rota oculta tipo `?debug=1`).

### Modo apresentação

**Observação**: feature útil em desktop (para projetor em workshop), mas problemática em mobile porque ao acionar volta para o topo, dificultando ver o resultado.

**Origem**: PSW tem botão "Modo apresentação" que oculta formulário e mostra só resultado, mas exige scroll de volta após terminar.

**Decisão para Armaduras v2.1**: não incluir agora.

**Recomendação para próxima revisão**:
- Em desktop, manter modo apresentação **com barra de menu fixa no topo**, permitindo navegação clara
- Em mobile, ou esconder o modo apresentação, ou redesenhar para que ao terminar a pessoa veja diretamente o resultado sem precisar acionar nada
- Avaliar se vale a pena ter o modo, ou se o layout normal já é suficiente para projetor

### Discoverability do resultado

**Observação**: ao terminar de responder, usuário não sabe imediatamente como ver o resultado. Barra de rolagem longa contribui para isso.

**Decisão para Armaduras v2.1**: botão "Ver resultado" aparece como sticky bar no rodapé (sempre visível durante o preenchimento), e fica destacado quando todas as 25 perguntas estão respondidas.

**Recomendação para revisão do PSW**: aplicar o mesmo padrão de sticky bar com botão de resultado contextual.

---

## Itens internos a observar em uso real do Armaduras

Registrados durante desenvolvimento, para revalidar com dados de uso:

### Conteúdo / matriz

- **#21** ("sou o único que sabe") alocado a CTR puro. Pessoa que marca alto pode ter motor AUT em vez de CTR. Observar.
- **#15** (acumular em silêncio) era cross AUT+HIP. Próximo de #09. Observar correlação.
- **#31** e **#32** (novos em v2.1) tocam o mesmo motor por ângulos diferentes (emoção × crença). Provável correlação alta — decisão consciente.
- **#26** ("salvador") teve sinal de motor possivelmente diferente de AGR em piloto inicial. Aguardar dados.
- **Acquiescência** (tendência a marcar 4-5 em tudo): se aparecer como padrão recorrente, revisitar decisão sobre não usar ipsatização.

### Apresentação

- **Percentual** pode sugerir "diagnóstico de completude" (100% = "sou totalmente perfeccionista"). Frase-âncora mitiga, mas monitorar leitura dos respondentes.
- **Devolutiva** longa em celular pode pesar. Observar se respondentes fecham antes de ler tudo.
- **Tempo de resposta** alvo: 4-5 min. Em piloto técnico, Kleber levou 7m43s (modo validação atenta). Em workshop real, esperar mais próximo do alvo.

### Técnico

- **Logo embarcada em base64** aumenta arquivo HTML para ~78KB. OK para MVP. Se virar relevante: salvar como arquivo separado e referenciar via `src="logo.jpg"`.
- **Sem coleta de dados** (Opção 1): tudo no `localStorage` do respondente. Para próximas iterações, avaliar se Carol quer painel com resultados agregados (Opção 2 ou 3 — exige backend, LGPD, política de privacidade).

---

## Ideias / extensões para versões futuras

Sem prazo definido, registrar à medida que surgem:

### Conteúdo

- Adicionar armaduras candidatas mapeadas mas não incluídas:
  - Distanciamento / Cinismo
  - Humor Defensivo
  - Racionalização
  - Blindagem Técnica
  - Comparação Defensiva
- Versões do instrumento para diferentes públicos (ex.: liderança vs. equipe técnica)

### Funcionalidade

- Exportar resultado direto para email da Carol (com consentimento explícito do respondente)
- Modo "comparar com workshop anterior" (requer salvar histórico por respondente)
- Versão facilitador: tela administrativa mostrando resultados agregados de uma turma (com login Carol)

### Pedagogia

- Fase 8 do plano original — Guia de Aplicação para o Facilitador — ficou suspensa. Retomar quando o instrumento estabilizar.

---

## Processo de atualização deste arquivo

Cada vez que houver:
- Feedback de respondente que sugira mudança
- Aprendizado em workshop real
- Decisão de não fazer algo agora (para registrar a razão)
- Ideia que surge mas não cabe na versão atual

Adicionar aqui com **data, contexto, decisão tomada** (se houver) e **status** (a fazer, decidido, descartado).
