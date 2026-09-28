<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover"><title>Next.js Learning Notes</title><style>:root{--bg:#f5f6fb;--card:#fff;--tx:#1e2233;--mut:#5b6178;--bd:#e3e6f2;--c1:#4f46e5;--c2:#0d9488;--c3:#d97706;--c4:#db2777;--c5:#64748b;--code:#111827;--ct:#e5e7eb;--ib:#eef2ff;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#0f1220;--card:#181c30;--tx:#e8eaf6;--mut:#9aa1c0;--bd:#2a3050;--c1:#818cf8;--c2:#2dd4bf;--c3:#fbbf24;--c4:#f472b6;--code:#0a0d1a;--ib:#22284a}}
:root[data-theme="dark"]{--bg:#0f1220;--card:#181c30;--tx:#e8eaf6;--mut:#9aa1c0;--bd:#2a3050;--c1:#818cf8;--c2:#2dd4bf;--c3:#fbbf24;--c4:#f472b6;--code:#0a0d1a;--ib:#22284a}
html{scroll-behavior:smooth;scroll-padding-top:env(safe-area-inset-top,0px)}
body{margin:0;background:var(--bg);color:var(--tx);font:16px/1.65 system-ui,-apple-system,"Segoe UI",Roboto,sans-serif}
.hero{background:linear-gradient(120deg,#4f46e5,#0d9488);color:#fff;padding:42px 20px;text-align:center}h1{margin:0;font-size:2.3rem}.hero p{margin:8px 0 0;opacity:.9}
.wrap{max-width:1250px;margin:0 auto;padding:20px;display:grid;grid-template-columns:280px 1fr;gap:24px}
nav{position:sticky;top:calc(env(safe-area-inset-top,0px) + 12px);align-self:start;max-height:88vh;overflow:auto;background:var(--card);border:1px solid var(--bd);border-radius:12px;padding:10px}
nav a{display:block;padding:3px 8px;border-radius:6px;color:var(--mut);text-decoration:none;font-size:.85rem}nav a:hover{background:var(--ib);color:var(--c1)}
nav a.n2{color:var(--c1);font-weight:700;margin-top:8px}nav a.n3{padding-left:20px;font-size:.8rem}
main{min-width:0}section{background:var(--card);border:1px solid var(--bd);border-radius:14px;padding:6px 22px 18px;margin-bottom:20px}
h2{font-size:1.6rem;color:var(--c1);border-bottom:3px solid var(--c1);padding-bottom:6px;margin:18px 0 12px}
h2 i{font-style:normal;background:var(--c1);color:#fff;border-radius:8px;padding:0 9px;margin-right:8px;font-size:1.2rem}
h3{font-size:1.2rem;color:var(--c2);border-left:6px solid var(--c2);padding-left:10px;margin:22px 0 8px 10px}
h4{font-size:1.02rem;color:var(--c3);border-left:4px solid var(--c3);padding-left:9px;margin:16px 0 6px 28px}
h5{font-size:.95rem;color:var(--c4);border-left:3px solid var(--c4);padding-left:8px;margin:14px 0 4px 46px}
h6{font-size:.9rem;color:var(--c5);margin:12px 0 4px 62px}
.lv3{margin-left:24px}.lv4{margin-left:42px}.lv5{margin-left:60px}.lv6{margin-left:76px}h3.lv3{margin-left:10px}h4.lv4{margin-left:28px}h5.lv5{margin-left:46px}h6.lv6{margin-left:62px}
p{margin:6px 0}ul,ol{margin:6px 0;padding-left:26px}li{margin:3px 0}ul.lv3,ol.lv3{margin-left:24px}ul.lv4,ol.lv4{margin-left:42px}ul.lv5,ol.lv5{margin-left:60px}
code{background:var(--ib);color:var(--c1);padding:1px 6px;border-radius:5px;font:.88em ui-monospace,Consolas,monospace}mark{background:#fde68a;color:#78350f;padding:0 4px;border-radius:4px}
.cb{position:relative;margin:10px 0;max-width:100%}.cb.lv2{margin-left:0}.fn{background:#374151;color:#fde68a;font:.8rem ui-monospace,Consolas,monospace;padding:4px 12px;border-radius:10px 10px 0 0}
pre{background:var(--code);color:var(--ct);padding:12px 14px;border-radius:10px;overflow-x:auto;font:.84rem/1.5 ui-monospace,Consolas,monospace;margin:0;tab-size:4}.fn+pre{border-radius:0 0 10px 10px}pre code{background:none;color:inherit;padding:0}
.cm{color:#9ca3af;font-style:italic}.st{color:#86efac}.kw{color:#c4b5fd}
.cp{position:absolute;top:6px;right:8px;background:#4f46e5;color:#fff;border:0;border-radius:6px;padding:2px 9px;font-size:.75rem;cursor:pointer;opacity:.85}
p.box{border-radius:10px;padding:8px 14px;border-left:5px solid}.warn{background:#fef3c7;border-color:#d97706;color:#78350f}.tip{background:#dcfce7;border-color:#16a34a;color:#14532d}
.tw{overflow-x:auto;margin:10px 0}table{border-collapse:collapse;width:100%;font-size:.92rem}th{background:var(--c1);color:#fff;text-align:left}th,td{padding:7px 10px;border:1px solid var(--bd);vertical-align:top}tr:nth-child(even) td{background:var(--ib)}
hr{border:0;border-top:2px dashed var(--bd);margin:18px 0}
.x h3~p,.x h3~ul,.x h3~pre,.x h3~.tw,.x h3~.box{margin-left:22px}.x h4{margin-left:26px}.x h4~p,.x h4~ul,.x h4~pre{margin-left:40px}.x .box{border-radius:10px;padding:8px 14px;margin:10px 0 10px 22px;border-left:5px solid}.x .note{background:#e0f2fe;border-color:#0284c7;color:#0c4a6e}.x .tip{background:#dcfce7;border-color:#16a34a;color:#14532d}.x .warn{background:#fef3c7;border-color:#d97706;color:#78350f}
@media(max-width:860px){.wrap{grid-template-columns:1fr;padding:12px}nav{display:none}h1{font-size:1.7rem}section{padding:4px 14px 14px}}
</style></head><body>
<header class="hero"><h1>Next.js Learning Notes</h1><p>Complete notes: har heading, example aur table ke saath</p></header>
<div class="wrap"><nav><a class="n2" href="#next-js-all-stack-and-their-role">Next.js All Stack and their role</a><a class="n2" href="#important-relationships-in-javascript-no">Important Relationships in JavaScript Node.js React Next.js</a><a class="n2" href="#framework-kya-hota-hai">Framework Kya Hota Hai?</a><a class="n3" href="#framework-ke-3-main-ideas">Framework ke 3 main ideas</a><a class="n3" href="#1-structure">1. Structure</a><a class="n3" href="#2-ready-features">2. Ready Features</a><a class="n3" href="#3-rules-conventions">3. Rules / Conventions</a><a class="n3" href="#framework-rule-simple-example">Framework Rule Simple Example</a><a class="n2" href="#frontend-vs-backend">Frontend vs Backend</a><a class="n3" href="#frontend">Frontend</a><a class="n3" href="#backend">Backend</a><a class="n2" href="#next-js-introduction">Next.js Introduction</a><a class="n3" href="#npm-node-package-manager">npm (Node Package Manager)</a><a class="n3" href="#extra-packages">Extra Packages</a><a class="n3" href="#package-install-command">Package Install Command</a><a class="n3" href="#simple-rule">Simple Rule</a><a class="n3" href="#npx-kya-hai">npx Kya Hai?</a><a class="n3" href="#important-symbols">Important Symbols</a><a class="n3" href="#abhi-sabse-important">Abhi sabse important</a><a class="n3" href="#system-requirements">System Requirements</a><a class="n3" href="#create-with-the-cli">Create with the CLI</a><a class="n3" href="#manual-installation">Manual Installation</a><a class="n3" href="#run-the-development-server">Run the Development Server</a><a class="n3" href="#typescript-setup">TypeScript Setup</a><a class="n3" href="#editor-setup">Editor Setup</a><a class="n3" href="#linting">Linting</a><a class="n3" href="#absolute-imports-amp-path-aliases">Absolute Imports &amp;amp; Path Aliases</a><a class="n3" href="#upgrade-your-app">Upgrade your app</a><a class="n2" href="#installation">Installation (official docs)</a><a class="n2" href="#project-structure-and-organization">Project structure and organization</a><a class="n3" href="#top-level-folders">Top-level folders</a><a class="n3" href="#top-level-files">Top-level files</a><a class="n3" href="#first-next-js-project">First Next.js Project</a><a class="n3" href="#routing-files">Routing Files</a><a class="n3" href="#nested-and-dynamic-routes">Nested and Dynamic Routes</a><a class="n3" href="#route-groups-and-private-folders">Route groups and private folders</a><a class="n3" href="#parallel-and-intercepted-routes">Parallel and Intercepted Routes</a><a class="n2" href="#layouts-and-pages">Layouts and Pages</a><a class="n3" href="#creating-a-page">Creating a page</a><a class="n3" href="#creating-a-layout">Creating a layout</a><a class="n3" href="#creating-a-nested-route">Creating a nested route</a><a class="n3" href="#nesting-layouts">Nesting Layouts</a><a class="n3" href="#dynamic-segment">Dynamic Segment</a><a class="n3" href="#search-parameters-query-parameters">Search Parameters / Query Parameters</a><a class="n3" href="#linking-between-pages">Linking between pages</a><a class="n3" href="#route-props-helpers-properties">Route Props Helpers(properties )</a><a class="n2" href="#linking-and-navigating">Linking and Navigating</a><a class="n3" href="#what-can-make-transitions-slow">What can make transitions slow?</a><a class="n2" href="#server-and-client-components">Server and Client Components</a><a class="n2" href="#fetching-data">Fetching Data</a><a class="n3" href="#server-components">Server Components</a><a class="n3" href="#1-fetch-api-example">1. fetch API example</a><a class="n3" href="#2-orm-database-example">2. ORM / Database example</a><a class="n3" href="#streaming">Streaming</a><a class="n2" href="#mutating-data">Mutating Data</a><a class="n3" href="#server-function-ko-invoke-karne-ke-2-mai">Server Function ko invoke karne ke 2 main ways</a><a class="n3" href="#1-server-file">1. Server file</a><a class="n3" href="#2-client-file">2. Client file</a><a class="n3" href="#form-example">Form Example</a><a class="n3" href="#event-handler-example">Event Handler Example</a><a class="n3" href="#pending-state">Pending State</a><a class="n3" href="#mutation-ke-baad-data-refresh">Mutation ke baad data refresh</a><a class="n3" href="#revalidate-data">Revalidate Data</a><a class="n3" href="#redirect-after-mutation">Redirect after Mutation</a><a class="n3" href="#cookies">Cookies</a><a class="n3" href="#sabse-important-concept">Sabse important concept:</a><a class="n2" href="#caching">Caching</a><a class="n3" href="#cache-components">Cache Components</a><a class="n3" href="#use-cache">use cache</a><a class="n3" href="#data-level-caching">Data-level caching</a><a class="n3" href="#ui-level-caching">UI-level caching</a><a class="n3" href="#cachelife">cacheLife</a><a class="n3" href="#cache-key">Cache Key</a><a class="n3" href="#uncached-data">Uncached Data</a><a class="n3" href="#cache-vs-uncached-data">Cache vs Uncached Data</a><a class="n3" href="#use-cache-private">use cache: private</a><a class="n3" href="#use-cache-remote">use cache: remote</a><a class="n3" href="#cache-storage">Cache Storage</a><a class="n2" href="#revalidation-kya-hai">Revalidation kya hai?</a><a class="n3" href="#cachelife-2">cacheLife</a><a class="n3" href="#built-in-profiles">Built-in profiles</a><a class="n3" href="#stale-revalidate-expire-teenon-ka-basic-">stale, revalidate, expire — teenon ka basic difference</a><a class="n3" href="#cachetag">cacheTag</a><a class="n3" href="#revalidatetag">revalidateTag</a><a class="n3" href="#updatetag">updateTag</a><a class="n3" href="#revalidatetag-vs-updatetag">revalidateTag vs updateTag</a><a class="n3" href="#revalidatepath">revalidatePath</a><a class="n3" href="#time-based-vs-on-demand-revalidation">Time-based vs On-demand Revalidation</a><a class="n3" href="#cachetag-revalidatetag-ka-relation">cacheTag + revalidateTag ka relation</a><a class="n3" href="#what-should-i-cache">What should I cache?</a><a class="n3" href="#sab-ko-ek-line-mein-yaad-karo">Sab ko ek line mein yaad karo</a><a class="n2" href="#error-handling-kya-hai">Error Handling kya hai?</a><a class="n3" href="#expected-errors">Expected Errors</a><a class="n3" href="#useactionstate">useActionState</a><a class="n3" href="#server-component-mein-expected-error">Server Component mein expected error</a><a class="n3" href="#notfound">notFound()</a><a class="n3" href="#uncaught-exceptions">Uncaught Exceptions</a><a class="n3" href="#error-boundary">Error Boundary</a><a class="n3" href="#nested-error-boundaries">Nested Error Boundaries</a><a class="n3" href="#retry">retry</a><a class="n3" href="#component-level-error-boundary">Component-level Error Boundary</a><a class="n3" href="#error-boundary-kis-error-ko-catch-nahi-k">Error Boundary kis error ko catch nahi karti?</a><a class="n3" href="#starttransition-ka-special-case">startTransition ka special case</a><a class="n3" href="#global-error">Global Error</a><a class="n3" href="#final-mental-model">Final mental model</a><a class="n3" href="#sabse-important-6-concepts">Sabse important 6 concepts:</a><a class="n2" href="#css-in-next-js">CSS in Next.js</a><a class="n3" href="#tailwind-css">Tailwind CSS</a><a class="n3" href="#css-modules">CSS Modules</a><a class="n3" href="#module-css-ka-fayda">.module.css ka fayda</a><a class="n3" href="#global-css">Global CSS</a><a class="n3" href="#global-css-vs-css-modules">Global CSS vs CSS Modules</a><a class="n3" href="#external-stylesheets">External Stylesheets</a><a class="n3" href="#css-ordering">CSS Ordering</a><a class="n3" href="#css-ko-predictable-kaise-rakhein">CSS ko predictable kaise rakhein?</a><a class="n3" href="#development-vs-production">Development vs Production</a><a class="n3" href="#is-section-ka-practical-choice">Is section ka practical choice</a><a class="n3" href="#example-2">Example:</a><a class="n3" href="#sabse-important-definitions">Sabse important definitions</a><a class="n2" href="#image-optimization">Image Optimization</a><a class="n3" href="#lt-image-gt-component">&amp;lt;Image&amp;gt; component</a><a class="n3" href="#local-images">Local Images</a><a class="n3" href="#static-image-import">Static Image Import</a><a class="n3" href="#placeholder-blur">placeholder="blur"</a><a class="n3" href="#dynamic-static-image-import">Dynamic Static Image Import</a><a class="n3" href="#remote-images">Remote Images</a><a class="n3" href="#remote-image-mein-width-height-kyun-deni">Remote Image mein width/height kyun deni hoti hai?</a><a class="n3" href="#fill">fill</a><a class="n3" href="#remote-images-ko-allow-karna">Remote Images ko allow karna</a><a class="n3" href="#local-vs-remote-vs-static-import">Local vs Remote vs Static Import</a><a class="n3" href="#lt-image-gt-ka-actual-benefit-kya-hai">&amp;lt;Image&amp;gt; ka actual benefit kya hai?</a><a class="n3" href="#sabse-important-concepts">Sabse important concepts</a><a class="n3" href="#ek-simple-mental-model">Ek simple mental model:</a><a class="n2" href="#font-optimization-simple-explanation">Font Optimization — simple explanation</a><a class="n3" href="#google-font-use-karna">Google Font use karna</a><a class="n3" href="#ek-font-family-ki-multiple-files">Ek font family ki multiple files</a><a class="n3" href="#sabse-important-mental-model">Sabse important mental model</a><a class="n2" href="#metadata">Metadata</a><a class="n3" href="#static-metadata">Static Metadata</a><a class="n3" href="#dynamic-metadata-generatemetadata">Dynamic Metadata — generateMetadata</a><a class="n3" href="#file-based-metadata">File-based Metadata</a><a class="n3" href="#favicon">Favicon</a><a class="n3" href="#og-image">OG Image</a><a class="n3" href="#generated-og-image">Generated OG Image</a><a class="n3" href="#cache-same-data-ko-dobara-fetch-hone-se-">cache() — same data ko dobara fetch hone se bachana</a><a class="n3" href="#streaming-metadata">Streaming Metadata</a><a class="n3" href="#tumhare-liye-core-mental-model">Tumhare liye core mental model</a><a class="n2" href="#route-handlers-simple-beginner-explanati">Route Handlers — simple beginner explanation</a><a class="n3" href="#1-route-handler-kahan-banta-hai">1. Route Handler kahan banta hai?</a><a class="n3" href="#2-page-tsx-vs-route-ts">2. page.tsx vs route.ts</a><a class="n3" href="#3-http-methods">3. HTTP Methods</a><a class="n3" href="#4-response-kaise-return-hota-hai">4. Response kaise return hota hai?</a><a class="n3" href="#5-nextrequest-aur-nextresponse">5. NextRequest aur NextResponse</a><a class="n3" href="#6-route-handler-aur-caching">6. Route Handler aur caching</a><a class="n3" href="#7-cache-components-ke-saath-route-handle">7. Cache Components ke saath Route Handler</a><a class="n3" href="#8-database-use-cache">8. Database + use cache</a><a class="n3" href="#9-route-ts-aur-page-tsx-same-level-par-n">9. route.ts aur page.tsx same level par nahi ho sakte</a><a class="n3" href="#10-route-handlers-layouts-client-navigat">10. Route Handlers layouts/client navigation ka part nahi hain</a><a class="n3" href="#11-dynamic-route-handler">11. Dynamic Route Handler</a><a class="n3" href="#final-mental-model-2">Final mental model</a><a class="n2" href="#proxy-simple-beginner-explanation">Proxy — simple beginner explanation</a><a class="n3" href="#1-proxy-kya-kar-sakta-hai">1. Proxy kya kar sakta hai?</a><a class="n3" href="#2-proxy-file-kahan-hoti-hai">2. Proxy file kahan hoti hai?</a><a class="n3" href="#3-basic-proxy">3. Basic Proxy</a><a class="n3" href="#4-request">4. request</a><a class="n3" href="#5-nextresponse">5. NextResponse</a><a class="n3" href="#6-matcher">6. matcher</a><a class="n3" href="#7-complete-example">7. Complete example</a><a class="n3" href="#8-proxy-kab-use-karna-hai">8. Proxy kab use karna hai?</a><a class="n3" href="#9-proxy-kis-kaam-ke-liye-nahi-hai">9. Proxy kis kaam ke liye nahi hai?</a><a class="n3" href="#route-handler-vs-proxy">Route Handler vs Proxy</a><a class="n2" href="#deploying-simple-beginner-explanation">Deploying — simple beginner explanation</a><a class="n3" href="#1-node-js-server">1. Node.js Server</a><a class="n3" href="#2-docker">2. Docker</a><a class="n3" href="#3-static-export">3. Static Export</a><a class="n3" href="#4-adapters">4. Adapters</a><a class="n3" href="#verified-adapters">Verified Adapters</a><a class="n3" href="#tumhare-project-ke-context-mein">Tumhare project ke context mein</a><a class="n3" href="#sabse-important-difference">Sabse important difference</a><a class="n2" href="#upgrading">Upgrading</a><a class="n3" href="#1-next-upgrade">1. next upgrade</a><a class="n3" href="#2-manual-upgrade">2. Manual upgrade</a><a class="n3" href="#3-canary-version">3. Canary version</a><a class="n3" href="#4-canary-mein-kya-available-hai">4. Canary mein kya available hai?</a><a class="n3" href="#tumhare-liye-sabse-important">Tumhare liye sabse important</a></nav><main><p class="lv1"><b>Sb se phely kuch basic hote woh pata hone bohot zarori hain for exmaple stack keya hota stack hum kon sa use ker rahe hain stack ke jo technology hain woh kis leye use hote hai nodejs nextjs javasript yeh sb keya library keya hote hai framwork keya hota kon sa stack from end per use hota kon sa backend per use hota h yeh sb baseic hai but yeh sb clear hona zarori tabhi ja ker hum next js ke puray stak ko learn ker serkt</b></p><p class="lv1"><b>Tech Stack</b><br>Website/application banane ke liye use hone wali technologies aur tools ka combination.</p><p class="lv1"><b>Next.js</b> <b>Complete Stack <br></b>HTML → CSS → JavaScript → TypeScript → React → Next.js → Node.js → npm/npx → Tailwind CSS → ESLint → API → Route Handlers → SQL → PostgreSQL → Prisma → Authentication → Authorization → Git → GitHub → Vercel → Environment Variables</p><section><h2 id="next-js-all-stack-and-their-role"><i>1</i>Next.js All Stack and their role</h2><div class="tw lv2"><table><tr><th><b>Technology</b></th><th><b>Technology</b></th></tr><tr><td><b>HTML Category: </b>Markup Language<b><br>Definition:</b> Website ka structure banata hai.<br><b>Example: </b><b>&lt;h1&gt;Trains&lt;/h1&gt;</b></td><td><b>CSS / Tailwind CSS Category: </b>Style <b><br>Definition: </b>Website ka design banata hai.<br><b>Example: </b><b>color: blue;</b></td></tr><tr><td><b>JavaScript Category: </b>Programming Language<b> Definition: </b>Website ka logic aur behavior banata hai.<br><b>Example: </b><b>console.log("Search");</b></td><td><b>TypeScript Category: </b>Programming<b> Language Definition: </b>JavaScript ko types ke saath safer banata hai.<br><b>Example: </b><b>let price: number = 5000;</b></td></tr><tr><td><b>React Category: </b>JavaScript Library<b><br>Definition: </b>Reusable UI components banata<b> hai.<br>Example: </b><b>function Card() { }</b></td><td><b>Next.js Category: </b>React Framework<b><br>Definition: </b>Complete web application banata hai.<br><b>Example: </b><b>app/trains/page.tsx</b></td></tr><tr><td><b>Node.js</b><b> Category: </b>JavaScript Runtime<b><br>Definition: </b>JavaScript ko server par run karta<b> hai.Example: </b><b>console.log("Server");</b></td><td><b>npm / npxCategory: </b>Package Tools<b> <br>Definition:</b> Packages install/manage aur tools run karte hain.<b><br>Example: </b><b>npm install axios</b></td></tr><tr><td><b>ESLint Category: </b>Code Checking Tool<b><br>Definition: </b>Code mein common mistakes detect karta hai.<br><b>Example: </b><b>npm run lint</b></td><td><b>API Category: </b>Communication Interface<b><br>Definition:</b> Frontend aur backend mein data exchange karwata hai.<br><b>Example: </b><b>fetch("/api/trains")</b></td></tr><tr><td><b>Route Handler Category: </b>Next.js Feature<b><br>Definition: </b>API requests ko handle karta hai.<b><br>Example: </b><b>/api/trains</b></td><td><b>SQL Category: </b>Query Languag<b>e<br>Definition: </b>Database se data query karta hai.<b><br>Example: </b><b>SELECT * FROM trains;</b></td></tr><tr><td><b>PostgreSQL Category: </b>Database<b><br>Definition: </b>Website ka data store karta hai.<b><br>Example: </b><b>Users, Trains, Bookings</b></td><td><b>Prisma Category: ORM<br>Definition:</b> App aur database ka connection easy karta hai.<br><b>Example: </b><b>prisma.train.findMany()</b></td></tr><tr><td><b>Authentication Category: </b>Security System<b><br>Definition:</b> User ki identity verify karta hai.<br><b>Example: </b><b>Login → User</b></td><td><b>Authorization Category: </b>Permission<b> <br>System Definition: </b>User ki permissions decide karta hai.<br><b>Example: </b><b>Admin → Delete</b></td></tr><tr><td><b>Git Category: </b>Version Control<b><br>Definition: </b>Code ki history aur changes track karta hai.<br><b>Example: </b><b>git add .</b></td><td><b>GitHub Category: </b>Code Hosting<b><br>Definition: </b>Code ko online store karta hai.<b><br>Example: </b><b>git push</b></td></tr><tr><td><b>VercelCategory: </b>Deployment Platform<b><br>Definition: </b>Website ko internet par live karta hai.<br><b>Example: </b><b>Deploy → Live</b></td><td><b>Environment Variables Category: </b>Configuration / Secrets<br><b>Definition: </b>Secret values safely store karti hain.<b><br>Example: </b><b>process.env.DATABASE_URL</b></td></tr></table></div></section><section><h2 id="important-relationships-in-javascript-no"><i>2</i>Important Relationships in JavaScript Node.js React Next.js</h2><p class="lv2">Node.js aur React ek doosre ke parent/child nahi hain.</p><p class="lv2">Unka role different hai:</p><ul class="lv2"><li><b>Node.js → JavaScript Runtime</b></li><li><b>React → UI Library</b></li><li><b>Next.js → React Framework</b></li></ul></section><section><h2 id="framework-kya-hota-hai"><i>3</i>Framework Kya Hota Hai?</h2><p class="lv2"><b>Framework = Website/application banane ka ready-made structure, rules aur tools.</b></p><p class="lv2">Framework sirf files organize nahi karta. Ye website/application banane ka <b>standard system</b> provide karta hai.</p><h3 id="framework-ke-3-main-ideas" class="lv3">Framework ke 3 main ideas</h3><h3 id="1-structure" class="lv3">1. Structure</h3><p class="lv3">Website ka code organized rakhta hai.</p><h3 id="2-ready-features" class="lv3">2. Ready Features</h3><p class="lv3">Routing, server-side functionality, API/Route Handlers jaise features provide karta hai.</p><h3 id="3-rules-conventions" class="lv3">3. Rules / Conventions</h3><p class="lv3">Kuch kaam karne ka standard tareeqa provide karta hai.</p><h3 id="framework-rule-simple-example" class="lv3">Framework Rule Simple Example</h3><p class="lv3">Maan lo hume Train Website mein /trains page banana hai. Next.js mein:</p><div class="cb lv3"><pre><code>app/
└── trains/
    └── page.tsx</code></pre></div><p class="lv3 box tip">Yani Next.js ke standard folder/file structure ko follow karne se route create ho jata hai.</p></section><section><h2 id="frontend-vs-backend"><i>4</i>Frontend vs Backend</h2><div class="cb lv2"><pre><code>                 WEB DEVELOPMENT
                                    │
          ┌────────────┴────────────┐
          │                                           │
      FRONTEND                           BACKEND
          │                                           │
   HTML + CSS + JS/TS               Server Logic
          │                                       │
        React                                Node.js
          │                                           │
       Next.js ───────────────→ API
                                    │
                                    ↓
                                Database
                                    │
                   Users / Trains /Bookings</code></pre></div><h3 id="frontend" class="lv3">Frontend</h3><p class="lv3"><b>Jo user browser mein dekhta aur use karta hai.</b></p><p class="lv3">Examples:</p><ul class="lv3"><li>Search Form</li><li>Buttons</li><li>Navbar</li><li>Train Cards</li><li>Booking Form</li></ul><h3 id="backend" class="lv3">Backend</h3><p class="lv3"><b>Server-side logic jo data aur requests handle karta hai.</b></p><p class="lv3">Examples:</p><ul class="lv3"><li>Login check</li><li>Booking process</li><li>Database se data lena</li><li>Data save karna</li><li>API requests handle karna</li></ul></section><section><h2 id="next-js-introduction"><i>5</i>Next.js Introduction</h2><p class="lv2">Next.js programming language nahi hai. Next.js React ka framework hai jo complete web applications/websites banane ke liye use hota hai.</p><ul class="lv2"><li><b>Next.js</b> → React ka framework jo complete web applications banane mein help karta hai. <b>Example:</b> Train booking website.</li><li><b>Rendering</b> → Page ko browser mein dikhane ke liye ready karna. <br><b>Example:</b> Train list page show hona.</li><li><b>Routing</b> → URL ko correct page se connect karna. <br><b>Example:</b> /trains → Trains page.</li><li><b>SSR (Server-Side Rendering)</b> → Page ko server par <b>request ke time</b> banata hai. <br><b>Example:</b> Latest train availability show karna.</li><li><b>SSG (Static Site Generation)</b> → Page ko <b>build ke time pehle se</b> bana kar ready rakhta hai. <b>Example:</b> Train booking guide page.</li><li><b>ISR (Incremental Static Regeneration)</b> → Pehle se bane page ko <b>baad mein update/re-generate</b> karta hai. <br><b>Example:</b> Train schedule page ko har 10 minutes mein update karna.</li><li><b>Frontend</b> → User ko website par jo nazar aur interact hota hai. <br><b>Example:</b> Search form.</li><li><b>Backend</b> → Server par chalne wala logic jo data handle karta hai. <br><b>Example:</b> Booking process.</li><li><b>Full-stack</b> → Frontend aur backend dono ek application mein handle karna. <br><b>Example:</b> Next.js website + API.</li><li><b>Performance</b> → Website ko fast aur efficient rakhna. <br><b>Example:</b> Images optimize karke page jaldi load karna.</li></ul><h3 id="npm-node-package-manager" class="lv3">npm (Node Package Manager)</h3><div class="cb lv3"><pre><code>npm = Packages install aur manage karne ka tool.</code></pre></div><ul class="lv3"><li>Version check:</li><li>npm -v</li><li>Hamare system mein:</li><li>11.17.0</li></ul><p class="lv3"><b><br><br>Packages Kab Install Karte Hain</b>?</p><p class="lv3">Default/Required Packages</p><p class="lv3">Project create karte waqt required packages automatically install ho sakte hain.</p><ul class="lv3"><li>Next.js</li><li>React</li><li>React DOM</li><li>TypeScript</li><li>Tailwind CSS</li><li>ESLint</li></ul><p class="lv3">jaise packages install hue.</p><h3 id="extra-packages" class="lv3">Extra Packages</h3><p class="lv3">Jab kisi <b>specific need</b> ki zaroorat ho, tab package install karte hain.</p><p class="lv3">Example:</p><ul class="lv3"><li>Payment</li><li>Charts</li><li>Date handling</li><li>Authentication</li></ul><h3 id="package-install-command" class="lv3">Package Install Command</h3><div class="cb lv3"><pre><code>npm install package-name</code></pre></div><p class="lv3">Meaning:<br>Project mein ye package install karo.</p><h3 id="simple-rule" class="lv3">Simple Rule</h3><ul class="lv3"><li>Required package → Project setup ke waqt install ho sakta hai.</li><li>Extra functionality → Need par package install karte hain.</li></ul><h3 id="npx-kya-hai" class="lv3">npx Kya Hai?</h3><div class="cb lv3"><pre><code>npx = Package/tool ko run karne ka command.</code></pre></div><p class="lv3">Example:<br>npx create-next-app@latest</p><p class="lv3">Meaning:<br>Next.js project create karne wala tool run karo</p><p class="lv3"><b>npm (Node Package Manager)</b> =</p><p class="lv3">Package install/manage karta hai. Example: npm.cmd install axios</p><p class="lv3"><b>npx (npm Package Executor)</b> = Package/tool run karta hai. Example: npx.cmd create-next-app@latest<br></p><div class="tw lv3"><table><tr><th><b>Command</b></th><th><b>Full Form / Meaning</b></th><th><b>Kya karta hai</b></th><th><b>Example / Use</b></th></tr><tr><td>cd</td><td>Change Directory</td><td>Folder change karta hai</td><td>cd next-learning → next-learning folder mein jao</td></tr><tr><td>cd ..</td><td>Parent Directory</td><td>Ek folder upar/peeche jata hai</td><td>cd ..</td></tr><tr><td>cd \</td><td>Root Directory</td><td>Drive ke main/root folder mein jata hai</td><td>cd \ → C:\</td></tr><tr><td>cd %USERPROFILE%</td><td>User Profile</td><td>Current Windows user ke main folder mein jata hai</td><td>cd %USERPROFILE% → C:\Users\saadk</td></tr><tr><td>pwd</td><td>Print Working Directory</td><td>Batata hai ke aap abhi kis folder mein ho</td><td>pwd</td></tr><tr><td>dir</td><td>Directory Listing</td><td>Current folder ki files aur folders dikhata hai</td><td>dir</td></tr><tr><td>ls</td><td>List</td><td>Files aur folders ki list dikhata hai</td><td>ls</td></tr><tr><td>mkdir</td><td>Make Directory</td><td>Naya folder banata hai</td><td>mkdir projects</td></tr><tr><td>rmdir</td><td>Remove Directory</td><td>Folder delete karta hai</td><td>rmdir old-folder</td></tr><tr><td>code .</td><td>VS Code + Current Folder</td><td>Current folder ko VS Code mein open karta hai</td><td>code .</td></tr><tr><td>explorer .</td><td>File Explorer + Current Folder</td><td>Current folder ko Windows File Explorer mein open karta hai</td><td>explorer .</td></tr><tr><td>node -v</td><td>Node Version</td><td>Node.js ki installed version check karta hai</td><td>node -v</td></tr><tr><td>npm.cmd -v</td><td>npm Version</td><td>npm ki installed version check karta hai</td><td>npm.cmd -v</td></tr><tr><td>npm.cmd install</td><td>Install Packages</td><td>Project ki required packages install karta hai</td><td>npm.cmd install</td></tr><tr><td>npm.cmd install axios</td><td>Install Package</td><td>Naya package project mein install karta hai</td><td>npm.cmd install axios</td></tr><tr><td>npm.cmd uninstall axios</td><td>Uninstall Package</td><td>Package ko project se remove karta hai</td><td>npm.cmd uninstall axios</td></tr><tr><td>npm.cmd run dev</td><td>Run Development</td><td>Next.js development server start karta hai</td><td>npm.cmd run dev</td></tr><tr><td>npm.cmd run build</td><td>Run Build</td><td>Production ke liye project build karta hai</td><td>npm.cmd run build</td></tr><tr><td>npm.cmd start</td><td>Start Production</td><td>Production build ko start karta hai</td><td>npm.cmd start</td></tr><tr><td>npm.cmd run lint</td><td>Run Lint</td><td>Code ko ESLint se check karta hai</td><td>npm.cmd run lint</td></tr><tr><td>npx.cmd create-next-app@latest</td><td>Run Next.js Tool</td><td>Naya Next.js project create karta hai</td><td>npx.cmd create-next-app@latest</td></tr><tr><td>clear</td><td>Clear Screen</td><td>Terminal ki screen clean karta hai</td><td>clear</td></tr><tr><td>Ctrl + C</td><td>Stop Process</td><td>Running command/server ko stop karta hai</td><td>Next.js server stop karne ke liye</td></tr><tr><td>git init</td><td>Initialize Git</td><td>Folder ko Git repository banata hai</td><td>git init</td></tr><tr><td>git status</td><td>Git Status</td><td>Git mein current changes check karta hai</td><td>git status</td></tr><tr><td>git add .</td><td>Add Changes</td><td>Current project ke changes ko commit ke liye select karta hai</td><td>git add .</td></tr><tr><td>git commit</td><td>Save Point</td><td>Changes ka Git history save point banata hai</td><td>git commit -m "Initial project"</td></tr><tr><td>git push</td><td>Push Changes</td><td>Local changes ko GitHub par bhejta hai</td><td>git push</td></tr></table></div><h3 id="important-symbols" class="lv3">Important Symbols</h3><div class="tw lv3"><table><tr><th><b>Symbol</b></th><th><b>Meaning</b></th><th><b>Example</b></th></tr><tr><td>.</td><td>Current folder</td><td>code . → current folder VS Code mein open</td></tr><tr><td>..</td><td>Ek folder upar</td><td>cd ..</td></tr><tr><td>\</td><td>Folder/path separator</td><td>C:\Users\saadk\next-learning</td></tr><tr><td>%USERPROFILE%</td><td>Current Windows user ka main folder</td><td>cd %USERPROFILE%</td></tr><tr><td>@latest</td><td>Latest available version</td><td>create-next-app@latest</td></tr></table></div><h3 id="abhi-sabse-important" class="lv3">Abhi sabse important</h3><div class="tw lv3"><table><tr><th><b>Command</b></th><th><b>Simple Meaning</b></th></tr><tr><td><b>cd</b></td><td><b>Folder mein jana</b></td></tr><tr><td><b>cd ..</b></td><td><b>Ek folder upar jana</b></td></tr><tr><td><b>cd %USERPROFILE%</b></td><td><b>Apne Windows user folder mein jana</b></td></tr><tr><td><b>pwd</b></td><td><b>Abhi kahan ho check karna</b></td></tr><tr><td><b>dir</b></td><td><b>Folder ke andar kya hai dekhna</b></td></tr><tr><td><b>code .</b></td><td><b>VS Code mein current folder kholna</b></td></tr><tr><td><b>node -v</b></td><td><b>Node version check</b></td></tr><tr><td><b>npm.cmd -v</b></td><td><b>npm version check</b></td></tr><tr><td><b>npm.cmd install</b></td><td><b>Packages install</b></td></tr><tr><td><b>npm.cmd run dev</b></td><td><b>Next.js website ko development mode mein start karna</b></td></tr><tr><td><b>npm.cmd run build</b></td><td><b>Production build banana</b></td></tr><tr><td><b>npm.cmd run lint</b></td><td><b>Code check karna</b></td></tr><tr><td><b>npx.cmd create-next-app@latest</b></td><td><b>Next.js project banana</b></td></tr><tr><td><b>Ctrl + C</b></td><td><b>Running server/command stop karna</b></td></tr></table></div></section><section><h2 id="installation"><i>6</i>Installation (official docs se add kiya)</h2><div class="x"><h3 id="system-requirements">System Requirements</h3>
<ul><li>Node.js minimum <b>20.9</b>; macOS, Windows (WSL bhi), Linux</li><li>Browsers: Chrome 111+, Edge 111+, Firefox 111+, Safari 16.4+</li></ul>
<h3 id="create-with-the-cli">Create with the CLI</h3>
<pre><code>npx create-next-app@latest my-app --yes
cd my-app
npm run dev      # http://localhost:3000</code></pre>
<ul><li><code>--yes</code> defaults: TypeScript, Tailwind, ESLint, App Router, Turbopack, alias <code>@/*</code>, AGENTS.md</li><li>Prompts: project name, defaults ya customize (TypeScript, linter ESLint/Biome/None, React Compiler, Tailwind, <code>src/</code>, App Router, import alias)</li></ul>
<h3 id="manual-installation">Manual Installation</h3>
<pre><code>npm i next@latest react@latest react-dom@latest</code></pre>
<h4>package.json scripts</h4>
<ul><li><code>next dev</code> dev server (Turbopack default), <code>next build</code> production build, <code>next start</code> production server, <code>eslint</code> linting</li><li>Webpack chahiye to <code>--webpack</code> flag</li></ul>
<h4>app folder banana</h4>
<p><code>app/layout.tsx</code> root layout hai. Ye required hai aur isme <code>&lt;html&gt;</code> aur <code>&lt;body&gt;</code> hote hain. Phir <code>app/page.tsx</code> home page.</p>
<pre><code>export default function Page() {
  return &lt;h1&gt;Hello, Next.js!&lt;/h1&gt;
}</code></pre>
<div class="box tip">Root layout bhool jao to <code>next dev</code> khud bana deta hai. <code>public/</code> folder optional hai (static files, <code>/profile.png</code>).</div>
<h3 id="run-the-development-server">Run the Development Server</h3>
<p><code>npm run dev</code>, phir <code>http://localhost:3000</code> kholo. <code>app/page.tsx</code> edit karke save karo, browser me turant update.</p>
<h3 id="typescript-setup">TypeScript Setup</h3>
<p>Minimum v5.1.0. File ko <code>.ts/.tsx</code> rename karo aur <code>next dev</code> chalao, <code>tsconfig.json</code> aur dependencies auto ban jate hain. VS Code me "TypeScript: Select TypeScript Version" → "Use Workspace Version" se Next.js plugin on hota hai.</p>
<h3 id="editor-setup">Editor Setup</h3>
<p><code>page.tsx</code>, <code>layout.tsx</code> jaise same naam ke tabs confuse karte hain. VS Code 1.88+ me <code>workbench.editor.customLabels.patterns</code> se folder ke naam ke saath label karo. JetBrains me ye automatic hai.</p>
<h3 id="linting">Linting</h3>
<ul><li>ESLint (<code>"lint": "eslint"</code>, config <code>eslint.config.mjs</code>) ya Biome (<code>biome check</code>)</li><li>Next.js 16 me <code>next build</code> ab linter automatically nahi chalata</li></ul>
<h3 id="absolute-imports-amp-path-aliases">Absolute Imports &amp; Path Aliases</h3>
<pre><code>// Before
import { Button } from '../../../components/button'
// After
import { Button } from '@/components/button'</code></pre>
<p><code>tsconfig.json</code> / <code>jsconfig.json</code> me <code>baseUrl</code> aur <code>paths</code> set karo, jaise <code>"@/components/*": ["components/*"]</code>.</p>
<h3 id="upgrade-your-app">Upgrade your app</h3>
<p><code>npx next upgrade</code> se latest version. Bundled docs bhi update hoti hain (details section 18).</p>
</div></section><section><h2 id="project-structure-and-organization"><i>7</i>Project structure and organization</h2><h3 id="top-level-folders" class="lv3">Top-level folders</h3><ul class="lv3"><li>app	App Router</li><li>pages	Pages Router</li><li>public	Static assets to be served</li><li>src	Optional application source folder</li></ul><h3 id="top-level-files" class="lv3">Top-level files</h3><ul class="lv3"><li>next.config.js		Next.js ki settings/configuration</li><li>package.json		Project ke packages + commands/scripts</li><li>instrumentation.ts	OpenTelemetry / instrumentation setup</li><li>proxy.ts		Next.js ki request proxy handling</li><li>.env			Environment variables rakhne ki file</li><li>.env.local		Local machine ke environment variables</li><li>.env.production	Production environment ke variables</li><li>.env.development	Development environment ke variables</li><li>eslint.config.mjs	ESLint ki settings</li><li>.gitignore		Git ko batata hai kin files/folders ko track nahi karna</li><li>next-env.d.ts		Next.js ke liye TypeScript declarations</li><li>tsconfig.json		TypeScript ki settings</li><li>jsconfig.json		JavaScript project ki settings</li></ul><div class="cb lv3"><pre><code>next-learning/
│
├── .next/                → Next.js ka generated data
│
├── app/                  → Application ka main code
│   ├── favicon.ico       → Browser tab ka icon
│   ├── globals.css       → Global CSS/design
│   ├── layout.tsx        → Common layout
│   └── page.tsx          → Page/UI
│
├── node_modules/         → Installed packages
│
├── public/               → Static files
│
├── package-lock.json     → npm dependencies ka locked record
│
├── package.json          → Project configuration + packages + scripts
│
├── next.config.ts        → Next.js configuration
│
├── tsconfig.json         → TypeScript configuration
│
├── eslint.config.mjs     → ESLint configuration
│
└── postcss.config.mjs   → PostCSS configuration</code></pre></div><h3 id="first-next-js-project" class="lv3">First Next.js Project</h3><ol class="lv3"><li>VS Code open	Coding environment open</li><li>Terminal open	Commands chalane ki jagah</li><li>node -v	Check karo Node.js installed hai aur version kya hai</li><li>npm.cmd -v	Check karo npm installed hai aur version kya hai</li><li>cd %USERPROFILE%	Apne Windows user folder mein jao</li><li>npx.cmd create-next-app@latest	Naya Next.js project create karne ka tool start</li><li>Project name do	Example: train-website</li><li>Next.js questions ka answer	TypeScript, Tailwind, App Router etc. select karo</li><li>Installation complete	Next.js project ready</li><li>cd train-website	Apne naye project ke folder mein jao</li><li>npm.cmd run dev	Development server start karo</li><li>http://localhost:3000	Apni website browser mein dekho</li></ol><h3 id="routing-files" class="lv3">Routing Files</h3><div class="cb lv3"><pre><code>app/
│
├── layout.tsx          → Common UI
│
├── page.tsx            → Home Page
│
├── loading.tsx         → Loading UI
│
├── error.tsx           → Error UI
│
├── not-found.tsx       → Not Found UI
│
├── about/
│   └── page.tsx        → /about
│
├── products/
│   ├── page.tsx        → /products
│   └── loading.tsx     → Products loading UI
│
└── api/
    └── users/
        └── route.ts    → /api/users API</code></pre></div><h3 id="nested-and-dynamic-routes" class="lv3">Nested and Dynamic Routes</h3><ol class="lv3"><li><b>Nested Route:</b> Folders ko nest karke URL ke andar multiple segments banana, jaise app/blog/authors/page.tsx → /blog/authors.</li><li><b>Dynamic Route:</b> URL ke kisi segment ko dynamic banane ke liye [ ] use karna, jaise app/blog/[slug]/page.tsx → /blog/hello, /blog/nextjs, etc.</li></ol><div class="tw lv3"><table><tr><th><b>File</b></th><th><b>URL</b></th><th><b>Type</b></th></tr><tr><td>app/page.tsx</td><td>/</td><td>Normal</td></tr><tr><td>app/blog/page.tsx</td><td>/blog</td><td>Nested</td></tr><tr><td>app/blog/authors/page.tsx</td><td>/blog/authors</td><td>Nested</td></tr><tr><td>app/blog/[slug]/page.tsx</td><td>/blog/anything</td><td>Nested + Dynamic</td></tr></table></div><h3 id="route-groups-and-private-folders" class="lv3">Route groups and private folders</h3><ul class="lv3"><li><b>Route Group (group)</b> → Code organize karta hai bina URL mein naam add kiye, example: app/(shop)/cart/page.tsx → https://example.com/cart.</li><li><b>Private Folder _folder</b> → Non-routing/supporting files rakhne ke liye hota hai, example: app/blog/_components/Post.tsx → koi URL nahi banta.</li></ul><div class="cb lv3"><pre><code>app/
│
├── (marketing)/
│   ├── page.tsx
│   │    ↓ URL: https:<span class="cm">//example.com/</span>
│   │
│   └── about/
│       └── page.tsx
│            ↓ URL: https:<span class="cm">//example.com/about</span>
│
├── (shop)/
│   └── cart/
│       └── page.tsx
│            ↓ URL: https:<span class="cm">//example.com/cart</span>
│
└── blog/
    ├── page.tsx
    │    ↓ URL: https:<span class="cm">//example.com/blog</span>
    │
    ├── _components/
    │   └── Post.tsx
    │        ↓ URL: ❌ Koi URL nahi
    │
    └── _lib/
        └── data.ts</code></pre></div><p class="lv3">↓ URL: ❌ Koi URL nahi</p><h3 id="parallel-and-intercepted-routes" class="lv3">Parallel and Intercepted Routes</h3><h4 id="parallel-route-folder" class="lv4">Parallel Route @folder</h4><p class="lv4">Ek hi layout mein multiple UI slots render karna, example: app/@sidebar/page.tsx → sidebar UI, app/@main/page.tsx → main UI.</p><div class="cb lv4"><pre><code>app/
├── layout.tsx
├── @sidebar/
│   └── page.tsx
│
└── @main/
    └── page.tsx
┌──────────────────────────────────┐
│                 │                                        │
│   SIDEBAR    │        MAIN CONTENT               │
│                │                                     │
└──────────────────────────────────┘</code></pre></div><h4 id="intercepted-route" class="lv4">Intercepted Route</h4><div class="cb lv4"><pre><code>(.)folder</code></pre></div><p class="lv4">Same-level route ko current page ke andar/modal mein show karna, example: app/blog/(.)post/page.tsx → post ko modal mein show karna.</p><p class="lv4"><b>(..)folder</b><br>Parent-level route ko current page ke andar/modal mein show karna, example: app/blog/(..)login/page.tsx → parent ka login route overlay mein show karna.</p><p class="lv4"><b>(..)(..)folder</b> <br>2 levels upar ke route ko current page mein intercept karna, example: app/a/b/(..)(..)login/page.tsx → root-level login ko overlay mein show karna.</p><p class="lv4"><b>Intercepted Route (...)folder</b> <br>Root app se kisi route ko current page mein intercept karna, example: app/blog/(...)login/page.tsx → root-level login ko current view mein overlay karna</p></section><section><h2 id="layouts-and-pages"><i>8</i>Layouts and Pages</h2><h3 id="creating-a-page" class="lv3">Creating a page</h3><p class="lv3">Kisi specific URL par dikhne wali unique UI/content hoti hai. Example: /about par About page aur /trains par Trains page.</p><div class="cb lv3"><div class="fn">app/Page.tsx</div><pre><code><span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Home() {
  <span class="kw">return</span> &lt;h1&gt;Hello Next.js!&lt;/h1&gt;
}</code></pre></div><p class="lv3"><b>export default</b> → Home function ko file ke bahar available karta hai, taake Next.js ise page ke taur par use kar sake.</p><p class="lv3"><b>app/page.tsx</b> → Home page ki file hai.</p><p class="lv3"><b>function Home() </b>→ Ek function hai jo Home page banata hai.</p><p class="lv3"><b>return</b> → Batata hai page par kya dikhana hai.</p><h3 id="creating-a-layout" class="lv3">Creating a layout</h3><p class="lv3">Aisi common UI hoti hai jo multiple pages par same rehti hai. Example: Navbar aur Footer jo /about, /trains aur /contact sab pages par same ho.</p><div class="cb lv3"><pre><code>app/layout.tsx</code></pre></div><ul class="lv3"><li><b>function → function banane ka keyword</b><br> → Function kya hota hai? Ek code block jo ek specific kaam karta hai.</li><li><b>DashboardLayout → function ka naam</b><br> → Is function ko hum DashboardLayout naam se bulate hain.</li><li><b>( ) → parameter area<br></b> → Function ko input/parameters dene ki jagah.</li><li><b>{ children } → parameter<br></b> → Object ke andar se children value nikalta hai.</li><li><b>: → TypeScript type separator<br></b> → Batata hai ke parameter/property ka type kya hai.</li><li><b>{ children: React.ReactNode }</b> → parameter ka type<br> → Batata hai ke children kis type ki value ho sakti hai.</li><li><b>) → parameter area close</b><br> → Parameters yahan khatam hote hain.</li><li><b>{ } → function body</b><br> → Function ka actual code iske andar hota hai.</li><li><b>return → output dene ka keyword<br></b> → Function kya output/UI dega, woh batata hai.</li><li><b>&lt;html&gt; → HTML element<br></b> → Sabse outer HTML container.</li><li><b>&lt;body&gt; → HTML element<br></b> → Page ka body/content area.</li><li><b>&lt;main&gt; → HTML element<br></b> → Main content ke liye container.</li><li><b>{children} → children ki actual value<br></b> → Jo page/layout andar aaya hai, woh yahan render hota hai.</li></ul><h3 id="creating-a-nested-route" class="lv3">Creating a nested route</h3><p class="lv3">Aisa route jisme URL multiple segments se mil kar bana ho, jaise /blog/post.</p><ul class="lv3"><li>Root Segment → URL ka starting / part.</li><li>Leaf Segment → Route ka last segment, jaise /blog/[slug] mein [slug].</li><li>Folder → Next.js mein URL segment banata hai.</li><li>[slug] → Dynamic segment hai, jisme URL ki value change ho sakti hai.</li></ul><h3 id="nesting-layouts" class="lv3">Nesting Layouts</h3><p class="lv3">Jab ek layout ke andar doosra layout ho aur parent layout, child layout ko children ke through wrap kare.</p><ul class="lv3"><li>Root Layout → app/layout.tsx; poori application ka sabse outer layout.</li><li>Blog Layout → app/blog/layout.tsx; sirf /blog ke andar wale pages ka layout.</li><li>children → Child layout ya page jo parent layout ke andar render hota hai.</li><li>Layout hierarchy → Parent layout → child layout → page.</li></ul><h3 id="dynamic-segment" class="lv3">Dynamic Segment</h3><p class="lv3">Aisa URL segment jiska naam/value fixed nahi hota, balki data ke according change hota hai.</p><ul class="lv3"><li>[slug] → Dynamic segment banane ke liye folder ke naam ko square brackets [] mein likhte hain.</li><li>app/blog/[slug]/page.tsx → Ek hi page.tsx se multiple blog post URLs ban sakte hain.</li><li>Example: [slug] ki jagah hello, nextjs, my-first-post aa sakta hai.</li><li>Result: /blog/hello, /blog/nextjs, /blog/my-first-post</li><li>Faida → Har blog post ke liye alag folder/page manually banane ki zaroorat nahi; ek dynamic route data ke basis par different posts handle karta hai.</li></ul><h3 id="search-parameters-query-parameters" class="lv3">Search Parameters / Query Parameters</h3><p class="lv3">URL ke ? ke baad aane wali information ko search parameters kehte hain.</p><p class="lv3"><b>Example: </b>/products?category=shoes&amp;page=2</p><h3 id="linking-between-pages" class="lv3">Linking between pages</h3><p class="lv3">ko tum website ke clickable link/button ki tarah samjho; user click karta hai aur specified route par chala jata hai.</p><h3 id="route-props-helpers-properties" class="lv3">Route Props Helpers(properties )</h3><p class="lv3">Next.js ke utility types hain jo tumhare route structure ke hisaab se params, searchParams, children aur named slots ke types automatically bana dete hain.</p><div class="tw lv3"><table><tr><th><b>Helper</b></th><th><b>Kahan use hota hai</b></th><th><b>Kya deta hai</b></th></tr><tr><td>PageProps</td><td>page.tsx</td><td>params + searchParams</td></tr><tr><td>LayoutProps</td><td>layout.tsx</td><td>children + named slots</td></tr></table></div></section><section><h2 id="linking-and-navigating"><i>9</i>Linking and Navigating</h2><ul class="lv2"><li><b>Linking</b><br> Ek page/route se doosre page/route par jane ke liye link banana.</li><li><b>Navigating</b> <br>User ka ek route se doosre route par move hona.</li></ul><p class="lv2"><b>Server Rendering</b> <br>Server par page ka HTML/UI generate hota hai, phir browser ko bheja jata hai.</p><div class="cb lv2"><pre><code><span class="cm">// app/about/page.tsx</span>
<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Page() {
  <span class="kw">return</span> &lt;h1&gt;About Us&lt;/h1&gt;
}</code></pre></div><p class="lv2"><b>Prefetching</b><br>User click karne se pehle Next.js future page ka data/code pehle se load kar leta hai.</p><p class="lv2">Example: /blog par Blog Post ka &lt;Link&gt; hai, Next.js us page ko pehle load kar sakta hai.</p><div class="cb lv2"><pre><code><span class="kw">import</span> Link <span class="kw">from</span> <span class="st">'next/link'</span>

&lt;Link href=<span class="st">"/about"</span>&gt;About&lt;/Link&gt;</code></pre></div><p class="lv2"><b>Streaming<br></b>Page ka jo content ready ho, woh browser ko parts mein bheja jata hai, poora page ready hone ka wait nahi karta.</p><p class="lv2">Example: heading pehle show ho jaye aur slow posts baad mein aa jayein.</p><div class="cb lv2"><pre><code><span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Page() {
  <span class="kw">return</span> (
    &lt;&gt;
      &lt;h1&gt;My Blog&lt;/h1&gt;
      {/* slow content baad mein stream ho sakta hai */}
    &lt;/&gt;
  )
}</code></pre></div><p class="lv2"><b>Client-side transitions</b><br>Link click karne par poora browser/page reload kiye baghair Next.js current page ko new route ke content se update karta hai. Example: /home → /about par click, bina full reload</p><div class="cb lv2"><pre><code><span class="kw">import</span> Link <span class="kw">from</span> <span class="st">'next/link'</span>

&lt;Link href=<span class="st">"/about"</span>&gt;Go to About&lt;/Link&gt;</code></pre></div><h3 id="what-can-make-transitions-slow" class="lv3">What can make transitions slow?</h3><p class="lv3">Transition → ek route/page se doosre route/page par navigation.</p><p class="lv3">Next.js normally navigation ko fast banane ke liye prefetching, client-side transitions aur streaming jaisi optimizations use karta hai. Lekin kuch situations mein transition slow feel ho sakta hai.</p><h4 id="1-dynamic-routes-without-loading-tsx" class="lv4">1. Dynamic routes without loading.tsx</h4><p class="lv4">Problem:</p><p class="lv4">Dynamic route par navigate karte waqt client ko server ka response wait karna pad sakta hai. Is wajah se user ko lag sakta hai ke app respond nahi kar rahi.</p><p class="lv4">Solution: Dynamic route ke andar loading.tsx add karo.</p><p class="lv4">Example:</p><div class="cb lv4"><div class="fn">app/blog/[slug]/loading.tsx</div><pre><code><span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Loading() {
<span class="kw">return</span> &lt;LoadingSkeleton /&gt;
}</code></pre></div><h4 id="2-dynamic-segments-without-generatestati" class="lv4">2. Dynamic segments without generateStaticParams</h4><p class="lv4">Agar dynamic route ko build time par generate kiya ja sakta hai,</p><p class="lv4">lekin generateStaticParams nahi diya gaya, to route request ke</p><p class="lv4">time par dynamically render ho sakta hai.</p><p class="lv4">Solution: generateStaticParams use karo.</p><p class="lv4">File:</p><div class="cb lv4"><div class="fn">app/blog/[slug]/page.tsx</div><pre><code><span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> generateStaticParams() {       <span class="cm">// Static params generate</span>
  <span class="kw">const</span> posts = <span class="kw">await</span> fetch(<span class="st">'https://.../posts'</span>)         <span class="cm">// Posts data fetch</span>
    .then((res) =&gt; res.json())                              <span class="cm">// Response ko JSON mein convert</span>
  <span class="kw">return</span> posts.map((post) =&gt; ({                              <span class="cm">// Har post ka parameter create</span></code></pre></div><p class="lv4">slug: post.slug,                                  		// Post ka slug set</p><div class="cb lv4"><pre><code>  }))                                                           <span class="cm">// map complete</span>
}                                                               <span class="cm">// Function complete</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">async</span> <span class="kw">function</span> Page({                    <span class="cm">// Page component</span></code></pre></div><p class="lv4">params,                                              		// Dynamic route params</p><div class="cb lv4"><pre><code>}: {                                                            <span class="cm">// Type definition start</span></code></pre></div><p class="lv4">params: Promise&lt;{ slug: string }&gt;                    	// params ka TypeScript type</p><div class="cb lv4"><pre><code>}) {                                                            <span class="cm">// Function body start</span>
  <span class="kw">const</span> { slug } = <span class="kw">await</span> params                             <span class="cm">// Actual slug get</span>
  <span class="cm">// ...                                                            // Baqi page code</span>
}                                                                <span class="cm">// Function complete</span></code></pre></div><h4 id="3-slow-networks" class="lv4">3. Slow networks</h4><p class="lv4">Slow ya unstable internet par prefetching user ke click karne se<br> pehle complete nahi ho sakti.</p><p class="lv4">Is situation mein navigation slow feel ho sakti hai.</p><p class="lv4">Iske liye useLinkStatus use karke navigation ke waqt immediate<br> feedback dikha sakte ho.</p><p class="lv4">File:</p><div class="cb lv4"><pre><code>app/ui/loading-indicator.tsx</code></pre></div><p class="lv4">Code:</p><div class="cb lv4"><pre><code><span class="st">'use client'</span>                                             <span class="cm">// Client Component</span>
<span class="kw">import</span> { useLinkStatus } <span class="kw">from</span> <span class="st">'next/link'</span>         <span class="cm">// useLinkStatus import</span>
<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> LoadingIndicator() {      <span class="cm">// LoadingIndicator component</span>
  <span class="kw">const</span> { pending } = useLinkStatus()             <span class="cm">// Navigation status get</span>
  <span class="kw">return</span> (                                              <span class="cm">// UI return</span>
    &lt;span                                               <span class="cm">// Span element</span></code></pre></div><p class="lv4">aria-hidden                                  		// Accessibility attribute</p><div class="cb lv4"><pre><code>      className={<span class="st">`link-hint ${pending ? 'is-pending' : ''}`</span>}  <span class="cm">// Pending class</span>
    /&gt;                                                  <span class="cm">// Span close</span>
  )                                                     <span class="cm">// Return close</span>
}                                                        <span class="cm">// Function complete</span></code></pre></div><p class="lv4 box warn"><b>Important:</b></p><p class="lv4">pending = true</p><p class="lv4">→ Navigation chal rahi hai.</p><p class="lv4">pending = false</p><p class="lv4">→ Navigation pending nahi hai.</p><h4 id="4-debounce-loading-indicator" class="lv4">4. Debounce loading indicator</h4><p class="lv4">Agar navigation bohat fast ho to loading indicator unnecessarily<br> flash kar sakta hai.</p><p class="lv4">Isliye indicator ko thoda delay de sakte ho.</p><p class="lv4">Example:</p><p class="lv4">Navigation 50ms mein complete<br> → Loading indicator show na ho.</p><p class="lv4">Navigation 500ms leti hai<br> → Loading indicator show ho.</p><p class="lv4">Next.js example mein around 100ms ka initial animation delay<br> use kiya ja sakta hai.</p><p class="lv4">Isse fast navigation par unnecessary loading indicator nahi dikhega.</p><h4 id="5-useoffline" class="lv4">5. useOffline</h4><p class="lv4">useOffline ek experimental hook hai.</p><p class="lv4">Iska purpose connectivity drop hone par prefetched routes ko<br> navigable rakhna hai.</p><p class="lv4 box warn">Important:</p><p class="lv4">useOffline = Experimental feature</p><h4 id="6-progress-bar" class="lv4">6. Progress bar</h4><p class="lv4">Loading indicator ke ilawa navigation ke waqt progress bar bhi<br> show kar sakte ho.</p><p class="lv4">Basic concept:</p><p class="lv4">Link click<br> → Progress bar start<br> → New page load<br> → Progress bar complete</p><h4 id="7-disabling-prefetching" class="lv4">7. Disabling prefetching</h4><p class="lv4">Agar prefetching disable karni ho to Link par:</p><div class="cb lv4"><pre><code>&lt;Link prefetch={false} href=<span class="st">"/blog"</span>&gt;       <span class="cm">// Prefetch disable + /blog target</span></code></pre></div><p class="lv4">Blog                                      // Clickable text</p><div class="cb lv4"><pre><code>&lt;/Link&gt;                                     <span class="cm">// Link close</span></code></pre></div><h4 id="8-hover-par-prefetching" class="lv4">8. Hover par prefetching</h4><p class="lv4">Prefetch completely disable karne ke bajaye sirf hover par prefetch<br> kar sakte ho.</p><p class="lv4">Iska faida ye hai ke user jis link mein interested lag raha hai,<br> sirf us route ko prefetch kiya ja sakta hai.</p><div class="tw lv4"><table><tr><th><b>Topic</b></th><th><b>Definition</b></th><th><b>Example</b></th></tr><tr><td>Dynamic routes without loading.tsx</td><td>Dynamic page load hone mein time lag sakta hai. loading.tsx wait ke waqt loading UI dikhata hai.</td><td>/blog/[slug] → page load hone tak Loading... show.</td></tr><tr><td>Dynamic segments without generateStaticParams</td><td>Dynamic pages build time par generate nahi hote. Isliye request ke waqt server ko page render karna pad sakta hai.</td><td>/blog/[slug] → generateStaticParams() se /blog/nextjs pehle generate.</td></tr><tr><td>Slow networks</td><td>Slow internet par prefetch click se pehle complete nahi hoti. useLinkStatus navigation ke waqt feedback deta hai.</td><td>Link click → internet slow → loading indicator show.</td></tr><tr><td>Debounce loading indicator</td><td>Loader ko thoda delay se show karte hain. Isse fast navigation par loader flicker nahi karta.</td><td>50ms load → loader nahi; 500ms load → loader show.</td></tr><tr><td>useOffline</td><td>Experimental hook hai jo connection drop hone par prefetched routes ko usable rakhne mein help karta hai.</td><td>Route prefetch ho chuka → internet drop → route accessible reh sakta hai.</td></tr><tr><td>Progress bar</td><td>Navigation ke waqt progress bar user ko batata hai ke page load ho raha hai.</td><td>Link click → progress bar start → page load → progress bar finish.</td></tr><tr><td>Disabling prefetching</td><td>prefetch={false} link ki prefetching band karta hai. Ye unnecessary resource usage kam kar sakta hai.</td><td>&lt;Link prefetch={false} href="/blog"&gt; → click se pehle /blog fetch nahi hoga.</td></tr><tr><td>Hydration not completed</td><td>Large JavaScript bundle hydration ko slow kar sakta hai. Iski wajah se Link ki prefetching bhi late start ho sakti hai.</td><td>Large JS → hydration slow → prefetch late → navigation slow feel.</td></tr></table></div><div class="tw lv4"><table><tr><th><b>Topic</b></th><th><b>Definition</b></th><th><b>Example</b></th></tr><tr><td>Native History API</td><td>Browser ki built-in history ko page reload kiye bina change karne ka method hai. Next.js isko apne Router ke saath sync karta hai.</td><td>URL ko /products?sort=asc mein change karna without full page reload.</td></tr><tr><td>window.history.pushState</td><td>Browser history mein new entry add karta hai. Isliye user Back button se previous state par ja sakta hai.</td><td>/products → Sort Ascending → /products?sort=asc → Back → /products</td></tr><tr><td>window.history.replaceState</td><td>Browser history ki current entry ko replace karta hai. Isliye user Back se replaced state par nahi ja sakta.</td><td>/en/about → locale French → /fr/about; Back karne par /en/about ki separate history entry nahi hogi.</td></tr></table></div></section><section><h2 id="server-and-client-components"><i>10</i>Server and Client Components</h2><ul class="lv2"><li>Server Component → Aisa component jo server par render hota hai aur data fetching, caching aur streaming ke liye use hota hai.</li><li>Client Component → Aisa component jo browser/client par interactive functionality aur browser APIs ke liye use hota hai.</li></ul><p class="lv2"><b>Server Component</b></p><div class="cb lv2"><pre><code><span class="kw">export</span> <span class="kw">default</span> <span class="kw">async</span> <span class="kw">function</span> Page() {                      <span class="cm">// Server Component</span>
  <span class="kw">const</span> data = <span class="kw">await</span> fetch(<span class="st">'https://api.example.com/posts'</span>)     <span class="cm">// Server par data fetch</span>
    .then((res) =&gt; res.json())                               <span class="cm">// Response ko JSON mein convert</span>

  <span class="kw">return</span> &lt;h1&gt;{data.title}&lt;/h1&gt;                               <span class="cm">// Data ko page par show</span>
}</code></pre></div><p class="lv2"><b>Client Component</b></p><div class="cb lv2"><pre><code><span class="st">'use client'</span>                                                <span class="cm">// Client Component</span>
<span class="kw">import</span> { useState } <span class="kw">from</span> <span class="st">'react'</span>                        <span class="cm">// useState import</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Counter() {                     <span class="cm">// Client Component</span>
  <span class="kw">const</span> [count, setCount] = useState(0)             <span class="cm">// Counter ki state</span>

  <span class="kw">return</span> (                                                  <span class="cm">// UI return</span>
    &lt;button onClick={() =&gt; setCount(count + 1)}&gt;    <span class="cm">// Click par count increase</span>
      {count}                                               <span class="cm">// Current count show</span>
    &lt;/button&gt;                                               <span class="cm">// Button close</span>
  )                                                         <span class="cm">// Return close</span>
}                                                           <span class="cm">// Function close</span></code></pre></div></section><section><h2 id="fetching-data"><i>11</i>Fetching Data</h2><h3 id="server-components" class="lv3">Server Components</h3><p class="lv3">Server Components mein data fetch karne ke <b>2 common methods</b> hain:</p><div class="tw lv3"><table><tr><th><b>Method</b></th><th><b>Definition</b></th><th><b>Example</b></th></tr><tr><td>fetch API</td><td>API se data request karke fetch karne ke liye use hota hai.</td><td>fetch('https://api.example.com/posts')</td></tr><tr><td>ORM / Database</td><td>Direct database se data read/write karne ke liye ORM ya database client use kar sakte ho.</td><td>const posts = await db.post.findMany()</td></tr></table></div><h3 id="1-fetch-api-example" class="lv3">1. fetch API example</h3><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">default</span> <span class="kw">async</span> <span class="kw">function</span> Page() {                  <span class="cm">// Server Component</span>
  <span class="kw">const</span> res = <span class="kw">await</span> fetch(<span class="st">'https://api.example.com/posts'</span>)  <span class="cm">// API se data fetch</span>
  <span class="kw">const</span> posts = <span class="kw">await</span> res.json()                            <span class="cm">// Response ko JSON mein convert</span>
  <span class="kw">return</span> &lt;h1&gt;{posts[0].title}&lt;/h1&gt;                              <span class="cm">// First post ka title show</span>
}
                            <span class="cm">// Function close</span></code></pre></div><h3 id="2-orm-database-example" class="lv3">2. ORM / Database example</h3><p class="lv3">ORM (Object-Relational Mapping) → ek tool/library jo tumhare database ke saath JavaScript/TypeScript code ke through easily interact karne deta hai, bina har baar raw SQL likhne ke.</p><div class="cb lv3"><pre><code><span class="kw">const</span> posts = <span class="kw">await</span> db.post.findMany()      <span class="cm">// Database se saare posts lao</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">async</span> <span class="kw">function</span> Page() {              <span class="cm">// Server Component</span>
  <span class="kw">const</span> posts = <span class="kw">await</span> db.post.findMany()            <span class="cm">// Database se posts fetch</span>
  <span class="kw">return</span> &lt;h1&gt;{posts[0].title}&lt;/h1&gt;                          <span class="cm">// First post ka title show</span>
}                                                               <span class="cm">// Function close</span></code></pre></div><h3 id="streaming" class="lv3">Streaming</h3><p class="lv3"><b>Server page ke different parts ko ek saath wait karne ke bajaye, jo part ready ho usko pehle client ko bhejta hai.</b></p><p class="lv3">Iske 2 main methods hain:</p><p class="lv3"><b>loading.tsx</b> → poori route/page ke liye loading UI</p><div class="cb lv3"><pre><code>
<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Loading() {             <span class="cm">// Loading component</span>
  <span class="kw">return</span> &lt;div&gt;Loading...&lt;/div&gt;                  <span class="cm">// Loading UI show</span>
}

&lt;Suspense&gt; → page ke specific part ke liye loading UI

<span class="kw">import</span> { Suspense } <span class="kw">from</span> <span class="st">'react'</span>                 <span class="cm">// Suspense import</span>
<span class="kw">import</span> BlogList <span class="kw">from</span> <span class="st">'@/components/BlogList'</span>    <span class="cm">// BlogList component import</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> BlogPage() {            <span class="cm">// Blog page component</span>
  <span class="kw">return</span> (                                              <span class="cm">// UI return</span>
    &lt;div&gt;                                               <span class="cm">// Page container</span>
      &lt;h1&gt;Welcome to the Blog&lt;/h1&gt;                  <span class="cm">// Ye immediately show hoga</span>

      &lt;Suspense fallback={&lt;div&gt;Loading...&lt;/div&gt;}&gt;   <span class="cm">// BlogList ke liye loading UI</span>
        &lt;BlogList /&gt;                                    <span class="cm">// Slow/dynamic blog list</span>
      &lt;/Suspense&gt;                                       <span class="cm">// Suspense close</span>
    &lt;/div&gt;                                              <span class="cm">// Container close</span>
  )                                                         <span class="cm">// Return close</span>
}                                                           <span class="cm">// Function close</span></code></pre></div></section><section><h2 id="mutating-data"><i>12</i>Mutating Data</h2><p class="lv2">Is section mein Next.js batata hai ke <b>database/data ko create, update ya delete</b> kaise karte hain. Source ke mutabiq Server Functions is ka main method hain.</p><div class="cb lv2"><pre><code><span class="st">'use server'</span>                                            <span class="cm">// Server Function banata hai</span>
<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> createPost(formData: FormData) {  <span class="cm">// Server Function</span>
  <span class="kw">const</span> title = formData.get(<span class="st">'title'</span>)                   <span class="cm">// Form se title get</span>
  <span class="kw">const</span> content = formData.get(<span class="st">'content'</span>)           <span class="cm">// Form se content get</span>
  <span class="cm">// Database mein post create karo                 // Yahan data mutate hoga</span>
}                                                           <span class="cm">// Function close</span></code></pre></div><h3 id="server-function-ko-invoke-karne-ke-2-mai" class="lv3">Server Function ko invoke karne ke 2 main ways</h3><div class="tw lv3"><table><tr><th><b>Method</b></th><th><b>Simple meaning</b></th><th><b>Example</b></th></tr><tr><td>Forms</td><td>Form submit hone par Server Function call hoti hai.</td><td>&lt;form action={createPost}&gt;</td></tr><tr><td>Event Handlers</td><td>Client Component mein event, jaise click, se Server Function call kar sakte ho.</td><td>onClick={() =&gt; createPost()}</td></tr></table></div><h3 id="1-server-file" class="lv3">1. Server file</h3><div class="cb lv3"><div class="fn">app/actions.ts</div><pre><code><span class="st">'use server'</span>                                    <span class="cm">// Is file ke exports server par run honge</span>
<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> createPost() {        <span class="cm">// Server Function</span>
  <span class="cm">// ...                                            // Data mutation</span>
}                                                   <span class="cm">// Function close</span></code></pre></div><h3 id="2-client-file" class="lv3">2. Client file</h3><div class="cb lv3"><pre><code><span class="st">'use client'</span>                                        <span class="cm">// Client Component</span>
<span class="kw">import</span> { createPost } <span class="kw">from</span> <span class="st">'@/app/actions'</span>  <span class="cm">// Server Function import</span>

<span class="kw">export</span> <span class="kw">function</span> Button() {                      <span class="cm">// Client Component</span>
  <span class="kw">return</span> &lt;button formAction={createPost}&gt;Create&lt;/button&gt; <span class="cm">// Server Function call</span>
}                                                       <span class="cm">// Function close</span></code></pre></div><h3 id="form-example" class="lv3">Form Example</h3><div class="cb lv3"><pre><code><span class="kw">import</span> { createPost } <span class="kw">from</span> <span class="st">'@/app/actions'</span>          <span class="cm">// Server Function import</span>

<span class="kw">export</span> <span class="kw">function</span> Form() {                            <span class="cm">// Form component</span>
  <span class="kw">return</span> (                                                  <span class="cm">// UI return</span>
    &lt;form action={createPost}&gt;                          <span class="cm">// Submit par Server Function call</span>
      &lt;input <span class="kw">type</span>=<span class="st">"text"</span> name=<span class="st">"title"</span> /&gt;            <span class="cm">// Title input</span>
      &lt;input <span class="kw">type</span>=<span class="st">"text"</span> name=<span class="st">"content"</span> /&gt;          <span class="cm">// Content input</span>
      &lt;button <span class="kw">type</span>=<span class="st">"submit"</span>&gt;Create&lt;/button&gt;     <span class="cm">// Form submit button</span>
    &lt;/form&gt;                                                 <span class="cm">// Form close</span>
  )                                                         <span class="cm">// Return close</span>
}</code></pre></div><h4 id="server-function" class="lv4">Server Function:</h4><div class="cb lv4"><pre><code><span class="st">'use server'</span>                                                <span class="cm">// Server Function</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> createPost(formData: FormData) {  <span class="cm">// Form data receive</span>
  <span class="kw">const</span> title = formData.get(<span class="st">'title'</span>)                   <span class="cm">// Title get</span>
  <span class="kw">const</span> content = formData.get(<span class="st">'content'</span>)               <span class="cm">// Content get</span>
  <span class="cm">// Database mein post create karo                      // Data mutate</span>
}</code></pre></div><h3 id="event-handler-example" class="lv3">Event Handler Example</h3><p class="lv3">Client Component mein onClick ke through bhi Server Function invoke kar sakte ho.</p><div class="cb lv3"><pre><code><span class="st">'use client'</span>                                                <span class="cm">// Client Component</span>

<span class="kw">import</span> { incrementLike } <span class="kw">from</span> <span class="st">'./actions'</span>               <span class="cm">// Server Function import</span>
<span class="kw">import</span> { useState } <span class="kw">from</span> <span class="st">'react'</span>                        <span class="cm">// useState import</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> LikeButton({ initialLikes }: { initialLikes: number }) { <span class="cm">// Component</span>
  <span class="kw">const</span> [likes, setLikes] = useState(initialLikes)      <span class="cm">// Likes state</span>

  <span class="kw">return</span> (                                                  <span class="cm">// UI return</span>
    &lt;&gt;                                                      <span class="cm">// Fragment start</span>
      &lt;p&gt;Total Likes: {likes}&lt;/p&gt;                       <span class="cm">// Current likes show</span>

      &lt;button                                                   <span class="cm">// Button start</span>
        onClick={<span class="kw">async</span> () =&gt; {                              <span class="cm">// Click par function</span>
          <span class="kw">const</span> updatedLikes = <span class="kw">await</span> incrementLike()        <span class="cm">// Server Function call</span></code></pre></div><p class="lv3">setLikes(updatedLikes)               			// New likes set</p><div class="cb lv3"><pre><code>        }}                                                      <span class="cm">// onClick close</span></code></pre></div><p class="lv3">&gt;                                         				// Button content start</p><p class="lv3">Like                                    				// Button text</p><div class="cb lv3"><pre><code>      &lt;/button&gt;                                                 <span class="cm">// Button close</span>
    &lt;/&gt;                                                         <span class="cm">// Fragment close</span>
  )                                                             <span class="cm">// Return close</span>
}                                                               <span class="cm">// Function close</span></code></pre></div><h3 id="pending-state" class="lv3">Pending State</h3><p class="lv3">Server Function execute hone mein time lag sakta hai. useActionState se pata chal sakta hai ke action pending hai ya nahi.</p><div class="cb lv3"><pre><code><span class="st">'use client'</span>                                                <span class="cm">// Client Component</span>

<span class="kw">import</span> { useActionState, startTransition } <span class="kw">from</span> <span class="st">'react'</span>     <span class="cm">// React APIs</span>
<span class="kw">import</span> { createPost } <span class="kw">from</span> <span class="st">'@/app/actions'</span>          <span class="cm">// Server Function</span>

<span class="kw">export</span> <span class="kw">function</span> Button() {                              <span class="cm">// Button component</span>
  <span class="kw">const</span> [state, action, pending] = useActionState(createPost, false) <span class="cm">// Action state</span>

  <span class="kw">return</span> (                                                      <span class="cm">// UI return</span>
    &lt;button onClick={() =&gt; startTransition(action)}&gt;        <span class="cm">// Action start</span>
      {pending ? <span class="st">'Creating...'</span> : <span class="st">'Create Post'</span>}             <span class="cm">// Pending ke hisaab se text</span>
    &lt;/button&gt;                                                   <span class="cm">// Button close</span>
  )                                                             <span class="cm">// Return close</span>
}                                                               <span class="cm">// Function close</span></code></pre></div><p class="lv3">pending = true → Server Function chal rahi hai.</p><p class="lv3">pending = false → Server Function complete/idle hai.</p><h3 id="mutation-ke-baad-data-refresh" class="lv3">Mutation ke baad data refresh</h3><p class="lv3">Agar data update karne ke baad current page par latest data dikhana ho, refresh() use kar sakte ho.</p><div class="cb lv3"><pre><code><span class="st">'use server'</span>                                                <span class="cm">// Server Function</span>

<span class="kw">import</span> { refresh } <span class="kw">from</span> <span class="st">'next/cache'</span>                    <span class="cm">// refresh import</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> updatePost() {                    <span class="cm">// Update function</span>
  <span class="cm">// Database mein data update karo                     // Mutation</span></code></pre></div><p class="lv3">refresh()                                    				// Current UI refresh</p><div class="cb lv3"><pre><code>}                                                           <span class="cm">// Function close</span></code></pre></div><p class="lv3">refresh() → Client Router ko refresh karta hai taake UI latest state show kare.</p><h3 id="revalidate-data" class="lv3">Revalidate Data</h3><p class="lv3">Mutation ke baad Next.js cache ko update karna ho to:</p><ul class="lv3"><li><code>revalidatePath()</code> → specific route/path ki cached data revalidate.</li><li><code>revalidateTag()</code> → specific cache tag ki data revalidate.</li></ul><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="st">'use server'</span>                                            <span class="cm">// Server Function</span>

<span class="kw">import</span> { revalidatePath } <span class="kw">from</span> <span class="st">'next/cache'</span>         <span class="cm">// revalidatePath import</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> createPost() {                    <span class="cm">// Create function</span>
  <span class="cm">// Database mein post create karo                     // Mutation</span></code></pre></div><p class="lv3">revalidatePath('/posts')                     		// /posts ki data revalidate</p><div class="cb lv3"><pre><code>}                                                       <span class="cm">// Function close</span></code></pre></div><h3 id="redirect-after-mutation" class="lv3">Redirect after Mutation</h3><p class="lv3">Mutation complete hone ke baad user ko doosre page par bhejna ho to redirect() use kar sakte ho.</p><div class="cb lv3"><pre><code><span class="st">'use server'</span>                                            <span class="cm">// Server Function</span>

<span class="kw">import</span> { redirect } <span class="kw">from</span> <span class="st">'next/navigation'</span>          <span class="cm">// redirect import</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> createPost() {                <span class="cm">// Create function</span>
  <span class="cm">// Database mein post create karo                     // Mutation</span></code></pre></div><p class="lv3">redirect('/posts')                           			// User ko /posts par bhejo</p><div class="cb lv3"><pre><code>}                                                       <span class="cm">// Function close</span></code></pre></div><p class="lv3 box warn">Important: redirect() ke baad wali code execute nahi hoti.</p><h3 id="cookies" class="lv3">Cookies</h3><p class="lv3">Server Action ke andar cookies ko:</p><div class="cb lv3"><pre><code>get → read
set → create/update
delete → remove</code></pre></div><p class="lv3">kar sakte ho.</p><div class="cb lv3"><pre><code><span class="st">'use server'</span>                                                <span class="cm">// Server Function</span>

<span class="kw">import</span> { cookies } <span class="kw">from</span> <span class="st">'next/headers'</span>                  <span class="cm">// Cookies API import</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> exampleAction() {             <span class="cm">// Server Function</span>
  <span class="kw">const</span> cookieStore = <span class="kw">await</span> cookies()                   <span class="cm">// Cookies access</span></code></pre></div><p class="lv3">cookieStore.get('name')?.value               			// Cookie read</p><p class="lv3">cookieStore.set('name', 'Delba')             			// Cookie set</p><p class="lv3">cookieStore.delete('name')                  			// Cookie delete</p><div class="cb lv3"><pre><code>}                               <span class="cm">// Function close</span></code></pre></div><h3 id="sabse-important-concept" class="lv3">Sabse important concept:</h3><ul class="lv3"><li>Fetching Data → data lana</li><li>Mutating Data → data create/update/delete karna</li><li>Server Function → server par mutation ka kaam karne wali async function</li><li>Server Action → form/mutation ke liye use ki jane wali Server Function</li><li>'use server' → function/file ko server-side banata hai</li><li>refresh() → current UI ko latest state ke saath refresh</li><li>revalidatePath() → specific path ki cached data revalidate</li><li>redirect() → mutation ke baad user ko doosre route par bhejna.</li></ul></section><section><h2 id="caching"><i>13</i>Caching</h2><p class="lv2"><b>Definition:</b> Kisi data/result ko save karna taake next time same kaam dobara na karna pade aur response fast ho.</p><p class="lv2"><b>Example:</b></p><div class="cb lv2"><pre><code>First request
   ↓
Database → Data → Cache

Next request
   ↓
Cache → Data</code></pre></div><p class="lv2 box tip">Yani database ka same kaam baar baar nahi karna.</p><h3 id="cache-components" class="lv3">Cache Components</h3><p class="lv3"><b>Definition:</b> Next.js ka caching system jo caching aur prerendering ko control karta hai.</p><p class="lv3">Isko enable karne ke liye:</p><div class="cb lv3"><pre><code><span class="kw">const</span> nextConfig = {</code></pre></div><p class="lv3">cacheComponents: true,</p><div class="cb lv3"><pre><code>}</code></pre></div><p class="lv3">Simple matlab:</p><div class="cb lv3"><pre><code>cacheComponents: true
        ↓
Cache Components ON</code></pre></div><h3 id="use-cache" class="lv3">use cache</h3><p class="lv3"><b>Definition:</b> Kisi async function ya component ke <b>result ko cache</b> karne ka main Next.js directive.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">async</span> <span class="kw">function</span> getUsers() {
  <span class="st">'use cache'</span>

  <span class="kw">return</span> db.query(<span class="st">'SELECT * FROM users'</span>)
}</code></pre></div><p class="lv3">Yahan:</p><div class="cb lv3"><pre><code>getUsers()
   ↓
Database
   ↓
Result
   ↓
Cache</code></pre></div><p class="lv3">Next time same cached result available ho sakta hai.</p><h3 id="data-level-caching" class="lv3">Data-level caching</h3><p class="lv3"><b>Definition:</b> Sirf <b>data fetch karne wale function</b> ko cache karna.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">async</span> <span class="kw">function</span> getUsers() {
  <span class="st">'use cache'</span>

  <span class="kw">return</span> db.query(<span class="st">'SELECT * FROM users'</span>)
}</code></pre></div><p class="lv3">Yahan <code>getUsers()</code> cached hai, <b>poora page nahi</b>.</p><h3 id="ui-level-caching" class="lv3">UI-level caching</h3><p class="lv3"><b>Definition:</b> Pura <b>component/page/layout ka result</b> cache karna.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">default</span> <span class="kw">async</span> <span class="kw">function</span> Page() {
  <span class="st">'use cache'</span>

  <span class="kw">const</span> users = <span class="kw">await</span> db.query(<span class="st">'SELECT * FROM users'</span>)

  <span class="kw">return</span> &lt;h1&gt;{users[0].name}&lt;/h1&gt;
}</code></pre></div><p class="lv3">Yahan poora <code>Page</code> cache ho raha hai.</p><h3 id="cachelife" class="lv3">cacheLife</h3><p class="lv3"><b>Definition:</b> Cache ko <b>kitni der tak fresh rakhna hai</b>, ye define karta hai.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="st">'use cache'</span></code></pre></div><p class="lv3">cacheLife('hours')</p><p class="lv3">Simple:</p><div class="cb lv3"><pre><code>Cache banao
   ↓
Kitni der valid?
   ↓
cacheLife()</code></pre></div><p class="lv3">Next.js docs <code>use cache</code> ke saath <code>cacheLife</code> use karne recommend karti hain.</p><h3 id="cache-key" class="lv3">Cache Key</h3><p class="lv3"><b>Definition:</b> Cache mein result ko identify karne wali value. Different input → different cache entry.</p><p class="lv3">Example:</p><p class="lv3">getUser(1)</p><p class="lv3">getUser(2)</p><p class="lv3">Yahan <code>1</code> aur <code>2</code> different inputs hain, isliye dono ke cached results separate ho sakte hain.</p><h3 id="uncached-data" class="lv3">Uncached Data</h3><p class="lv3"><b>Definition:</b> Aisa data jo har request par fresh chahiye, isliye usko <code>use cache</code> nahi karte.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">async</span> <span class="kw">function</span> LatestPosts() {
  <span class="kw">const</span> data = <span class="kw">await</span> fetch(<span class="st">'https://api.example.com/posts'</span>)

  <span class="kw">return</span> data
}</code></pre></div><p class="lv3">Agar fresh data chahiye:</p><div class="cb lv3"><pre><code>Request
  ↓
Fresh API data</code></pre></div><p class="lv3">Cache nahi.</p><h3 id="cache-vs-uncached-data" class="lv3">Cache vs Uncached Data</h3><p class="lv3">Ye <b>Caching chapter ka sabse important concept</b> hai:</p><div class="cb lv3"><pre><code>Data same/reusable hai?
        ↓
       YES
        ↓
    use cache</code></pre></div><p class="lv3">Aur:</p><div class="cb lv3"><pre><code>Data har request fresh chahiye?
        ↓
       YES
        ↓
   Don't use cache</code></pre></div><p class="lv3">Yahi basic decision tumhein sabse pehle samajhna hai.</p><h3 id="use-cache-private" class="lv3">use cache: private</h3><p class="lv3"><b>Definition:</b> Aisa cached data jo <b>user/request specific</b> ho, jaise cookies ya search parameters se related data.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">async</span> <span class="kw">function</span> UserData() {
  <span class="st">'use cache: private'</span>

  <span class="cm">// user-specific data</span>
}</code></pre></div><p class="lv3">Simple:</p><div class="cb lv3"><pre><code>User A → apna cached data
User B → apna cached data</code></pre></div><h3 id="use-cache-remote" class="lv3">use cache: remote</h3><p class="lv3"><b>Definition:</b> Cache ko <b>durable shared remote storage</b> mein rakhne ka tareeqa.</p><p class="lv3">Simple:</p><div class="cb lv3"><pre><code>Server A ─┐
Server B ─┼──→ Remote Cache
Server C ─┘</code></pre></div><p class="lv3 box tip">Yani multiple server instances same remote cache use kar sakte hain.</p><h3 id="cache-storage" class="lv3">Cache Storage</h3><p class="lv3"><b>Definition:</b> Cached result ko Next.js different places par store kar sakta hai.</p><p class="lv3">Main 3 jagah docs mein hain:</p><p class="lv3">1. Prerendered HTML</p><p class="lv3">2. Shared Store</p><p class="lv3">3. Browser</p></section><section><h2 id="revalidation-kya-hai"><i>14</i>Revalidation kya hai?</h2><p class="lv2"><b>Revalidation = cached data ko dobara fresh/update karna.</b></p><p class="lv2">Caching mein hum data save karte hain taake next request fast ho. Lekin agar database mein data change ho jaye, purana cached data aa sakta hai.</p><p class="lv2">Revalidation ka kaam:</p><div class="cb lv2"><pre><code>Cache mein old data
       ↓
