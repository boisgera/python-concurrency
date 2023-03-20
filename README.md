# Python Concurrency

## Problem exposition I

(Long-running) program characteristics: latency & throughput.

Definition and examples ; for latency, user input (game, web app, etc.),
web request, file/database read/write, etc. Througput easy: data crunching
mostly (computations).

-> IO-bound vs CPU-bound programs.

Improvement for IO-bound programs mostly : multitasking. Search for concrete 
example of long-running task + user inputs. Multi-tasking can dramatically 
reduce the latency and only hurt throughput a little.

**TODO.** example with button widget in jupyter notebook.

Nota: multi-tasking = running tasks (~= functions but not quite!) concurrently

Sometimes multi-tasking can even improve the troughput, with a better usage
of computer ressources. Example: periodic task + sleep, or web request.
(TODO: analyze the ressources).

TODO: aiohttp requests examples with pokemons.

## Problem exposition II

Other line of reasing: some problems are naturally described with multiple
tasks. So we just want a language paradigm that can capture the natural
spec without too many alterations of the spec, too many transformations,
and too many brittle-ness / change cost wrt changing spec.

Embedded example: blink slowly a green LED while watching for some numeric data 
(e.g. GPU temperature) and if it crosses a threshold, emit a periodic alarm
and blink rapidly a red LED.

Show: "classic", manual solution, show how hard-to-read and brittle it is
(wrt change). Show how a multi-tasking SPEC.

TODO: find a simpler example, build it step-by-step to prove how painful it is.


## Standard solution

One standard solution to implement multitacking in Python: `async`/`await` 
(keywords) and `asyncio` (standard library).
