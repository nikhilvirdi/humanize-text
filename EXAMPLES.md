# Examples

Before and after examples of humanize-text. Each prompt is a plain request with no style instructions, so the "before" text is the model's default output.

## ChatGPT

### 1. Technology in modern education

**Prompt:** Write a short paragraph about the role of technology in modern education.

**Before:**
> Technology plays a vital role in modern education by making learning more accessible, interactive, and effective. Digital platforms, smart classrooms, educational apps, and online resources allow students to learn anytime and anywhere. Technology also helps teachers explain complex concepts through videos, animations, and virtual simulations. Furthermore, artificial intelligence and online learning tools provide personalized learning experiences. Overall, technology has transformed traditional education into a more flexible, engaging, and efficient learning environment.

**After:**
> Technology plays a vital role in modern education by making learning more accessible, interactive, and effective. Digital platforms, smart classrooms, educational apps, and online resources let students learn anytime and anywhere. Technology also helps teachers explain complex concepts through videos, animations, and virtual simulations. Artificial intelligence and online learning tools provide personalized learning experiences. Technology has transformed traditional education into a more flexible, engaging, and efficient learning environment.

**Changes:** "Furthermore" and "Overall" were deleted as a transition and a summary marker. The final sentence still states the conclusion, so nothing is lost. "Allow" became "let," a synonym. The list of learning tools, the sentence order, and the claim that technology transformed education are unchanged. One open item remains: "plays a vital role" is a possible inflated-significance defect, which a stricter pass would cut.

### 2. Financial literacy

**Prompt:** Write a short paragraph on the importance of financial literacy.

**Before:**
> Financial literacy is an essential life skill that helps individuals manage their money wisely and make informed financial decisions. It teaches people the importance of budgeting, saving, investing, and managing expenses. Understanding financial concepts also helps individuals avoid unnecessary debt and plan for future goals. In today's world, financial literacy promotes financial independence, responsible spending, and long-term economic security.

**After:**
> Financial literacy is a life skill that helps people manage their money well and make sound financial decisions. It teaches the value of budgeting, saving, investing, and keeping track of expenses. Knowing how financial concepts work also makes it easier to avoid unnecessary debt and plan for future goals. Today, financial literacy promotes financial independence, careful spending, and long-term economic security.

**Changes:** "an essential life skill" became "a life skill," which lowers the importance claim. This is a judgment call, since "essential" reads as puffery but still carries the author's emphasis. "Wisely" became "well," a small shift from judgment to competence. "Teaches people the importance of" became "teaches the value of," a synonym, and "In today's world" was cut to "Today." Two drifts remain: "informed" became "sound," which changes a knowledge-based claim into a quality claim, and "managing expenses" became "keeping track of expenses," which narrows the scope. "Responsible spending" became "careful spending," which shifts from accountability to attention.

### 3. Exercise and mental health

**Prompt:** Explain why regular exercise is important for mental health.

**Before:**
> Regular exercise plays an important role in maintaining good mental health. It helps reduce stress, anxiety, and symptoms of depression by releasing chemicals called endorphins, which improve mood and create a sense of well-being. Exercise also improves sleep quality, boosts self-confidence, and enhances concentration. Activities such as walking, cycling, yoga, and sports help keep the mind active and relaxed. Overall, regular physical activity contributes to a healthier, happier, and more balanced life.

**After:**
> Regular exercise plays an important role in maintaining good mental health. It helps reduce stress, anxiety, and symptoms of depression by releasing chemicals called endorphins, which improve mood and create a sense of well-being. Exercise also improves sleep quality, builds self-confidence, and sharpens concentration. Activities such as walking, cycling, yoga, and sports keep the mind active and relaxed. Regular physical activity adds up to a healthier, happier, and more balanced life.

**Changes:** "Overall," was deleted, and "contributes to" became "adds up to," which names a total rather than one factor. "Boosts" became "builds" and "enhances" became "sharpens," both small shifts in how the improvement is described. The one real drift is that "help" was removed from "help keep the mind active," which turns a contribution into a certain effect. The endorphin mechanism and the partial list marked by "such as" are unchanged.

## Claude

### 4. Teamwork in the workplace

**Prompt:** Explain why teamwork is important in the workplace.

