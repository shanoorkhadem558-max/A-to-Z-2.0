# A-to-Z-2.0
It is import { createFileRoute } from "@tanstack/react-router";
import storefront from "@/assets/storefront.jpg";
import { Gift, Wallet, Smile, MapPin } from "lucide-react";

export const Route = createFileRoute("/")({
  component: HomePage,
});

const categories = [
  { en: "Gifts", bn: "উপহার", sub: "Customized & Ready", emoji: "🎁", bg: "bg-pink-100", text: "text-pink-600" },
  { en: "Toys", bn: "খেলনা", sub: "Action & Educational", emoji: "🧸", bg: "bg-blue-100", text: "text-blue-600" },
  { en: "Sports", bn: "ক্রীড়া সামগ্রী", sub: "Kits & Gear", emoji: "⚽", bg: "bg-green-100", text: "text-green-600" },
  { en: "Perfumes", bn: "সুগন্ধি", sub: "Luxury Scents", emoji: "✨", bg: "bg-purple-100", text: "text-purple-600" },
  { en: "Household", bn: "গৃহস্থালী", sub: "Daily Essentials", emoji: "🏺", bg: "bg-amber-100", text: "text-amber-700" },
  { en: "Decor", bn: "সজ্জা", sub: "Festive & Home", emoji: "🪔", bg: "bg-rose-100", text: "text-rose-600" },
];

const reviews = [
  { name: "Samiraay", bnName: "সমীরায়", text: "Such a great place to buy gifts, also a great collection and great staff.", bnText: "উপহার কেনার জন্য দারুণ জায়গা, সংগ্রহ এবং কর্মীরাও চমৎকার।", stars: 5 },
  { name: "Mayuk Adak", bnName: "ময়ূখ অদক", text: "Good shop in Singur. Reasonable prices and a wide selection.", bnText: "সিঙ্গুরের ভালো দোকান। দাম যুক্তিসঙ্গত এবং সংগ্রহ অনেক।", stars: 4 },
  { name: "Dipak Deshi", bnName: "দীপক দেশি", text: "Best place for sports items in town. Polite owner.", bnText: "শহরের সেরা ক্রীড়াসামগ্রীর দোকান। মালিক ভদ্র।", stars: 5 },
];

const valueProps = [
  { icon: Gift, en: "Wide Collection", bn: "বিশাল সংগ্রহ", desc: "Gifts, toys, sports & daily essentials under one roof." },
  { icon: Wallet, en: "Budget Friendly", bn: "সাশ্রয়ী মূল্য", desc: "Great products at prices that fit every pocket." },
  { icon: Smile, en: "Friendly Staff", bn: "সহায়ক কর্মী", desc: "We help you find exactly what you need." },
  { icon: MapPin, en: "Easy to Reach", bn: "সহজে পৌঁছানো যায়", desc: "Right on Station Road, near Singur Cinema Hall." },
];

function Stars({ n }: { n: number }) {
  return (
    <div className="flex text-brand-primary text-xs" aria-label={`${n} of 5 stars`}>
      {"★★★★★".slice(0, n)}
      <span className="text-stone-300">{"★★★★★".slice(n)}</span>
    </div>
  );
}

