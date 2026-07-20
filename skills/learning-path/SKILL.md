---
description: Build a personalised secure-coding learning path from SecDim courses and hands-on labs. Use when the user asks for a learning path, study plan, roadmap, or "what should I learn next" in secure coding.
---

# Secure coding learning path

Use the `secdim` MCP tools to build a short, ordered plan rather than dumping every
search result.

1. Call `get_secdim_profile` to see what the user has already completed and their
   current skill level. If the tool errors or returns no profile, continue without it.
2. Before searching, ask for whatever of the following the user hasn't already given:
   - their security experience level (e.g. new to secure coding, some exposure, experienced)
   - their preferred language(s)/framework(s)
   - their objective (e.g. a specific vulnerability class, OWASP Top 10 coverage, a
     certification/interview, general upskilling)
   - how much time per week they want to commit
   Don't ask for details already stated in the conversation or already clear from the
   profile.
3. Call `search_learn_courses` and `search_play_challenges` filtered by that
   language/framework/topic.
4. Drop anything the profile shows as already completed.
5. Order the remaining items beginner → advanced, matching the stated experience level.
6. Interleave course topics with matching labs: a course/topic teaches the concept, the
   paired lab is where the user practices fixing it.
7. Size the plan to the stated weekly time commitment (e.g. fewer, longer items per week
   for a light commitment; more items for a heavier one), and note the expected pace
   (e.g. "~2 items/week").
8. Present the result as a short numbered plan (5-8 steps), each with the resource name,
   what it covers, and why it's next — not a raw list of every match.
