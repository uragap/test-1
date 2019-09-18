A brief history of SPDY and HTTP/2

That said, unless you are implementing a web server (or a custom client) by
working with raw TCP sockets, then you won’t see any difference: all the new,
low-level framing is performed by the client and server on your behalf. The only
observable differences will be improved performance and availability of new
capabilities like request prioritization, flow control, and server push.

SPDY was an experimental protocol, developed at Google and announced in
mid 2009, whose primary goal was to try to reduce the load latency of web pages
by addressing some of the well-known performance limitations of HTTP/1.1.
Specifically, the outlined project goals were set as follows:

Note: To achieve the 50% PLT improvement, SPDY aimed to make more efficient use
of the underlying TCP connection by introducing a new binary framing layer to
enable request and response multiplexing, prioritization, and header
compression; seeLatency as a Performance Bottleneck{: .external}.

Not long after the initial announcement, Mike Belshe and Roberto Peon, both
software engineers at Google, shared their first results, documentation, and
source code for the experimental implementation of the new SPDY protocol:

Fast-forward to 2012 and the new experimental protocol was supported in Chrome,
Firefox, and Opera, and a rapidly growing number of sites, both large (for example,
Google, Twitter, Facebook) and small, were deploying SPDY within their
infrastructure. In effect, SPDY was on track to become a de facto standard
through growing industry adoption.

Observing this trend, the HTTP Working Group (HTTP-WG) kicked off a new
effort to take the lessons learned from SPDY, build and improve on them, and
deliver an official "HTTP/2" standard. A new charter was drafted, an open call
for HTTP/2 proposals was made, and after a lot of discussion within the working
group, the SPDY specification was adopted as a starting point for the new HTTP/2
protocol.

In early 2015 the IESG reviewed and approved the new HTTP/2 standard for
publication. Shortly after that, the Google Chrome team announced their schedule
to deprecate SPDY and NPN extension for TLS.