Revalidation
       ↓
Fresh data</code></pre></div><p class="lv2">Next.js ke is section mein <b>2 main ways</b> hain:</p><ul class="lv2"><li><b>Time-based revalidation</b> → fixed time ke baad cache refresh.</li><li><b>On-demand revalidation</b> → jab data change ho, manually cache invalidate/refresh.</li></ul><h3 id="cachelife-2" class="lv3">cacheLife</h3><p class="lv3"><b><code>cacheLife</code></b><b> = cache ko batata hai ke cached data kitni der tak valid/revalidate hona chahiye.</b></p><p class="lv3">Ye <code>use cache</code> ke andar use hota hai.</p><div class="cb lv3"><pre><code><span class="kw">import</span> { cacheLife } <span class="kw">from</span> <span class="st">'next/cache'</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> getProducts() {
  <span class="st">'use cache'</span></code></pre></div><p class="lv3">cacheLife('hours')</p><div class="cb lv3"><pre><code>  <span class="kw">return</span> db.query(<span class="st">'SELECT * FROM products'</span>)
}</code></pre></div><p class="lv3">Simple execution:</p><ul class="lv3"><li><code>'use cache'</code> → is function ka result cache karo.</li><li><code>cacheLife('hours')</code> → cache ke liye <code>hours</code> profile use karo.</li><li>Database se products aayenge.</li><li>Same cached result ko defined lifetime ke according use kiya jayega.</li></ul><h3 id="built-in-profiles" class="lv3">Built-in profiles</h3><div class="tw lv3"><table><tr><th><b>Profile</b></th><th><b><code>stale</code></b></th><th><b><code>revalidate</code></b></th><th><b><code>expire</code></b></th></tr><tr><td><code>seconds</code></td><td>30s</td><td>1s</td><td>60s</td></tr><tr><td><code>minutes</code></td><td>5m</td><td>1m</td><td>1h</td></tr><tr><td><code>hours</code></td><td>5m</td><td>1h</td><td>1d</td></tr><tr><td><code>days</code></td><td>5m</td><td>1d</td><td>1w</td></tr><tr><td><code>weeks</code></td><td>5m</td><td>1w</td><td>30d</td></tr><tr><td><code>max</code></td><td>5m</td><td>30d</td><td>1y</td></tr></table></div><p class="lv3">Source ke mutabiq <code>default</code> profile bhi available hai: <code>5m / 15m / never</code>.</p><h3 id="stale-revalidate-expire-teenon-ka-basic-" class="lv3">stale, revalidate, expire — teenon ka basic difference</h3><p class="lv3">Ye <code>cacheLife</code> ke andar cache ki lifetime define karte hain.</p><div class="cb lv3"><pre><code><span class="st">'use cache'</span>

