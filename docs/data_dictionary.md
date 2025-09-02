# Data Dictionary

This document describes the structure and content of the tables used in the game localization analysis project. Each table represents a different aspect of the dataset.

---

## Table 1: `original_texts`

This table contains the cleaned and structured game localization content. Each row represents a single translation unit from the game files.  

- **name** — A descriptive key that indicates the context and placement of the translation unit in the game (e.g., user interface, mission dialogues, achievements). It usually includes a unique English identifier.  
- **wording** — The actual source text string.  
- **uid** — A unique numeric identifier for the translation unit.  
- **voice** — If the line is voice-overed, this field contains the unique character code associated with the speaker; otherwise, it is left empty.  
- **tags** — Optional tags attached to the line (e.g., placeholders, gameplay triggers, conditions).  
- **category** — A higher-level class derived from the `name` field, grouping translation units into categories such as missions, user interface, achievements, etc.  
- **words_number** — The word count of the `wording` field.  

---

## Table 2: `text_classification`

This table provides aggregated statistics of translation units grouped by category, derived from the `original_texts` table. Each row corresponds to one category of in-game content.  

- **category** — The category of the translation unit, inherited from the `category` field in the `original_texts` table.  
- **TUs_number** — The number of translation units (TUs) within the given category.  
- **words_number** — The total number of words across all translation units in the given category.  

---

## Table 3: `tags_distribution`

This table summarizes the distribution of tags across translation units. Each row represents a unique tag and the number of times it appears in the dataset.  

- **tag** — The tag label assigned to translation units (e.g., metadata, gameplay-specific markers).  
- **occurrences_number** — The number of occurrences of the given tag across all translation units.  

---

## Table 4: `VO_text`

This table contains only the voice-overed translation units extracted from the `original_texts` table (i.e., entries with a non-empty `voice` field). Irrelevant fields have been removed, and some additional attributes are included.  

- **name** — A descriptive key that indicates the context and placement of the translation unit in the game (similar to `original_texts`).  
- **wording** — The actual source text string spoken by the character.  
- **voice** — The unique character code identifying the speaker.  
- **character** — The in-game name of the character associated with the voiced line.   
- **mission/event_code** — A specific identifier linking the voiced line to the corresponding mission or in-game event.  
- **mission/event_name** — The actual name of the mission or event as displayed in the game (player-facing title).
- **words_number** — The word count of the `wording` field. 

---

## Table 5: `VO_summary`

This table provides aggregated statistics for each character with voice-overed lines. It summarizes the number of translation units and the total word count spoken by each character.  

- **character** — The in-game name of the character.  
- **voice_code** — The unique voice identifier of the character, as used in the `VO_text` table.  
- **TUs_number** — The total number of translation units (lines) spoken by the character.  
- **words_number** — The total number of words spoken by the character.  

---

## Table 6: `mission_distribution`

This table represents the distribution of translation units and words across missions or in-game events. It summarizes the number of translation units and the total word count associated with each mission.  

- **mission/event_name** — The actual name of the mission or event as displayed in the game (player-facing title).  
- **mission/event_code** — A specific identifier linking the voiced line to the corresponding mission or in-game event.
- **TUs_number** — The number of translation units (TUs) linked to the mission/event.  
- **words_number** — The total word count of all translation units within the mission/event.  
