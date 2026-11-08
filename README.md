## humanize-text

Fidelity-first text humanizer: removes AI tells, audits for drift, and leaves the author's facts and stance intact. Works with Claude, ChatGPT, Gemini, and any other LLM.

### How to Use It

The skill makes small, targeted edits, the way a copyeditor would. It removes common AI-writing patterns such as inflated significance, stock phrases, tacked-on commentary, and mechanical rhythm. Everything else stays as written.

**Example**

Before:
> Learning to code opens up a world of opportunities by developing problem-solving, logical thinking, and creativity. It empowers you to turn ideas into reality, build useful applications, automate everyday tasks, and solve real-world problems. Coding also prepares you for exciting career opportunities in technology and beyond. Most importantly, it teaches you to think differently, embrace challenges, and continuously learn new skills in an ever-evolving digital world.

After:
> Learning to code develops problem-solving, logical thinking, and creativity. It lets you turn ideas into working things: useful applications, automated everyday tasks, and solutions to real problems. It also prepares you for careers in technology and other fields. Most importantly, it changes how you think. You get comfortable with challenges and keep learning new skills as the digital world changes.

For more examples like this, see [EXAMPLES.md](EXAMPLES.md).

### Installation

#### Claude

1. Download [`claude/humanize-text.zip`](claude/humanize-text.zip).
2. In Claude, open **Customize**, scroll to **Skills**, click **Add** in the top right, and upload the zip.

Second method: open a new chat, attach [`SKILL/SKILL.md`](SKILL/SKILL.md), and send: "Use the attached SKILL.md to add the skill named 'humanise-text' or name of your choice."

#### Gemini

1. Download [`gemini/humanize-text.zip`](gemini/humanize-text.zip).
2. Open Gemini's settings, find the skills section, and upload the zip.

Second method: open a new chat, attach [`SKILL/SKILL.md`](SKILL/SKILL.md), and send: "Use the attached SKILL.md to add the skill named 'humanise-text' or name of your choice."

#### ChatGPT

1. Follow OpenAI's official guide: [Skills in ChatGPT](https://help.openai.com/en/articles/20001066-skills-in-chatgpt). Availability depends on your plan, so check the guide first.

Second method: open a new chat, attach [`chatgpt/prompt.md`](chatgpt/prompt.md), and paste the contents of [`SKILL/SKILL.md`](SKILL/SKILL.md) below it.

### Usage

Ask the model to humanize a draft, for example "humanize this essay" or "remove the AI patterns from this email," and paste the text. The model returns the rewritten text. Ask for a change summary if you want to see what it changed.

### How It Works

The skill follows a fixed workflow. It reads the full text, marks each defect against its catalog, and makes the smallest edit that fixes it. Before it delivers, it runs two checks. The drift audit compares the rewrite with the original. The mechanical audit scans the final text for leftover patterns.

The guiding rules are:

- **Fidelity.** Facts, numbers, names, quotes, citations, and the author's stance stay the same.
- **No invention.** Vague praise is cut, never replaced with made-up detail.
- **Minimal edits.** Sentences that are already clean stay untouched.
- **Fix the defect, not the word.** Swapping one stock word for another does not count as a fix.
- **Voice stays.** First person, opinions, humor, and register survive.

### Limitations

The skill does not guarantee that text will pass an AI detector, and it is not meant to hide authorship where honesty is required. Its output still needs human review, especially for technical accuracy. The skill flags references that may be invented and claims without support. It reports them for you to check and does not repair them.

### Acknowledgements

The defect catalog is informed by Wikipedia's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) and [Signs of AI use in comments](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_use_in_comments) guides. The research in the references below also shaped the approach.

### References

1. Wikipedia contributors, "Wikipedia:Signs of AI writing," Wikipedia. https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing
2. Wikipedia contributors, "Wikipedia:Signs of AI use in comments," Wikipedia. https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_use_in_comments
3. "Interpretable Stylistic Variation in Human and LLM Writing Across Genres, Models, and Decoding Strategies." https://www.alphaxiv.org/pdf/2604.14111
4. GPTZero, "AI patterns." https://gptzero.me/news/ai-patterns
5. Google DeepMind, "How LLMs Distort Our Written Language," arXiv:2603.18161. https://arxiv.org/abs/2603.18161
6. "Do LLMs write like humans? Variation in grammatical and rhetorical styles," arXiv:2410.16107. https://arxiv.org/html/2410.16107v2
7. "How to spot when writing is AI: The 6 elements of robot style," Hunting the Muse. https://huntingthemuse.net/library/how-to-tell-if-writing-is-ai
8. "Word Overuse and Alignment in Large Language Models: The Influence of Learning from Human Feedback," arXiv:2508.01930. https://arxiv.org/pdf/2508.01930

### License

MIT. See [LICENSE](LICENSE).