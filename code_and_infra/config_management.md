# Config Management
Use a recent version of Chef (only hosted in github or your own repos). If you have the techical ability to do so, run Chef headless and deliver the codebase to each host for local runs.

Write linters and checks for your chef code to prevent bad or nonfunctional code from affecting your servers.

Be wary of your config management vendor, and keep your CM code simple (even if this means avoiding features). Between having CM drop off and run a script, and a highly complex cookbook/recipe, prefer the former.

Whether you use cloud hosts or hosts in a machine room, prefer to reimage hosts when their purpose changes; writing CM code for more than trivial transitions becomes a nightmare.

