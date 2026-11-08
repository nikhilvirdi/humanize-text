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

#### Any model (generic)

1. Open [`Generic/SKILL.md`](Generic/SKILL.md) and copy its full contents.
2. Start a new chat in the model and paste the contents.
3. Send this small, strict prompt: "Apply the instructions above strictly. Rewrite only the text I send next, and reply with the rewritten text only."

This works in any model, including Claude and Gemini.

#### Claude  <img width="3840" height="3840" alt="image" src="https://github.com/user-attachments/assets/17d93173-f429-49ce-8867-fc532d867319" />


1. Download [`Claude/humanize-text.zip`](Claude/humanize-text.zip).
2. In Claude, open **Customize**, scroll to **Skills**, click **Add** in the top right, and upload the zip.

#### Gemini <img width="960" height="960" alt="image" src="https://github.com/user-attachments/assets/5a05f100-4eaf-477f-ac3b-94bf3a341a0f" />


1. Download [`Gemini/humanize-text.zip`](Gemini/humanize-text.zip).
2. Open Gemini's settings, find the skills section, and upload the zip.

#### ChatGPT  <img width="3840" height="3840" alt="image" src="https://github.com/user-attachments/assets/6dce5132-f71d-450a-a5fa-92a80ff93818" />


1. Follow OpenAI's official guide: [Skills in ChatGPT](https://help.openai.com/en/articles/20001066-skills-in-chatgpt). Availability depends on your plan, so check the guide first.

The `legacy/` folder contains the initial version of the skill, kept for reference. Use the current files above.

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