cacheLife({</code></pre></div><p class="lv3">stale: 3600,</p><p class="lv3">revalidate: 7200,</p><p class="lv3">expire: 86400,</p><div class="cb lv3"><pre><code>})</code></pre></div><ul class="lv3"><li><code>stale</code> → <b>1 hour</b> ke baad cached result stale maana jata hai.</li><li><code>revalidate</code> → <b>2 hours</b> ke baad revalidation interval.</li><li><code>expire</code> → <b>1 day</b> ke baad cache expire.</li></ul><p class="lv3">Source mein ye values isi example ke mutabiq di gayi hain.</p><p class="lv3"><b>Beginner ke liye abhi important:</b> <code>cacheLife('hours')</code> jaise ready-made profile use karna easy hai. Custom object tab use karte hain jab exact timing control chahiye.</p><h3 id="cachetag" class="lv3">cacheTag</h3><p class="lv3"><b><code>cacheTag</code></b><b> = cached data ko ek naam/tag dena, taake baad mein us specific cache ko manually invalidate kar saken.</b></p><div class="cb lv3"><pre><code><span class="kw">import</span> { cacheTag } <span class="kw">from</span> <span class="st">'next/cache'</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> getProducts() {
  <span class="st">'use cache'</span></code></pre></div><p class="lv3">cacheTag('products')</p><div class="cb lv3"><pre><code>  <span class="kw">return</span> db.query(<span class="st">'SELECT * FROM products'</span>)
}</code></pre></div><p class="lv3">Yahan:</p><div class="cb lv3"><pre><code>cached products
      ↓
