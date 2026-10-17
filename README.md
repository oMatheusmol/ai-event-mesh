# AI Event Mesh (AEM)

**AI Event Mesh (AEM)** is a category of automation system, defined by Matheus Mol, in which an AI model reads every incoming event, decides what should happen, and carries out the work, on its own or with as much human approval as each team chooses.

An AEM has three parts:

- **Events:** anything that happens in the systems you already use, such as an error in production, a new card in your issue tracker, an email, a webhook from your own backend.
- **Mesh:** one layer connected to all of those sources and to the places where work gets done.
- **AI:** a model that reads each event in context and decides what to do with it, instead of a fixed rule.

## The problem

Automation tools like Zapier, Make and n8n follow rules: when X happens, do Y. That works until something unexpected happens. Then the rule fails, and a person has to step in.

I spent years at companies that build RPA and automation. The pattern was always the same. A robot breaks at 3 a.m. Someone gets woken up. A night of data is lost. Days go into fixing something that should have been simple. Rules cannot handle what nobody wrote a rule for.

An AEM replaces the rule with a decision. A model looks at the event, understands what it means, and chooses the next step, the way a person on call would.

## How an AEM works

1. **Observe.** Observers watch your sources: error trackers, issue trackers, email, documents, message queues, webhooks, your own systems. You describe in plain language which events matter, for example "new cards assigned to me in the current sprint" or "errors in production that repeat more than ten times in an hour".
2. **Decide.** For each event, a model checks it against what you described and decides whether it becomes work, and how urgent it is.
3. **Plan.** Related events are grouped, and the work is split into pieces that can run in parallel, each with a clear brief.
4. **Execute.** Agents do the work: a code change with its tests and a pull request, or work without code, such as a report, a reply or a card.
5. **Govern.** Each team decides how much autonomy the system has: from acting on its own end to end, to waiting for a person's approval before any action. The level can differ per source, per project or per kind of action.
6. **Learn.** The system measures what you approved, what you changed and what failed, and adjusts how it handles the next event.

## An example

A team runs robots that process bank transactions every night. One night a website the robots depend on changes its layout, and the robots start failing.

- **With rule-based automation:** the robots keep failing until someone notices in the morning, reads the logs and rewrites the steps by hand.
- **With an AEM:** the error is observed as it happens; the model recognizes it as a layout change on one site; an agent prepares the fix, tests it and, depending on the team's policy, ships it on its own or leaves it ready for approval. Either way, nobody loses the night.

## How it differs from rule-based automation

| | Rule-based automation | AI Event Mesh |
|---|---|---|
| What decides | Rules written in advance | A model reading each event in context |
| Unexpected events | The rule fails; a person fixes it | The model decides the next step |
| Setup | Flows and conditions | Plain-language descriptions |
| Changes in your systems | Rules must be rewritten | The model adapts to the context |
| People | Monitor and fix | Set the goals and limits; approve when they choose to |

## Author

Created and maintained by **Matheus Mol** - [GitHub](https://github.com/oMatheusmol)
