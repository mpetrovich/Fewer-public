# Companies pack schema

Offline scored companies live as rows in the subject’s **Companies** database after Phase 2. ChatGPT **reads** those rows; it does not invent companies or construct opaque URL fields.

Do not duplicate this schema in phase files. Reference this page and fetch **Pack state schema**: https://raw.githubusercontent.com/mpetrovich/Fewer-public/main/pack-state-schema.md

## Row fields ChatGPT may rely on

| Pack property | Rules |
|---|---|
| `Company Name` | Display name (title). |
| `Company ID` | Opaque stable globally unique id from the company sourcing pipeline. Upsert ratings by this key when present. Do not assume how it is generated. |
| `LinkedIn Connections` | LinkedIn people-search URL for the user’s **1st- and 2nd-degree** connections at this company, or empty if the pack could not supply one. Constructed offline by the company source pipeline — treat as opaque. **Never invent or rebuild this URL in chat.** When present, give it to the user as a one-click link (especially in Phase 4). |
| `Description`, `Website`, `LinkedIn`, `Location`, `Company Size`, `Stage`, `Industries`, `Review Rank` | Operator / pack context. ChatGPT may use them for presentation and judgment. |

Subject ratings (chat: **Select** / **Reject** / **Unsure** + reason) are written on the same Companies rows as **Fit** + **Notes** per **Pack state schema**.