tag = <span class="st">"products"</span></code></pre></div><p class="lv3">Ab hum <code>"products"</code> tag ko use karke is cache ko revalidate kar sakte hain.</p><p class="lv3"><code>cacheTag</code> khud cache ko refresh nahi karta. <b>Ye sirf cache ko tag karta hai.</b></p><h3 id="revalidatetag" class="lv3">revalidateTag</h3><p class="lv3"><b><code>revalidateTag</code></b><b> = kisi tag se connected cached data ko invalidate/revalidate karna.</b></p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">import</span> { revalidateTag } <span class="kw">from</span> <span class="st">'next/cache'</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> updateUser(id: string) {
  <span class="cm">// Database mein user update karo</span></code></pre></div><p class="lv3">revalidateTag('user', 'max')</p><div class="cb lv3"><pre><code>}</code></pre></div><p class="lv3">Agar multiple cached functions ke paas same tag ho:</p><div class="cb lv3"><pre><code>Function A → tag <span class="st">"user"</span>
Function B → tag <span class="st">"user"</span>
Function C → tag <span class="st">"user"</span>

             ↓
      revalidateTag(<span class="st">"user"</span>)

             ↓

A, B, C ke related cache entries</code></pre></div><p class="lv3">revalidation ke liye invalidate</p><p class="lv3 box warn">Important behavior:</p><p class="lv3"><b><code>revalidateTag</code></b><b> stale-while-revalidate use karta hai.</b></p><p class="lv3">Matlab old/stale content temporarily serve ho sakta hai aur fresh content background mein generate hota hai.</p><h4 id="simple-real-example" class="lv4">Simple real example</h4><p class="lv4">Suppose website par:</p><p class="lv4">Products cache = old products</p><p class="lv4">Admin ne database mein product update kiya:</p><p class="lv4">Database</p><div class="cb lv4"><pre><code><span class="st">"iPhone 17"</span> → <span class="st">"iPhone 17 Pro"</span></code></pre></div><p class="lv4">Phir:</p><p class="lv4">revalidateTag('products', 'max')</p><p class="lv4">Next.js ko pata chalta hai:</p><p class="lv4"><code>"products"</code> wali cached information ko revalidation chahiye.</p><h3 id="updatetag" class="lv3">updateTag</h3><p class="lv3"><b><code>updateTag</code></b><b> = cache ko immediately expire kar deta hai, taake user apni ki hui change ko immediately dekh sake.</b></p><p class="lv3">Ye particularly <b>read-your-own-writes</b> situation ke liye hai.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">import</span> { updateTag } <span class="kw">from</span> <span class="st">'next/cache'</span>
<span class="kw">import</span> { redirect } <span class="kw">from</span> <span class="st">'next/navigation'</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> createPost(formData: FormData) {
  <span class="kw">const</span> post = <span class="kw">await</span> db.post.create({
    data: {</code></pre></div><p class="lv3">title: formData.get('title'),</p><p class="lv3">content: formData.get('content'),</p><div class="cb lv3"><pre><code>    },
  })</code></pre></div><p class="lv3">updateTag('posts')</p><p class="lv3">redirect(`/posts/${post.id}`)</p><div class="cb lv3"><pre><code>}</code></pre></div><p class="lv3">Flow:</p><div class="cb lv3"><pre><code>User post create karta hai
        ↓
Database mein post create
        ↓
updateTag(<span class="st">'posts'</span>)
        ↓
<span class="st">"posts"</span> cache immediately expire
        ↓
User ko fresh data milta hai</code></pre></div><p class="lv3"><code>updateTag</code> <b>sirf Server Actions</b> mein use ho sakta hai.</p><h3 id="revalidatetag-vs-updatetag" class="lv3">revalidateTag vs updateTag</h3><p class="lv3">Ye difference <b>bohat important</b> hai:</p><div class="tw lv3"><table><tr><th></th><th><b><code>updateTag</code></b></th><th><b><code>revalidateTag</code></b></th></tr><tr><td>Cache</td><td>Immediately expire</td><td>Stale-while-revalidate</td></tr><tr><td>User ko stale data mil sakta hai?</td><td>nahi</td><td>Haan</td></tr><tr><td>Server Action</td><td>✅</td><td>✅</td></tr><tr><td>Route Handler</td><td>❌</td><td>✅</td></tr><tr><td>Main use</td><td>User ko apni change immediately dikhani</td><td>Background refresh</td></tr></table></div><p class="lv3">Source explicitly isi distinction ko deta hai.</p><p class="lv3 box tip"><b>Easy memory trick:</b></p><div class="cb lv3"><pre><code>updateTag
   ↓
<span class="st">"meri change abhi dikhao"</span>

revalidateTag
   ↓