**Before:**
> Teamwork matters in the workplace for a few interconnected reasons:
>
> **Better outcomes through complementary skills.** No single person has every skill, perspective, or piece of knowledge needed to solve complex problems. Teams combine different strengths (someone strong in analysis, someone good at communication, someone with deep domain expertise), so the collective output is usually better than what any individual could produce alone.
>
> **Faster problem-solving.** When people pool their efforts, tasks that would take one person a long time get divided and parallelized. Brainstorming in a group also surfaces more potential solutions and catches blind spots an individual might miss.
>
> **Shared accountability and support.** Teams distribute workload and pressure. When someone hits a roadblock, colleagues can help troubleshoot, cover gaps, or offer a fresh perspective, reducing burnout and the risk of a single point of failure.
>
> **Innovation through diverse perspectives.** People with different backgrounds, experiences, and ways of thinking challenge each other's assumptions. This friction, when healthy, tends to produce more creative and robust solutions than solo work.
>
> **Stronger organizational culture.** Good teamwork builds trust, communication habits, and mutual respect that extend beyond any single project. This improves morale, retention, and the ability to collaborate smoothly on future work.
>
> **Efficient resource use.** Coordinated teams avoid duplicated effort and ensure that time, budget, and talent are applied where they're most needed, rather than scattered redundantly across individuals working in silos.
>
> In short, teamwork tends to produce results that are faster, more creative, and more resilient than the sum of individual efforts, while also making the work environment more sustainable for the people doing it.

**After:**
> Teamwork matters at work for several connected reasons.
>
> **Better outcomes through complementary skills.** No single person has every skill, perspective, or piece of knowledge a complex problem needs. Teams pool different strengths, such as analysis, communication, and deep domain expertise, so the group's output is usually better than what any one person could produce alone.
>
> **Faster problem-solving.** When people share the effort, tasks that would take one person a long time get divided and worked in parallel. Group brainstorming also surfaces more possible solutions and catches blind spots that an individual might miss.
>
> **Shared accountability and support.** Teams spread out workload and pressure. When someone gets stuck, colleagues can help troubleshoot, cover gaps, or offer a fresh view, which reduces burnout and the risk of depending on a single person.
>
> **Innovation through diverse perspectives.** People with different backgrounds and ways of thinking challenge each other's assumptions. When that friction is healthy, it tends to produce more creative and sturdier solutions than solo work does.
>
> **Stronger organizational culture.** Good teamwork builds trust, communication habits, and mutual respect that outlast any single project. That improves morale and retention and makes future collaboration smoother.
>
> **Efficient resource use.** Coordinated teams avoid duplicated effort and direct time, budget, and talent to where they are needed most, instead of spreading them thinly across people working in silos.
>
> Taken together, teamwork tends to produce results that are faster, more creative, and more resilient than individual efforts add up to, and it makes the work more sustainable for the people doing it.

**Changes:** "A few" became "several," which fits the six points better. "Interconnected" became "connected," which loses the mutual link, and "robust" became "sturdier," which shifts a resilience claim toward physical strength; "resilient" would keep the sense. "Extend beyond" became "outlast," which changes the claim from scope to time. "Single point of failure" was paraphrased as "depending on a single person," losing a term of art. "Pool," "group's output," and "worked in parallel" are synonyms or plainer forms with no meaning change. The six-point structure and the bold lead-ins are kept.

### 5. Pros and cons of social media

**Prompt:** Write a short paragraph on the pros and cons of social media.

**Before:**
> Social media offers clear benefits: it connects people across distances, gives individuals and small businesses a platform to reach wide audiences, provides quick access to news and information, and has enabled powerful social movements and communities to form around shared interests or causes. It also allows for creative expression and can be a valuable tool for learning and professional networking. However, these benefits come with significant drawbacks. Heavy use has been linked to anxiety, depression, and lowered self-esteem, particularly among younger users, often driven by social comparison and the curated, unrealistic nature of what people share. Misinformation spreads rapidly and can be hard to contain, privacy is frequently compromised through data collection, and the design of many platforms, built to maximize engagement, can foster addictive usage patterns that crowd out in-person relationships and focused attention. On balance, social media is a powerful tool whose value depends heavily on how, and how much, it's used.

