# TODO tool that will

- npm run todo -- <feature|bug> <title> [<x.y.z>]
- let issueId = Will create a issue on githost, with "<feature|bug> title>"
- if <x.y.z> not present, then highest of x.y.z will be taken. A new branch vx.y.z-issueId will be created checkout from x.y.z
- git fetch origin vx.y.z-issueId
- if x.y.z not present in TODO.md, create a new section give date say 1 month from now, and add link in bottom
- based on feature|bug add this to x.y.z section of todo.md
