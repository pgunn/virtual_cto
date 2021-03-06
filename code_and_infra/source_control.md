# Source Control
For as long as you can get away with it, use github to host all your repos. It has a solid UI, broad support (and any programmer you should consider hiring probably has already seen or used it), and its hook support is good enough for most purposes. For each entirely distinct project (meaning they do not share code), make a separate repo. When code is shared between separate coding projects (e.g. as a library), you should choose between:
A) Managing versioning of it as a separate deliverable into an environment. This has some initial overhead but can make it easier to coordinate changes to the library
B) Treating all code that depends on it as distinct parts of the same code repo. This has less overhead but as code complexity increases, its overheads tend to grow faster than the former option

You may eventually need to move to internal repos if you start hitting API rate limits on github, if you have enough repos or activity to otherwise make things cost prohibitive, or if other tooling you might want to use (e.g. Phabricator) requires you to. Hosting your own git repos is fine, but resist doing this if you can't provide an overall experience that's better than github (which is a reasonably high bar).

Avoid other features of Github like Issues (as I said elsewhere, use Jira for that).

Keep most of your repos private, and keep an eye on who has permissions to write to your repos. Require people to setup 2FA for their Github account if you let them use their personal ones, and yank their access as soon as they leave.

Don't let people check passwords or API keys into your repos (even private ones); use a separate system for that. If you keep config management code in a github repo, still keep passwords out of the repo; look into secrets-delivery mechanisms for that.