**After:**
> Social media offers real benefits. It connects people across distances, gives individuals and small businesses a way to reach wide audiences, provides quick access to news and information, and has helped social movements and communities form around shared interests or causes. It also gives people room for creative expression and can be useful for learning and professional networking. The drawbacks are serious, though. Heavy use has been linked to anxiety, depression, and lower self-esteem, especially among younger users, often because of social comparison and the curated, unrealistic way people present their lives. Misinformation spreads fast and is hard to contain, privacy often suffers through data collection, and many platforms are designed to maximize engagement, which can encourage addictive usage patterns that crowd out in-person relationships and focused attention. On balance, social media is a powerful tool, and its value depends heavily on how, and how much, it is used.

**Changes:** The long opening list was split into shorter sentences, which removes the mechanical rhythm of the original. "Has enabled" became "has helped," which weakens a causal claim, and "powerful" was dropped. "Significant drawbacks" became "serious drawbacks," which raises the emotional weight. "Can be hard to contain" became "is hard to contain," which removes a hedge and makes the claim absolute. This is the most serious drift in the set. "The nature of what people share" became "the way people present their lives," which widens the scope. "It's used" became "it is used," removing a contraction. The conclusion that value depends on use is kept.

### 6. Welcome message for a community

**Prompt:** Write a brief welcome message for new members of an online community.

**Before:**
> Welcome to the community! 🎉
>
> We're really glad you're here. This is a space to connect, share ideas, ask questions, and learn from each other — so don't be shy about jumping in. Whether you're here to contribute, get advice, or just see what everyone's talking about, there's a place for you.
>
> A few quick tips to get started:
>
> * Introduce yourself if you're comfortable — we'd love to know a bit about you.
> * Explore past discussions to get a feel for the vibe.
> * Don't hesitate to ask questions; everyone here was new once.
>
> Glad to have you aboard — looking forward to seeing what you bring to the group!

**After:**
> Welcome to the community! 🎉
>
> We're really glad you're here. This is a space to connect, share ideas, ask questions, and learn from each other, so don't be shy about jumping in. Whether you're here to contribute, get advice, or just see what everyone's talking about, there's a place for you.
>
> A few quick tips to get started:
>
> * Introduce yourself if you're comfortable; we'd love to know a bit about you.
> * Explore past discussions to get a feel for the vibe.
> * Don't hesitate to ask questions; everyone here was new once.
>
> Glad to have you aboard. Looking forward to seeing what you bring to the group!

**Changes:** Em dashes were replaced with commas, semicolons, and a sentence break, which the mechanical audit requires. None of these changes alters meaning, and the fragment "Looking forward" stands as the original's closing thought. The emoji stays because a community welcome is casual enough to allow it. This is the cleanest example, since the text was already natural.

## Gemini

### 7. Benefits of learning a second language

**Prompt:** Explain the benefits of learning a second language.