<span class="st">"background mein fresh kar do"</span></code></pre></div><h3 id="revalidatepath" class="lv3">revalidatePath</h3><p class="lv3"><b><code>revalidatePath</code></b><b> = specific URL/route ke cached data ko invalidate karna.</b></p><div class="cb lv3"><pre><code><span class="kw">import</span> { revalidatePath } <span class="kw">from</span> <span class="st">'next/cache'</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> updateUser(id: string) {
  <span class="cm">// Database mein user update karo</span></code></pre></div><p class="lv3">revalidatePath('/profile')</p><div class="cb lv3"><pre><code>}</code></pre></div><p class="lv3">Yahan:</p><div class="cb lv3"><pre><code>/profile
   ↓
us route ka cached data invalidate</code></pre></div><p class="lv3">Iska difference <code>revalidateTag</code> se:</p><div class="cb lv3"><pre><code>revalidateTag(<span class="st">'products'</span>)
        ↓
specific TAG se connected cache

revalidatePath(<span class="st">'/products'</span>)
        ↓
specific PATH/route ka cache</code></pre></div><p class="lv3">Source ke mutabiq jab tags ka pata na ho aur route ko revalidate karna ho, <code>revalidatePath</code> use kar sakte hain. Tag-based revalidation possible ho to docs usay prefer karte hain because it is more precise.</p><h3 id="time-based-vs-on-demand-revalidation" class="lv3">Time-based vs On-demand Revalidation</h3><p class="lv3">Ab poori picture:</p><h4 id="time-based" class="lv4">Time-based</h4><div class="cb lv4"><pre><code>use cache
   ↓
cacheLife(<span class="st">'hours'</span>)
   ↓
time pass hota hai
   ↓
cache revalidate</code></pre></div><p class="lv4">Yahan <b>time</b> decide karta hai ke cache kab refresh hoga.</p><h4 id="on-demand" class="lv4">On-demand</h4><div class="cb lv4"><pre><code>use cache
   ↓
cacheTag(<span class="st">'products'</span>)
   ↓
database mein change
   ↓
revalidateTag(<span class="st">'products'</span>)
   ↓
cache revalidate</code></pre></div><p class="lv4">Yahan <b>aapka code</b> decide karta hai ke cache kab invalidate/revalidate hoga.</p><h3 id="cachetag-revalidatetag-ka-relation" class="lv3">cacheTag + revalidateTag ka relation</h3><p class="lv3">Inko pair ki tarah yaad karo:</p><div class="cb lv3"><pre><code>cacheTag
   ↓
<span class="st">"Is cache ko products naam do"</span>

revalidateTag
   ↓
<span class="st">"products naam wale cache ko revalidate karo"</span></code></pre></div><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="cm">// Data ko cache + tag karo</span>
<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> getProducts() {
  <span class="st">'use cache'</span></code></pre></div><p class="lv3">cacheTag('products')</p><div class="cb lv3"><pre><code>  <span class="kw">return</span> db.query(<span class="st">'SELECT * FROM products'</span>)
}</code></pre></div><p class="lv3">Aur mutation ke baad:</p><div class="cb lv3"><pre><code><span class="cm">// Products cache ko revalidate karo</span></code></pre></div><p class="lv3">revalidateTag('products', 'max')</p><h3 id="what-should-i-cache" class="lv3">What should I cache?</h3><p class="lv3">Source ka basic rule:</p><p class="lv3"><b>Aisa data cache karo jo runtime/request-specific data par depend nahi karta aur jise kuch time tak cached form mein serve karna acceptable hai.</b></p><p class="lv3">Typical pattern:</p><div class="cb lv3"><pre><code><span class="st">'use cache'</span></code></pre></div><p class="lv3">cacheLife('hours')</p><p class="lv3">Agar CMS content hai aur har kuch minutes mein check karna unnecessary hai, source suggest karta hai:</p><p class="lv3">use cache</p><p class="lv3">+</p><p class="lv3">cacheTag</p><p class="lv3">+</p><p class="lv3">long cacheLife</p><p class="lv3">+</p><p class="lv3">content change hone par revalidateTag</p><p class="lv3">Example concept:</p><div class="cb lv3"><pre><code>CMS content
    ↓
cacheTag(<span class="st">'posts'</span>)</code></pre></div><p class="lv3">+</p><div class="cb lv3"><pre><code>cacheLife(<span class="st">'max'</span>)
    ↓
long-lived cache
    ↓
CMS mein actual change
    ↓
CMS webhook
    ↓
revalidateTag(<span class="st">'posts'</span>)
    ↓
fresh content</code></pre></div><p class="lv3">Isse har fixed interval par unnecessary revalidation karne ke bajaye <b>sirf content change hone par cache update</b> kiya ja sakta hai.</p><h3 id="sab-ko-ek-line-mein-yaad-karo" class="lv3">Sab ko ek line mein yaad karo</h3><div class="cb lv3"><pre><code>cacheLife      → <span class="st">"kitni der cache rakhna hai?"</span></code></pre></div><p class="lv3">cacheTag       → "cache ko kis naam/tag se identify karna hai?"</p><div class="cb lv3"><pre><code>revalidateTag  → <span class="st">"is tag ka cache revalidate karo"</span>
updateTag      → <span class="st">"is tag ka cache immediately expire karo"</span>
revalidatePath → <span class="st">"is route ka cache revalidate karo"</span></code></pre></div><p class="lv3">Aur sabse important:</p><div class="cb lv3"><pre><code>Caching
  ↓
data fast serve hota hai

Revalidation
  ↓
cached data ko fresh rakhta hai</code></pre></div></section><section><h2 id="error-handling-kya-hai"><i>15</i>Error Handling kya hai?</h2><p class="lv2"><b>Error Handling = application mein error aane par usko properly handle karke user ko suitable response/UI dena.</b></p><p class="lv2">Next.js docs errors ko <b>2 main categories</b> mein divide karti hain:</p><p class="lv2">Errors</p><div class="cb lv2"><pre><code>├── Expected errors
└── Uncaught exceptions</code></pre></div><h3 id="expected-errors" class="lv3">Expected Errors</h3><p class="lv3"><b>Expected error = aisa error jo application ke normal operation mein aa sakta hai aur jiska possibility developer ko pata hota hai.</b></p><p class="lv3">Examples:</p><ul class="lv3"><li>form validation fail hona</li><li>API request fail hona</li><li>user ka invalid data submit karna</li></ul><p class="lv3">In errors ko normally <b>explicitly handle</b> kiya jata hai aur error ko return value ke through client tak diya jata hai.</p><p class="lv3">Source specifically kehta hai ke expected errors ke liye <code>try/catch</code> + <code>throw</code> ki bajaye error ko <b>return value</b> ke taur par model karo.</p><h4 id="example" class="lv4">Example</h4><p class="lv4">Server Function:</p><div class="cb lv4"><pre><code><span class="st">'use server'</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> createPost(prevState: any, formData: FormData) {
  <span class="kw">const</span> title = formData.get(<span class="st">'title'</span>)
  <span class="kw">const</span> content = formData.get(<span class="st">'content'</span>)

  <span class="kw">const</span> res = <span class="kw">await</span> fetch(<span class="st">'https://api.vercel.app/posts'</span>, {</code></pre></div><p class="lv4">method: 'POST',</p><div class="cb lv4"><pre><code>    body: { title, content },
  })

  <span class="kw">const</span> json = <span class="kw">await</span> res.json()

  <span class="kw">if</span> (!res.ok) {
    <span class="kw">return</span> { message: <span class="st">'Failed to create post'</span> }
  }
}</code></pre></div><p class="lv4">Yahan important idea:</p><div class="cb lv4"><pre><code>Request
   ↓
failed?
   ↓
<span class="kw">return</span> { message: <span class="st">'Failed...'</span> }
   ↓
Client error message show karta hai</code></pre></div><p class="lv4"><b>Error throw nahi hua; error ko normal returned data ki tarah handle kiya gaya.</b></p><h3 id="useactionstate" class="lv3">useActionState</h3><p class="lv3"><b><code>useActionState</code></b><b> = Server Function ke returned result/state ko receive karke UI mein show karne mein help karta hai.</b></p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="st">'use client'</span>

<span class="kw">import</span> { useActionState } <span class="kw">from</span> <span class="st">'react'</span>
<span class="kw">import</span> { createPost } <span class="kw">from</span> <span class="st">'@/app/actions'</span>

<span class="kw">const</span> initialState = {</code></pre></div><p class="lv3">message: '',</p><div class="cb lv3"><pre><code>}

<span class="kw">export</span> <span class="kw">function</span> Form() {
  <span class="kw">const</span> [state, formAction, pending] =</code></pre></div><p class="lv3">useActionState(createPost, initialState)</p><div class="cb lv3"><pre><code>  <span class="kw">return</span> (
    &lt;form action={formAction}&gt;
      &lt;input <span class="kw">type</span>=<span class="st">"text"</span> name=<span class="st">"title"</span> required /&gt;

      &lt;textarea name=<span class="st">"content"</span> required /&gt;

      {state?.message &amp;&amp; (
        &lt;p&gt;{state.message}&lt;/p&gt;
      )}

      &lt;button disabled={pending}&gt;</code></pre></div><p class="lv3">Create Post</p><div class="cb lv3"><pre><code>      &lt;/button&gt;
    &lt;/form&gt;
  )
}</code></pre></div><p class="lv3 box warn">Important:</p><div class="cb lv3"><pre><code>createPost()
    ↓
returns { message: <span class="st">"Failed..."</span> }
    ↓
useActionState
    ↓
state.message
    ↓
UI par error message</code></pre></div><p class="lv3">So expected form errors ke liye basic pattern:</p><div class="cb lv3"><pre><code>Server Function
      ↓
<span class="kw">return</span> error state
      ↓
useActionState
      ↓
show message</code></pre></div><h3 id="server-component-mein-expected-error" class="lv3">Server Component mein expected error</h3><p class="lv3">Agar Server Component mein data fetch fail ho jaye, to response check karke conditionally UI return kar sakte ho.</p><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">default</span> <span class="kw">async</span> <span class="kw">function</span> Page() {
  <span class="kw">const</span> res = <span class="kw">await</span> fetch(<span class="st">`https://...`</span>)
  <span class="kw">const</span> data = <span class="kw">await</span> res.json()

  <span class="kw">if</span> (!res.ok) {
    <span class="kw">return</span> <span class="st">'There was an error.'</span>
  }

  <span class="kw">return</span> <span class="st">'...'</span>
}</code></pre></div><p class="lv3">Yahan:</p><div class="cb lv3"><pre><code>fetch()
  ↓
response
  ↓
res.ok?
 ├── yes → normal UI
 └── no  → error UI</code></pre></div><p class="lv3">Docs ke mutabiq Server Component mein failed response par error message return ya <code>redirect</code> use kiya ja sakta hai.</p><h3 id="notfound" class="lv3">notFound()</h3><p class="lv3"><b><code>notFound()</code></b><b> = jab requested resource/page exist nahi karti, to 404 UI trigger karna.</b></p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">import</span> { notFound } <span class="kw">from</span> <span class="st">'next/navigation'</span>
<span class="kw">import</span> { getPostBySlug } <span class="kw">from</span> <span class="st">'@/lib/posts'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">async</span> <span class="kw">function</span> Page({</code></pre></div><p class="lv3">params,</p><div class="cb lv3"><pre><code>}: {</code></pre></div><p class="lv3">params: Promise&lt;{ slug: string }&gt;</p><div class="cb lv3"><pre><code>}) {
  <span class="kw">const</span> { slug } = <span class="kw">await</span> params
  <span class="kw">const</span> post = getPostBySlug(slug)

  <span class="kw">if</span> (!post) {</code></pre></div><p class="lv3">notFound()</p><div class="cb lv3"><pre><code>  }

  <span class="kw">return</span> &lt;div&gt;{post.title}&lt;/div&gt;
}</code></pre></div><p class="lv3">Agar post nahi mili:</p><div class="cb lv3"><pre><code>post = null
   ↓
!post = true
   ↓
notFound()
   ↓
404 UI</code></pre></div><p class="lv3">Aur route mein:</p><div class="cb lv3"><div class="fn">app/blog/[slug]/not-found.tsx</div><pre><code><span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> NotFound() {
  <span class="kw">return</span> &lt;div&gt;404 - Page Not Found&lt;/div&gt;
}</code></pre></div><p class="lv3 box warn"><b>Important:</b> <code>notFound()</code> normal error handling se thora different hai. Ye specifically <b>resource not found / 404 situation</b> ke liye hai.</p><h3 id="uncaught-exceptions" class="lv3">Uncaught Exceptions</h3><p class="lv3">Ab second major category:</p><p class="lv3"><b>Uncaught exception = unexpected error jo application ke normal flow mein nahi hona chahiye, usually bug ya unexpected problem.</b></p><p class="lv3">Example concept:</p><div class="cb lv3"><pre><code>Application running
      ↓
unexpected exception
      ↓
throw error
      ↓
Error Boundary
      ↓
Fallback UI</code></pre></div><p class="lv3">Yahan expected error ki tarah manually <code>{ message: ... }</code> return karna main pattern nahi hai.</p><h3 id="error-boundary" class="lv3">Error Boundary</h3><p class="lv3"><b>Error Boundary = aisa component jo child components ke rendering errors ko catch karke fallback UI show karta hai.</b></p><p class="lv3">Next.js mein route segment ke andar:</p><div class="cb lv3"><pre><code>app/dashboard/error.tsx</code></pre></div><p class="lv3">rakh sakte ho.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="st">'use client'</span>

<span class="kw">import</span> { useEffect } <span class="kw">from</span> <span class="st">'react'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> ErrorPage({</code></pre></div><p class="lv3">error,</p><p class="lv3">retry,</p><div class="cb lv3"><pre><code>}: {</code></pre></div><p class="lv3">error: Error &amp; { digest?: string }</p><div class="cb lv3"><pre><code>  retry: () =&gt; void
}) {
  useEffect(() =&gt; {</code></pre></div><p class="lv3">console.error(error)</p><div class="cb lv3"><pre><code>  }, [error])

  <span class="kw">return</span> (
    &lt;div&gt;
      &lt;h2&gt;Something went wrong!&lt;/h2&gt;

      &lt;button onClick={() =&gt; retry()}&gt;</code></pre></div><p class="lv3">Try again</p><div class="cb lv3"><pre><code>      &lt;/button&gt;
    &lt;/div&gt;
  )
}</code></pre></div><p class="lv3">Basic structure:</p><div class="cb lv3"><pre><code>Normal Component
      ↓
   ERROR!
      ↓
error.tsx
      ↓
Fallback UI</code></pre></div><p class="lv3">Source ke mutabiq <code>error.tsx</code> Error Boundary create karta hai aur ye <b>Client Component</b> hona zaroori hai.</p><h3 id="nested-error-boundaries" class="lv3">Nested Error Boundaries</h3><p class="lv3">Next.js mein <code>error.tsx</code> different route levels par ho sakti hai.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code>app/
├── error.tsx
├── dashboard/
│   ├── error.tsx
│   └── settings/
│       └── error.tsx</code></pre></div><p class="lv3">Agar <code>settings</code> mein error aaye:</p><div class="cb lv3"><pre><code>settings error
     ↓
nearest error boundary
     ↓
settings/error.tsx</code></pre></div><p class="lv3">Agar nearest boundary handle nahi karti, error parent boundary ki taraf bubble kar sakta hai.</p><p class="lv3"><b>Main idea:</b></p><p class="lv3">Error boundary ko route hierarchy mein different levels par rakh kar granular error handling ki ja sakti hai.</p><h3 id="retry" class="lv3">retry</h3><p class="lv3"><code>retry</code> error boundary ka function hai jo failed route segment ko recover/re-render karne ki attempt karta hai.</p><div class="cb lv3"><pre><code>&lt;button onClick={() =&gt; retry()}&gt;</code></pre></div><p class="lv3">Try again</p><div class="cb lv3"><pre><code>&lt;/button&gt;</code></pre></div><p class="lv3">Flow:</p><div class="cb lv3"><pre><code>Error
 ↓
Fallback UI
 ↓
User <span class="st">"Try again"</span>
 ↓
retry()
 ↓
segment ko dobara fetch/render karne ki attempt</code></pre></div><h3 id="component-level-error-boundary" class="lv3">Component-level Error Boundary</h3><p class="lv3">Normal <code>error.tsx</code> route segment level par hota hai.</p><p class="lv3">Agar tum <b>sirf kisi particular component tree</b> ke around error boundary chahte ho, source mein <code>catchError</code> diya gaya hai.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="st">'use client'</span>

<span class="kw">import</span> { catchError, <span class="kw">type</span> ErrorInfo } <span class="kw">from</span> <span class="st">'next/error'</span>

<span class="kw">function</span> ErrorFallback(
  props: { title: string },
  { error, retry }: ErrorInfo
) {
  <span class="kw">return</span> (
    &lt;div&gt;
      &lt;h2&gt;{props.title}&lt;/h2&gt;
      &lt;p&gt;{error.message}&lt;/p&gt;

      &lt;button onClick={() =&gt; retry()}&gt;</code></pre></div><p class="lv3">Try again</p><div class="cb lv3"><pre><code>      &lt;/button&gt;
    &lt;/div&gt;
  )
}

<span class="kw">export</span> <span class="kw">default</span> catchError(ErrorFallback)</code></pre></div><p class="lv3">Phir:</p><div class="cb lv3"><pre><code><span class="kw">import</span> ErrorBoundary <span class="kw">from</span> <span class="st">'./custom-error-boundary'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Component({</code></pre></div><p class="lv3">children,</p><div class="cb lv3"><pre><code>}: {</code></pre></div><p class="lv3">children: React.ReactNode</p><div class="cb lv3"><pre><code>}) {
  <span class="kw">return</span> (
    &lt;ErrorBoundary title=<span class="st">"Dashboard Error"</span>&gt;
      {children}
    &lt;/ErrorBoundary&gt;
  )
}</code></pre></div><p class="lv3">Concept:</p><p class="lv3">Page</p><div class="cb lv3"><pre><code>├── Header
├── ErrorBoundary
│    └── SomeComponent ← error
└── Footer</code></pre></div><p class="lv3">To boundary specific component tree ko protect kar sakti hai.</p><h3 id="error-boundary-kis-error-ko-catch-nahi-k" class="lv3">Error Boundary kis error ko catch nahi karti?</h3><p class="lv3">Ye <b>bohat important</b> hai.</p><p class="lv3">Error boundaries event handlers ke errors ko automatically catch nahi karti.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="st">'use client'</span>

<span class="kw">import</span> { useState } <span class="kw">from</span> <span class="st">'react'</span>

<span class="kw">export</span> <span class="kw">function</span> Button() {
  <span class="kw">const</span> [error, setError] = useState(null)

  <span class="kw">const</span> handleClick = () =&gt; {
    try {</code></pre></div><p class="lv3">throw new Error('Exception')</p><div class="cb lv3"><pre><code>    } catch (reason) {</code></pre></div><p class="lv3">setError(reason)</p><div class="cb lv3"><pre><code>    }
  }

  <span class="kw">if</span> (error) {
    <span class="cm">// fallback UI</span>
  }

  <span class="kw">return</span> (
    &lt;button <span class="kw">type</span>=<span class="st">"button"</span> onClick={handleClick}&gt;</code></pre></div><p class="lv3">Click me</p><div class="cb lv3"><pre><code>    &lt;/button&gt;
  )
}</code></pre></div><p class="lv3">Yahan error:</p><div class="cb lv3"><pre><code>User clicks button
      ↓
event handler runs
      ↓
error
      ↓
try/catch manually handle
      ↓
setError()
      ↓
UI update</code></pre></div><p class="lv3">Docs ke according event-handler ya async code ke errors ko error boundary generally handle nahi karti because ye rendering ke baad run hote hain.</p><h3 id="starttransition-ka-special-case" class="lv3">startTransition ka special case</h3><p class="lv3">Source ek special case batata hai:</p><p class="lv3">Agar <code>startTransition</code> ke andar error <b>unhandled</b> ho, to wo nearest Error Boundary tak bubble kar sakta hai.</p><div class="cb lv3"><pre><code><span class="st">'use client'</span>

<span class="kw">import</span> { useTransition } <span class="kw">from</span> <span class="st">'react'</span>

<span class="kw">export</span> <span class="kw">function</span> Button() {
  <span class="kw">const</span> [pending, startTransition] = useTransition()

  <span class="kw">const</span> handleClick = () =&gt;
    startTransition(() =&gt; {</code></pre></div><p class="lv3">throw new Error('Exception')</p><div class="cb lv3"><pre><code>    })

  <span class="kw">return</span> (
    &lt;button <span class="kw">type</span>=<span class="st">"button"</span> onClick={handleClick}&gt;</code></pre></div><p class="lv3">Click me</p><div class="cb lv3"><pre><code>    &lt;/button&gt;
  )
}</code></pre></div><p class="lv3">Isko abhi simply yaad rakho:</p><div class="cb lv3"><pre><code>Normal event handler error
        ↓
Error Boundary automatically nahi</code></pre></div><p class="lv3">startTransition ke andar</p><div class="cb lv3"><pre><code>unhandled error
        ↓
nearest Error Boundary</code></pre></div><h3 id="global-error" class="lv3">Global Error</h3><p class="lv3"><b><code>global-error.tsx</code></b><b> = root layout level ke error ko handle karne ke liye global fallback UI.</b></p><p class="lv3">Location:</p><div class="cb lv3"><pre><code>app/global-error.tsx</code></pre></div><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="st">'use client'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> GlobalError({</code></pre></div><p class="lv3">error,</p><p class="lv3">retry,</p><div class="cb lv3"><pre><code>}: {</code></pre></div><p class="lv3">error: Error &amp; { digest?: string }</p><div class="cb lv3"><pre><code>  retry: () =&gt; void
}) {
  <span class="kw">return</span> (
    &lt;html&gt;
      &lt;body&gt;
        &lt;h2&gt;Something went wrong!&lt;/h2&gt;

        &lt;button onClick={() =&gt; retry()}&gt;</code></pre></div><p class="lv3">Try again</p><div class="cb lv3"><pre><code>        &lt;/button&gt;
      &lt;/body&gt;
    &lt;/html&gt;
  )
}</code></pre></div><p class="lv3 box warn"><b>Important difference:</b></p><p class="lv3">Normal <code>error.tsx</code> route segment ko replace/fallback UI deta hai.</p><p class="lv3"><code>global-error.tsx</code> root layout ko replace karta hai, isliye isko <b>khud </b><b><code>&lt;html&gt;</code></b><b> aur </b><b><code>&lt;body&gt;</code></b><b> provide karne padte hain.</b></p><h3 id="final-mental-model" class="lv3">Final mental model</h3><p class="lv3">Is poore chapter ko is tarah yaad karo:</p><div class="cb lv3"><pre><code>                   ERROR
                      │
          ┌───────────┴───────────┐
          │                       │
     Expected Error         Uncaught Exception
          │                       │
   Normal possibility          Unexpected
          │                       │
   Handle explicitly          Throw error
          │                       │
   ┌──────┴──────┐          Error Boundary
   │             │                │
Server       Server Component   fallback UI
Function          │
   │          notFound()
   │
useActionState</code></pre></div><h3 id="sabse-important-6-concepts" class="lv3">Sabse important 6 concepts:</h3><ul class="lv3"><li><b>Expected Error</b> → normal operation mein expected failure; explicitly handle karo.</li><li><b><code>useActionState</code></b> → Server Function ka returned error/state UI mein show karne mein help karta hai.</li><li><b><code>notFound()</code></b> → resource na mile to 404 UI.</li><li><b>Error Boundary / </b><b><code>error.tsx</code></b> → unexpected rendering errors ke liye fallback UI.</li><li><b><code>catchError</code></b> → specific component tree ke around error boundary.</li><li><b><code>global-error.tsx</code></b> → root-level/global error UI.</li></ul></section><section><h2 id="css-in-next-js"><i>16</i>CSS in Next.js</h2><p class="lv2"><b>CSS = website ke HTML/JSX elements ko style karne ka system</b> — colors, spacing, size, layout, fonts, etc.</p><p class="lv2">Next.js mein docs ke mutabiq main styling options:</p><p class="lv2">CSS</p><div class="cb lv2"><pre><code>├── Tailwind CSS
├── CSS Modules
├── Global CSS
├── External Stylesheets
├── Sass
└── CSS-in-JS</code></pre></div><h3 id="tailwind-css" class="lv3">Tailwind CSS</h3><p class="lv3"><b>Tailwind CSS = utility classes ka framework jahan tum directly JSX ke </b><b><code>className</code></b><b> mein styling classes likhte ho.</b></p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Page() {
  <span class="kw">return</span> (
    &lt;main className=<span class="st">"flex min-h-screen flex-col items-center justify-between p-24"</span>&gt;
      &lt;h1 className=<span class="st">"text-4xl font-bold"</span>&gt;</code></pre></div><p class="lv3">Welcome to Next.js!</p><div class="cb lv3"><pre><code>      &lt;/h1&gt;
    &lt;/main&gt;
  )
}</code></pre></div><p class="lv3">Yahan:</p><div class="cb lv3"><pre><code>className
   ↓
<span class="st">"flex min-h-screen flex-col ..."</span>
   ↓
Tailwind utility classes
   ↓
element styled</code></pre></div><p class="lv3">For example:</p><ul class="lv3"><li><code>flex</code> → flex layout</li><li><code>min-h-screen</code> → minimum height screen ke barabar</li><li><code>flex-col</code> → items column mein</li><li><code>items-center</code> → center alignment</li><li><code>p-24</code> → padding</li><li><code>text-4xl</code> → text size</li><li><code>font-bold</code> → bold text</li></ul><p class="lv3 box warn"><b>Important:</b> Tailwind mein normally separate CSS file mein <code>.button { ... }</code> likhne ke bajaye utility classes use karte ho.</p><h4 id="next-js-setup" class="lv4">Next.js setup</h4><p class="lv4">Docs ke according:</p><div class="cb lv4"><pre><code>pnpm add -D tailwindcss @tailwindcss/postcss</code></pre></div><p class="lv4">Phir <code>postcss.config.mjs</code>:</p><div class="cb lv4"><pre><code><span class="kw">export</span> <span class="kw">default</span> {
  plugins: {
    <span class="st">'@tailwindcss/postcss'</span>: {},
  },
}</code></pre></div><p class="lv4">Aur <code>app/globals.css</code>:</p><div class="cb lv4"><pre><code>@<span class="kw">import</span> <span class="st">'tailwindcss'</span>;</code></pre></div><p class="lv4">Phir root layout mein:</p><div class="cb lv4"><pre><code><span class="kw">import</span> <span class="st">'./globals.css'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> RootLayout({</code></pre></div><p class="lv4">children,</p><div class="cb lv4"><pre><code>}: {</code></pre></div><p class="lv4">children: React.ReactNode</p><div class="cb lv4"><pre><code>}) {
  <span class="kw">return</span> (
    &lt;html lang=<span class="st">"en"</span>&gt;
      &lt;body&gt;{children}&lt;/body&gt;
    &lt;/html&gt;
  )
}</code></pre></div><p class="lv4">Iske baad Tailwind classes use kar sakte ho.</p><h3 id="css-modules" class="lv3">CSS Modules</h3><p class="lv3"><b>CSS Modules = CSS ko component/file ke scope tak limited rakhna.</b></p><p class="lv3">File:</p><div class="cb lv3"><div class="fn">app/blog/blog.module.css</div><pre><code>.blog {
  padding: 24px;
}</code></pre></div><p class="lv3">Phir component:</p><div class="cb lv3"><pre><code><span class="kw">import</span> styles <span class="kw">from</span> <span class="st">'./blog.module.css'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Page() {
  <span class="kw">return</span> (
    &lt;main className={styles.blog}&gt;</code></pre></div><p class="lv3">Blog</p><div class="cb lv3"><pre><code>    &lt;/main&gt;
  )
}</code></pre></div><p class="lv3">Yahan:</p><div class="cb lv3"><div class="fn">blog.module.css</div><pre><code>       ↓
<span class="kw">import</span> styles
       ↓
