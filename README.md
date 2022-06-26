# todo.md

todo.md is a very simple standard to manage your todos in a markdown file.  
Essentially a todo.md file is just a markdown file in which each heading represents a project and each task is defines using the `- [ ] task name here` syntax.  
Todo.md additionally defines a few extra useful features.  
These features are implemented using the special tag syntax that look either like that `@tagname` or if metadata for the tag is wanted like that `@tagname{some_metadata}`. The ability to specify metadata for a tag allows handling of special use cases like due dates using a simple consistent format like this: `@due{2025-06-28}`  

## Proposed features
One feature currently in discussion is a new date tagging for tasks using following syntax:
```
- [ ] optional_due_date | task description with optional tags
```
the optional_due_date is specified in a simple format that still has to be defined but that will allow specifying tasks that have to be done  
1. after a specific time (`>14:00`)
2. before a specific time (`<14:00`)
3. during a specifi time (either `11:00-14:00` or `11:00<t<14:00` or even the shorter version `11:00<<14:00`)
4. at a specific time (`14:00`)

## Blessed tags
In theory everyone can use tags as it suites you, but below are a few recommended "blessed" tags that may profit from the consistency between implementations:
- due - specify a due date using the ISO8601 or to be more specific the IEE 9333 date format
- location - specify a location the task has to be done at
- loc - alias for location
- duration - specify how long the task takes
- dur - alias for duration
- context  - the context in which the task has to be done, for example @context{work}
- ctx - alias for context
- priority - the priority tag is not implented using metadata like the rest, but by using numbered tags like @1 @2 @2.5 etc representing floats of priority, higher priority equals higher number