function HomePage() {
  return (
    <div className="min-h-screen bg-stone-50 text-slate-900 font-sans pb-12">
      <header className="bg-white px-5 py-3 flex justify-between items-center sticky top-0 z-50 border-b border-stone-200">
        <div className="flex flex-col leading-tight">
          <h1 className="text-xl font-bold text-brand-secondary">A to Z Shop</h1>
          <span className="font-bengali text-sm font-semibold text-brand-primary">এ টু জেড শপ</span>
        </div>
        <a href="tel:+919999999999" className="bg-brand-primary/10 text-brand-secondary text-xs font-semibold px-3 py-2 rounded-full font-bengali">
          ফোন করুন · Call
        </a>
      </header>

      <section className="relative">
        <img src={storefront} alt="A to Z Shop storefront in Singur" width={832} height={512} className="w-full h-64 object-cover" />
        <div className="absolute inset-0 bg-gradient-to-t from-black/40 to-transparent" />
        <div className="absolute -bottom-6 left-5 right-5 bg-white p-4 rounded-2xl shadow-lg border border-stone-100 flex justify-between items-center gap-3">
          <div>
            <div className="flex items-center gap-1 mb-1">
              <span className="text-brand-primary font-bold text-lg">4.3</span>
              <Stars n={4} />
              <span className="text-slate-400 text-xs ml-1">(76)</span>
            </div>
            <p className="text-xs text-green-600 font-medium flex items-center gap-1">
              <span className="w-2 h-2 bg-green-500 rounded-full animate-pulse" />
              <span>Open · <span className="font-bengali">খোলা আছে</span></span>
            </p>
          </div>
          <a href="#visit" className="bg-brand-secondary text-white px-4 py-2 rounded-lg text-sm font-semibold whitespace-nowrap">
            <span className="block leading-tight">Visit</span>
            <span className="font-bengali text-[10px] opacity-80">দেখুন</span>
          </a>
        </div>
      </section>

      <section className="px-5 pt-12 pb-2 text-center">
        <p className="font-bengali text-lg text-brand-secondary font-semibold leading-snug">সিঙ্গুরে আপনার বিশ্বাসের দোকান</p>
        <p className="text-sm text-slate-600 mt-1">Your trusted neighborhood store in Singur — everything from A to Z.</p>
      </section>

      <section className="mt-6 px-5">
        <h2 className="text-lg font-bold mb-4 flex justify-between items-end">
          <span>What we offer</span>
          <span className="text-xs font-bengali font-normal text-slate-500">আমাদের সংগ্রহ</span>
        </h2>
        <div className="grid grid-cols-2 gap-3">
          {categories.map((c) => (
            <div key={c.en} className="bg-white p-4 rounded-2xl border border-stone-100 shadow-sm">
              <div className={`w-10 h-10 ${c.bg} rounded-full mb-3 flex items-center justify-center text-lg ${c.text}`}>{c.emoji}</div>
              <p className="font-bold text-sm">{c.en}</p>
              <p className="font-bengali text-xs text-brand-primary font-semibold">{c.bn}</p>
              <p className="text-[10px] text-slate-500 mt-1">{c.sub}</p>
            </div>
          ))}
        </div>
      </section>

      <section id="visit" className="mt-10 px-5">
        <div className="bg-brand-secondary rounded-2xl p-6 text-white">
          <h3 className="text-lg font-bold mb-1">Visit us in Singur</h3>
          <p className="font-bengali text-base text-brand-primary font-semibold mb-4">সিঙ্গুরে আমাদের দোকানে আসুন</p>
          <div className="space-y-3 text-sm text-indigo-100 mb-6">
            <div>
              <p className="text-white font-semibold">Address · <span className="font-bengali">ঠিকানা</span></p>
              <p>Station Road, near Singur Cinema Hall, Hooghly, West Bengal 712409</p>
              <p className="font-bengali">সিঙ্গুর স্টেশন রোড, হুগলি — ৭১২৪০৯</p>
            </div>
            <div>
              <p className="text-white font-semibold">Hours · <span className="font-bengali">সময়সূচি</span></p>
              <p>Mon–Sun · 10:00 AM – 9:00 PM</p>
              <p className="font-bengali">সোম-রবি · সকাল ১০টা - রাত ৯টা</p>
            </div>
          </div>
          <div className="flex gap-3">
            <a href="tel:+919999999999" className="flex-1 bg-white text-brand-secondary py-3 rounded-xl font-bold text-center text-sm">Call <span className="font-bengali">· ফোন</span></a>
            <a href="https://maps.google.com/?q=A+to+Z+Shop+Singur" target="_blank" rel="noopener noreferrer" className="flex-1 border border-white/30 text-white py-3 rounded-xl font-bold text-center text-sm">Directions <span className="font-bengali">· পথ</span></a>
          </div>
        </div>
      </section>

      <section className="mt-10 overflow-hidden">
        <div className="px-5 mb-4 flex justify-between items-end">
          <h2 className="text-lg font-bold">Customer Love</h2>
          <span className="text-xs font-bengali text-slate-500">গ্রাহকদের মতামত</span>
        </div>
        <div className="flex gap-4 overflow-x-auto pb-4 px-5 no-scrollbar snap-x">
          {reviews.map((r) => (
            <article key={r.name} className="min-w-[280px] snap-start bg-white p-5 rounded-2xl border border-stone-100 shadow-sm">
              <Stars n={r.stars} />
              <p className="text-sm italic text-slate-700 mt-3 mb-2">"{r.text}"</p>
              <p className="font-bengali text-sm text-slate-600 mb-3">"{r.bnText}"</p>
              <div className="flex items-center gap-3 pt-3 border-t border-stone-100">
                <div className="w-8 h-8 rounded-full bg-brand-primary/20 flex items-center justify-center text-xs font-bold text-brand-secondary">{r.name.charAt(0)}</div>
                <div>
                  <p className="text-xs font-bold">{r.name}</p>
                  <p className="font-bengali text-[10px] text-slate-500">{r.bnName}</p>
                </div>
              </div>
            </article>
          ))}
        </div>
      </section>

      <section className="mt-8 px-5">
        <div className="bg-white rounded-3xl border border-stone-200 shadow-lg overflow-hidden">
          <div className="bg-brand-secondary p-5 text-white">
            <h2 className="text-lg font-bold leading-snug">Why shop with us?</h2>
            <p className="font-bengali text-sm mt-1 text-indigo-100">আমাদের দোকানে কেন কেনাকাটা করবেন?</p>
          </div>
          <div className="p-5 grid grid-cols-1 gap-4">
            {valueProps.map((v) => (
              <div key={v.en} className="flex gap-3">
                <div className="w-10 h-10 rounded-full bg-brand-primary/15 flex items-center justify-center shrink-0 text-brand-secondary">
                  <v.icon size={20} strokeWidth={2} />
                </div>
                <div>
                  <p className="text-sm font-bold text-brand-secondary">{v.en} <span className="font-bengali text-brand-primary font-semibold">· {v.bn}</span></p>
                  <p className="text-xs text-slate-500 mt-0.5">{v.desc}</p>
                </div>
              </div>
            ))}
          </div>
          <div className="px-5 pb-5">
            <a href="tel:+919999999999" className="block w-full bg-brand-primary text-white text-center py-3 rounded-xl font-bold text-sm">
              Call now & order · <span className="font-bengali">এখনই ফোন করুন</span>
            </a>
          </div>
        </div>
      </section>

      <footer className="mt-12 pt-8 border-t border-stone-200 text-center px-5">
        <p className="text-sm font-bold text-brand-secondary">A to Z Shop</p>
        <p className="font-bengali text-sm text-brand-primary font-semibold">এ টু জেড শপ</p>
        <p className="font-bengali text-xs text-slate-500 mt-2">আপনার বিশ্বাসের দোকান · সিঙ্গুর</p>
        <p className="text-[11px] text-slate-400 mt-1">&copy; {new Date().getFullYear()} A to Z Shop, Singur</p>
      </footer>
    </div>
  );
}
a website quotes for the shop a to z
import { QueryClient, QueryClientProvider } from "@tanstack/react-query";
import { Outlet, Link, createRootRouteWithContext, useRouter, HeadContent, Scripts } from "@tanstack/react-router";
import { useEffect, type ReactNode } from "react";
import appCss from "../styles.css?url";
import { reportLovableError } from "../lib/lovable-error-reporting";

