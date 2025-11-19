---

📁 ESTRUTURA DE PASTAS (para subir no GitHub)

projeto/
│
├── index.html
│
├── paginas/
│     ├── sobre.html
│     ├── contato.html
│     └── projetos.html
│
├── css/
│     ├── reset.css
│     ├── variables.css
│     ├── global.css
│     ├── layout.css
│     ├── components.css
│     └── utilities.css
│
├── js/
│     └── menu.js
│
└── imagens/
      ├── logo.png
      └── (suas imagens)


---

🎨 SISTEMA DE DESIGN COMPLETO

🎨 1. Variáveis de Cores (8 cores obrigatórias)

Arquivo: css/variables.css

:root {
  /* Primárias */
  --cor-primary-100: #e3f2fd;
  --cor-primary-500: #2196f3;
  --cor-primary-700: #1565c0;

  /* Secundárias */
  --cor-secondary-100: #fff3e0;
  --cor-secondary-500: #ff9800;
  --cor-secondary-700: #ef6c00;

  /* Neutras */
  --cor-gray-100: #f5f5f5;
  --cor-gray-300: #e0e0e0;
  --cor-gray-700: #616161;
  --cor-gray-900: #212121;

  /* Feedback */
  --cor-success: #4caf50;
  --cor-warning: #ffeb3b;
  --cor-error: #f44336;

  /* Tipografia */
  --font-primary: 'Inter', sans-serif;

  /* Tamanhos Tipográficos (5 níveis obrigatórios) */
  --font-xxl: 2.5rem;
  --font-xl: 2rem;
  --font-lg: 1.5rem;
  --font-md: 1.125rem;
  --font-sm: 1rem;

  /* Espaçamentos (Sistema modular) */
  --space-8: 8px;
  --space-16: 16px;
  --space-24: 24px;
  --space-32: 32px;
  --space-48: 48px;
  --space-64: 64px;

  /* Grid */
  --container-max: 1200px;
  --grid-gap: 16px;
}


---

🧩 LEIAUTE: GRID + FLEX + BREAKPOINTS

Arquivo: css/layout.css

🌐 Grid 12 colunas

.container {
  max-width: var(--container-max);
  margin: 0 auto;
  padding: 0 var(--space-16);
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: var(--grid-gap);
}


---

📱 Breakpoints (≥ 5)

/* mobile minimo */
@media (max-width: 480px) {}

/* mobile */
@media (max-width: 768px) {}

/* tablet */
@media (max-width: 992px) {}

/* desktop */
@media (max-width: 1200px) {}

/* telas grandes */
@media (min-width: 1400px) {}


---

🍔 MENU RESPONSIVO COM HAMBÚRGUER E DROPDOWN

HTML (coloque no header do index.html)

<header class="header">
  <div class="logo">Meu Projeto</div>

  <nav class="menu">
    <ul>
      <li><a href="index.html">Início</a></li>
      <li class="dropdown">
        <a href="#">Serviços</a>
        <ul class="submenu">
          <li><a href="#">Design</a></li>
          <li><a href="#">Desenvolvimento</a></li>
          <li><a href="#">Consultoria</a></li>
        </ul>
      </li>
      <li><a href="paginas/projetos.html">Projetos</a></li>
      <li><a href="paginas/contato.html">Contato</a></li>
    </ul>
  </nav>

  <button class="hamburger" aria-label="Menu Mobile">☰</button>
</header>

CSS

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: var(--space-16);
  background: var(--cor-primary-500);
  color: white;
}

.menu ul {
  display: flex;
  gap: var(--space-24);
}

.dropdown .submenu {
  display: none;
  position: absolute;
  background: white;
  padding: var(--space-16);
}

.dropdown:hover .submenu {
  display: block;
}

.hamburger {
  display: none;
  background: none;
  border: none;
  font-size: 2rem;
}

Mobile

@media (max-width: 768px) {
  .menu ul {
    display: none;
    flex-direction: column;
    background: white;
    position: absolute;
    top: 60px;
    right: 0;
    width: 70%;
    padding: var(--space-24);
  }

  .hamburger {
    display: block;
  }

  .menu.active ul {
    display: flex;
  }
}


---

🧩 COMPONENTES DE INTERFACE

🟦 Botões (com todos os estados)

.btn {
  padding: var(--space-16) var(--space-24);
  border-radius: 8px;
  border: none;
  cursor: pointer;
  background: var(--cor-primary-500);
  color: white;
  transition: 0.2s;
}

.btn:hover { background: var(--cor-primary-700); }
.btn:active { transform: scale(0.97); }
.btn:disabled { background: var(--cor-gray-300); cursor: not-allowed; }


---

🗂 Cards Responsivos

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: var(--space-24);
}

.card {
  background: white;
  border-radius: 12px;
  padding: var(--space-24);
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}


---

📝 Formulários com feedback visual

input, textarea {
  width: 100%;
  padding: var(--space-16);
  border: 1px solid var(--cor-gray-300);
  border-radius: 8px;
}

input:focus {
  outline: 2px solid var(--cor-primary-500);
}

input.error {
  border-color: var(--cor-error);
}


---

⚠️ Alerts, Toasts e Modal

Alerts

.alert {
  padding: var(--space-16);
  border-radius: 8px;
}

.alert-success { background: var(--cor-success); color: white; }
.alert-error { background: var(--cor-error); color: white; }
.alert-warning { background: var(--cor-warning); }

Modal

.modal {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.6);
  justify-content: center;
  align-items: center;
}

.modal-content {
  background: white;
  padding: var(--space-32);
  border-radius: 12px;
}


---
