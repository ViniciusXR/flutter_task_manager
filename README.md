# 📱 Task Manager Pro

<div align="center">

![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?style=for-the-badge&logo=dart&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![iOS](https://img.shields.io/badge/iOS-000000?style=for-the-badge&logo=ios&logoColor=white)

**Aplicativo completo de gerenciamento de tarefas desenvolvido em Flutter**

[Características](#-características) •
[Tecnologias](#-tecnologias) •
[Instalação](#-instalação) •
[Estrutura](#-estrutura-do-projeto) •
[Funcionalidades](#-funcionalidades)

</div>

---

## 📋 Sobre o Projeto

Task Manager Pro é um aplicativo móvel moderno e completo para gerenciamento de tarefas, desenvolvido com Flutter e Material Design 3. O projeto foi criado como parte do curso de Engenharia de Software da PUC Minas, na disciplina de Laboratório de Desenvolvimento de Aplicações Móveis e Distribuídas.

### 🎯 Para que serve?

O aplicativo permite aos usuários:
- ✅ Criar e organizar tarefas de forma eficiente
- 🏷️ Categorizar tarefas por tipo (trabalho, pessoal, estudos, etc.)
- 📅 Definir prazos e receber alertas de vencimento
- 🔔 Configurar lembretes com notificações locais
- 🎨 Personalizar a experiência com temas claro/escuro
- 🔍 Buscar e filtrar tarefas rapidamente
- 📊 Visualizar estatísticas e progresso

---

## ✨ Características

- 🎨 **Interface Moderna** - Design baseado em Material Design 3
- 🌓 **Tema Claro/Escuro** - Alternância automática ou manual
- 📱 **Responsivo** - Funciona em diferentes tamanhos de tela
- 💾 **Persistência Local** - Dados salvos usando SQLite
- 🔔 **Notificações Push** - Lembretes locais agendados
- 🎯 **Filtros Avançados** - Por status, categoria, prioridade
- 🔍 **Busca em Tempo Real** - Encontre tarefas instantaneamente
- 🚩 **Sistema de Prioridades** - Baixa, Média, Alta, Urgente
- ⏰ **Alertas de Vencimento** - Destaque visual para tarefas atrasadas

---

## 🚀 Tecnologias

### Core
- **Flutter** ^3.9.2 - Framework multiplataforma
- **Dart** ^3.9.2 - Linguagem de programação

### Persistência de Dados
- **sqflite** ^2.3.0 - Banco de dados SQLite local
- **path_provider** ^2.1.1 - Acesso a diretórios do sistema
- **path** ^1.8.3 - Manipulação de caminhos de arquivo

### Notificações
- **flutter_local_notifications** ^17.2.3 - Notificações locais
- **timezone** ^0.9.4 - Gerenciamento de fusos horários

### Utilidades
- **uuid** ^4.2.1 - Geração de IDs únicos
- **intl** ^0.19.0 - Internacionalização e formatação

---

## 📦 Instalação

### Pré-requisitos

- Flutter SDK (>= 3.9.2)
- Dart SDK (>= 3.9.2)
- Android Studio / Xcode (para emuladores)
- Git

### Passo a Passo

1. **Clone o repositório**
```bash
git clone https://github.com/ViniciusXR/flutter_task_manager.git
cd flutter_task_manager
```

2. **Instale as dependências**
```bash
flutter pub get
```

3. **Execute o aplicativo**

Para Android:
```bash
flutter run
```

Para dispositivo específico:
```bash
flutter devices  # Lista dispositivos disponíveis
flutter run -d <device_id>
```

4. **Build para produção**

Android:
```bash
flutter build apk --release
```

iOS:
```bash
flutter build ios --release
```

---

## 📁 Estrutura do Projeto

```
flutter_task_manager/
├── android/                      # Configurações Android
│   ├── app/
│   │   ├── src/main/
│   │   │   └── AndroidManifest.xml  # Permissões e configurações
│   │   └── build.gradle.kts         # Build e dependências
│   └── ...
├── ios/                          # Configurações iOS
├── lib/                          # Código fonte Dart
│   ├── main.dart                 # Ponto de entrada do app
│   ├── models/                   # Modelos de dados
│   │   ├── task.dart            # Modelo de Tarefa
│   │   └── category.dart        # Modelo de Categoria
│   ├── screens/                  # Telas do aplicativo
│   │   ├── task_list_screen.dart    # Tela principal (lista)
│   │   └── task_form_screen.dart    # Tela de formulário
│   ├── widgets/                  # Widgets reutilizáveis
│   │   └── task_card.dart       # Card de tarefa
│   └── services/                 # Serviços
│       ├── database_service.dart        # Gerenciamento SQLite
│       └── notification_service.dart    # Gerenciamento de notificações
├── test/                         # Testes
├── pubspec.yaml                  # Dependências do projeto
├── analysis_options.yaml         # Configurações de análise
└── README.md                     # Este arquivo
```

### Arquitetura

O projeto segue uma arquitetura em camadas:

```
┌─────────────────────────────────────┐
│         Presentation Layer          │
│  (Screens, Widgets, UI Components)  │
├─────────────────────────────────────┤
│         Business Logic Layer        │
│     (State Management, Models)      │
├─────────────────────────────────────┤
│          Service Layer              │
│  (Database, Notifications, APIs)    │
├─────────────────────────────────────┤
│          Data Layer                 │
│      (SQLite, Local Storage)        │
└─────────────────────────────────────┘
```

---

## 🎯 Funcionalidades

### 📝 Gerenciamento de Tarefas

#### Criar Tarefa
- Título e descrição
- Seleção de prioridade (Baixa, Média, Alta, Urgente)
- Escolha de categoria (8 categorias pré-definidas)
- Data de vencimento opcional
- Lembrete com data e hora
- Marcar como completa/incompleta

#### Editar Tarefa
- Modificar qualquer campo
- Atualizar lembretes
- Alterar categoria e prioridade

#### Deletar Tarefa
- Confirmação antes de excluir
- Cancelamento automático de notificações

### 🏷️ Sistema de Categorias

8 categorias pré-definidas com cores e ícones únicos:

| Categoria | Cor | Ícone | Uso |
|-----------|-----|-------|-----|
| 💼 Trabalho | Azul | work | Tarefas profissionais |
| 👤 Pessoal | Verde | person | Tarefas pessoais |
| 🛒 Compras | Laranja | shopping_cart | Lista de compras |
| ❤️ Saúde | Vermelho | favorite | Saúde e bem-estar |
| 📚 Estudos | Roxo | school | Educação e cursos |
| 💰 Finanças | Verde-água | attach_money | Finanças pessoais |
| 🏠 Casa | Marrom | home | Tarefas domésticas |
| 📁 Outros | Cinza | category | Diversos |

### 📅 Data de Vencimento

- **Seleção fácil**: DatePicker integrado
- **Alerta visual**: Badge "VENCIDA" em vermelho
- **Destaque**: Borda vermelha em tarefas atrasadas
- **Ordenação**: Opção de ordenar por vencimento
- **Flexível**: Data opcional

### 🔔 Sistema de Notificações

- **Agendamento**: Selecione data e hora
- **Notificação push**: Alerta no horário exato
- **Cancelamento automático**: Ao completar tarefa
- **Reagendamento**: Ao desmarcar tarefa completa
- **Permissões**: Solicita automaticamente

### 🎨 Temas

- **Tema Claro**: Para uso diurno
- **Tema Escuro**: Economiza bateria, melhor à noite
- **Modo Sistema**: Segue configuração do dispositivo
- **Alternância fácil**: Botão no AppBar

### 🔍 Busca e Filtros

#### Busca em Tempo Real
- Busca por título
- Busca por descrição
- Case-insensitive
- Resultados instantâneos

#### Filtros por Status
- Todas as tarefas
- Apenas pendentes
- Apenas concluídas

#### Filtro por Categoria
- Todas as categorias
- Filtro individual por categoria
- Visual com ícones e cores

### ⚡ Ordenação

Múltiplos critérios de ordenação:

- **Por Data de Criação**: Mais recentes primeiro
- **Por Vencimento**: Próximas a vencer primeiro
- **Por Prioridade**: Urgente → Alta → Média → Baixa
- **Por Título**: Ordem alfabética (A-Z)

### 📊 Estatísticas

Card de estatísticas na tela principal:
- Total de tarefas
- Tarefas pendentes
- Tarefas concluídas
- Visual com ícones e cores

### 🎯 Estados Visuais

#### Cards de Tarefa
- Checkbox de conclusão
- Badge de categoria colorido
- Badge de prioridade
- Badge de vencimento (se definido)
- Badge de lembrete (se agendado)
- Alerta "VENCIDA" para tarefas atrasadas
- Botão de deletar

#### Estados Especiais
- Tarefas completas: Texto riscado, opacidade reduzida
- Tarefas vencidas: Borda e badge vermelhos
- Tarefas com lembrete: Ícone de sino laranja
- Layout responsivo com wrap

---

## 🎮 Como Usar

### Criando uma Tarefa

1. Toque no botão **"+ Nova Tarefa"** (FAB)
2. Preencha o título (obrigatório)
3. Adicione descrição (opcional)
4. Selecione prioridade
5. Escolha uma categoria
6. Defina data de vencimento (opcional)
7. Configure lembrete (opcional)
8. Toque em **"Criar Tarefa"**

### Organizando Tarefas

1. **Buscar**: Digite no campo de busca
2. **Filtrar por status**: Menu com ícone de filtro
3. **Filtrar por categoria**: Menu com ícone de categoria
4. **Ordenar**: Menu com ícone de ordenação
5. **Alternar tema**: Menu com ícone de brilho

### Gerenciando Tarefas

- **Marcar como completa**: Toque no checkbox
- **Editar**: Toque no card da tarefa
- **Deletar**: Toque no ícone de lixeira
- **Atualizar lista**: Puxe para baixo (pull-to-refresh)

---

## 📊 Relatório Técnico - Laboratório 2: Interface Profissional

### 1. Implementações Realizadas

#### Funcionalidades Principais

**Laboratório 1 - Fundamentos (Base SQLite)**
- ✅ CRUD completo de tarefas
- ✅ Persistência com SQLite (sqflite)
- ✅ Modelo Task básico (id, title, description, isCompleted, priority, createdAt)
- ✅ Interface simples com lista de tarefas
- ✅ Formulário de criação/edição
- ✅ Sistema de prioridades (Baixa, Média, Alta, Urgente)

**Laboratório 2 - Interface Profissional (Novas Implementações)**

1. **Sistema de Temas (Customização 1)**
   - Tema Claro com esquema de cores Material Design 3
   - Tema Escuro otimizado para economia de bateria
   - Modo Sistema que detecta preferência do dispositivo
   - Alternância rápida via botão no AppBar
   - Persistência da escolha do usuário

2. **Busca em Tempo Real (Customização 2)**
   - Campo de busca integrado no AppBar
   - Busca por título e descrição simultaneamente
   - Atualização instantânea (case-insensitive)
   - Visual com ícone de busca e hint text
   - Função de limpar busca rápida

3. **Sistema de Ordenação Avançado (Customização 3)**
   - Por Data de Criação (mais recentes primeiro)
   - Por Prioridade (Urgente → Alta → Média → Baixa)
   - Por Título (ordem alfabética A-Z)
   - Por Data de Vencimento (implementação do Exercício 1)
   - Menu dropdown intuitivo com ícones

4. **Data de Vencimento (Exercício 1)**
   - Campo `dueDate` (DateTime nullable) no modelo
   - DatePicker com validação de datas
   - Propriedade computada `isOverdue` para detectar atraso
   - Alertas visuais: badge vermelho "VENCIDA" + borda vermelha
   - Ordenação inteligente (tarefas próximas a vencer primeiro)
   - Migração de banco de dados (v1 → v2)

5. **Sistema de Categorias (Exercício 2)**
   - Modelo `Category` com 8 categorias pré-definidas
   - Propriedades: id, name, color, icon
   - Dropdown visual com ícones coloridos
   - Filtro por categoria no AppBar
   - Cores distintivas em badges e bordas
   - Campo `categoryId` no modelo Task

6. **Notificações Locais (Exercício 3)**
   - Serviço completo `NotificationService`
   - Integração com `flutter_local_notifications` e `timezone`
   - Seleção de data e hora para lembretes
   - Agendamento automático de notificações
   - Cancelamento ao completar/deletar tarefa
   - Reagendamento ao desmarcar tarefa
   - Permissões Android (SCHEDULE_EXACT_ALARM, POST_NOTIFICATIONS)
   - Fallback para alarmes inexatos quando necessário

#### Componentes Material Design 3 Utilizados

- **AppBar**: Com actions (tema, ordenação, filtros)
- **FloatingActionButton**: Criação de novas tarefas
- **Card**: Exibição de tarefas com elevation e bordas
- **Checkbox**: Marcar tarefas como completas
- **TextField**: Busca e formulários
- **DropdownButton**: Seleção de prioridade, categoria, filtros
- **IconButton**: Ações rápidas (deletar, limpar)
- **Badge**: Indicadores visuais (categoria, vencimento, lembrete)
- **Chip**: Tags de prioridade
- **ListTile**: Estatísticas
- **DatePicker**: Seleção de datas
- **TimePicker**: Seleção de horários
- **SnackBar**: Feedback de ações
- **Dialog**: Confirmações
- **Wrap**: Layout responsivo para badges
- **ColorScheme**: Esquema de cores consistente

---

### 2. Desafios Encontrados

#### Desafio 1: Android Gradle Desugaring
**Problema:** Erro de compilação ao adicionar `flutter_local_notifications`:
```
Dependency requires core library desugaring to be enabled for 'androidx.core:core:1.13.0'
```

**Causa:** O pacote de notificações requer APIs Java 8+ que não estão disponíveis em versões antigas do Android.

**Solução Implementada:**
```kotlin
// android/app/build.gradle.kts
android {
    compileOptions {
        isCoreLibraryDesugaringEnabled = true
    }
}

dependencies {
    coreLibraryDesugaring("com.android.tools:desugar_jdk_libs:2.0.3")
}
```

#### Desafio 2: Formatação de Datas com DateFormat
**Problema:** Crash ao criar tarefas com `DateFormat('dd/MM/yyyy').format(date)`:
```
FormatException: Invalid date format
```

**Causa:** Incompatibilidade entre o padrão de formatação e a localização do sistema.

**Solução Implementada:**
```dart
// Substituição de DateFormat por formatação manual
String _formatDate(DateTime date) {
  return '${date.day.toString().padLeft(2, '0')}/'
         '${date.month.toString().padLeft(2, '0')}/'
         '${date.year}';
}
```

#### Desafio 3: Permissões de Alarmes Exatos (Android 12+)
**Problema:** `PlatformException: exact_alarms_not_permitted` ao agendar notificações.

**Causa:** Android 12+ requer permissão explícita para alarmes exatos (`SCHEDULE_EXACT_ALARM`).

**Solução Implementada:**
1. Adicionadas permissões no `AndroidManifest.xml`:
```xml
<uses-permission android:name="android.permission.SCHEDULE_EXACT_ALARM"/>
<uses-permission android:name="android.permission.USE_EXACT_ALARM"/>
<uses-permission android:name="android.permission.POST_NOTIFICATIONS"/>
```

2. Implementado fallback no código:
```dart
try {
  await flutterLocalNotificationsPlugin.zonedSchedule(
    /* ... */
    androidScheduleMode: AndroidScheduleMode.exactAllowWhileIdle,
  );
} catch (e) {
  // Fallback para alarme inexato
  await flutterLocalNotificationsPlugin.zonedSchedule(
    /* ... */
    androidScheduleMode: AndroidScheduleMode.inexactAllowWhileIdle,
  );
}
```

#### Desafio 4: Migração de Banco de Dados
**Problema:** Adicionar novos campos sem perder dados existentes.

**Solução:** Sistema de versionamento com migração automática:
```dart
await db.execute('''
  ALTER TABLE tasks ADD COLUMN dueDate TEXT;
  ALTER TABLE tasks ADD COLUMN categoryId TEXT DEFAULT 'work';
  ALTER TABLE tasks ADD COLUMN reminderTime TEXT;
''');
```

---

### 3. Melhorias Implementadas

#### Além do Roteiro Básico

1. **Estatísticas em Tempo Real**
   - Card na tela principal com total, pendentes e concluídas
   - Atualização automática ao modificar tarefas
   - Ícones e cores diferenciadas

2. **Alertas Visuais Inteligentes**
   - Badge "VENCIDA" em vermelho para tarefas atrasadas
   - Borda vermelha destacando urgência
   - Ícone de warning (⚠️) em tarefas vencidas
   - Texto riscado e opacidade para tarefas completas

3. **Layout Responsivo com Wrap**
   - Múltiplos badges (categoria + prioridade + vencimento + lembrete)
   - Adaptação automática ao tamanho da tela
   - Quebra de linha inteligente quando necessário

4. **Sistema de Cores por Categoria**
   - 8 cores distintas e harmoniosas
   - Aplicação consistente em badges e bordas
   - Paleta baseada em Material Design

5. **Cancelamento Inteligente de Notificações**
   - Automático ao completar tarefa
   - Automático ao deletar tarefa
   - Reagendamento ao desmarcar como completa

6. **Validações Avançadas**
   - Apenas datas futuras para lembretes
   - Campos opcionais mas validados
   - Feedback visual ao usuário

#### Customizações de UI/UX

1. **AppBar com Gradiente Visual**
   - Design profissional com múltiplas actions
   - Organização hierárquica de funcionalidades
   - Ícones intuitivos e consistentes

2. **FloatingActionButton Destacado**
   - Cor primária chamativa
   - Posicionamento estratégico
   - Label descritivo

3. **Cards Elevados e Sombras**
   - Elevation para profundidade
   - Margin e padding consistentes
   - Bordas arredondadas

4. **Feedback Tátil**
   - SnackBars para confirmações
   - Diálogos para ações destrutivas
   - Estados visuais (hover, pressed)

---

### 4. Aprendizados

#### Principais Conceitos Aprendidos

1. **Gerenciamento de Estado Avançado**
   - StatefulWidget vs StatelessWidget
   - setState() para atualizações reativas
   - Passagem de callbacks entre widgets
   - Sincronização entre múltiplas telas

2. **Persistência de Dados Complexa**
   - Migração de schemas SQLite
   - Campos nullable e valores default
   - Queries com JOINs e filtros
   - Versionamento de banco de dados

3. **Notificações Locais**
   - Configuração de canais Android
   - Agendamento com timezone
   - Permissões runtime
   - Tratamento de erros específicos da plataforma

4. **Material Design 3**
   - Sistema de temas (light/dark)
   - ColorScheme e customização
   - Componentes modernos (badges, chips)
   - Responsividade e layouts flexíveis

5. **Integração Android/iOS**
   - Configurações nativas (Gradle, Podfile)
   - Permissões específicas de plataforma
   - Core library desugaring
   - AndroidManifest.xml e Info.plist

6. **Arquitetura de Software**
   - Separação em camadas (models, services, screens, widgets)
   - Single Responsibility Principle
   - Código reutilizável e modular
   - Services para lógica de negócio

#### Diferenças entre Lab 1 e Lab 2

| Aspecto | Lab 1 (SQLite Básico) | Lab 2 (Interface Profissional) |
|---------|----------------------|-------------------------------|
| **Foco** | Persistência de dados | UI/UX e funcionalidades avançadas |
| **Interface** | Simples, funcional | Profissional, polida |
| **Temas** | Tema único padrão | Claro/Escuro/Sistema |
| **Campos** | 6 campos básicos | 9 campos (+ dueDate, categoryId, reminderTime) |
| **Notificações** | Nenhuma | Sistema completo |
| **Categorias** | Nenhuma | 8 categorias com cores |
| **Busca** | Básica ou inexistente | Tempo real com filtros |
| **Ordenação** | Data ou prioridade | 4 critérios diferentes |
| **Alertas Visuais** | Mínimos | Múltiplos badges e indicadores |
| **Validações** | Básicas | Avançadas com feedback |
| **Banco de Dados** | Versão 1 | Versão 2 (migração automática) |
| **Pacotes** | 3-4 pacotes | 7+ pacotes |
| **Configuração Android** | Básica | Avançada (desugaring, permissões) |
| **Complexidade** | Baixa-Média | Média-Alta |

**Evolução Principal:**
- Lab 1 ensinou **COMO** persistir dados
- Lab 2 ensinou **COMO** criar uma experiência profissional completa

---

### 5. Próximos Passos

#### Funcionalidades Desejadas

1. **🎨 Categorias Personalizadas**
   - Criar categorias customizadas
   - Escolher cor e ícone próprios
   - CRUD completo de categorias
   - Migração de tarefas entre categorias

2. **📊 Dashboard de Estatísticas**
   - Gráficos de pizza (tarefas por categoria)
   - Gráficos de barra (tarefas por semana/mês)
   - Percentual de conclusão
   - Tempo médio de conclusão
   - Produtividade por período

3. **📅 Visualização em Calendário**
   - Calendário mensal com tarefas
   - Destaque em dias com vencimentos
   - Arrastar e soltar para reagendar
   - Visualização semanal/diária

4. **🔄 Tarefas Recorrentes**
   - Repetir diariamente/semanalmente/mensalmente
   - Gerar automaticamente novas instâncias
   - Marcar conclusão individual ou série
   - Editar série ou instância única

5. **👥 Compartilhamento e Colaboração**
   - Compartilhar tarefas via link
   - Listas compartilhadas entre usuários
   - Sistema de permissões
   - Sincronização em nuvem (Firebase)

6. **🔍 Busca Avançada**
   - Filtros combinados (categoria + status + prioridade)
   - Busca por data range
   - Saved searches (buscas salvas)
   - Histórico de buscas

7. **🎯 Subtarefas (Checklist)**
   - Tarefas com múltiplos itens
   - Barra de progresso por subtarefa
   - Indent/outdent para hierarquia
   - Reordenação de subtarefas

8. **📎 Anexos e Notas**
   - Anexar imagens/arquivos
   - Notas de voz
   - Links externos
   - Tags e hashtags

9. **⏱️ Pomodoro Timer**
   - Timer integrado para tarefas
   - Histórico de sessões
   - Estatísticas de foco
   - Pausas programadas

10. **🌐 Backend e Sincronização**
    - API REST com Node.js/Django
    - Sincronização multi-dispositivo
    - Backup automático em nuvem
    - Modo offline-first

#### Melhorias Técnicas

1. **🧪 Testes Automatizados**
   - Unit tests para models e services
   - Widget tests para UI
   - Integration tests end-to-end
   - Cobertura de 80%+

2. **📱 Performance**
   - Lazy loading de tarefas
   - Paginação de lista
   - Cache de imagens
   - Otimização de queries SQL

3. **♿ Acessibilidade**
   - Semantic labels completos
   - Suporte a screen readers
   - Contraste de cores WCAG AA
   - Tamanhos de fonte ajustáveis

4. **🌍 Internacionalização**
   - Múltiplos idiomas (PT, EN, ES)
   - Formatos de data localizados
   - Strings externalizadas
   - RTL support

5. **🔐 Segurança**
   - Criptografia de dados sensíveis
   - Autenticação biométrica
   - Backup criptografado
   - PIN/password opcional

---

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 👨‍💻 Autor

**Vinícius Xavier Ramalho**

- GitHub: [@ViniciusXR](https://github.com/ViniciusXR)
- Instituição: PUC Minas - Engenharia de Software
- Disciplina: Laboratório de Desenvolvimento de Aplicações Móveis e Distribuídas

---
