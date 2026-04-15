This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.

## Réponses aux questions

- Q2 : Pour la route `/login`, j'ai créé un seul fichier : `app/login/page.tsx`. Avec React Router, il faudrait au minimum : le composant de page, la déclaration de `<Route>` dans `App.tsx` et l'import du composant, soit trois éléments.

- Q3 : En Next.js, l'id est reçu via `params` passé en prop au Server Component. En React Router, on utilisait le hook client `useParams()`. La différence fondamentale est que Next.js fournit les paramètres côté serveur, alors que React Router les lit côté client.

- Q5 : En React SPA, il fallait souvent une dizaine de lignes supplémentaires pour `useState`, `useEffect`, le `fetch`, le `.then`, `setProjects` et l'état de chargement. Ici, le composant `DashboardPage` est `async` et la récupération des projets se fait directement dans la fonction, ce qui réduit beaucoup de code.

- Q6 : La requête GET `/projects` n'apparaît pas dans le navigateur parce qu'elle est exécutée par le serveur Next.js pendant le rendu, pas par le client. Le navigateur reçoit du HTML déjà rempli.

- Q7 : `use client` est nécessaire sur la page Login car elle utilise `useState`, `onChange` et `onSubmit`, donc de l'interactivité côté client. La page Dashboard est purement affichage / SSR, donc elle peut rester un Server Component.

- Q8 : L'équivalent de `useNavigate()` en Next.js est `useRouter()` depuis `next/navigation`.

- Q9 : Dans un React SPA, la source HTML affiche généralement un `<div id="root"></div>` vide et un `<script>` : les noms des projets ne sont pas présents dans le HTML initial.

- Q10 : Dans Next.js, la source HTML contient déjà le contenu rendu, y compris les noms des projets. C'est la preuve du SSR.

- Q11 : En React Router, on faisait en sorte que le header soit en dehors de `<Routes>` (ou dans `App.tsx` autour de la zone de routing) pour qu'il ne se remonte pas à chaque navigation.

- Q12 : Pour un layout spécifique au Dashboard, on crée `app/dashboard/layout.tsx`.

- Q13 : Un Server Component ne peut pas utiliser `onClick` parce que les gestionnaires d'événements sont une fonctionnalité côté client.

- Q14 : Non, il n'est pas nécessaire de transformer toute la page en Client Component. On peut garder la page en Server Component et embarquer un sous-composant client uniquement pour le bouton interactif.

- Q15 : Le fait que le fetch se fasse côté serveur et non dans le navigateur cache l'URL `:4000` du client, ce qui est plus sûr pour l'architecture et limite l'exposition directe du backend.
