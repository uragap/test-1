Como desarrolladores, a menudo nos enfrentamos con decisiones que afectarán todo arquitectura de nuestras aplicaciones. Una de las decisiones centrales que los desarrolladores web deben make es donde implementar la lógica y el renderizado en su aplicación. Esto puede ser Es difícil, ya que hay varias formas diferentes de crear un sitio web.

Nuestra comprensión de este espacio está informada por nuestro trabajo en Chrome hablando con sitios grandes en los últimos años. En términos generales, alentaríamos los desarrolladores deben considerar la representación del servidor o la representación estática en un enfoque de rehidratación.

Para entender mejor las arquitecturas que estamos eligiendo cuando hacemos esta decisión, necesitamos tener una comprensión sólida de cada enfoque y terminología consistente para usar cuando se habla de ellos. Las diferencias entre Estos enfoques ayudan a ilustrar las compensaciones de renderizar en la web a través de La lente del rendimiento.


Terminology {: #terminology }

Rendering

    SSR: Server-Side Rendering - rendering a client-side or universal app to HTML on the server.
    CSR: Client-Side Rendering - rendering an app in a browser, generally using the DOM.
    Rehydration: “booting up” JavaScript views on the client such that they reuse the server-rendered HTML’s DOM tree and data.
    Prerendering: running a client-side application at build time to capture its initial state as static HTML.

Performance

    TTFB: Time to First Byte - seen as the time between clicking a link and the first bit of content coming in.
    FP: First Paint - the first time any pixel gets becomes visible to the user.
    FCP: First Contentful Paint - the time when requested content (article body, etc) becomes visible.
    TTI: Time To Interactive - the time at which a page becomes interactive (events wired up, etc).

Server Rendering {: #server-rendering }

Server rendering generates the full HTML for a page on the server in response
to navigation. This avoids additional round-trips for data fetching and
templating on the client, since it’s handled before the browser gets a
response.

Server rendering generally produces a fast First Paint (FP) and First
Contentful Paint (FCP). Running page logic and rendering on the server makes it
possible to avoid sending lots of JavaScript to the client, which helps achieve
a fast Time to Interactive (TTI). This makes sense, since with server
rendering you’re really just sending text and links to the user’s browser. This
approach can work well for a large spectrum of device and network conditions,
and opens up interesting browser optimizations like streaming document parsing.

Server Rendering {: #server-rendering }

Server rendering generates the full HTML for a page on the server in response
to navigation. This avoids additional round-trips for data fetching and
templating on the client, since it’s handled before the browser gets a
response.

Server Rendering {: #server-rendering }

Server rendering generates the full HTML for a page on the server in response
to navigation. This avoids additional round-trips for data fetching and
templating on the client, since it’s handled before the browser gets a
response.

Server Rendering {: #server-rendering }

Server Rendering {: #server-rendering }

Server Rendering {: #server-rendering }

Server Rendering {: #server-rendering }

Server Rendering {: #server-rendering }