styles.blog
       ↓
.blog CSS apply</code></pre></div><h3 id="module-css-ka-fayda" class="lv3">.module.css ka fayda</h3><p class="lv3">Suppose do different files mein:</p><div class="cb lv3"><pre><code>.title {
  color: red;
}</code></pre></div><p class="lv3">aur:</p><div class="cb lv3"><pre><code>.title {
  color: blue;
}</code></pre></div><p class="lv3">CSS Modules unique class names generate karta hai, isliye normally ek component ki <code>.title</code> doosre component ki <code>.title</code> se collide nahi karti.</p><p class="lv3"><b>Simple definition:</b></p><p class="lv3">CSS Module = component-specific/scoped CSS.</p><h3 id="global-css" class="lv3">Global CSS</h3><p class="lv3"><b>Global CSS = aisi CSS jo application ke multiple/all routes par apply ho sakti hai.</b></p><p class="lv3">Example:</p><div class="cb lv3"><pre><code>body {
  padding: 20px 20px 60px;
  max-width: 680px;
  margin: 0 auto;
}</code></pre></div><p class="lv3">Root layout:</p><div class="cb lv3"><pre><code><span class="kw">import</span> <span class="st">'./global.css'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> RootLayout({</code></pre></div><p class="lv3">children,</p><div class="cb lv3"><pre><code>}: {</code></pre></div><p class="lv3">children: React.ReactNode</p><div class="cb lv3"><pre><code>}) {
  <span class="kw">return</span> (
    &lt;html lang=<span class="st">"en"</span>&gt;
      &lt;body&gt;{children}&lt;/body&gt;
    &lt;/html&gt;
  )
}</code></pre></div><p class="lv3">Flow:</p><div class="cb lv3"><div class="fn">global.css</div><pre><code>    ↓
Root Layout
    ↓
application routes
    ↓
global styles available</code></pre></div><p class="lv3">Docs ke mutabiq global CSS <code>app</code> directory ke layout, page, ya component se import ho sakti hai. Lekin recommendation hai ke <b>truly global styles</b> ke liye global CSS use karo, component styling ke liye Tailwind/CSS Modules use karo.</p><h3 id="global-css-vs-css-modules" class="lv3">Global CSS vs CSS Modules</h3><p class="lv3">Ye difference important hai:</p><div class="tw lv3"><table><tr><th><b>Global CSS</b></th><th><b>CSS Modules</b></th></tr><tr><td>Broad application styling</td><td>Specific component styling</td></tr><tr><td><code>.blog { ... }</code></td><td><code>.blog { ... }</code> inside module</td></tr><tr><td>Globally available styles</td><td>Locally scoped styles</td></tr><tr><td><code>import './global.css'</code></td><td><code>import styles from './blog.module.css'</code></td></tr><tr><td>Body/base styles ke liye useful</td><td>Component-specific design ke liye useful</td></tr></table></div><p class="lv3">Simple:</p><p class="lv3">Global CSS</p><div class="cb lv3"><pre><code>→ <span class="st">"poori application ke liye"</span></code></pre></div><p class="lv3">CSS Module</p><div class="cb lv3"><pre><code>→ <span class="st">"is component ke liye"</span></code></pre></div><h3 id="external-stylesheets" class="lv3">External Stylesheets</h3><p class="lv3"><b>External stylesheet = kisi external package/library ki CSS ko apni application mein import karna.</b></p><p class="lv3">Example Bootstrap:</p><div class="cb lv3"><pre><code><span class="kw">import</span> <span class="st">'bootstrap/dist/css/bootstrap.css'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> RootLayout({</code></pre></div><p class="lv3">children,</p><div class="cb lv3"><pre><code>}: {</code></pre></div><p class="lv3">children: React.ReactNode</p><div class="cb lv3"><pre><code>}) {
  <span class="kw">return</span> (
    &lt;html lang=<span class="st">"en"</span>&gt;
      &lt;body className=<span class="st">"container"</span>&gt;
        {children}
      &lt;/body&gt;
    &lt;/html&gt;
  )
}</code></pre></div><p class="lv3">Yahan:</p><div class="cb lv3"><pre><code>bootstrap
   ↓
bootstrap/dist/css/bootstrap.css
   ↓
<span class="kw">import</span>
   ↓
Bootstrap CSS available</code></pre></div><p class="lv3 box tip">Yani CSS tumhari khud ki file se nahi aa rahi; <b>external package</b> se aa rahi hai.</p><div class="cb lv3"><pre><code>Docs ye bhi mention karti hain ke React 19 mein &lt;link rel=<span class="st">"stylesheet"</span> href=<span class="st">"..."</span> /&gt; use kiya ja sakta hai.</code></pre></div><h3 id="css-ordering" class="lv3">CSS Ordering</h3><p class="lv3">Ye concept important hai:</p><p class="lv3"><b>CSS ka order import order par depend kar sakta hai.</b></p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">import</span> { BaseButton } <span class="kw">from</span> <span class="st">'./base-button'</span>
<span class="kw">import</span> styles <span class="kw">from</span> <span class="st">'./page.module.css'</span></code></pre></div><p class="lv3"><code>BaseButton</code> ke andar:</p><div class="cb lv3"><pre><code><span class="kw">import</span> styles <span class="kw">from</span> <span class="st">'./base-button.module.css'</span></code></pre></div><p class="lv3">To dependency/import order ki wajah se CSS ordering affect ho sakti hai.</p><p class="lv3">Simple:</p><div class="cb lv3"><div class="fn">page.tsx</div><pre><code>   ↓
BaseButton <span class="kw">import</span>
   ↓
base-button.module.css
   ↓
page.module.css</code></pre></div><p class="lv3">Next.js production build mein CSS ko automatically optimize/chunk karta hai, lekin <b>CSS import order</b> final styling ko affect kar sakta hai.</p><h3 id="css-ko-predictable-kaise-rakhein" class="lv3">CSS ko predictable kaise rakhein?</h3><p class="lv3">Docs ki recommendations ka simple version:</p><ul class="lv3"><li>CSS imports ko unnecessarily different files mein spread na karo.</li><li>Global CSS aur Tailwind ko root level par import karo.</li><li><b>Tailwind</b> ko common styling ke liye use karo.</li><li><b>CSS Modules</b> ko component-specific custom CSS ke liye use karo.</li></ul><p class="lv3">CSS Module naming consistent rakho:<br><br> button.module.css</p><div class="cb lv3"><pre><code>card.module.css</code></pre></div><ul class="lv3"><li>blog.module.css<br></li><li>Shared styling ko shared components mein rakho.</li><li>Auto import-sorting tools se CSS import order accidentally change na hone do.</li><li><code>cssChunking</code> option se CSS chunking behavior control kiya ja sakta hai.</li></ul><h3 id="development-vs-production" class="lv3">Development vs Production</h3><p class="lv3">Next.js CSS ko development aur production mein differently process karta hai.</p><h4 id="development" class="lv4">Development</h4><div class="cb lv4"><pre><code>next dev</code></pre></div><p class="lv4">CSS change karo:</p><div class="cb lv4"><pre><code>CSS change
   ↓
Fast Refresh
   ↓
browser mein update</code></pre></div><p class="lv4">Isliye development mein styling changes quickly appear hoti hain.</p><h4 id="production" class="lv4">Production</h4><div class="cb lv4"><pre><code>next build</code></pre></div><p class="lv4">Next.js CSS ko optimize karta hai:</p><div class="cb lv4"><pre><code>Multiple CSS files
      ↓
optimized
      ↓
minified + code-split CSS
      ↓
route ke liye required CSS load</code></pre></div><p class="lv4">Docs ke according production mein CSS automatically many minified/code-split <code>.css</code> files mein concatenate hoti hai, taake route ke liye minimum required CSS load ho.</p><h3 id="is-section-ka-practical-choice" class="lv3">Is section ka practical choice</h3><p class="lv3">Tumhare Next.js project ke liye abhi simple mental model rakho:</p><div class="cb lv3"><pre><code>                    CSS
                      │
        ┌─────────────┼─────────────┐
        │             │             │
    Tailwind      CSS Modules    Global CSS
        │             │             │
  common UI       component      truly global</code></pre></div><p class="lv3">styling         styling        styles</p><h3 id="example-2" class="lv3">Example:</h3><p class="lv3"><b>Button ka design:</b></p><div class="cb lv3"><pre><code>&lt;button className=<span class="st">"px-4 py-2 rounded"</span>&gt;</code></pre></div><p class="lv3">Save</p><div class="cb lv3"><pre><code>&lt;/button&gt;</code></pre></div><p class="lv3">→ <b>Tailwind</b></p><p class="lv3"><b>Ek special Blog component:</b></p><div class="cb lv3"><div class="fn">Blog.module.css</div><pre><code>className={styles.blog}</code></pre></div><p class="lv3">→ <b>CSS Module</b></p><p class="lv3"><b>Entire website ka </b><b><code>body</code></b><b>:</b></p><div class="cb lv3"><pre><code>body {
  margin: 0;
}</code></pre></div><p class="lv3">→ <b>Global CSS</b></p><h3 id="sabse-important-definitions" class="lv3">Sabse important definitions</h3><ul class="lv3"><li><b>Tailwind CSS</b> → utility classes se styling.</li><li><b>CSS Module</b> → component/file scoped CSS.</li><li><b>Global CSS</b> → application-wide/broad CSS.</li><li><b>External stylesheet</b> → external package ki CSS.</li><li><b>CSS ordering</b> → CSS import order styling result ko affect kar sakta hai.</li><li><b>Development CSS</b> → <code>next dev</code> mein Fast Refresh ke through changes quickly apply.</li><li><b>Production CSS</b> → <code>next build</code> mein CSS optimize, minify aur code-split hoti hai.</li></ul></section><section><h2 id="image-optimization"><i>17</i>Image Optimization</h2><p class="lv2"><b>Image Optimization = images ko aise serve karna ke website fast load ho, image ka size device ke according ho aur loading ke waqt layout unnecessarily move na ho.</b></p><p class="lv2">Next.js ka main tool:</p><div class="cb lv2"><pre><code><span class="kw">import</span> Image <span class="kw">from</span> <span class="st">'next/image'</span></code></pre></div><p class="lv2">Yahan <code>Image</code> Next.js ka optimized image component hai jo normal HTML <code>&lt;img&gt;</code> ko extend karta hai.</p><p class="lv2">Docs ke mutabiq iske main benefits:</p><ul class="lv2"><li><b>Size optimization</b> → device ke according suitable image size serve karna, modern formats jaise WebP use karna.</li><li><b>Visual stability</b> → image load hone par layout shift prevent karna.</li><li><b>Faster page loads</b> → viewport mein aane par images load karna; optional blur placeholder.</li><li><b>Asset flexibility</b> → remote images ko bhi resize/optimize kar sakna.</li></ul><h3 id="lt-image-gt-component" class="lv3">&lt;Image&gt; component</h3><p class="lv3">Basic:</p><div class="cb lv3"><pre><code><span class="kw">import</span> Image <span class="kw">from</span> <span class="st">'next/image'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Page() {
  <span class="kw">return</span> (
    &lt;Image</code></pre></div><p class="lv3">src="/profile.png"</p><p class="lv3">alt="Picture of the author"</p><div class="cb lv3"><pre><code>      width={500}
      height={500}
    /&gt;
  )
}</code></pre></div><p class="lv3">Simple breakdown:</p><ul class="lv3"><li><code>import</code> → bahar se cheez import karo.</li><li><code>Image</code> → imported component ka naam.</li><li><code>'next/image'</code> → Next.js ka Image module.</li><li><code>&lt;Image /&gt;</code> → image render karta hai.</li><li><code>src</code> → image ka source.</li><li><code>alt</code> → image ka alternative text.</li><li><code>width</code> → image ki width.</li><li><code>height</code> → image ki height.</li></ul><h3 id="local-images" class="lv3">Local Images</h3><p class="lv3"><b>Local image = tumhare project ke andar stored image.</b></p><p class="lv3">Next.js mein static assets ke liye:</p><p class="lv3">next-learning/</p><div class="cb lv3"><pre><code>├── app/
└── public/
    └── profile.png</code></pre></div><p class="lv3">Agar:</p><p class="lv3">public/profile.png</p><p class="lv3">to <code>&lt;Image&gt;</code> mein:</p><div class="cb lv3"><pre><code>&lt;Image</code></pre></div><p class="lv3">src="/profile.png"</p><p class="lv3">alt="Profile"</p><div class="cb lv3"><pre><code>  width={500}
  height={500}
/&gt;</code></pre></div><p class="lv3 box warn"><b>Important:</b> <code>public</code> URL mein nahi likhna.</p><p class="lv3">❌ Wrong:</p><p class="lv3">src="/public/profile.png"</p><p class="lv3">✅ Correct:</p><p class="lv3">src="/profile.png"</p><p class="lv3">Reason:</p><p class="lv3"><code>public</code> folder ki files website ke base URL <code>/</code> se accessible hoti hain.</p><h3 id="static-image-import" class="lv3">Static Image Import</h3><p class="lv3">Agar image ko directly import karo:</p><div class="cb lv3"><pre><code><span class="kw">import</span> Image <span class="kw">from</span> <span class="st">'next/image'</span>
<span class="kw">import</span> ProfileImage <span class="kw">from</span> <span class="st">'./profile.png'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Page() {
  <span class="kw">return</span> (
    &lt;Image
      src={ProfileImage}</code></pre></div><p class="lv3">alt="Picture of the author"</p><div class="cb lv3"><pre><code>    /&gt;
  )
}</code></pre></div><p class="lv3">Yahan ek important difference hai.</p><p class="lv3">Normal local path:</p><p class="lv3">src="/profile.png"</p><p class="lv3">mein tum <code>width</code> aur <code>height</code> provide karte ho.</p><p class="lv3">Lekin <b>static import</b>:</p><div class="cb lv3"><pre><code><span class="kw">import</span> ProfileImage <span class="kw">from</span> <span class="st">'./profile.png'</span></code></pre></div><p class="lv3">karne par Next.js automatically image ki:</p><ul class="lv3"><li><code>width</code></li><li><code>height</code></li><li><code>blurDataURL</code></li></ul><p class="lv3">determine/provide kar sakta hai.</p><p class="lv3">Isliye:</p><div class="cb lv3"><pre><code>&lt;Image
  src={ProfileImage}</code></pre></div><p class="lv3">alt="Picture of the author"</p><div class="cb lv3"><pre><code>/&gt;</code></pre></div><p class="lv3">enough ho sakta hai.</p><p class="lv3">Docs ke mutabiq width/height se image ka ratio determine hota hai aur loading ke waqt <b>Cumulative Layout Shift (CLS)</b> prevent karne mein help milti hai.</p><h3 id="placeholder-blur" class="lv3">placeholder="blur"</h3><p class="lv3">Static image import ke saath Next.js blur data bhi provide kar sakta hai.</p><p class="lv3">Tum optionally:</p><div class="cb lv3"><pre><code>&lt;Image
  src={ProfileImage}</code></pre></div><p class="lv3">alt="Picture of the author"</p><p class="lv3">placeholder="blur"</p><div class="cb lv3"><pre><code>/&gt;</code></pre></div><p class="lv3">use kar sakte ho.</p><p class="lv3">Simple flow:</p><div class="cb lv3"><pre><code>Image loading
      ↓
small blur placeholder
      ↓
actual image load
      ↓
actual image displayed</code></pre></div><p class="lv3 box tip">Yani user ko blank area ke bajaye temporarily blurred version nazar aa sakta hai.</p><h3 id="dynamic-static-image-import" class="lv3">Dynamic Static Image Import</h3><p class="lv3">Agar tum static <code>import</code> directly nahi kar sakte, docs Server Component mein dynamic <code>import()</code> ka example deti hain.</p><div class="cb lv3"><pre><code><span class="kw">import</span> Image <span class="kw">from</span> <span class="st">'next/image'</span>

<span class="kw">async</span> <span class="kw">function</span> PostImage({</code></pre></div><p class="lv3">imageFilename,</p><p class="lv3">alt,</p><div class="cb lv3"><pre><code>}: {</code></pre></div><p class="lv3">imageFilename: string</p><p class="lv3">alt: string</p><div class="cb lv3"><pre><code>}) {
  <span class="kw">const</span> { <span class="kw">default</span>: image } = <span class="kw">await</span> <span class="kw">import</span>(</code></pre></div><p class="lv3">`../content/blog/images/${imageFilename}`</p><div class="cb lv3"><pre><code>  )

  <span class="kw">return</span> &lt;Image src={image} alt={alt} /&gt;
}</code></pre></div><p class="lv3">Yahan important idea:</p><div class="cb lv3"><pre><code>imageFilename
      ↓
dynamic <span class="kw">import</span>()
      ↓
image object
      ↓
width + height + blurDataURL
      ↓
&lt;Image&gt;</code></pre></div><p class="lv3">Docs ke mutabiq path mein <b>static prefix</b> hona chahiye:</p><p class="lv3">../content/blog/images/</p><p class="lv3">Aur specific path rakhna important hai, kyunki us prefix se matching files bundle ho sakti hain.</p><h3 id="remote-images" class="lv3">Remote Images</h3><p class="lv3"><b>Remote image = image tumhare project ke andar nahi, kisi external server par stored hai.</b></p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">import</span> Image <span class="kw">from</span> <span class="st">'next/image'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> Page() {
  <span class="kw">return</span> (
    &lt;Image</code></pre></div><p class="lv3">src="https://s3.amazonaws.com/my-bucket/profile.png"</p><p class="lv3">alt="Picture of the author"</p><div class="cb lv3"><pre><code>      width={500}
      height={500}
    /&gt;
  )
}</code></pre></div><p class="lv3">Yahan:</p><div class="cb lv3"><pre><code>Your Next.js app
       ↓</code></pre></div><p class="lv3">https://s3.amazonaws.com/...</p><div class="cb lv3"><pre><code>       ↓
remote image</code></pre></div><h3 id="remote-image-mein-width-height-kyun-deni" class="lv3">Remote Image mein width/height kyun deni hoti hai?</h3><p class="lv3">Local static import ke waqt Next.js build time par image ko inspect kar sakta hai.</p><p class="lv3">Remote image ke case mein:</p><div class="cb lv3"><pre><code>Next.js build
      ↓
remote server ki image
      ↓
build time par available nahi</code></pre></div><p class="lv3">Isliye tumhein manually:</p><div class="cb lv3"><pre><code>width={500}
height={500}</code></pre></div><p class="lv3">dene hote hain.</p><p class="lv3">Ye image ka <b>aspect ratio</b> determine karne mein help karta hai aur layout shift avoid karta hai.</p><h3 id="fill" class="lv3">fill</h3><p class="lv3">Remote image ke liye docs ek alternative deti hain:</p><div class="cb lv3"><pre><code>&lt;Image</code></pre></div><p class="lv3">src="https://example.com/image.png"</p><p class="lv3">alt="Example"</p><p class="lv3">fill</p><div class="cb lv3"><pre><code>/&gt;</code></pre></div><p class="lv3"><b><code>fill</code></b><b> = image ko parent element ki available size fill karne dena.</b></p><p class="lv3">Simple:</p><div class="cb lv3"><pre><code>Parent
┌──────────────────────┐
│                      │
│       Image          │
│                      │
└──────────────────────┘</code></pre></div><p class="lv3">Image parent ki space fill karti hai.</p><h3 id="remote-images-ko-allow-karna" class="lv3">Remote Images ko allow karna</h3><p class="lv3">Next.js security ke liye har random remote image URL ko automatically allow nahi karta.</p><p class="lv3">Tumhein <code>next.config.ts</code> mein supported remote pattern define karna hota hai.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">import</span> <span class="kw">type</span> { NextConfig } <span class="kw">from</span> <span class="st">'next'</span>

<span class="kw">const</span> config: NextConfig = {
  images: {</code></pre></div><p class="lv3">remotePatterns: [</p><div class="cb lv3"><pre><code>      {</code></pre></div><p class="lv3">protocol: 'https',</p><p class="lv3">hostname: 's3.amazonaws.com',</p><p class="lv3">port: '',</p><p class="lv3">pathname: '/my-bucket/',</p><p class="lv3">search: '',</p><div class="cb lv3"><pre><code>      },</code></pre></div><p class="lv3">],</p><div class="cb lv3"><pre><code>  },
}

<span class="kw">export</span> <span class="kw">default</span> config</code></pre></div><p class="lv3">Iska simple meaning:</p><div class="cb lv3"><div class="fn">Next.js</div><pre><code>   ↓
Remote image allowed?
   ↓
