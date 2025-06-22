# Report on "Lapse" Terminology Consistency

## 1. Introduction

This report investigates the usage of terminology related to card "lapses" within the project's documentation. The primary question is whether the documentation consistently portrays the "card" as the actor that lapses (Style A: "the card lapses") or the "user" as the actor who lapses the card (Style B: "the user lapses the card"). This analysis aims to provide a recommendation for a consistent style.

The investigation was prompted by a comment on the line in `src/searching.md`: "cards that been lapsed more than 3 times."

## 2. Methodology

To gather data, all markdown files (`*.md`) in the repository were searched for occurrences of the word "lapse" and its variations (lapses, lapsed, lapsing). The `grep` command used was:

```bash
grep -i -n -w -E "lapse|lapses|lapsed|lapsing" $(find . -name "*.md")
```

The results were then manually analyzed and categorized into:
- **Style A:** The card is the actor or is acted upon (e.g., "the card lapsed", "lapsed cards").
- **Style B:** The user is the actor (e.g., "user lapses the card").
- **Other:** The term "lapse(s)" is used as a noun (e.g., count of lapses, a general concept) or as a header/title.

## 3. Statistics

The analysis of the search results yielded the following counts:

*   **Style A (Card Lapses / Is Lapsed):** 11 occurrences
*   **Style B (User Lapses Card):** 0 direct occurrences
*   **Other (Noun, Header, General Concept):** 9 occurrences

## 4. Examples

### Style A: Card Lapses / Is Lapsed

This style is characterized by the card being the subject of the verb "lapse" or being described by the adjective "lapsed".

*   `./src/leeches.md:8: Each time a review card "lapses" (is`
*   `./src/searching.md:252: Cards that have [lapsed](deck-options.md#lapses) fall into several of the previous categories, so it may`
*   `./src/deck-options.md:207: The options listed here affect such lapsed cards.`
*   `./src/searching.md:311: cards that been lapsed more than 3 times.` (The original line in question)

### Style B: User Lapses Card

No direct instances of this style were found in the documentation. The user's action (clicking "Again") is identified as the *cause* of a lapse, but the phrasing does not make the user the direct actor of the verb "lapse" with the card as the object.

*   Example of causal link (not Style B): `./src/deck-options.md:207: When you click **Again** on a review card, it is called a _lapse_.`

### Other Uses

The term "lapse(s)" is also frequently used as a noun or a title.

*   `./src/filtered-decks.md:115: in, and the order they will be reviewed in. If you select "most lapses"` (Noun: a counter)
*   `./src/deck-options.md:205: ## Lapses` (Section Header)
*   `./src/browsing.md:166: | Lapses          | How often the card was rated “Again”.` (Column Header / Property)
*   `./src/searching.md:310: prop:lapses>3` (Search syntax property)

## 5. Recommendation

Based on the findings:

1.  **Standardize on Style A:** The documentation predominantly uses Style A, where the **card lapses** or **is lapsed**. This is the clear existing convention.
2.  **Consistency:** Future documentation and modifications should adhere to this style.
3.  **Grammar for the original line:** The specific line `src/searching.md:311: "cards that been lapsed more than 3 times."` should be corrected for grammar while maintaining Style A. Suggestions include:
    *   "cards that **have** lapsed more than 3 times." (More active, card as actor)
    *   "cards that **have been** lapsed more than 3 times." (Passive, card acted upon)
    *   "cards that **were** lapsed more than 3 times." (Passive, card acted upon)

    Given the context of `prop:lapses>3` (which refers to a property of the card), "cards that **have** lapsed more than 3 times" is concise and aligns well.

Adopting Style A consistently will ensure clarity and uniformity across the documentation. The "actor" in the context of a card becoming a "leech" or requiring re-learning due to incorrect answers is consistently the card itself entering the "lapsed" state.
