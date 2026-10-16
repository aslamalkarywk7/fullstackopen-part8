# Full Stack Open — Part 8: GraphQL library app (8.1–8.26)

Separate submission repository for Part 8.

My other submissions (parts 0–5, 7) live in
https://github.com/aslamalkarywk7/fullstackopen,
part 6 in https://github.com/aslamalkarywk7/fullstackopen-part6.

## library-backend

Apollo Server (Express middleware) + Mongoose + JWT + subscriptions.

```bash
cd library-backend
npm install
cp .env.example .env   # MONGODB_URI, JWT_SECRET (never commit .env)
npm run dev            # GraphQL on :4000
```

- 8.1–8.7: bookCount/authorCount, allBooks (+author/genre filters),
  allAuthors with bookCount, addBook (creates missing authors),
  editAuthor (null when missing).
- 8.13–8.15: MongoDB persistence, refactored files, validation errors
  as GraphQLError.
- 8.16: users (favoriteGenre), login (hardcoded password `secret`),
  auth-required addBook/editAuthor.
- 8.23: bookAdded subscription (WebSockets). 8.26: author bookCount
  computed from a single extra query (no n+1).

## library-frontend

Apollo Client + subscriptions.

```bash
cd library-frontend
npm install
npm run dev            # :5173, talks to :4000
```

- 8.8–8.12: authors/books views, add book, birth-year select.
- 8.17–8.22: login/logout, genre buttons (GraphQL-filtered),
  recommendations by favorite genre, cache kept in sync.
- 8.24–8.25: bookAdded subscription alerts and updates the book view.
