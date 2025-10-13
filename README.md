# Dizai Story Activity

**Descrição:**
Uma aplicação interativa de leitura, desenvolvida em **React** e **TypeScript**. O projeto propõe atividades de alfabetização por meio da leitura de histórias curtas, incentivando as escreverem com base no que foi lido. A utilização de síntese de voz torna a experiência mais interativa e acessível, promovendo a compreensão e o interesse pela leitura de forma lúdica e envolvente.
---

#Tecnologias Utilizadas

<custom-element data-json="%7B%22type%22%3A%22table-metadata%22%2C%22attributes%22%3A%7B%22title%22%3A%22Tecnologias%22%7D%7D" />

| Categoria          | Tecnologias/Recursos                                                                 |
|--------------------|-------------------------------------------------------------------------------------|
| **Frontend**       | React, TypeScript, HTML5, CSS3, TailwindCSS                                         |
| **Hooks**          | `useSpeechSynthesis` (síntese de voz), `useState`, `useEffect`, `useRef`           |
| **Armazenamento**  | `localStorage` (para salvar progresso da história e desenhos)                       |
| **Manipulação Gráfica** | Canvas API (desenho interativo)                                                   |
| **Estilo**         | TailwindCSS, CSS customizado (animações)                                          |
| **Responsividade** | Suporte a eventos de mouse e touch (para dispositivos móveis)                     |
| **Acessibilidade** | Uso de `aria-label` em botões e elementos interativos                              |

---



### **Pré-requisitos**
- Node.js (v16 ou superior)
- npm ou yarn
   
cd diz-ai-story-activity
npm install
npm run dev
diz-ai-story-activity/
├── src/
│   ├── components/
│   │   ├── StoryActivity.tsx   # Componente principal da atividade
│   │   └── Icons.tsx           # Ícones personalizados
│   ├── hooks/
│   │   └── useSpeechSynthesis.ts  # Hook para síntese de voz
│   ├── App.tsx                 # Ponto de entrada da aplicação
│   └── index.tsx               # Renderização do React
├── public/                     # Arquivos estáticos (HTML, imagens, etc.)
├── package.json                # Dependências e scripts
├── tsconfig.json               # Configuração do TypeScript
└── README.md                   # Este arquivo