function NotFoundComponent() {
  return (
    <div className="flex min-h-screen items-center justify-center bg-background px-4">
      <div className="max-w-md text-center">
        <h1 className="text-7xl font-bold text-foreground">404</h1>
        <h2 className="mt-4 text-xl font-semibold text-foreground">Page not found</h2>
        <p className="mt-2 text-sm text-muted-foreground">The page you're looking for doesn't exist or has been moved.</p>
        <div className="mt-6">
          <Link to="/" className="inline-flex items-center justify-center rounded-md bg-primary px-4 py-2 text-sm font-medium text-primary-foreground transition-colors hover:bg-primary/90">Go home</Link>
        </div>
      </div>
    </div>
  );
}

function ErrorComponent({ error, reset }: { error: Error; reset: () => void }) {
  console.error(error);
  const router = useRouter();
  useEffect(() => { reportLovableError(error, { boundary: "tanstack_root_error_component" }); }, [error]);
  return (
    <div className="flex min-h-screen items-center justify-center bg-background px-4">
      <div className="max-w-md text-center">
        <h1 className="text-xl font-semibold tracking-tight text-foreground">This page didn't load</h1>
        <p className="mt-2 text-sm text-muted-foreground">Something went wrong on our end. You can try refreshing or head back home.</p>
        <div className="mt-6 flex flex-wrap justify-center gap-2">
          <button onClick={() => { router.invalidate(); reset(); }} className="inline-flex items-center justify-center rounded-md bg-primary px-4 py-2 text-sm font-medium text-primary-foreground transition-colors hover:bg-primary/90">Try again</button>
          <a href="/" className="inline-flex items-center justify-center rounded-md border border-input bg-background px-4 py-2 text-sm font-medium text-foreground transition-colors hover:bg-accent">Go home</a>
        </div>
      </div>
    </div>
  );
}