**Before:**
> Learning a second language does far more than just give you a new way to order food on vacation or chat with locals abroad. It is one of the most powerful workouts you can give your brain, reshaping its structure and offering lifelong cognitive, professional, and personal advantages.
>
> Here are the primary benefits of bilingualism and multilingualism, backed by cognitive and social science:
>
> **1. Cognitive Superpowers & Brain Health**
>
> * **Enhanced Executive Function:** Managing two languages requires your brain to constantly choose one while actively suppressing the other. This acts like a heavy-duty workout for the prefrontal cortex, strengthening your ability to focus, solve complex problems, switch between tasks, and filter out distractions.
> * **Delayed Cognitive Decline:** Studies consistently show that lifelong bilingualism can delay the onset of symptoms of dementia and Alzheimer's disease by an average of 4 to 5 years compared to monolinguals. While it doesn't prevent the underlying disease, it builds cognitive reserve, allowing the brain to cope better with damage.
> * **Improved Memory and Creativity:** Learning grammatical rules, vocabulary structures, and idiomatic expressions sharpens working memory. It also fosters cognitive flexibility, the ability to think about things from multiple perspectives, which naturally boosts creative problem-solving.
>
> **2. Professional & Economic Edge**
>
> * **Expanded Career Opportunities:** In an increasingly interconnected global economy, companies across technology, healthcare, finance, tourism, and diplomacy actively seek professionals who can bridge language gaps.
> * **Competitive Salary Advantage:** Being bilingual often commands a financial premium. Depending on the industry and languages spoken, bilingual employees can see wage bumps ranging from 5% to 20%.
> * **Better Decision-Making:** Research suggests that when people think and make decisions in a foreign language, they rely less on emotional gut reactions and more on analytical reasoning, leading to more pragmatic choices.
>
> **3. Empathy, Culture, and Perspective**
>
> * **Deepened Cultural Understanding:** Language is deeply intertwined with culture. Learning a new tongue gives you direct access to the literature, humor, cinema, and worldview of another community, fostering genuine empathy rather than relying on translations or stereotypes.
> * **Native-Level Shifts in Perception:** Different languages carve up reality in unique ways. For example, some languages assign grammatical genders to objects (making a bridge "masculine" in one language and "feminine" in another), which subtly influences how speakers describe and perceive those objects.
>
> **4. Easier Acquisition of Further Languages**
>
> * **The Snowball Effect:** The hardest part of multilingualism is learning your second language because your brain has to build entirely new neural pathways. Once you are bilingual, learning a third or fourth language becomes significantly easier. You develop metacognitive awareness, an understanding of how languages work, making grammar, syntax acquisition, and vocabulary retention much faster.
>
> Whether you want to protect your long-term brain health, boost your resume, or connect more deeply with another culture, picking up a new language is one of the most rewarding investments you can make in yourself.

**After:**
> Learning a second language does far more than help you order food on vacation or chat with locals abroad. It is a serious workout for your brain, reshaping its structure and offering lifelong cognitive, professional, and personal advantages.
>
> Here are the main benefits of bilingualism and multilingualism, backed by cognitive and social science:
>
> **1. Cognitive Benefits & Brain Health**
>
> * **Enhanced Executive Function:** Managing two languages requires your brain to keep choosing one while actively suppressing the other. This works the prefrontal cortex hard, strengthening your ability to focus, solve complex problems, switch between tasks, and filter out distractions.
> * **Delayed Cognitive Decline:** Studies consistently show that lifelong bilingualism can delay the onset of symptoms of dementia and Alzheimer's disease by an average of 4 to 5 years compared to monolinguals. It doesn't prevent the underlying disease, but it builds cognitive reserve, so the brain copes better with damage.
> * **Improved Memory and Creativity:** Learning grammatical rules, vocabulary, and idiomatic expressions sharpens working memory. It also builds cognitive flexibility, the ability to see things from multiple perspectives, which naturally supports creative problem-solving.
>
> **2. Professional & Economic Edge**
>
> * **Expanded Career Opportunities:** In an increasingly interconnected global economy, companies in technology, healthcare, finance, tourism, and diplomacy actively look for professionals who can bridge language gaps.
> * **Competitive Salary Advantage:** Being bilingual often comes with a financial premium. Depending on the industry and languages spoken, bilingual employees can see wage increases of 5% to 20%.
> * **Better Decision-Making:** Research suggests that when people think and decide in a foreign language, they rely less on emotional gut reactions and more on analytical reasoning, which leads to more pragmatic choices.
>
> **3. Empathy, Culture, and Perspective**
>
> * **Deeper Cultural Understanding:** Language is closely tied to culture. Learning a new language gives you direct access to another community's literature, humor, cinema, and worldview, which builds genuine empathy instead of relying on translations or stereotypes.
> * **Shifts in Perception:** Different languages divide up reality in different ways. For example, some languages assign grammatical gender to objects, making a bridge "masculine" in one language and "feminine" in another, which subtly influences how speakers describe and perceive those objects.
>
> **4. Easier Acquisition of Further Languages**
>
> * **The Snowball Effect:** The hardest part of multilingualism is learning your second language, because your brain has to build entirely new neural pathways. Once you're bilingual, learning a third or fourth language gets much easier. You develop metacognitive awareness, an understanding of how languages work, which makes grammar, syntax, and vocabulary retention much faster.
>
> Whether you want to protect your long-term brain health, boost your resume, or connect more deeply with another culture, learning a new language is a rewarding investment in yourself.

