As developers, we are often faced with decisions that will affect the entire
architecture of our applications. One of the core decisions web developers must
make is where to implement logic and rendering in their application. This can be
a difficult, since there are a number of different ways to build a website.

Our understanding of this space is informed by our work in Chrome talking to
large sites over the past few years. Broadly speaking, we would encourage
developers to consider server rendering or static rendering over a full
rehydration approach.

In order to better understand the architectures we’re choosing from when we make
this decision, we need to have a solid understanding of each approach and
consistent terminology to use when speaking about them. The differences between
these approaches help illustrate the trade-offs of rendering on the web through
the lens of performance.

## Terminology {: #terminology }

**Rendering**

- **SSR:** Server-Side Rendering - rendering a client-side or universal app to
  HTML on the server.
- **CSR:** Client-Side Rendering - rendering an app in a browser, generally
  using the DOM.
- **Rehydration:**  “booting up” JavaScript views on the client such that they
  reuse the server-rendered HTML’s DOM tree and data.
- **Prerendering:**  running a client-side application at build time to capture
  its initial state as static HTML.

**Performance**

- **TTFB:**  Time to First Byte - seen as the time between clicking a link and
  the first bit of content coming in.
- **FP:**  First Paint - the first time any pixel gets becomes visible to the
  user.
- **FCP:**  First Contentful Paint - the time when requested content (article
  body, etc) becomes visible.
- **TTI:**  Time To Interactive - the time at which a page becomes interactive
  (events wired up, etc).

## Server Rendering {: #server-rendering }

_Server rendering generates the full HTML for a page on the server in response
to navigation. This avoids additional round-trips for data fetching and
templating on the client, since it’s handled before the browser gets a
response._

Server rendering generally produces a fast [First Paint]&nbsp;(FP) and [First
Contentful Paint]&nbsp;(FCP). Running page logic and rendering on the server makes it
possible to avoid sending lots of JavaScript to the client, which helps achieve
a fast [Time to Interactive]&nbsp;(TTI). This makes sense, since with server
rendering you’re really just sending text and links to the user’s browser. This
approach can work well for a large spectrum of device and network conditions,
and opens up interesting browser optimizations like streaming document parsing.

<img src="../../images/2019/02/rendering-on-the-web/server-rendering-tti.png"
alt="Diagram showing server rendering and JS execution affecting FCP and TTI"
width="350">




[First Paint]: https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics#first_paint_and_first_contentful_paint
[First Contentful Paint]: https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics#first_paint_and_first_contentful_paint
[Time to Interactive]: https://developers.google.com/web/tools/lighthouse/audits/time-to-interactive
[Time to First Byte]: https://en.wikipedia.org/wiki/Time_to_first_byte