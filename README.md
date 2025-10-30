# Diz ai Story 

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
https://ai.studio/apps/drive/1JSnEoZHSrBkjd9yDccCMKvp9_FD23caZ
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

Como não tenho acesso ao repositório ou ao código-fonte completo do seu projeto (apenas ao componente `StoryActivity.tsx` que você compartilhou anteriormente), não posso fornecer o código-fonte inteiro da aplicação. No entanto, posso **reconstruir a estrutura básica do projeto** com base no que você já enviou, incluindo os arquivos essenciais para que você possa montar um projeto funcional localmente.

Aqui está a estrutura e o código dos arquivos principais que você provavelmente precisa:

---

### **1. Estrutura do Projeto**
```
dizai-story-activity/
├── src/
│   ├── components/
│   │   ├── StoryActivity.tsx   # Componente que você já compartilhou
│   │   └── Icons.tsx           # Arquivo de ícones (exemplo abaixo)
│   ├── hooks/
│   │   └── useSpeechSynthesis.ts # Hook para síntese de voz (exemplo abaixo)
│   ├── App.tsx                 # Ponto de entrada (exemplo abaixo)
│   └── index.tsx               # Renderização do React (exemplo abaixo)
├── public/
│   └── index.html              # HTML base (exemplo abaixo)
├── package.json                # Dependências (exemplo abaixo)
├── tsconfig.json               # Configuração do TypeScript (exemplo abaixo)
└── README.md                   # O README que te forneci
```

---

### **2. `src/components/Icons.tsx`**
Crie este arquivo para os ícones usados no `StoryActivity`:

```tsx
// src/components/Icons.tsx
import React from 'react';

export const IconCheckCircle: React.FC<{ className?: string }> = ({ className }) => (
  <svg xmlns="http://www.w3.org/2000/svg" className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
  </svg>
);

export const IconSound: React.FC<{ className?: string }> = ({ className }) => (
  <svg xmlns="http://www.w3.org/2000/svg" className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
  </svg>
);

export const IconRefresh: React.FC<{ className?: string }> = ({ className }) => (
  <svg xmlns="http://www.w3.org/2000/svg" className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15" />
  </svg>
);
```

---

### **3. `src/hooks/useSpeechSynthesis.ts`**
Hook para síntese de voz:

```tsx
// src/hooks/useSpeechSynthesis.ts
import { useEffect } from 'react';

export const useSpeechSynthesis = () => {
  const speak = (text: string) => {
    if ('speechSynthesis' in window) {
      const utterance = new SpeechSynthesisUtterance(text);
      utterance.lang = 'pt-BR';
      window.speechSynthesis.speak(utterance);
    } else {
      console.warn('API de síntese de voz não suportada neste navegador.');
    }
  };

  return { speak };
};
```

---

### **4. `src/App.tsx`**
Ponto de entrada da aplicação:

```tsx
// src/App.tsx
import React from 'react';
import StoryActivity from './components/StoryActivity';

const App: React.FC = () => {
  const handleBack = () => {
    console.log('Voltar para os níveis');
  };

  const handleComplete = () => {
    console.log('Nível concluído!');
  };

  return (
    <div className="min-h-screen bg-gray-100 flex items-center justify-center p-4">
      <StoryActivity onBack={handleBack} onComplete={handleComplete} />
    </div>
  );
};

export default App;
```

---

### **5. `src/index.tsx`**
Renderização do React:

```tsx
// src/index.tsx
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import './index.css';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
```

---

### **6. `public/index.html`**
HTML base:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Dizai Story Activity</title>
</head>
<body>
  <div id="root"></div>
</body>
</html>
```

---

### **7. `package.json`**
Dependências do projeto:

```json
{
  "name": "diz-ai-story-activity",
  "version": "1.0.0",
  "private": true,
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "typescript": "^4.9.5"
  },
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "devDependencies": {
    "@types/react": "^18.2.0",
    "@types/react-dom": "^18.2.0",
    "autoprefixer": "^10.4.14",
    "postcss": "^8.4.27",
    "tailwindcss": "^3.3.3",
    "vite": "^4.4.9"
  }
}
```

---

### **8. `tsconfig.json`**
Configuração do TypeScript:

```json
{
  "compilerOptions": {
    "target": "es5",
    "lib": ["dom", "dom.iterable", "esnext"],
    "allowJs": true,
    "skipLibCheck": true,
    "esModuleInterop": true,
    "allowSyntheticDefaultImports": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noFallthroughCasesInSwitch": true,
    "module": "esnext",
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx",
    "baseUrl": ".",
    "paths": {
      "@/*": ["src/*"]
    }
  },
  "include": ["src"],
  "exclude": ["node_modules"]
}
```

---

### **9. `tailwind.config.js`** (Opcional)
Se quiser usar TailwindCSS, crie este arquivo:

```js
// tailwind.config.js
module.exports = {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

---

### **10. `postcss.config.js`** (Opcional)
Para processar o TailwindCSS:

```js
// postcss.config.js
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```

---

### **Como Rodar o Projeto**
1. Instale as dependências:
   ```bash
   npm install

2. Inicie o servidor de desenvolvimento:
   ```bash
   npm run dev
   

