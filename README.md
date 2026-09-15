# 🛡️ TechMatch ATS

> Desafio **Vibe Coding — JobMatch ATS** (DIO), construído do zero no [Lovable](https://lovable.dev).
> Aplicação que compara um currículo de tecnologia (DevOps, Cibersegurança, Suporte, Infraestrutura) com uma vaga e devolve uma versão ATS-friendly, sem nunca inventar experiência que a pessoa não tem.

---

## 🎯 Qual problema a aplicação resolve

Currículos bons de profissionais de tecnologia costumam ser barrados antes mesmo de chegar ao RH, porque os sistemas de triagem automática (ATS — Application Tracking System) ranqueiam candidatos por palavras-chave e formatação, não por competência real. O **TechMatch ATS** resolve isso: o usuário cola a vaga e o currículo, recebe o score de compatibilidade, vê quais palavras-chave faltam e recebe uma versão do currículo reescrita para passar no filtro — **sem inventar nada que a pessoa não tenha feito**.

---

## 🧠 Mega Prompt utilizado

### Versão final (colada no Lovable)

```markdown
# Contexto e Objetivo
Crie uma aplicação web chamada **TechMatch ATS**, focada em otimizar currículos de profissionais de tecnologia (DevOps, Cibersegurança, Suporte e Infraestrutura) para passarem nos filtros de Application Tracking Systems (ATS). A aplicação comparará a descrição de uma vaga com o currículo atual do usuário, apontará o nível de match e gerará uma versão "ATS-friendly" otimizada.

# Identidade Visual e Design System
- **Design System:** Utilize os componentes do `shadcn/ui` para garantir uma interface limpa, acessível e profissional.
- **Tema:** Dark mode por padrão (estética hacker/tech elegante, lembrando um terminal moderno ou estilo Frosted Glass).
- **Paleta de Cores:**
  - Fundo: Slate escuro (Slate-950)
  - Primária: Verde Neon ou Cyan (para botões de ação principal e destaques de match alto).
  - Secundária: Cinza chumbo para cards e áreas de input.
  - Alertas/Avisos: Laranja/Amarelo suave para destacar palavras-chave faltando.

# Fluxo da Aplicação (Layout de Página Única / Dashboard)

## 1. Área de Input (Split Screen ou Cards Lado a Lado)
- **Card Esquerdo (A Vaga):** Um `Textarea` limpo onde o usuário cola a descrição completa da vaga.
- **Card Direito (O Currículo):** Um `Textarea` onde o usuário cola o texto do seu currículo atual.
- **Botão Central:** Um botão grande e chamativo ("Analisar Match & Otimizar CV") usando a cor Primária.

## 2. Área de Resultados (Aparece após a análise)
- **Score de Match:** Um gráfico circular ou barra de progresso mostrando a porcentagem de compatibilidade.
- **Análise de Palavras-Chave (Tags usando shadcn Badge):**
  - "Keywords Encontradas" (Badges verdes).
  - "Keywords Faltando" (Badges laranjas/vermelhas).
- **Feedback Estratégico:** Uma breve seção de texto gerada pela IA explicando o que precisa ser melhorado na estrutura do currículo para essa vaga específica.

## 3. O Currículo Otimizado (ATS-Friendly)
- Uma área com visual de documento (`Paper` ou `Card` branco/claro no meio do tema dark para dar contraste) exibindo a versão reescrita do currículo.
- **Ações:** Botões para "Copiar Texto" e "Exportar para PDF" (usando bibliotecas padrão de frontend para PDF).

# Regras Estritas de Inteligência Artificial e Lógica
1. **Verdade Absoluta (Anti-Alucinação):** A IA deve atuar apenas como uma ferramenta de formatação e otimização de SEO para o currículo. É ESTRITAMENTE PROIBIDO inventar, inferir ou adicionar experiências, cargos, graduações ou habilidades que não estejam no texto original do currículo colado pelo usuário.
2. **Disclaimer Visível:** Adicione um banner ou texto discreto e permanente na interface dizendo: *"O TechMatch ATS otimiza a sua apresentação, mas nunca inventa experiências que você não tem. Revise seu currículo antes de enviar."*
3. **Privacidade (SecOps):** A aplicação deve processar os dados em memória/sessão, não armazenando currículos de forma persistente em bancos de dados públicos sem consentimento. (Aviso LGPD no rodapé).

# Passo a Passo Inicial de Construção
Gere o esqueleto do layout, implemente os formulários de entrada usando `shadcn/ui`, e estruture os estados para exibir a área de resultados. Faça um mock da análise para eu validar a interface antes de integrarmos chamadas reais a LLMs.
