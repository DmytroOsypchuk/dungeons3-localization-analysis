# Workflow: Dungeons 3 In-Game Text Analysis for Localisation

## Project Description
The goal of this project was to analyze the localisation content of the game *Dungeons 3*. Specifically, the objectives were to:

- Classify translation units by content group (e.g., UI elements, quests, dialogues, system messages, etc.).
- Determine the size of each content group in terms of the number of translation units and the total word count.
- Identify tags associated with each translation unit and count the occurrences of each tag.
- Count the number of lines for each character and analyze how these lines are distributed across missions.

This analysis supports the localisation process by grouping translation units for easier translation workflow and estimating the text volume required for voice-over.

## Data Sources
- Game text files extracted directly from *Dungeons 3* using the UABEAvalonia tool.

## Tools
- **Google Sheets** – for data organization, cleaning, and analysis.
- **Tableau** – for data visualization and dashboards to summarize insights.

## Workflow Steps

1. **Data Extraction**
   - Extracted raw in-game text from game files using UABEAvalonia.
   - Retained only the text variable and converted escape sequences into standard line breaks, which allowed transforming the document into a CSV format for further analysis.

2. **Data Organization**
   - Imported extracted text into Google Sheets.
   - Structured data with columns for translation unit name, wording, uid, voice, and tags.

3. **Content Classification**
   - Classified each translation unit into content groups (UI elements, quests, dialogues, system messages, etc.).
   - Leveraged the contextual naming of keys to perform classification by extracting and standardizing the relevant part of the key.
   - Merged similar categories (e.g., *errors* and *system messages*) to streamline analysis.

4. **Quantitative Analysis**
   - Calculated the size of each content group:
     - Number of translation units
     - Total word count (measured with spreadsheet formulas applied consistently across all entries).
   - Counted the occurrence of each tag associated with translation units.
   - Counted lines and words per character.
   - Analyzed the distribution of characters’ lines and word counts across missions and events.

## Conclusions
- The analysis resulted in the distribution of text into 24 categories. These categories can be converted into separate files for easier processing, as the elements within each category are contextually related. For team-based work, such files can also be assigned to different translators based on their skills and experience.  
- Determining the size of each category allows for better planning of localisation timelines.  
- The analysis showed that only 122 tags were present across 8,182 translation units, meaning tags do not significantly affect the localisation process.  
- The number of lines and words for each character was established, which is valuable for planning voice-over recording. The most talkative character was the **Narrator**, with 52,415 words across 2,523 translation units, while the least talkative was the **Stone Elemental**, with only 46 words across 7 translation units.  
- The number of lines and words per character was also determined on a mission-by-mission basis.

## Summary
This project demonstrated a structured approach to analysing in-game text for localisation purposes. By extracting, cleaning, and classifying over 8,000 translation units, the analysis provided insights into content distribution, workload estimation, and character dialogue volumes. These findings support more efficient task allocation among translators, more accurate planning of localisation timelines, and informed preparation for voice-over production. Overall, the workflow established a clear methodology that can be reused or adapted for similar localisation projects in the future.
