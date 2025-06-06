# ⏱️ Ignite Timer

<div align="center">
  <img src="src/assets/logo-ignite.svg" alt="Ignite Timer Logo" width="80" height="80">
  
  <p>Um timer inteligente para técnica Pomodoro, desenvolvido para aumentar produtividade e foco no trabalho.</p>

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Styled Components](https://img.shields.io/badge/styled--components-DB7093?style=for-the-badge&logo=styled-components&logoColor=white)
![React Router](https://img.shields.io/badge/React_Router-CA4245?style=for-the-badge&logo=react-router&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)

</div>

## 📋 Sobre o Projeto

O **Ignite Timer** é uma aplicação web moderna para gerenciamento de tempo baseada na técnica Pomodoro. Permite criar ciclos de trabalho personalizados, acompanhar o progresso em tempo real e manter um histórico completo das tarefas realizadas.

### ✨ Principais Funcionalidades

- ⏰ **Timer Customizável**: Configure ciclos de 5 a 60 minutos
- 📝 **Gestão de Tarefas**: Nomeie e organize suas atividades
- 📊 **Histórico Completo**: Acompanhe todas as sessões realizadas
- 🎯 **Status em Tempo Real**: Visualize tarefas concluídas, interrompidas ou em andamento
- 💾 **Persistência Local**: Dados salvos automaticamente no navegador
- 🔄 **Navegação Intuitiva**: Interface limpa e responsiva

## 🛠️ Tecnologias Utilizadas

### Core

- **React 18** - Biblioteca principal para construção da interface
- **TypeScript** - Tipagem estática para maior segurança e produtividade
- **Vite** - Build tool moderna e performática

### Estilização

- **Styled Components** - CSS-in-JS para componentes estilizados
- **Phosphor React** - Biblioteca de ícones moderna e consistente

### Roteamento & Formulários

- **React Router DOM** - Navegação SPA com roteamento declarativo
- **React Hook Form** - Gerenciamento eficiente de formulários
- **Zod** - Validação de schemas TypeScript-first

### Gerenciamento de Estado

- **React Context API** - Estado global da aplicação
- **useReducer** - Gerenciamento de estado complexo
- **Immer** - Atualizações imutáveis simplificadas

### Utilitários

- **date-fns** - Manipulação e formatação de datas
- **LocalStorage** - Persistência de dados no navegador

## 🏗️ Arquitetura do Projeto

```
src/
├── @types/           # Definições de tipos TypeScript
├── assets/          # Recursos estáticos (logos, imagens)
├── components/      # Componentes reutilizáveis
│   └── Header/
├── contexts/        # Contextos React (estado global)
├── layouts/         # Layouts da aplicação
├── pages/           # Páginas da aplicação
│   ├── Home/        # Timer principal
│   └── History/     # Histórico de ciclos
├── reducers/        # Reducers para gerenciamento de estado
├── styles/          # Temas e estilos globais
└── Router.tsx       # Configuração de rotas
```

### 🔄 Padrões Implementados

- **Compound Component Pattern**: Componentes compostos para maior flexibilidade
- **Context + Reducer Pattern**: Gerenciamento de estado previsível
- **Custom Hooks**: Lógica reutilizável encapsulada
- **Controlled Components**: Formulários controlados com validação
- **Composition over Inheritance**: Composição de componentes

## 🚀 Como Executar

### Pré-requisitos

- Node.js (versão 16 ou superior)
- npm ou yarn

### Instalação

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/ignite-timer.git

# Entre na pasta do projeto
cd ignite-timer

# Instale as dependências
npm install

# Execute o projeto
npm run dev
```

A aplicação estará disponível em `http://localhost:5173`

## 📺 Demonstração

### Tela Principal - Timer

- Interface limpa para configurar tarefas
- Countdown visual em tempo real
- Controles intuitivos de start/stop

### Tela de Histórico

- Tabela responsiva com todas as sessões
- Status coloridos (Concluído, Interrompido, Em andamento)
- Formatação de datas em português brasileiro

## 🎯 Funcionalidades Técnicas Destacadas

### Context API + useReducer

Implementação robusta de gerenciamento de estado global:

```typescript
interface CyclesContextType {
  cycles: Cycle[]
  activeCycle: Cycle | undefined
  createNewCycle: (data: CreateCycleData) => void
  interruptCurrentCycle: () => void
  markCurrentCycleAsFinished: () => void
}
```

### Validação com Zod

Schema de validação type-safe:

```typescript
const newCycleFormValidationSchema = zod.object({
  task: zod.string().min(1, 'Informe o nome da tarefa'),
  minutesAmount: zod
    .number()
    .min(5, 'O ciclo precisa ser de no mínimo 5 minutos.')
    .max(60, 'O ciclo precisa ser de no máximo 60 minutos.'),
})
```

### Persistência Inteligente

Dados persistem automaticamente no localStorage:

```typescript
useEffect(() => {
  const stateJSON = JSON.stringify(cyclesState)
  localStorage.setItem('@ignite-timer:cycles-state-1.0.0', stateJSON)
}, [cyclesState])
```

## 📱 Responsividade

- Design adaptável para desktop, tablet e mobile
- Componentes flexíveis com CSS Grid e Flexbox
- Tipografia responsiva e espaçamentos consistentes

## 🔮 Possíveis Melhorias Futuras

- [ ] Notificações push quando o ciclo terminar
- [ ] Tema escuro/claro
- [ ] Estatísticas detalhadas de produtividade
- [ ] Integração com calendário
- [ ] Export de dados para CSV
- [ ] Sons personalizáveis
- [ ] PWA (Progressive Web App)

## 📄 Licença

Este projeto foi desenvolvido durante o curso Ignite da Rocketseat como projeto educacional.

---

<div align="center">
  Desenvolvido com ❤️ e ☕ usando React + TypeScript
  
  <p>Se este projeto foi útil, considere dar uma ⭐!</p>
</div>