https</code></pre></div><p class="lv3">+</p><p class="lv3">s3.amazonaws.com</p><p class="lv3">+</p><div class="cb lv3"><pre><code>/my-bucket/**
   ↓
YES</code></pre></div><p class="lv3">Lekin:</p><p class="lv3">https://another-site.com/image.png</p><p class="lv3">allowed pattern mein nahi hai, to Next.js usko automatically accepted remote image source nahi samjhega.</p><p class="lv3">Docs specifically recommend karti hain ke remote patterns ko <b>as specific as possible</b> rakho.</p><h3 id="local-vs-remote-vs-static-import" class="lv3">Local vs Remote vs Static Import</h3><p class="lv3">Ye distinction yaad rakho:</p><div class="tw lv3"><table><tr><th><b>Type</b></th><th><b>Example</b></th><th><b>Width/Height</b></th></tr><tr><td>Local <code>public</code></td><td><code>/profile.png</code></td><td>Usually manually</td></tr><tr><td>Static import</td><td><code>import Profile from './profile.png'</code></td><td>Automatically provided</td></tr><tr><td>Remote</td><td><code>https://example.com/a.png</code></td><td>Manually required</td></tr><tr><td>Remote + <code>fill</code></td><td>External image filling parent</td><td><code>fill</code> alternative</td></tr></table></div><h3 id="lt-image-gt-ka-actual-benefit-kya-hai" class="lv3">&lt;Image&gt; ka actual benefit kya hai?</h3><p class="lv3">Normal:</p><div class="cb lv3"><pre><code>&lt;img src=<span class="st">"/profile.png"</span> /&gt;</code></pre></div><p class="lv3">Next.js:</p><div class="cb lv3"><pre><code>&lt;Image</code></pre></div><p class="lv3">src="/profile.png"</p><p class="lv3">alt="Profile"</p><div class="cb lv3"><pre><code>  width={500}
  height={500}
/&gt;</code></pre></div><p class="lv3">Next.js <code>&lt;Image&gt;</code> component additional optimization provide karta hai:</p><div class="cb lv3"><pre><code>&lt;Image&gt;
   │
   ├── Correct image sizing
   ├── Modern image formats
   ├── Layout shift protection
   ├── Lazy loading
   ├── Optional blur placeholder
   └── Remote image optimization</code></pre></div><h3 id="sabse-important-concepts" class="lv3">Sabse important concepts</h3><ul class="lv3"><li><b><code>&lt;Image&gt;</code></b> → Next.js ka optimized image component.</li><li><b><code>src</code></b> → local ya remote image source.</li><li><b>Local image</b> → project ke <code>public</code> folder mein image.</li><li><b>Static import</b> → image ko <code>import</code> karne par Next.js dimensions/blur data automatically determine kar sakta hai.</li><li><b>Remote image</b> → external server ki image; dimensions manually dene hote hain.</li><li><b><code>width</code></b><b> + </b><b><code>height</code></b> → aspect ratio/layout stability ke liye.</li><li><b><code>fill</code></b> → image ko parent ki available space fill karwana.</li><li><b><code>placeholder="blur"</code></b> → actual image load hone tak blur preview.</li><li><b><code>remotePatterns</code></b> → kaun se remote image URLs allowed hain.</li><li><b>Image optimization</b> → correctly sized images, modern formats, lazy loading aur layout stability ke through better image delivery.</li></ul><h3 id="ek-simple-mental-model" class="lv3">Ek simple mental model:</h3><div class="cb lv3"><pre><code>             &lt;Image&gt;
                 │
       ┌─────────┴─────────┐
       │                   │
     Local               Remote
       │                   │
 public/              external URL
       │                   │
       └─────────┬─────────┘
                 │
          Next.js optimization
                 │
        faster + stable images</code></pre></div></section><section><h2 id="font-optimization-simple-explanation"><i>18</i>Font Optimization — simple explanation</h2><p class="lv2"><b>Font Optimization</b> ka matlab hai website ke fonts ko aise load karna ke <b>website fast rahe, font properly load ho, aur layout shift na ho</b>.</p><p class="lv2">Next.js mein iske liye <b><code>next/font</code></b> module use hota hai.</p><h4 id="1-next-font" class="lv4">1. next/font</h4><p class="lv4"><code>next/font</code> → Next.js ka built-in font optimization system hai.</p><p class="lv4">Iske 2 main sources hain:</p><div class="cb lv4"><pre><code><span class="kw">import</span> { Geist } <span class="kw">from</span> <span class="st">'next/font/google'</span></code></pre></div><ul class="lv4"><li><code>next/font/google</code> → Google Fonts use karne ke liye.</li></ul><div class="cb lv4"><pre><code><span class="kw">import</span> localFont <span class="kw">from</span> <span class="st">'next/font/local'</span></code></pre></div><ul class="lv4"><li><code>next/font/local</code> → apni local font files (<code>.woff2</code> etc.) use karne ke liye.</li></ul><p class="lv4">Next.js fonts ko <b>self-host</b> karta hai, yani Google Font use karne ke bawajood browser directly Google ko font request nahi bhejta. Font tumhari deployment ki same domain se serve hota hai.</p><h3 id="google-font-use-karna" class="lv3">Google Font use karna</h3><p class="lv3">Source ka example:</p><div class="cb lv3"><pre><code><span class="kw">import</span> { Geist } <span class="kw">from</span> <span class="st">'next/font/google'</span>              <span class="cm">// Google se Geist font import</span>

<span class="kw">const</span> geist = Geist({                                 <span class="cm">// Geist font configure</span></code></pre></div><p class="lv3">subsets: ['latin'],                                 // Latin characters use</p><div class="cb lv3"><pre><code>})

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> RootLayout({                 <span class="cm">// Root Layout function</span></code></pre></div><p class="lv3">children,                                           // Page ka UI</p><div class="cb lv3"><pre><code>}: {</code></pre></div><p class="lv3">children: React.ReactNode                          // children ka TypeScript type</p><div class="cb lv3"><pre><code>}) {
  <span class="kw">return</span> (                                            <span class="cm">// UI return</span>
    &lt;html lang=<span class="st">"en"</span> className={geist.className}&gt;      <span class="cm">// Geist font HTML par apply</span>
      &lt;body&gt;{children}&lt;/body&gt;                         <span class="cm">// Page ka content</span>
    &lt;/html&gt;                                           <span class="cm">// html close</span>
  )
}</code></pre></div><h4 id="important-cheezen" class="lv4">Important cheezen</h4><ul class="lv4"><li><code>Geist</code> → font ka imported function.</li><li><code>Geist({...})</code> → font ko configure karta hai.</li><li><code>subsets: ['latin']</code> → Latin characters ke liye font.</li><li><code>geist</code> → configured font ka variable.</li><li><code>geist.className</code> → Next.js generated CSS class.</li><li><code>className={geist.className}</code> → font ko <code>&lt;html&gt;</code> par apply karta hai.</li><li>Root Layout mein lagane se <b>poori application</b> mein font apply ho jata hai.</li></ul><h4 id="variable-font" class="lv4">Variable font</h4><p class="lv4">Docs ke according <b>variable fonts</b> performance aur flexibility ke liye recommended hain.</p><p class="lv4">Variable font ka simple concept:</p><p class="lv4"><b>Ek font file mein multiple font weights/styles ko handle karna.</b></p><p class="lv4">Agar variable font available na ho, to weight specify karna hota hai.</p><h4 id="weight-specify-karna" class="lv4">Weight specify karna</h4><p class="lv4">Example:</p><div class="cb lv4"><pre><code><span class="kw">import</span> { Roboto } <span class="kw">from</span> <span class="st">'next/font/google'</span>             <span class="cm">// Roboto import</span>

<span class="kw">const</span> roboto = Roboto({                               <span class="cm">// Roboto configure</span></code></pre></div><p class="lv4">weight: '400',                                      // Font weight 400</p><p class="lv4">subsets: ['latin'],                                 // Latin characters</p><div class="cb lv4"><pre><code>})

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> RootLayout({                 <span class="cm">// Root Layout</span></code></pre></div><p class="lv4">children,                                           // Page content</p><div class="cb lv4"><pre><code>}: {</code></pre></div><p class="lv4">children: React.ReactNode                          // children ka type</p><div class="cb lv4"><pre><code>}) {
  <span class="kw">return</span> (                                            <span class="cm">// UI return</span>
    &lt;html lang=<span class="st">"en"</span> className={roboto.className}&gt;     <span class="cm">// Roboto apply</span>
      &lt;body&gt;{children}&lt;/body&gt;                         <span class="cm">// Page content</span>
    &lt;/html&gt;                                           <span class="cm">// html close</span>
  )
}</code></pre></div><p class="lv4">Yahan:</p><ul class="lv4"><li><code>weight: '400'</code> → font ka weight specify karta hai.</li><li><code>400</code> → normal/regular weight ke liye use kiya gaya example.</li><li><code>roboto.className</code> → configured Roboto font ko apply karta hai.</li></ul><h4 id="local-font" class="lv4">Local Font</h4><p class="lv4">Agar tumhare paas apni font file hai, jaise:</p><p class="lv4">my-font.woff2</p><p class="lv4">to:</p><div class="cb lv4"><pre><code><span class="kw">import</span> localFont <span class="kw">from</span> <span class="st">'next/font/local'</span>              <span class="cm">// Local font function import</span>

<span class="kw">const</span> myFont = localFont({                           <span class="cm">// Local font configure</span></code></pre></div><p class="lv4">src: './my-font.woff2',                            // Font file ka path</p><div class="cb lv4"><pre><code>})

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">function</span> RootLayout({                 <span class="cm">// Root Layout</span></code></pre></div><p class="lv4">children,                                           // Page content</p><div class="cb lv4"><pre><code>}: {</code></pre></div><p class="lv4">children: React.ReactNode                          // children ka type</p><div class="cb lv4"><pre><code>}) {
  <span class="kw">return</span> (                                            <span class="cm">// UI return</span>
    &lt;html lang=<span class="st">"en"</span> className={myFont.className}&gt;     <span class="cm">// Local font apply</span>
      &lt;body&gt;{children}&lt;/body&gt;                         <span class="cm">// Page content</span>
    &lt;/html&gt;                                           <span class="cm">// html close</span>
  )
}</code></pre></div><h5 id="yahan-important-difference" class="lv5">Yahan important difference:</h5><p class="lv5">src: './my-font.woff2'</p><p class="lv5">Ye path <b>us file ke relative hai jahan </b><b><code>localFont()</code></b><b> call ho raha hai</b>.</p><p class="lv5">Example:</p><div class="cb lv5"><pre><code>app/
├── fonts/
│   └── my-font.woff2
└── layout.tsx</code></pre></div><p class="lv5"><code>layout.tsx</code> se font ka path:</p><p class="lv5">src: './fonts/my-font.woff2'</p><p class="lv5">Source ke example mein agar font <code>app/fonts/</code> mein ho aur call <code>app/fonts/...</code> context ke mutabiq ho, path us calling file ke relative resolve hota hai.</p><h3 id="ek-font-family-ki-multiple-files" class="lv3">Ek font family ki multiple files</h3><p class="lv3">Agar same font ke different versions hain:</p><p class="lv3">Regular</p><p class="lv3">Italic</p><p class="lv3">Bold</p><p class="lv3">Bold Italic</p><p class="lv3">to <code>src</code> mein <b>array</b> de sakte ho:</p><div class="cb lv3"><pre><code><span class="kw">const</span> roboto = localFont({</code></pre></div><p class="lv3">src: [</p><div class="cb lv3"><pre><code>    {</code></pre></div><p class="lv3">path: './Roboto-Regular.woff2',       // Regular font file</p><p class="lv3">weight: '400',                         // Regular weight</p><p class="lv3">style: 'normal',                      // Normal style</p><div class="cb lv3"><pre><code>    },
    {</code></pre></div><p class="lv3">path: './Roboto-Italic.woff2',        // Italic font file</p><p class="lv3">weight: '400',                         // Regular weight</p><p class="lv3">style: 'italic',                      // Italic style</p><div class="cb lv3"><pre><code>    },
    {</code></pre></div><p class="lv3">path: './Roboto-Bold.woff2',          // Bold font file</p><p class="lv3">weight: '700',                         // Bold weight</p><p class="lv3">style: 'normal',                      // Normal style</p><div class="cb lv3"><pre><code>    },
    {</code></pre></div><p class="lv3">path: './Roboto-BoldItalic.woff2',    // Bold italic file</p><p class="lv3">weight: '700',                         // Bold weight</p><p class="lv3">style: 'italic',                      // Italic style</p><div class="cb lv3"><pre><code>    },</code></pre></div><p class="lv3">],</p><div class="cb lv3"><pre><code>})</code></pre></div><p class="lv3">Yahan:</p><ul class="lv3"><li><code>src: []</code> → multiple font files.</li><li><code>path</code> → actual font file ka path.</li><li><code>weight</code> → font ki thickness.</li><li><code>style</code> → <code>normal</code> ya <code>italic</code>.</li></ul><h3 id="sabse-important-mental-model" class="lv3">Sabse important mental model</h3><div class="cb lv3"><pre><code>next/font
   │
   ├── next/font/google
   │       └── Google Font
   │
   └── next/font/local
           └── apni .woff/.woff2 font</code></pre></div><p class="lv3">Aur font ko page/app par lagane ka basic process:</p><div class="cb lv3"><pre><code>Import font
   ↓
Font configure karo
   ↓
className lo
   ↓
HTML/element par className lagao</code></pre></div><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">const</span> geist = Geist({</code></pre></div><p class="lv3">subsets: ['latin'],</p><div class="cb lv3"><pre><code>})

&lt;html className={geist.className}&gt;</code></pre></div></section><section><h2 id="metadata"><i>19</i>Metadata</h2><p class="lv2"><b>Metadata → website ke baare mein information jo search engines aur social platforms ko di jati hai.</b></p><p class="lv2">Example:</p><div class="cb lv2"><pre><code><span class="kw">import</span> <span class="kw">type</span> { Metadata } <span class="kw">from</span> <span class="st">'next'</span>

<span class="kw">export</span> <span class="kw">const</span> metadata: Metadata = {</code></pre></div><p class="lv2">title: 'My Blog',</p><p class="lv2">description: 'My personal blog',</p><div class="cb lv2"><pre><code>}</code></pre></div><ul class="lv2"><li><code>Metadata</code> → Next.js ka TypeScript type.</li><li><code>metadata</code> → metadata object ka naam.</li><li><code>title</code> → page ka title.</li><li><code>description</code> → page ki description.</li><li><code>export</code> → Next.js ko ye metadata available karata hai.</li></ul><p class="lv2">Next.js is information ko automatically relevant <code>&lt;head&gt;</code> tags mein convert karta hai.</p><h3 id="static-metadata" class="lv3">Static Metadata</h3><p class="lv3"><b>Static metadata → jab metadata fixed ho aur har request par change na ho.</b></p><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">const</span> metadata: Metadata = {</code></pre></div><p class="lv3">title: 'My Blog',</p><p class="lv3">description: 'My personal blog',</p><div class="cb lv3"><pre><code>}</code></pre></div><p class="lv3">Ye <code>layout.tsx</code> ya <code>page.tsx</code> se export ki ja sakti hai.</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code>app/
├── layout.tsx
└── blog/
    └── page.tsx</code></pre></div><p class="lv3">Agar blog ka title fixed hai:</p><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">const</span> metadata: Metadata = {</code></pre></div><p class="lv3">title: 'My Blog',</p><div class="cb lv3"><pre><code>}</code></pre></div><p class="lv3">to static metadata enough hai.</p><h3 id="dynamic-metadata-generatemetadata" class="lv3">Dynamic Metadata — generateMetadata</h3><p class="lv3"><b>Dynamic metadata → jab metadata kisi data ke basis par change hoti hai.</b></p><p class="lv3">For example:</p><p class="lv3">/blog/hello-world</p><p class="lv3">/blog/nextjs-guide</p><p class="lv3">/blog/seo-guide</p><p class="lv3">Har blog post ka title different hai.</p><p class="lv3">Isliye:</p><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> generateMetadata({ params }: Props): Promise&lt;Metadata&gt; {
  <span class="kw">const</span> { slug } = <span class="kw">await</span> params

  <span class="kw">const</span> post = <span class="kw">await</span> getPost(slug)

  <span class="kw">return</span> {</code></pre></div><p class="lv3">title: post.title,</p><p class="lv3">description: post.description,</p><div class="cb lv3"><pre><code>  }
}</code></pre></div><p class="lv3">Yahan:</p><ul class="lv3"><li><code>generateMetadata</code> → metadata generate karne wala function.</li><li><code>params</code> → URL se dynamic value.</li><li><code>slug</code> → URL ka dynamic segment.</li><li><code>getPost(slug)</code> → us specific post ka data.</li><li><code>post.title</code> → us post ka title.</li><li><code>post.description</code> → us post ki description.</li></ul><p class="lv3">Source ke example mein <code>/blog/[slug]</code> ke liye post data fetch karke title aur description generate kiye ja rahe hain.</p><p class="lv3"><b>Simple difference:</b></p><div class="cb lv3"><pre><code>Fixed information
      ↓
metadata
Data ke according changing information
      ↓
generateMetadata()</code></pre></div><h3 id="file-based-metadata" class="lv3">File-based Metadata</h3><p class="lv3">Next.js kuch special files ko automatically metadata ke liye recognize karta hai:</p><p class="lv3">favicon.ico</p><p class="lv3">apple-icon.jpg</p><p class="lv3">icon.jpg</p><p class="lv3">opengraph-image.jpg</p><p class="lv3">twitter-image.jpg</p><p class="lv3">robots.txt</p><p class="lv3">sitemap.xml</p><p class="lv3">Source mein ye special file conventions listed hain.</p><h3 id="favicon" class="lv3">Favicon</h3><p class="lv3"><b>Favicon → browser tab/bookmarks mein website ko represent karne wala small icon.</b></p><p class="lv3">Tumhare project mein:</p><div class="cb lv3"><pre><code>app/
├── favicon.ico
├── layout.tsx
└── page.tsx</code></pre></div><p class="lv3"><code>app/favicon.ico</code> rakhne se Next.js usko favicon ke taur par use karta hai.</p><h3 id="og-image" class="lv3">OG Image</h3><p class="lv3"><b>OG image → jab tumhari website ka link social media par share hota hai to represent karne wali image.</b></p><p class="lv3">Static OG image:</p><div class="cb lv3"><pre><code>app/
├── opengraph-image.jpg
├── layout.tsx
└── page.tsx</code></pre></div><p class="lv3">Ye application ka OG image ban sakti hai.</p><p class="lv3">Specific route ke liye:</p><div class="cb lv3"><pre><code>app/
├── opengraph-image.jpg
└── blog/
    ├── opengraph-image.jpg
    └── page.tsx</code></pre></div><p class="lv3"><code>blog/opengraph-image.jpg</code> <b>blog route ke liye more specific</b> hai, isliye upar wale general OG image par precedence rakhti hai.</p><h3 id="generated-og-image" class="lv3">Generated OG Image</h3><p class="lv3">Agar har blog post ke liye <b>automatically different OG image</b> generate karni ho, to:</p><div class="cb lv3"><pre><code>app/
└── blog/
    └── [slug]/
        └── opengraph-image.tsx</code></pre></div><p class="lv3">Aur:</p><div class="cb lv3"><pre><code><span class="kw">import</span> { ImageResponse } <span class="kw">from</span> <span class="st">'next/og'</span>

<span class="kw">export</span> <span class="kw">default</span> <span class="kw">async</span> <span class="kw">function</span> Image({</code></pre></div><p class="lv3">params,</p><div class="cb lv3"><pre><code>}: {</code></pre></div><p class="lv3">params: Promise&lt;{ slug: string }&gt;</p><div class="cb lv3"><pre><code>}) {
  <span class="kw">const</span> { slug } = <span class="kw">await</span> params

  <span class="kw">return</span> <span class="kw">new</span> ImageResponse(
    &lt;div&gt;</code></pre></div><p class="lv3">My Blog Post</p><div class="cb lv3"><pre><code>    &lt;/div&gt;
  )
}</code></pre></div><p class="lv3"><b><code>ImageResponse</code></b><b> → JSX + CSS se dynamic image generate karta hai.</b></p><p class="lv3">Source ke mutabiq ye data-dependent OG images ke liye useful hai.</p><h3 id="cache-same-data-ko-dobara-fetch-hone-se-" class="lv3">cache() — same data ko dobara fetch hone se bachana</h3><p class="lv3">Kabhi same blog post data <b>2 jagah</b> chahiye:</p><div class="cb lv3"><pre><code>generateMetadata()
        ↓
     getPost()

Page()
        ↓
     getPost()</code></pre></div><p class="lv3">Agar dono same <code>getPost()</code> call kar rahe hain, React ka <code>cache()</code> return value ko memoize kar sakta hai:</p><div class="cb lv3"><pre><code><span class="kw">import</span> { cache } <span class="kw">from</span> <span class="st">'react'</span>

<span class="kw">export</span> <span class="kw">const</span> getPost = cache(<span class="kw">async</span> (slug: string) =&gt; {
  <span class="kw">const</span> post = <span class="kw">await</span> db.query.posts.findFirst(...)
  <span class="kw">return</span> post
})</code></pre></div><p class="lv3">Phir dono jagah:</p><div class="cb lv3"><pre><code><span class="kw">const</span> post = <span class="kw">await</span> getPost(slug)</code></pre></div><p class="lv3">use kar sakte hain. Source ke example mein isi purpose ke liye React <code>cache</code> use kiya gaya hai.</p><h3 id="streaming-metadata" class="lv3">Streaming Metadata</h3><p class="lv3">Dynamic page mein <code>generateMetadata()</code> ko data aane mein time lag sakta hai.</p><p class="lv3">Next.js dynamically rendered pages mein metadata ko separately stream kar sakta hai, taake <b>UI ko metadata ka wait na karna pade</b>.</p><p class="lv3">Simple:</p><div class="cb lv3"><pre><code>Page rendering
     ↓
UI ready
     ↓
UI browser ko mil sakti hai
     ↓
generateMetadata complete
     ↓
metadata HTML mein inject</code></pre></div><p class="lv3">Prerendered pages mein streaming metadata use nahi hoti because metadata build time par resolve ho jati hai.</p><h3 id="tumhare-liye-core-mental-model" class="lv3">Tumhare liye core mental model</h3><div class="cb lv3"><pre><code>Metadata
│
├── metadata
│     └── fixed metadata
│
├── generateMetadata()
│     └── dynamic metadata
│
├── favicon.ico
│     └── browser/site icon
│
├── opengraph-image.jpg
│     └── social sharing image
│
├── opengraph-image.tsx
│     └── dynamic OG image
│
└── robots.txt / sitemap.xml
      └── search-engine related files</code></pre></div></section><section><h2 id="route-handlers-simple-beginner-explanati"><i>20</i>Route Handlers — simple beginner explanation</h2><p class="lv2"><b>Route Handler → Next.js mein backend/API endpoint banane ka tareeqa.</b></p><p class="lv2"><code>page.tsx</code> normally <b>UI/page</b> banata hai, jabke <code>route.ts</code> <b>HTTP requests handle</b> karta hai.</p><h3 id="1-route-handler-kahan-banta-hai" class="lv3">1. Route Handler kahan banta hai?</h3><p class="lv3"><code>app</code> folder ke andar <code>route.ts</code> file:</p><div class="cb lv3"><pre><code>app/
└── api/
    └── route.ts
<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> GET(request: Request) {   <span class="cm">// GET request handle</span>
}</code></pre></div><ul class="lv3"><li><code>route.ts</code> → Route Handler ki special file.</li><li><code>GET</code> → GET HTTP request handle karega.</li><li><code>request</code> → incoming request.</li><li><code>Request</code> → Web API ka request type.</li></ul><p class="lv3">Route Handlers <b>sirf </b><b><code>app</code></b><b> directory</b> mein available hain. Source ke mutabiq ye <code>pages</code> directory ke API Routes ka equivalent hain.</p><h3 id="2-page-tsx-vs-route-ts" class="lv3">2. page.tsx vs route.ts</h3><p class="lv3">Ye difference sabse important hai:</p><div class="cb lv3"><div class="fn">page.tsx</div><pre><code>   ↓
UI / webpage

route.ts
   ↓
HTTP request / response</code></pre></div><p class="lv3">Example:</p><div class="cb lv3"><pre><code>app/
├── page.tsx
└── api/
    └── route.ts</code></pre></div><p class="lv3">URLs:</p><div class="cb lv3"><pre><code>/       → page.tsx
/api    → route.ts</code></pre></div><p class="lv3"><code>page.tsx</code> browser ko webpage UI dega.</p><p class="lv3"><code>route.ts</code> API response de sakta hai.</p><h3 id="3-http-methods" class="lv3">3. HTTP Methods</h3><p class="lv3">Route Handlers ye methods support karte hain:</p><p class="lv3">GET</p><p class="lv3">POST</p><p class="lv3">PUT</p><p class="lv3">PATCH</p><p class="lv3">DELETE</p><p class="lv3">HEAD</p><p class="lv3">OPTIONS</p><p class="lv3">Example:</p><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> GET(request: Request) {       <span class="cm">// GET request</span>
}

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> POST(request: Request) {      <span class="cm">// POST request</span>
}

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> DELETE(request: Request) {    <span class="cm">// DELETE request</span>
}</code></pre></div><p class="lv3">Agar unsupported method call ho, Next.js <code>405 Method Not Allowed</code> response deta hai.</p><h3 id="4-response-kaise-return-hota-hai" class="lv3">4. Response kaise return hota hai?</h3><p class="lv3">Simple example:</p><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> GET() {                        <span class="cm">// GET request handle</span>
  <span class="kw">return</span> Response.json({                             <span class="cm">// JSON response return</span></code></pre></div><p class="lv3">message: 'Hello World',                          // response data</p><div class="cb lv3"><pre><code>  })
}</code></pre></div><p class="lv3">Request:</p><p class="lv3">GET /api</p><p class="lv3">Response:</p><div class="cb lv3"><pre><code>{
  <span class="st">"message"</span>: <span class="st">"Hello World"</span>
}</code></pre></div><p class="lv3">Yahan:</p><ul class="lv3"><li><code>Response</code> → Web API ka response object.</li><li><code>Response.json()</code> → JSON response create karta hai.</li><li><code>{ message: 'Hello World' }</code> → response ka data.</li></ul><h3 id="5-nextrequest-aur-nextresponse" class="lv3">5. NextRequest aur NextResponse</h3><p class="lv3">Next.js native <code>Request</code> aur <code>Response</code> ke saath apne extended versions bhi provide karta hai:</p><p class="lv3">Request</p><p class="lv3">Response</p><p class="lv3">↓ Next.js extensions</p><p class="lv3">NextRequest</p><p class="lv3">NextResponse</p><p class="lv3">Ye advanced use cases mein convenient helpers provide karte hain.</p><h3 id="6-route-handler-aur-caching" class="lv3">6. Route Handler aur caching</h3><p class="lv3">Source ke according <b>Route Handlers default mein cached nahi hote</b>.</p><p class="lv3">GET ko explicitly cache karna ho to route configuration use kar sakte ho:</p><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">const</span> dynamic = <span class="st">'force-static'</span>             <span class="cm">// GET ko static/cacheable mode</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> GET() {                      <span class="cm">// GET handler</span>
  <span class="kw">const</span> res = <span class="kw">await</span> fetch(<span class="st">'https://example.com'</span>)   <span class="cm">// data fetch</span>

  <span class="kw">const</span> data = <span class="kw">await</span> res.json()                    <span class="cm">// JSON data</span>

  <span class="kw">return</span> Response.json({ data })                   <span class="cm">// response</span>
}</code></pre></div><p class="lv3 box warn">Important:</p><p class="lv3">GET</p><div class="cb lv3"><pre><code>→ caching opt-in possible</code></pre></div><p class="lv3">POST</p><p class="lv3">PUT</p><p class="lv3">PATCH</p><p class="lv3">DELETE</p><div class="cb lv3"><pre><code>→ cached nahi hote</code></pre></div><p class="lv3">Source specifically kehta hai ke same <code>route.ts</code> mein cached <code>GET</code> ke saath doosre HTTP methods hone se woh automatically cached nahi hote.</p><h3 id="7-cache-components-ke-saath-route-handle" class="lv3">7. Cache Components ke saath Route Handler</h3><p class="lv3">Agar <b>Cache Components enabled</b> hain, to GET Route Handlers normal UI routes ke similar model follow karte hain.</p><h4 id="static-example" class="lv4">Static example</h4><div class="cb lv4"><pre><code><span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> GET() {
  <span class="kw">return</span> Response.json({</code></pre></div><p class="lv4">projectName: 'Next.js',</p><div class="cb lv4"><pre><code>  })
}</code></pre></div><p class="lv4">Ismein:</p><ul class="lv4"><li>database nahi</li><li>request-specific information nahi</li><li>random value nahi</li></ul><p class="lv4">Isliye source ke mutabiq ye <b>build time par prerender</b> ho sakta hai.</p><h4 id="dynamic-example" class="lv4">Dynamic example</h4><div class="cb lv4"><pre><code><span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> GET() {
  <span class="kw">return</span> Response.json({</code></pre></div><p class="lv4">randomNumber: Math.random(),</p><div class="cb lv4"><pre><code>  })
}</code></pre></div><p class="lv4"><code>Math.random()</code> predictable nahi hai.</p><p class="lv4">Isliye build ke waqt prerendering yahan stop ho kar request-time rendering ki taraf defer hoti hai.</p><h4 id="runtime-data-example" class="lv4">Runtime data example</h4><div class="cb lv4"><pre><code><span class="kw">import</span> { headers } <span class="kw">from</span> <span class="st">'next/headers'</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> GET() {
  <span class="kw">const</span> headersList = <span class="kw">await</span> headers()

  <span class="kw">const</span> userAgent = headersList.get(<span class="st">'user-agent'</span>)

  <span class="kw">return</span> Response.json({</code></pre></div><p class="lv4">userAgent,</p><div class="cb lv4"><pre><code>  })
}</code></pre></div><p class="lv4">Yahan:</p><p class="lv4">headers()</p><p class="lv4">request-specific information access kar raha hai.</p><p class="lv4">Isliye prerendering build time par complete nahi hoti.</p><p class="lv4">Source ke examples mein <code>Math.random()</code> ko non-deterministic operation aur <code>headers()</code> ko runtime/request-specific data ke example ke taur par use kiya gaya hai.</p><h3 id="8-database-use-cache" class="lv3">8. Database + use cache</h3><p class="lv3">Agar Route Handler ko database se data lena hai aur us data ko cache karna hai, source ke mutabiq <code>use cache</code> ko <b>directly Route Handler body mein nahi lagate</b>.</p><p class="lv3">Helper function banao:</p><div class="cb lv3"><pre><code><span class="kw">import</span> { cacheLife } <span class="kw">from</span> <span class="st">'next/cache'</span>             <span class="cm">// cacheLife import</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> GET() {                      <span class="cm">// GET handler</span>
  <span class="kw">const</span> products = <span class="kw">await</span> getProducts()             <span class="cm">// cached helper se products</span>

  <span class="kw">return</span> Response.json(products)                   <span class="cm">// JSON response</span>
}

<span class="kw">async</span> <span class="kw">function</span> getProducts() {                     <span class="cm">// helper function</span>
  <span class="st">'use cache'</span>                                       <span class="cm">// is function ko cache</span></code></pre></div><p class="lv3">cacheLife('hours')                               // cache profile: hours</p><div class="cb lv3"><pre><code>  <span class="kw">return</span> <span class="kw">await</span> db.query(<span class="st">'SELECT * FROM products'</span>)  <span class="cm">// database query</span>
}</code></pre></div><p class="lv3 box warn">Important structure:</p><div class="cb lv3"><pre><code>GET()
 │
 └── getProducts()
       │
       ├── <span class="st">'use cache'</span>
       ├── cacheLife()
       └── database query</code></pre></div><p class="lv3 box tip">Yani <b>Route Handler request handle karta hai</b>, aur helper function <b>database data ko cache karta hai</b>.</p><p class="lv3">Source ke mutabiq cached response <code>cacheLife</code> ke according revalidate hota hai jab new request aati hai.</p><h3 id="9-route-ts-aur-page-tsx-same-level-par-n" class="lv3">9. route.ts aur page.tsx same level par nahi ho sakte</h3><p class="lv3">Ye important rule hai:</p><div class="cb lv3"><pre><code>app/
├── page.tsx
└── route.ts</code></pre></div><p class="lv3">❌ Conflict</p><p class="lv3">Lekin:</p><div class="cb lv3"><pre><code>app/
├── page.tsx
└── api/
    └── route.ts</code></pre></div><p class="lv3">✅ Valid</p><p class="lv3">Source ke examples:</p><p class="lv3">Page                         Route                  Result</p><div class="cb lv3"><pre><code>app/page.js                  app/route.js           Conflict

app/page.js                  app/api/route.js       Valid

app/[user]/page.js           app/api/route.js       Valid</code></pre></div><p class="lv3">Simple rule:</p><p class="lv3"><b>Same route segment par </b><b><code>page.tsx</code></b><b> aur </b><b><code>route.ts</code></b><b> ek saath nahi ho sakte.</b></p><h3 id="10-route-handlers-layouts-client-navigat" class="lv3">10. Route Handlers layouts/client navigation ka part nahi hain</h3><p class="lv3"><code>page.tsx</code>:</p><div class="cb lv3"><pre><code>layout
  ↓
page</code></pre></div><p class="lv3">Route Handler:</p><div class="cb lv3"><pre><code>HTTP Request
     ↓
route.ts
     ↓
Response</code></pre></div><p class="lv3">Source specifically kehta hai ke Route Handlers <b>layouts ya client-side navigation mein </b><b><code>page</code></b><b> ki tarah participate nahi karte</b>.</p><h3 id="11-dynamic-route-handler" class="lv3">11. Dynamic Route Handler</h3><p class="lv3">Route Handlers dynamic folders ke andar bhi ho sakte hain:</p><div class="cb lv3"><pre><code>app/
└── users/
    └── [id]/
        └── route.ts</code></pre></div><p class="lv3">URL:</p><p class="lv3">/users/123</p><p class="lv3">/users/456</p><p class="lv3">/users/789</p><p class="lv3">Har <code>id</code> ke liye same Route Handler use hoga.</p><p class="lv3">Source ka TypeScript helper example:</p><div class="cb lv3"><pre><code><span class="kw">import</span> <span class="kw">type</span> { NextRequest } <span class="kw">from</span> <span class="st">'next/server'</span>

<span class="kw">export</span> <span class="kw">async</span> <span class="kw">function</span> GET(</code></pre></div><p class="lv3">_req: NextRequest,</p><p class="lv3">ctx: RouteContext&lt;'/users/[id]'&gt;</p><div class="cb lv3"><pre><code>) {
  <span class="kw">const</span> { id } = <span class="kw">await</span> ctx.params

  <span class="kw">return</span> Response.json({ id })
}</code></pre></div><h4 id="ismein" class="lv4">Ismein:</h4><ul class="lv4"><li><code>NextRequest</code> → Next.js ka extended request type.</li><li><code>ctx</code> → route context.</li><li><code>RouteContext&lt;'/users/[id]'&gt;</code> → is route ke context ka TypeScript type.</li><li><code>ctx.params</code> → dynamic route parameters.</li><li><code>id</code> → URL se mila dynamic value.</li></ul><p class="lv4">Agar request:</p><p class="lv4">/users/123</p><p class="lv4">to:</p><p class="lv4">id = "123"</p><p class="lv4">aur response:</p><div class="cb lv4"><pre><code>{
  <span class="st">"id"</span>: <span class="st">"123"</span>
}</code></pre></div><h3 id="final-mental-model-2" class="lv3">Final mental model</h3><div class="cb lv3"><pre><code>Route Handler
│
├── route.ts
│     └── API / HTTP request handler
│
├── GET
├── POST
├── PUT
├── PATCH
├── DELETE
├── HEAD
└── OPTIONS
       │
       ↓
    Response</code></pre></div></section><section><h2 id="proxy-simple-beginner-explanation"><i>21</i>Proxy — simple beginner explanation</h2><p class="lv2"><b>Proxy → request complete hone se pehle code run karne ka mechanism hai.</b></p><p class="lv2">Next.js 16 mein <b>Middleware ka naam change karke Proxy</b> kar diya gaya hai. Functionality same hai.</p><p class="lv2">Simple mental model:</p><div class="cb lv2"><pre><code>User Request
     ↓
   Proxy
     ↓
Request ko check/modify
     ↓
Next.js route/page
     ↓
Response</code></pre></div><h3 id="1-proxy-kya-kar-sakta-hai" class="lv3">1. Proxy kya kar sakta hai?</h3><p class="lv3">Incoming request ko dekh kar Proxy:</p><ul class="lv3"><li><b>Redirect</b> kar sakta hai → user ko doosre URL par bhejna.</li><li><b>Rewrite</b> kar sakta hai → request ko internally doosre page/route par bhejna.</li><li><b>Request headers</b> modify kar sakta hai.</li><li><b>Response headers</b> modify kar sakta hai.</li><li><b>Direct response</b> de sakta hai.</li></ul><h3 id="2-proxy-file-kahan-hoti-hai" class="lv3">2. Proxy file kahan hoti hai?</h3><p class="lv3">Project root mein:</p><p class="lv3">next-learning/</p><div class="cb lv3"><pre><code>├── app/
├── public/
├── proxy.ts
├── package.json
└── ...</code></pre></div><p class="lv3">Ya agar project <code>src</code> use karta hai:</p><p class="lv3">src/</p><div class="cb lv3"><pre><code>├── app/
└── proxy.ts</code></pre></div><p class="lv3 box warn">Important: <b>ek project mein sirf ek </b><b><code>proxy.ts</code></b><b> file supported hai.</b></p><p class="lv3">Lekin us file ke andar logic ko separate files/modules mein divide kar sakte ho.</p><h3 id="3-basic-proxy" class="lv3">3. Basic Proxy</h3><div class="cb lv3"><pre><code><span class="kw">import</span> { NextResponse } <span class="kw">from</span> <span class="st">'next/server'</span>          <span class="cm">// NextResponse import</span>
<span class="kw">import</span> <span class="kw">type</span> { NextRequest } <span class="kw">from</span> <span class="st">'next/server'</span>     <span class="cm">// NextRequest type import</span>

<span class="kw">export</span> <span class="kw">function</span> proxy(request: NextRequest) {      <span class="cm">// Proxy function</span>
  <span class="kw">return</span> NextResponse.redirect(                    <span class="cm">// redirect response</span></code></pre></div><p class="lv3">new URL('/home', request.url)                   // /home par redirect</p><div class="cb lv3"><pre><code>  )
}</code></pre></div><p class="lv3">Iska simple execution:</p><div class="cb lv3"><pre><code>User /about open karta hai
        ↓
proxy() run
        ↓
request receive
        ↓
NextResponse.redirect()
        ↓
/home</code></pre></div><h3 id="4-request" class="lv3">4. request</h3><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">function</span> proxy(request: NextRequest) {</code></pre></div><p class="lv3"><code>request</code> → <b>incoming HTTP request ki information</b>.</p><p class="lv3 box tip">Yani Proxy ko pata ho sakta hai ke request kis URL/path se aa rahi hai aur source ke mutabiq incoming request properties ke basis par logic kiya ja sakta hai.</p><h3 id="5-nextresponse" class="lv3">5. NextResponse</h3><p class="lv3">NextResponse.redirect(...)</p><p class="lv3"><code>NextResponse</code> → Next.js ka response helper hai.</p><p class="lv3">Is example mein:</p><p class="lv3">NextResponse.redirect(</p><p class="lv3">new URL('/home', request.url)</p><div class="cb lv3"><pre><code>)</code></pre></div><p class="lv3">matlab:</p><p class="lv3"><b>current request ko </b><b><code>/home</code></b><b> par redirect karo.</b></p><h3 id="6-matcher" class="lv3">6. matcher</h3><p class="lv3 box warn">Sabse important part:</p><div class="cb lv3"><pre><code><span class="kw">export</span> <span class="kw">const</span> config = {</code></pre></div><p class="lv3">matcher: '/about/:path*',</p><div class="cb lv3"><pre><code>}</code></pre></div><p class="lv3"><code>matcher</code> → decide karta hai <b>Proxy kin paths par run karega</b>.</p><p class="lv3">Example:</p><p class="lv3">/about</p><p class="lv3">/about/team</p><p class="lv3">/about/contact</p><p class="lv3"><code>/about/:path*</code> in paths ko match karne ke liye use ho sakta hai.</p><p class="lv3">Agar Proxy ko sirf <code>/about</code> section ke liye chalana hai, <code>matcher</code> useful hai.</p><h3 id="7-complete-example" class="lv3">7. Complete example</h3><div class="cb lv3"><pre><code><span class="kw">import</span> { NextResponse } <span class="kw">from</span> <span class="st">'next/server'</span>          <span class="cm">// NextResponse import</span>
<span class="kw">import</span> <span class="kw">type</span> { NextRequest } <span class="kw">from</span> <span class="st">'next/server'</span>     <span class="cm">// Request type import</span>

<span class="kw">export</span> <span class="kw">function</span> proxy(request: NextRequest) {      <span class="cm">// Proxy function</span>
  <span class="kw">return</span> NextResponse.redirect(                    <span class="cm">// Redirect response</span></code></pre></div><p class="lv3">new URL('/home', request.url)                   // User ko /home bhejo</p><div class="cb lv3"><pre><code>  )
}

<span class="kw">export</span> <span class="kw">const</span> config = {                             <span class="cm">// Proxy configuration</span></code></pre></div><p class="lv3">matcher: '/about/:path*',                         // Sirf /about paths match</p><div class="cb lv3"><pre><code>}</code></pre></div><p class="lv3">Execution:</p><div class="cb lv3"><pre><code>User
 ↓
/about
 ↓
matcher check
 ↓
match ho gaya
 ↓
proxy()
 ↓
redirect
 ↓
/home</code></pre></div><h3 id="8-proxy-kab-use-karna-hai" class="lv3">8. Proxy kab use karna hai?</h3><p class="lv3">Source ke according common uses:</p><div class="cb lv3"><pre><code>Proxy
│
├── Headers modify
│
├── A/B testing ke basis par rewrite
│
└── Request properties ke basis par redirect</code></pre></div><p class="lv3"><b>Simple redirect ke liye</b> pehle <code>next.config.ts</code> ka <code>redirects</code> configuration consider karna chahiye.</p><p class="lv3">Proxy tab useful hai jab tumhein <b>request ki information ya complex logic</b> chahiye.</p><h3 id="9-proxy-kis-kaam-ke-liye-nahi-hai" class="lv3">9. Proxy kis kaam ke liye nahi hai?</h3><p class="lv3">Ye important hai:</p><p class="lv3"><b>Proxy slow data fetching ke liye intended nahi hai.</b></p><p class="lv3">Aur source ke according Proxy ko <b>full session management ya authorization solution</b> ke taur par use nahi karna chahiye.</p><p class="lv3">Permission-based redirects jaisi <b>optimistic checks</b> ke liye use ho sakta hai.</p><p class="lv3">Also, Proxy mein <code>fetch()</code> ke:</p><p class="lv3">options.cache</p><p class="lv3">options.next.revalidate</p><p class="lv3">options.next.tags</p><p class="lv3">ka effect nahi hota.</p><h3 id="route-handler-vs-proxy" class="lv3">Route Handler vs Proxy</h3><p class="lv3">Ye dono confuse mat karna:</p><div class="cb lv3"><pre><code>Proxy
  ↓
Request complete hone SE PEHLE
  ↓
Request ko check/modify/redirect/rewrite
Route Handler
  ↓
HTTP method handle
  ↓</code></pre></div><p class="lv3">GET / POST / PUT / DELETE ...</p><div class="cb lv3"><pre><code>  ↓
Response</code></pre></div></section><section><h2 id="deploying-simple-beginner-explanation"><i>22</i>Deploying — simple beginner explanation</h2><p class="lv2"><b>Deployment → apni Next.js application ko development computer se production/server par publish karna, taake real users website use kar saken.</b></p><p class="lv2">Source ke mutabiq Next.js ko mainly <b>4 ways</b> se deploy kiya ja sakta hai:</p><div class="cb lv2"><pre><code>Next.js Deployment
│
├── Node.js server     → All features
├── Docker             → All features
├── Static <span class="kw">export</span>      → Limited features
└── Adapters           → Platform ke hisaab se vary</code></pre></div><h3 id="1-node-js-server" class="lv3">1. Node.js Server</h3><p class="lv3"><b>Node.js deployment → Next.js application ko Node.js server par run karna.</b></p><p class="lv3">Tumhare <code>package.json</code> mein ye scripts honi chahiye:</p><div class="cb lv3"><pre><code>{
  <span class="st">"scripts"</span>: {
    <span class="st">"dev"</span>: <span class="st">"next dev"</span>,       <span class="cm">// Development server</span>
    <span class="st">"build"</span>: <span class="st">"next build"</span>,   <span class="cm">// Production build</span>
    <span class="st">"start"</span>: <span class="st">"next start"</span>    <span class="cm">// Production server start</span>
  }
}</code></pre></div><p class="lv3">Phir:</p><div class="cb lv3"><pre><code>npm run build</code></pre></div><ul class="lv3"><li><code>next build</code> → application ka production build banata hai.</li></ul><p class="lv3">Uske baad:</p><div class="cb lv3"><pre><code>npm run start</code></pre></div><ul class="lv3"><li><code>next start</code> → production Next.js server start karta hai.</li></ul><p class="lv3">Simple:</p><div class="cb lv3"><pre><code>Code
 ↓
npm run build
 ↓
Production build
 ↓
npm run start
 ↓
Node.js server
 ↓
Users</code></pre></div><p class="lv3">Source ke mutabiq Node.js deployment <b>all Next.js features</b> support karta hai.</p><h3 id="2-docker" class="lv3">2. Docker</h3><p class="lv3"><b>Docker deployment → Next.js application ko Docker container ke andar package karke run karna.</b></p><p class="lv3">Simple concept:</p><div class="cb lv3"><pre><code>Next.js App
    ↓
Docker Image
    ↓
Docker Container
    ↓
Server</code></pre></div><p class="lv3">Docker ka benefit yahan ye hai ke application aur uski required runtime/dependencies ko container ke andar package karke different Docker-supporting platforms par run kiya ja sakta hai.</p><p class="lv3">Source ke mutabiq Docker deployment bhi <b>all Next.js features</b> support karta hai.</p><p class="lv3">Development ke liye source specifically Mac/Windows par normally:</p><div class="cb lv3"><pre><code>npm run dev</code></pre></div><p class="lv3">use karne ko prefer karta hai instead of Docker, performance considerations ki wajah se.</p><h3 id="3-static-export" class="lv3">3. Static Export</h3><p class="lv3"><b>Static export → Next.js app ko static HTML/CSS/JS files mein export karna.</b></p><p class="lv3">Ye files phir aise server par host ho sakti hain jo static files serve karta ho, jaise source mein:</p><ul class="lv3"><li>AWS S3</li><li>Nginx</li><li>Apache</li></ul><p class="lv3">Simple:</p><div class="cb lv3"><pre><code>Next.js App
    ↓
Static Export
    ↓
HTML + CSS + JS
    ↓
Static Hosting</code></pre></div><p class="lv3">Lekin important:</p><p class="lv3"><b>Static export mein woh Next.js features available nahi hote jo server require karte hain.</b></p><p class="lv3">Isliye source ise <b>Limited</b> feature support kehta hai.</p><h3 id="4-adapters" class="lv3">4. Adapters</h3><p class="lv3"><b>Adapter → Next.js application ko kisi specific platform ki infrastructure ke according adapt karne ka mechanism.</b></p><p class="lv3">Simple:</p><div class="cb lv3"><div class="fn">Next.js</div><pre><code>   ↓
Adapter
   ↓
Specific Platform</code></pre></div><p class="lv3">Source ke mutabiq adapters ka feature support <b>vary</b> karta hai.</p><h3 id="verified-adapters" class="lv3">Verified Adapters</h3><p class="lv3">Source mein verified adapters ke examples:</p><ul class="lv3"><li>Vercel</li><li>Bun</li></ul><p class="lv3">Verified adapters open source hain aur Next.js compatibility test suite run karte hain.</p><p class="lv3">Other platforms apni Next.js integrations provide karte hain, including:</p><ul class="lv3"><li>Appwrite</li><li>AWS Amplify</li><li>Cloudflare</li><li>Deno Deploy</li><li>Firebase App Hosting</li><li>Netlify</li></ul><p class="lv3">Source ke according in platforms ki feature support/compatibility vary kar sakti hai.</p><h3 id="tumhare-project-ke-context-mein" class="lv3">Tumhare project ke context mein</h3><p class="lv3">Abhi tumhara project:</p><p class="lv3">next-learning/</p><div class="cb lv3"><pre><code>├── app/
├── public/
├── package.json
├── next.config.ts
└── ...</code></pre></div><p class="lv3">Development mein:</p><div class="cb lv3"><pre><code>npm run dev</code></pre></div><p class="lv3">Aur jab project production ke liye ready ho:</p><div class="cb lv3"><pre><code>npm run build</code></pre></div><p class="lv3">phir:</p><div class="cb lv3"><pre><code>npm run start</code></pre></div><p class="lv3"><b>Ye Node.js deployment ka basic process hai.</b></p><h3 id="sabse-important-difference" class="lv3">Sabse important difference</h3><div class="cb lv3"><pre><code>npm run dev
        ↓
Development
        ↓
Tum coding/test kar rahe ho


npm run build
        ↓
Production build
        ↓

npm run start
        ↓
Production server</code></pre></div><p class="lv3">Aur deployment options ko yaad rakhne ka easiest way:</p><div class="tw lv3"><table><tr><th><b>Option</b></th><th><b>Simple meaning</b></th><th><b>Feature support</b></th></tr><tr><td><b>Node.js server</b></td><td>Next.js ko Node server par run karo</td><td>All</td></tr><tr><td><b>Docker</b></td><td>Next.js ko container mein run karo</td><td>All</td></tr><tr><td><b>Static export</b></td><td>Static HTML/CSS/JS files</td><td>Limited</td></tr><tr><td><b>Adapters</b></td><td>Specific platform ke liye adapt</td><td>Varies</td></tr></table></div></section><section><h2 id="upgrading"><i>23</i>Upgrading</h2><p class="lv2"><b>Upgrading</b> page ka main purpose hai: <b>Next.js ko newer version par update karna</b>. Tumhare beginner level ke liye is page se ye core concepts samajhne hain:</p><h3 id="1-next-upgrade" class="lv3">1. next upgrade</h3><p class="lv3">Next.js 16.1.0+ mein latest Next.js version par upgrade karne ke liye:</p><div class="cb lv3"><pre><code>pnpm next upgrade</code></pre></div><ul class="lv3"><li><code>pnpm</code> → package manager</li><li><code>next</code> → Next.js ka command-line tool</li><li><code>upgrade</code> → Next.js ko latest version par update karne ka command</li></ul><p class="lv3">Yani:</p><p class="lv3"><b><code>pnpm next upgrade</code></b><b> → mere project ka Next.js latest version par update karo.</b></p><p class="lv3">Docs ke mutabiq, <b>Next.js 16.1.0 se pehle</b> versions mein <code>upgrade</code> command available nahi hai.</p><p class="lv3">Un older versions ke liye:</p><div class="cb lv3"><pre><code>npx @next/codemod@canary upgrade latest</code></pre></div><ul class="lv3"><li><code>npx</code> → package ko temporarily run karta hai</li><li><code>@next/codemod</code> → Next.js ka upgrade/codemod tool</li><li><code>upgrade latest</code> → latest Next.js version par upgrade</li></ul><h3 id="2-manual-upgrade" class="lv3">2. Manual upgrade</h3><p class="lv3">Agar command ke bajaye manually latest packages install karne hain:</p><div class="cb lv3"><pre><code>pnpm i next@latest react@latest react-dom@latest eslint-config-next@latest</code></pre></div><ul class="lv3"><li><code>pnpm</code> → package manager</li><li><code>i</code> → <code>install</code> ka short form</li><li><code>next@latest</code> → Next.js ka latest version</li><li><code>react@latest</code> → React ka latest version</li><li><code>react-dom@latest</code> → React DOM ka latest version</li><li><code>eslint-config-next@latest</code> → Next.js ki latest ESLint configuration</li></ul><p class="lv3">Simple:</p><div class="cb lv3"><pre><code>Next.js project
     ↓
next@latest</code></pre></div><p class="lv3">react@latest</p><p class="lv3">react-dom@latest</p><div class="cb lv3"><pre><code>eslint-config-next@latest
     ↓
Updated project</code></pre></div><p class="lv3 box warn"><b>Important:</b> sirf <code>next</code> update nahi ho raha; docs yahan Next.js ke saath related React packages aur ESLint config ko bhi latest karne ko keh rahe hain.</p><h3 id="3-canary-version" class="lv3">3. Canary version</h3><p class="lv3"><b>Canary = Next.js ki latest development/pre-release version.</b></p><p class="lv3">Agar latest stable version properly kaam kar raha hai aur tum newest canary features test karna chahte ho:</p><div class="cb lv3"><pre><code>pnpm add next@canary</code></pre></div><ul class="lv3"><li><code>pnpm</code> → package manager</li><li><code>add</code> → package install/update karo</li><li><code>next@canary</code> → Next.js ki canary version</li></ul><p class="lv3">Docs ka sequence:</p><div class="cb lv3"><pre><code>Latest stable Next.js
        ↓
Check karo sab properly working hai
        ↓
next@canary install karo</code></pre></div><p class="lv3 box tip">Yani canary ko directly bina stable version verify kiye use karne ka source yahan recommendation nahi de raha.</p><h3 id="4-canary-mein-kya-available-hai" class="lv3">4. Canary mein kya available hai?</h3><p class="lv3">Is source ke mutabiq currently Authentication se related ye features canary mein available hain:</p><ul class="lv3"><li><code>forbidden</code></li><li><code>unauthorized</code></li><li><code>forbidden.js</code></li><li><code>unauthorized.js</code></li><li><code>authInterrupts</code></li></ul><p class="lv3">Ye authentication/authorization handling se related Next.js features hain.</p><h3 id="tumhare-liye-sabse-important" class="lv3">Tumhare liye sabse important</h3><p class="lv3">Abhi tum <b>Next.js 16.3.3</b> use kar rahe ho, isliye tumhare liye <code>next upgrade</code> command available hone wali range mein hai.</p><p class="lv3">Beginner ke taur par is page ka simple mental model yaad rakho:</p><div class="cb lv3"><pre><code>Stable Latest
    ↓
pnpm next upgrade
    ↓
Latest stable Next.js

Canary
    ↓
pnpm add next@canary
    ↓
Latest development/pre-release features</code></pre></div></section></main></div>
<script>document.querySelectorAll('.cb').forEach(function(b){var x=document.createElement('button');x.textContent='Copy';x.className='cp';x.onclick=function(){var t=b.querySelector('pre').innerText;try{navigator.clipboard.writeText(t);x.textContent='Copied';setTimeout(function(){x.textContent='Copy'},1200)}catch(e){}};b.appendChild(x)});</script>
</body></html>
