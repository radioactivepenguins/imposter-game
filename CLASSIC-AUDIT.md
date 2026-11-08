# Complete V2 hint audit

Reviewed all **1,080** existing pairs against relevance, specificity, difficulty, familiarity, and consistency. **461 hints changed; 619 retained.** All **45 categories**, word labels, and entry order are preserved. No words were added or removed, so existing content history remains valid. Each category still contains 24 entries. The Question database is byte-for-byte unchanged.

This comparison uses the newest saved Moonlight revision as the baseline, not the earlier original ZIP. The detailed CSV includes every entry, including retained ones.

## Editorial standard

1. Relevance: a familiar, meaningful association with the word; correct misleading descriptions.
2. Specificity: a useful action, trait, setting, purpose, or context rather than a blanket category such as Science, Outdoors, or Teamwork.
3. Difficulty: avoid names, slogans, exact word echoes, signature catchphrases, and uniquely identifying facts when a broader cue works.
4. Fairness: prefer everyday language. Replace niche vocabulary such as an animal being a “browser.”
5. Consistency: aim for the same useful-but-incomplete amount of information within each category. Comparable brands may deliberately share hints.

These are editorial judgments, not measured player success rates. The hints narrow the context without promising identical difficulty for every group. Familiarity varies most for celebrities, memes, and cultural holidays; no live group playtest was performed.

## Examples

| Word | Previous hint | V2 hint |
| --- | --- | --- |
| Great Wall of China | Built for defense | Fortification |
| Dumplings | Savory filling | Savory filling |
| Minecraft | Building shelter | Crafting and survival |
| Football | Contact | Full-contact teamwork |
| Glacier | Frozen | Frozen landscape |
| Ariel | Animated sidekick | Curious ocean royalty |
| Winnie the Pooh | Fairy-tale royalty | Gentle woodland friend |
| Giraffe | Long-legged browser | High branches |
| Tennis | Back and forth | Racket rallies |
| Doctor | Healthcare | Diagnosing patients |
| Jazz | Live band | Instrumental improvisation |
| Friends | Friends and dating | Apartment neighbors |
| Side Eye | Silent judgment | Unspoken doubt |

Dumplings → “Savory filling” was already appropriate in the latest version and was retained. The audit did not change useful hints merely to increase the change count.

## Category coverage

| Category | Reviewed | Changed | Retained |
| --- | ---: | ---: | ---: |
| Food | 24 | 2 | 22 |
| Drinks | 24 | 1 | 23 |
| Fast Food | 24 | 0 | 24 |
| Restaurants & Dining | 24 | 1 | 23 |
| Cards & Party Games | 24 | 3 | 21 |
| Board Games | 24 | 2 | 22 |
| Video Games | 24 | 3 | 21 |
| Sports | 24 | 24 | 0 |
| Athletes | 24 | 24 | 0 |
| Celebrities | 24 | 24 | 0 |
| Musicians | 24 | 24 | 0 |
| Movies | 24 | 2 | 22 |
| TV Shows | 24 | 4 | 20 |
| Fictional Characters | 24 | 8 | 16 |
| Countries | 24 | 0 | 24 |
| Cities | 24 | 0 | 24 |
| Famous Landmarks | 24 | 2 | 22 |
| Animals | 24 | 2 | 22 |
| Cars & Vehicles | 24 | 4 | 20 |
| Car Brands | 24 | 0 | 24 |
| Clothing | 24 | 24 | 0 |
| Fashion Brands | 24 | 0 | 24 |
| Technology | 24 | 2 | 22 |
| Apps & Social Media | 24 | 0 | 24 |
| Internet Culture | 24 | 6 | 18 |
| Memes | 24 | 2 | 22 |
| College Life | 24 | 2 | 22 |
| School | 24 | 24 | 0 |
| Relationships | 24 | 24 | 0 |
| Jobs & Professions | 24 | 24 | 0 |
| Household Items | 24 | 7 | 17 |
| Stores | 24 | 1 | 23 |
| Vacation & Travel | 24 | 3 | 21 |
| Holidays | 24 | 24 | 0 |
| Music Genres | 24 | 24 | 0 |
| Historical Figures | 24 | 24 | 0 |
| Nature | 24 | 24 | 0 |
| Weather | 24 | 24 | 0 |
| Casino & Gambling | 24 | 24 | 0 |
| Parties | 24 | 24 | 0 |
| Money & Finance | 24 | 2 | 22 |
| Hobbies | 24 | 24 | 0 |
| Toys | 24 | 5 | 19 |
| Superheroes | 24 | 4 | 20 |
| Everyday Objects | 24 | 9 | 15 |

## Data validation

All entries have exactly three nonempty string fields: category, word, and hint. Words are unique ignoring case; no hint contains the complete secret word ignoring case. All 1,080 entries remain reachable through the existing category-balanced selection. File paths and the window.CLASSIC_WORDS interface are unchanged.
