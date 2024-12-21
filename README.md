// Importation des modules nécessaires
import { Links, LiveReload, Meta, Outlet, Scripts, ScrollRestoration } from "@remix-run/react";
import styles from "./styles/app.css";
import ShopifyProvider from "./utils/ShopifyProvider";

// Fichier CSS global
export function links() {
  return [{ rel: "stylesheet", href: styles }];
}

// Métadonnées pour le site
export const meta = () => ({
  charset: "utf-8",
  title: "QIVERA VERA Boutique",
  viewport: "width=device-width,initial-scale=1",
});

export default function App() {
  return (
    <html lang="fr">
      <head>
        <Meta />
        <Links />
      </head>
      <body>
        <ShopifyProvider>
          <Outlet /> {/* Gère les routes imbriquées */}
        </ShopifyProvider>
        <ScrollRestoration />
        <Scripts />
        <LiveReload />
      </body>
    </html>
  );
}

// ShopifyProvider.js - Gestion des appels API Shopify
import { createContext, useContext } from "react";

const ShopifyContext = createContext();

export function ShopifyProvider({ children }) {
  const shopifyApiUrl = process.env.SHOPIFY_API_URL;
  const shopifyApiKey = process.env.SHOPIFY_API_KEY;

  const fetchShopifyData = async (endpoint, options = {}) => {
    const response = await fetch(`${shopifyApiUrl}${endpoint}`, {
      headers: {
        "Content-Type": "application/json",
        "X-Shopify-Storefront-Access-Token": shopifyApiKey,
      },
      ...options,
    });
    if (!response.ok) {
      throw new Error(`Erreur Shopify: ${response.statusText}`);
    }
    return response.json();
  };

  return (
    <ShopifyContext.Provider value={{ fetchShopifyData }}>
      {children}
    </ShopifyContext.Provider>
  );
}

export const useShopify = () => useContext(ShopifyContext);

// Exemple de route imbriquée - /routes/index.jsx
import { useLoaderData } from "@remix-run/react";
import { useShopify } from "../utils/ShopifyProvider";

export const loader = async ({ request }) => {
  const url = new URL(request.url);
  const response = await fetch(`${process.env.SHOPIFY_API_URL}/products`, {
    headers: {
      "Content-Type": "application/json",
      "X-Shopify-Storefront-Access-Token": process.env.SHOPIFY_API_KEY,
    },
  });
  if (!response.ok) {
    throw new Response("Erreur lors du chargement des produits", { status: response.status });
  }
  return response.json();
};

export default function Index() {
  const products = useLoaderData();

  return (
    <div>
      <h1>Bienvenue sur la boutique QIVERA VERA</h1>
      <ul>
        {products.map((product) => (
          <li key={product.id}>{product.title}</li>
        ))}
      </ul>
    </div>
  );
}

// Exemple de configuration API Shopify (fichier .env)
// SHOPIFY_API_URL=https://your-shopify-store.myshopify.com/api/2023-04/graphql.json
// SHOPIFY_API_KEY=your-shopify-access-token

--->