export const Route = createRootRouteWithContext<{ queryClient: QueryClient }>()({
  head: () => ({
    meta: [
      { charSet: "utf-8" },
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      { title: "A to Z Shop — Gifts, Toys & Sports in Singur | এ টু জেড শপ" },
      { name: "description", content: "A to Z Shop in Singur — your neighborhood store for gifts, toys, sports gear, perfumes and household items. 4.3★ from 76 reviews." },
      { name: "author", content: "A to Z Shop" },
      { property: "og:title", content: "A to Z Shop — Gifts, Toys & Sports in Singur | এ টু জেড শপ" },
      { property: "og:description", content: "A to Z Shop in Singur — your neighborhood store for gifts, toys, sports gear, perfumes and household items. 4.3★ from 76 reviews." },
      { property: "og:type", content: "website" },
      { name: "twitter:card", content: "summary_large_image" },
      { name: "twitter:title", content: "A to Z Shop — Gifts, Toys & Sports in Singur | এ টু জেড শপ" },
      { name: "twitter:description", content: "A to Z Shop in Singur — your neighborhood store for gifts, toys, sports gear, perfumes and household items. 4.3★ from 76 reviews." },
      { property: "og:image", content: "https://pub-bb2e103a32db4e198524a2e9ed8f35b4.r2.dev/e93f8ebc-f584-4ed9-bd67-c8a4c5ad2b1d/id-preview-e31a9395--8b850820-1b78-4c28-883f-c42908db12bb.lovable.app-1784364682962.png" },
      { name: "twitter:image", content: "https://pub-bb2e103a32db4e198524a2e9ed8f35b4.r2.dev/e93f8ebc-f584-4ed9-bd67-c8a4c5ad2b1d/id-preview-e31a9395--8b850820-1b78-4c28-883f-c42908db12bb.lovable.app-1784364682962.png" },
    ],
    links: [
      { rel: "preconnect", href: "https://fonts.googleapis.com" },
      { rel: "preconnect", href: "https://fonts.gstatic.com", crossOrigin: "anonymous" },
      { rel: "stylesheet", href: "https://fonts.googleapis.com/css2?family=Hind+Siliguri:wght@400;600;700&family=Inter:wght@400;500;600;700;800&display=swap" },
      { rel: "stylesheet", href: appCss },
    ],
  }),
  shellComponent: RootShell,
  component: RootComponent,
  notFoundComponent: NotFoundComponent,
  errorComponent: ErrorComponent,
});

function RootShell({ children }: { children: ReactNode }) {
  return (
    <html lang="en">
      <head><HeadContent /></head>
      <body>{children}<Scripts /></body>
    </html>
  );
}

function RootComponent() {
  const { queryClient } = Route.useRouteContext();
  return (
    <QueryClientProvider client={queryClient}>
      <Outlet />
    </QueryClientProvider>
  );
}
@import "tailwindcss";

@theme {
  --font-sans: "Inter", system-ui, sans-serif;
  --font-bengali: "Hind Siliguri", sans-serif;
  --color-brand-primary: #F59E0B;
  --color-brand-secondary: #1E1B4B;
  --color-brand-accent: #E11D48;
}

.font-bengali {
  font-family: var(--font-bengali);
}