**Changes:** "Just" was cut from "just give you," which is filler. "One of the most powerful workouts" became "a serious workout," and "one of the most rewarding investments" became "a rewarding investment." Both cuts remove unsupported superlatives, which lowers the claims. This is a judgment call that should be stated as deliberate. "Superpowers" became "Benefits," which removes hype. "Boosts creative problem-solving" became "supports," which weakens the claim; this is a drift. "Native-Level" was dropped from a heading, which removes a qualifier. "Acts like a heavy-duty workout" became "works hard," removing a metaphor that repeated the intro. The figures and the gender example are unchanged.

### 8. Why urban green spaces matter

**Prompt:** Write a short paragraph about why urban green spaces matter.

**Before:**
> Urban green spaces (such as parks, tree-lined streets, and community gardens) are vital lifelines for modern cities that go far beyond mere aesthetics. Ecologically, they act as natural cooling sinks that combat the urban heat island effect, improve air quality by filtering pollutants, and provide essential habitats for local wildlife. For human residents, these pockets of nature offer proven mental and physical health benefits, reducing stress, encouraging outdoor activity, and fostering a vital sense of community connection in densely populated environments.

**After:**
> Urban green spaces, such as parks, tree-lined streets, and community gardens, do more for cities than make them look nice. Ecologically, they act as natural coolers that counter the urban heat island effect, clean the air by filtering pollutants, and give local wildlife places to live. For residents, they offer proven mental and physical health benefits: less stress, more time spent outdoors, and a stronger sense of connection to neighbors in crowded areas.

**Changes:** "Vital lifelines" and the "mere aesthetics" framing were cut as puffery, and the meaning is kept in "do more for cities than make them look nice." "Cooling sinks" became "coolers," which loses the term for something that absorbs heat, and "habitats" became "places to live," which loses an ecological term. "Human residents" became "residents," which drops the contrast with wildlife. "Encouraging outdoor activity" became "more time spent outdoors," which shifts from physical activity to presence. "Fostering a vital sense of community connection" became "a stronger sense of connection to neighbors," which implies a prior baseline and narrows "community." "Densely populated" became "crowded," which adds a negative tone. Restorations still pending: "habitats," "physical activity," "community connection," and "densely populated."

### 9. How the internet changed communication

**Prompt:** Write a brief overview of how the internet changed communication.

**Before:**
> The internet completely revolutionized communication by obliterating physical distance and time barriers. It shifted the paradigm from slow, one-to-one asynchronous methods (like postal mail and landline telephones) to instantaneous, many-to-many global connectivity.
>
> Key milestones in this transformation include:
>
> * **The Rise of Email and Instant Messaging:** Replaced physical letters and delayed phone calls with real-time text exchange across continents.
> * **The Democratization of Voice and Video:** Technologies like VoIP and video conferencing transformed international calling from an expensive luxury into a free, everyday commodity, adding back crucial non-verbal cues.
> * **Social Media and Global Networks:** Transformed individuals from passive consumers of information into active publishers, creating vast, interconnected communities that transcend geographic borders.

**After:**
> The internet changed communication by removing the distance and delay that used to shape it. It moved people from slow, one-to-one methods like postal mail and landline phones to instant, many-to-many connection around the world.
>
> Some of the key changes:
>
> * **Email and instant messaging:** These replaced letters and delayed phone calls with real-time text exchanges across continents.
> * **Voice and video:** VoIP and video conferencing turned international calling from an expensive luxury into a free, everyday part of life, and they added back nonverbal cues.
> * **Social media and online networks:** People went from passive consumers of information to active publishers, and online communities now span geographic borders.

**Changes:** "Completely revolutionized" became "changed," which removes puffery and weakens the claim on purpose. "Obliterating... barriers" became "removing... delay," which turns a barrier into a result of one. "Shifted the paradigm" became "moved people," which turns an abstract claim into a concrete one. "Asynchronous" was dropped; it is a technical term, so this is a drift. "Crucial" was dropped, which is an intensity change. "Instantaneous" became "instant," a synonym. "Commodity" became "part of life," which moves from an economic term to a social description. "Vast, interconnected" was dropped, and "online" was added to "communities," which is new content. "Transcend" became "span," a near-synonym. The bullets keep their original order.