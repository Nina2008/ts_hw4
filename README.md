# Менеджер задач на TypeScript

Консольний застосунок для керування списком задач з акцентом на типобезпеку TypeScript.

## Можливості TypeScript

- `interface Task` — модель задачі
- `enum` — `TaskStatus`, `TaskPriority`
- `type CreateTaskInput` — `Pick` для полів при створенні (id, createdAt генеруються автоматично)
- `type UpdateTaskInput` — `Partial` + `Pick` для часткового оновлення
- `findById<T extends Identifiable>` — generic-функція пошуку за id
- `isTask(value: unknown): value is Task` — type guard
- `TaskNotFoundError` — обробка помилок при update/delete

## Запуск

```bash
npm install
npm run dev
```

Або збірка та запуск:

```bash
npm run build
npm start
```

## Структура

```
src/
  types/task.ts    — типи, enum, utility types
  utils/findById.ts — generic пошук
  utils/isTask.ts   — type guard
  TaskManager.ts    — сервіс CRUD + фільтрація
  seed.ts           — 8 початкових задач
  index.ts          — демонстрація операцій
```
