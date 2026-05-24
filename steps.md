1. init
npx create-next-app@latest eng-phrases
cd eng-phrases
npm install prisma @prisma/client
npx prisma init --datasource-provider sqlite

2. База данных (Prisma schema)

prisma/schema.prisma

model Phrase {
  id        Int      @id @default(autoincrement())
  text      String
  category  String?
  level     Int      @default(0) // степень изученности 0–5
  createdAt DateTime @default(now())
}

После этого:
npx prisma migrate dev --name init

3. Создать базу (миграция)
npx prisma migrate dev --name init

▶️ 4. Запуск проекта
npm run dev
Открываешь: http://localhost:3000