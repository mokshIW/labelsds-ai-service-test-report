# Overall AI Services Test Result

| Service                         | 🥇 1st | 🥈 2nd | 🥉 3rd | ❌ 4th | Notes                                                              |
| ------------------------------- | ------ | ------ | ------ | ------ | ------------------------------------------------------------------ |
| **ChatGPT (4o / o4-mini-high)** | **7**  | 1      | 2      | 0      | Consistently strong, best formatting, only weak in early rounds    |
| **Perplexity AI**               | 3      | 4      | 2      | 1      | Strong early showing, dropped in later tests due to depth limits   |
| **Copilot**                     | 0      | 3      | 6      | 1      | Often accurate, but markdown/formatting kept it from rising higher |
| **Gemini**                      | 0      | 2      | 0      | **8**  | Regularly violated prompt (Google links, no files) — not usable    |

## Summary Verdict

- **OpenAI's ChatGPT** is the most **reliable, automation-ready AI** for this task. It wins in accuracy, formatting, and prompt compliance.
- **Perplexity** is a great fallback when ChatGPT isn't available — solid search depth, but not as consistent with link formatting or file extraction.
- **Copilot** usually finds the right info but lacks polish in how it presents links and dates. Not ready for automation without cleanup.
- **Gemini** consistently broke prompt rules by returning search result links and unreliable sources. Not viable for this type of task.

> In **Test 10**, we switched to **Pro-tier models** (e.g. ChatGPT o4-mini-high, Gemini 2.5 Pro) to evaluate their performance in a real-world research context. Only ChatGPT’s Pro version maintained top-tier output quality.

# Full Prompts & AI Responses (Reference Archive Below)

# AI Prompt 1

You are a web research assistant. Your task is to search the internet and find the most up-to-date Label and SDS (Safety Data Sheet) documents for a pesticide or chemical product.

**Focus on:**

- Searching official manufacturer websites, EPA databases, and trusted agricultural product portals.
- Returning direct PDF links to the Label and SDS documents if possible.
- If direct links are unavailable, return the most relevant page URL where the document can be downloaded manually.
- Prioritize files that mention a newer revision date than the ones provided.
- For SDS documents, look for “Revision Date,” “Revised,” or “Updated” on the document (not “Printed” date).
- If a newer document is found, suggest a filename in the format: `ProductName_Label_YYYY-MM-DD.pdf` or `ProductName_SDS_YYYY-MM-DD.pdf`

**Return format:**

1.  **Was a newer Label found?** Yes/No

    - Link: [paste PDF link or webpage]
    - Document Date (if known): [e.g., Jan 5, 2024]
    - Suggested File Name: [e.g., SonoraHerbicide_Label_2024-01-05.pdf]

2.  **Was a newer SDS found?** Yes/No
    - Link: [paste PDF link or webpage]
    - Document Date (if known): [e.g., Mar 12, 2024]
    - Suggested File Name: [e.g., SonoraHerbicide_SDS_2024-03-12.pdf]

If nothing is found or the document is outdated, say so clearly.

---

**DATA:**

- **Product Name:** Sonora Herbicide
- **Manufacturer:** Alligare
- **EPA Registration #:** 81927-69
- **Last Known Label Date:** December 28, 2018
- **Last Known SDS Date:** March 28, 2023
- **Reference Page (if needed):** https://alligare.com/product/sonora-herbicide/

---

# Results

## 1. Perplexity AI (Free Model) Response (RANK 1):

**Was a newer Label found?** Yes

- Link: https://alligare.com/wp-content/uploads/2024/06/Sonora-2.5Gal-Book_PA_customer-copy.pdf
- Document Date (if known): June 2024 (file uploaded June 2024; content references 2024 use patterns)
- Suggested File Name: SonoraHerbicide_Label_2024-06-01.pdf

**Was a newer SDS found?** No

- Link: https://alligare.com/wp-content/uploads/2024/06/Alligare-Sonora-Herbicide-SDS-v2.0-032823.pdf
- Document Date (if known): March 28, 2023 (explicitly stated as the revision date on the SDS)
- Suggested File Name: SonoraHerbicide_SDS_2023-03-28.pdf

**Summary:**
A newer product label for Sonora Herbicide is available as of June 2024, which is more recent than the previously known December 2018 version. However, the most recent Safety Data Sheet remains dated March 28, 2023; no update beyond this revision was found.

## 2. Microsoft Copilot AI (Free Model) Response (RANK 4):

Here’s what I found regarding the latest Label and SDS documents for Sonora Herbicide:

**Was a newer Label found?** No

The most relevant page for the product label is here, but it does not indicate a newer revision date than December 28, 2018.

- Link: https://alligare.com/product/sonora-herbicide/

**Was a newer SDS found?** No

The most recent SDS available is from March 28, 2023, which matches the last known SDS date. You can access it here.

- Link: https://alligare.com/wp-content/uploads/2024/06/Alligare-Sonora-Herbicide-SDS-v2.0-032823.pdf

It looks like there are no newer versions of these documents beyond what you already have. Let me know if you need help with anything else.

## 3. Google Gemini AI (Free Model - 2.0 Flash Model) Response (RANK 2):

Here is the information about the Label and SDS documents for Sonora Herbicide:

**Was a newer Label found?** No

- Link: https://labelsds.com/images/user_uploads/Alligare%20Sonora%20Label%2011-6-18.pdf
- Document Date (if known): November 6, 2018
- Suggested File Name: SonoraHerbicide_Label_2018-11-06.pdf

**Was a newer SDS found?** No

- Link: https://alligare.com/wp-content/uploads/2024/06/Alligare-Sonora-Herbicide-SDS-v2.0-032823.pdf
- Document Date (if known): March 28, 2023
- Suggested File Name: SonoraHerbicide_SDS_2023-03-28.pdf

I was unable to find any newer documents than the ones you provided. The links above point to the most recent Label and SDS based on the search results. Do you need any further assistance?

## 4. OpenAI ChatGPT AI (Free Model - 4o Model) Response (RANK 3):

Here is the most up-to-date information available for Alligare Sonora Herbicide (EPA Reg. No. 81927-69):

1.  **Was a newer Label found?** Yes

    - Link: Sonora Herbicide Label PDF
      https://alligare.com/wp-content/uploads/2024/06/Sonora-2.5Gal-Book_PA_customer-copy.pdf
    - Document Date (if known): December 28, 2018 (as indicated on the label)
    - Suggested File Name: SonoraHerbicide_Label_2018-12-28.pdf

2.  **Was a newer SDS found?** No
    - Link: Sonora Herbicide SDS PDF
      https://alligare.com/wp-content/uploads/2024/06/Alligare-Sonora-Herbicide-SDS-v2.0-032823.pdf
    - Document Date (if known): March 28, 2023
    - Suggested File Name: SonoraHerbicide_SDS_2023-03-28.pdf

**Summary:**

**Label:** The most recent label available is dated December 28, 2018. This matches the last known label date and is accessible via the provided link.

**SDS:** The latest Safety Data Sheet is dated March 28, 2023, which aligns with the last known SDS date. No newer version has been found.
US EPA

For further details or updates, you may refer to the Alligare Sonora Herbicide product page.

## Result Summary - TEST 1

| Rank | Service       | Reason                                               |
| ---- | ------------- | ---------------------------------------------------- |
| 🥇 1 | Perplexity AI | Found and confirmed newer label PDF; perfect format  |
| 🥈 2 | Gemini        | Clean output, but didn’t find newer label            |
| 🥉 3 | ChatGPT       | Found correct file but failed on date parsing        |
| ❌ 4 | Copilot       | Missed updated label, weak formatting, poor sourcing |

# AI Prompt 2

You are a web research assistant. Your task is to search the internet and find the most up-to-date Label and SDS (Safety Data Sheet) documents for a pesticide or chemical product.

**Focus on:**

- Searching official manufacturer websites, EPA databases, and trusted agricultural product portals.
- Returning direct PDF links to the Label and SDS documents if possible.
- If direct links are unavailable, return the most relevant page URL where the document can be downloaded manually.
- Prioritize files that mention a newer revision date than the ones provided.
- For SDS documents, look for “Revision Date,” “Revised,” or “Updated” on the document (not “Printed” date).
- If a newer document is found, suggest a filename in the format: `ProductName_Label_YYYY-MM-DD.pdf` or `ProductName_SDS_YYYY-MM-DD.pdf`

**Return format:**

1.  **Was a newer Label found?** Yes/No

    - Link: [paste PDF link or webpage]
    - Document Date (if known): [e.g., Jan 5, 2024]
    - Suggested File Name: [e.g., FanfareES_Label_2024-01-05.pdf]

2.  **Was a newer SDS found?** Yes/No
    - Link: [paste PDF link or webpage]
    - Document Date (if known): [e.g., Mar 12, 2024]
    - Suggested File Name: [e.g., FanfareES_SDS_2024-03-12.pdf]

If nothing is found or the document is outdated, say so clearly.

---

**DATA:**

- **Product Name:** Fanfare ES
- **Manufacturer:** Adama
- **EPA Registration #:** 66222-236
- **Last Known Label Date:** February 3, 2020
- **Last Known SDS Date:** October 26, 2015
- **Reference Page (if needed):** https://www.adama.com/us/en/crop-protection/insecticides/fanfare-es.html

---

# Results 2

## 1. Perplexity AI (Free Model) Response (RANK 1):

**Was a newer Label found?** Yes

- Link: https://www3.epa.gov/pesticides/chem_search/ppls/066222-00236-20220304.pdf
- Document Date (if known): March 4, 2022
- Suggested File Name: FanfareES_Label_2022-03-04.pdf

**Was a newer SDS found?** No

- Link: https://s3-us-west-1.amazonaws.com/agrian-cg-fs1-production/pdfs/Fanfare_ES_MSDS1w.pdf
- Document Date (if known): October 26, 2015
- Suggested File Name: FanfareES_SDS_2015-10-26.pdf

**Summary:**
A newer Fanfare ES label dated March 4, 2022, is available from the EPA, which is more recent than the previously known February 3, 2020 version. However, the most recent SDS found remains dated October 26, 2015; no update beyond this revision was located.

## 2. Microsoft Copilot AI (Free Model) Response (RANK 4):

Here’s what I found regarding the latest Label and SDS documents for Fanfare ES:

**Was a newer Label found?** Yes

- Link: EPA Label Page
  https://ordspub.epa.gov/ords/pesticides/f?p=PPLS:102:::NO::P102_REG_NUM:66222-236
- Document Date: March 4, 2022
- Suggested File Name: FanfareES_Label_2022-03-04.pdf

**Was a newer SDS found?** No

- Link: https://s3-us-west-1.amazonaws.com/agrian-cg-fs1-production/pdfs/Fanfare_ES_MSDS1w.pdf
- Document Date: October 26, 2015

It looks like the label has been updated since the last known version, but the SDS remains unchanged. Let me know if you need further assistance!

## 3. Google Gemini AI (Free Model - 2.0 Flash Model) Response (RANK 2):

**Was a newer Label found?** Yes

- Link: https://www3.epa.gov/pesticides/chem_search/ppls/066222-00236-20220304.pdf
- Document Date (if known): March 4, 2022
- Suggested File Name: FanfareES_Label_2022-03-04.pdf

**Was a newer SDS found?** Yes

- Link: https://s3-us-west-1.amazonaws.com/agrian-cg-fs1-production/pdfs/Fanfare_ES_MSDS1w.pdf
- Document Date (if known): October 26, 2015
- Suggested File Name: FanfareES_SDS_2015-10-26.pdf

Although the SDS found has the same date as the last known SDS date you provided, it is often beneficial to have a direct link to the document for ease of access. The label found has a more recent date than the one provided.

## 4. OpenAI ChatGPT AI (Free Model - 4o Model) Response (RANK 3):

After conducting a thorough search, here are the most up-to-date Label and Safety Data Sheet (SDS) documents for Fanfare ES (EPA Reg. No. 66222-236) by Adama:

1.  **Was a newer Label found?** Yes

    - Link: Fanfare ES Label PDF
      https://www3.epa.gov/pesticides/chem_search/ppls/066222-00236-20220304.pdf
    - Document Date: March 4, 2022
    - Suggested File Name: FanfareES_Label_2022-03-04.pdf

2.  **Was a newer SDS found?** No
    - Link: Fanfare ES SDS PDF
      https://s3-us-west-1.amazonaws.com/agrian-cg-fs1-production/pdfs/Fanfare_ES_MSDS1w.pdf
    - Document Date: October 26, 2015
    - Suggested File Name: FanfareES_SDS_2015-10-26.pdf

**Summary:**

**Label:** A newer label dated March 4, 2022, has been found, which is more recent than the last known label dated February 3, 2020.

**SDS:** No newer SDS has been located beyond the existing document dated October 26, 2015.

For further information or updates, you may refer to the Adama Fanfare ES product page.

## Result Summary - TEST 2

| Rank | Service       | Reason                                                                                    |
| ---- | ------------- | ----------------------------------------------------------------------------------------- |
| 🥇 1 | Perplexity AI | Found correct label PDF with clear date; cleanest, structured, automation-friendly output |
| 🥈 2 | Gemini        | Accurate results; slightly misleading SDS "Yes", otherwise well formatted                 |
| 🥉 3 | ChatGPT       | Good structure, but over-explained; not as concise or automation-ready                    |
| ❌ 4 | Copilot       | Correct label date but returned webpage, not PDF; least structured output                 |

# AI Prompt 3

You are a web research assistant. Your task is to search the internet and find the most up-to-date Label and SDS (Safety Data Sheet) documents for a pesticide or chemical product.

**Focus on:**

- Searching official manufacturer websites, EPA databases, and trusted agricultural product portals.
- Returning direct **plain PDF URLs** to the Label and SDS documents if possible.
- Do not embed links in text — show the full URL directly.
- If direct links are unavailable, return the most relevant page URL where the document can be downloaded manually.
- Prioritize files that mention a newer revision date than the ones provided.
- For SDS documents, look for “Revision Date,” “Revised,” or “Updated” on the document (not “Printed” date).
- If a newer document is found, suggest a filename in the format: `ProductName_Label_YYYY-MM-DD.pdf` or `ProductName_SDS_YYYY-MM-DD.pdf`

**Return format:**

1.  **Was a newer Label found?** Yes/No

    - Link: [paste full URL of PDF or webpage here — no embedded text]
    - Document Date (if known): [e.g., Jan 5, 2024]
    - Suggested File Name: [e.g., ImidaPro2SC_Label_2024-01-05.pdf]

2.  **Was a newer SDS found?** Yes/No
    - Link: [paste full URL of PDF or webpage here — no embedded text]
    - Document Date (if known): [e.g., Mar 12, 2024]
    - Suggested File Name: [e.g., ImidaPro2SC_SDS_2024-03-12.pdf]

If nothing is found or the document is outdated, say so clearly.

---

**DATA:**

- **Product Name:** ImidaPro 2SC
- **Manufacturer:** Agrisel
- **EPA Registration #:** 83529-2-72159
- **Last Known Label Date:** November 22, 2019
- **Last Known SDS Date:** September 1, 2014
- **Reference Page (if needed):** https://agrisel.com/2019/08/agrisel-imidapro-2sc/

---

# Results 3

## 1. Perplexity AI (Free Model) Response:

**Was a newer Label found?** Yes

- Link: https://www.domyown.com/msds/ImidaPro_2SC_Label_2020.pdf
- Document Date (if known): 2020 (file name and content indicate 2020; this is newer than Nov 22, 2019)
- Suggested File Name: ImidaPro2SC_Label_2020-01-01.pdf

**Was a newer SDS found?** No

- Link: https://www.domyown.com/msds/ImidaPro+2SC+SDS.pdf
- Document Date (if known): September 1, 2014 (no newer SDS found; all available SDS documents reference 2014)
- Suggested File Name: ImidaPro2SC_SDS_2014-09-01.pdf

If you require only documents with explicit revision dates on the first page, please specify. No SDS newer than 2014 was identified in this search.

## 2. Microsoft Copilot AI (Free Model) Response:

Here’s what I found regarding the latest Label and SDS documents for ImidaPro 2SC:

**Was a newer Label found?** No

- Link: https://www3.epa.gov/pesticides/chem_search/ppls/072159-00002-20090217.pdf
- Document Date: February 17, 2009

**Was a newer SDS found?** No

- Link: https://agrisel.com/wp-content/uploads/2019/08/ImidaPro2SC___SDS.pdf
- Document Date: August 2019

It looks like there are no newer versions of these documents beyond what you already have. Let me know if you need help with anything else.

## 3. Google Gemini AI (Free Model - 2.0 Flash Model) Response (RANK 2):

**Was a newer Label found?** Yes

- Link: https://www.google.com/search?q=https://www3.epa.gov/pesticides/chem_search/ppls/083529-00002-20230308.pdf
- Document Date (if known): March 8, 2023
- Suggested File Name: ImidaPro2SC_Label_2023-03-08.pdf

**Was a newer SDS found?** Yes

- Link: https://www.google.com/search?q=https://agrisel.com/wp-content/uploads/2020/07/ImidaPro-2SC-SDS.pdf
- Document Date (if known): July 1, 2020
- Suggested File Name: ImidaPro2SC_SDS_2020-07-01.pdf

## 4. OpenAI ChatGPT AI (Free Model - 4o Model) Response:

Here are the most up-to-date documents available for ImidaPro 2SC (EPA Reg. No. 83529-2-72159) by Agrisel:

1.  **Was a newer Label found?** Yes

    - Link: https://www.domyown.com/msds/ImidaPro_2SC_Label_2020.pdf
    - Document Date: November 22, 2019
    - Suggested File Name: ImidaPro2SC_Label_2019-11-22.pdf

2.  **Was a newer SDS found?** No
    - Link: https://www.domyown.com/msds/ImidaPro%2B2SC%2BSDS.pdf
    - Document Date: September 1, 2014
    - Suggested File Name: ImidaPro2SC_SDS_2014-09-01.pdf

**Summary:**

**Label:** The most recent label available is dated November 22, 2019, which matches the last known label date.

**SDS:** The latest Safety Data Sheet is dated September 1, 2014, aligning with the last known SDS date.

For further information or updates, you may refer to the Agrisel ImidaPro 2SC product page.

## Result Summary - TEST 3

| Rank | Service       | Reason                                                                 |
| ---- | ------------- | ---------------------------------------------------------------------- |
| 🥇 1 | Perplexity AI | Found newer 2020 label, correct SDS; clean direct links; best accuracy |
| 🥈 2 | ChatGPT (4o)  | Matched Perplexity on content; slightly worse date handling            |
| 🥉 3 | Copilot       | Provided working links, but label is outdated (2009); SDS was accurate |
| ❌ 4 | Gemini        | Gave fake Google search links; none of them actually worked            |

# AI Prompt 4

You are a web research assistant. Your task is to search the internet and find the most up-to-date Label and SDS (Safety Data Sheet) documents for a pesticide or chemical product.

**Focus on:**

- Searching official manufacturer websites, EPA databases, and trusted agricultural product portals.
- Returning direct **plain PDF URLs** to the Label and SDS documents if possible.
- Do not embed links in text — show the full URL directly.
- If direct links are unavailable, return the most relevant page URL where the document can be downloaded manually.
- Prioritize files that mention a newer revision date than the ones provided.
- For SDS documents, look for “Revision Date,” “Revised,” or “Updated” on the document (not “Printed” date).
- If a newer document is found, suggest a filename in the format: `ProductName_Label_YYYY-MM-DD.pdf` or `ProductName_SDS_YYYY-MM-DD.pdf`

**Return format:**

1.  **Was a newer Label found?** Yes/No

    - Link: [paste full URL of PDF or webpage here — no embedded text]
    - Document Date (if known): [e.g., Jan 5, 2024]
    - Suggested File Name: [e.g., ImidaPro2SC_Label_2024-01-05.pdf]

2.  **Was a newer SDS found?** Yes/No
    - Link: [paste full URL of PDF or webpage here — no embedded text]
    - Document Date (if known): [e.g., Mar 12, 2024]
    - Suggested File Name: [e.g., ImidaPro2SC_SDS_2024-03-12.pdf]

If nothing is found or the document is outdated, say so clearly.

---

**DATA:**

- **Product Name:** Pendulum 2G Granule Herbicide
- **Manufacturer:** BASF
- **EPA Registration #:** 241-375
- **Last Known Label Date:** May 1, 2008
- **Last Known SDS Date:** April 3, 2023
- **Reference Page (if needed):** https://betterplants.basf.us/products/pendulum--2g-herbicide.html

---

# Results 4

## 1. Perplexity AI (Free Model) Response:

**Was a newer Label found?** No

- Link: https://betterplants.basf.us/products/pendulum--2g-herbicide.html
- Document Date (if known): May 1, 2008
- Suggested File Name: Pendulum2G_Label_2008-05-01.pdf

**Was a newer SDS found?** No

- Link: https://betterplants.basf.us/products/pendulum--2g-herbicide.html
- Document Date (if known): April 3, 2023
- Suggested File Name: Pendulum2G_SDS_2023-04-03.pdf

No newer label or SDS than those already known could be found. The manufacturer’s site and trusted portals only provide the May 1, 2008 label and the April 3, 2023 SDS.

## 2. Microsoft Copilot AI (Free Model) Response:

Here’s what I found regarding the latest Label and SDS documents for Pendulum 2G Granule Herbicide:

**Was a newer Label found?** Yes

- Link: https://iaspub.epa.gov/apex/pesticides/f?p=PPLS:102:::NO::P102_REG_NUM:241-375
- Document Date: May 1, 2009
- Suggested File Name: Pendulum2G_Label_2009-05-01.pdf

**Was a newer SDS found?** No

- Link: https://www.domyown.com/msds/Pendulum_2G_SDS.pdf
- Document Date: December 4, 2015

It looks like the label has been updated since the last known version, but the SDS remains outdated compared to the last known date. Let me know if you need further assistance!

## 3. Google Gemini AI (Free Model - 2.0 Flash Model) Response:

**Was a newer Label found?** Yes

- Link: https://www.google.com/search?q=https://www3.epa.gov/pesticides/chem_search/ppls/000241-00375-20230811.pdf
- Document Date (if known): August 11, 2023
- Suggested File Name: Pendulum2G_Label_2023-08-11.pdf

**Was a newer SDS found?** No

- Link: https://www.google.com/search?q=https://betterplants.basf.us/media/filer_public/a2/6a/a26a136b-961f-4389-a91e-8801b4a854a2/pendulum_2g_herbicide_sds.pdf
- Document Date (if known): April 3, 2023
- Suggested File Name: Pendulum2G_SDS_2023-04-03.pdf

## 4. OpenAI ChatGPT AI (Free Model - 4o Model) Response:

Here are the most up-to-date documents available for Pendulum 2G Granule Herbicide (EPA Reg. No. 241-375) by BASF:

1.  **Was a newer Label found?** No

    - Link: https://www3.epa.gov/pesticides/chem_search/ppls/000241-00375-20090501.pdf
    - Document Date: May 1, 2009
    - Suggested File Name: Pendulum2G_Label_2009-05-01.pdf

2.  **Was a newer SDS found?** No
    - Link: https://labelsds.com/images/user_uploads/Pendulum%202G%20SDS%204-3-23.pdf
    - Document Date: April 3, 2023
    - Suggested File Name: Pendulum2G_SDS_2023-04-03.pdf

**Summary:**

**Label:** The most recent label available is dated May 1, 2009, which is newer than the last known label date of May 1, 2008.

**SDS:** The latest Safety Data Sheet is dated April 3, 2023, aligning with the last known SDS date.

For further information or updates, you may refer to the BASF Pendulum 2G Herbicide product page.

## Result Summary - TEST 4

| Rank | Service       | Reason                                                                                           |
| ---- | ------------- | ------------------------------------------------------------------------------------------------ |
| 🥇 1 | ChatGPT (4o)  | Found **direct, accurate PDF links** (label & SDS); best date accuracy; fully prompt-compliant   |
| 🥈 2 | Perplexity AI | Correct SDS, but returned **webpage instead of direct label PDF** and listed outdated label date |
| 🥉 3 | Copilot       | Got the 2009 label date right, but **label link was generic**, and SDS was **outdated (2015)**   |
| ❌ 4 | Gemini        | Gave **search queries** instead of usable links; not automation-ready                            |

# AI Prompt 5

You are a web research assistant. Your task is to search the internet and find the most up-to-date Label and SDS (Safety Data Sheet) documents for a pesticide or chemical product.

Focus on:

- Searching official manufacturer websites, EPA databases, and trusted agricultural product portals.
- Returning direct **plain PDF URLs** to the Label and SDS documents if possible.
- Do not embed links in text — show the full URL directly.
- If direct links are unavailable, return the most relevant page URL where the document can be downloaded manually.
- Prioritize files that mention a newer revision date than the ones provided.
- For SDS documents, look for “Revision Date,” “Revised,” or “Updated” on the document (not “Printed” date).
- If a newer document is found, suggest a filename in the format: ProductName_Label_YYYY-MM-DD.pdf or ProductName_SDS_YYYY-MM-DD.pdf

Return format:

1.  **Was a newer Label found?** Yes/No

    - Link: [paste full URL of PDF or webpage here — no embedded text]
    - Document Date (if known): [e.g., Jan 5, 2024]
    - Suggested File Name: [e.g., Sequestar13Mn_Label_2024-01-05.pdf]

2.  **Was a newer SDS found?** Yes/No
    - Link: [paste full URL of PDF or webpage here — no embedded text]
    - Document Date (if known): [e.g., Mar 12, 2024]
    - Suggested File Name: [e.g., Sequestar13Mn_SDS_2024-03-12.pdf]

If nothing is found or the document is outdated, say so clearly.

---

**DATA:**

- **Product Name:** Sequestar 13% Mn
- **Manufacturer:** Brandt
- **EPA Registration #:** Not provided
- **Last Known Label Date:** August 1, 2018
- **Last Known SDS Date:** November 12, 2018
- **Reference Page (if needed):** https://brandt.co/lines/brandt-sequestar/

---

# Results 5

## 1. Perplexity AI (Free Model) Response:

| Found? | Direct Link or Page URL                   | Document Date               | Suggested File Name                |
| ------ | ----------------------------------------- | --------------------------- | ---------------------------------- |
| No     | https://brandt.co/lines/brandt-sequestar/ | August 1, 2018 (last known) | Sequestar13Mn_Label_2018-08-01.pdf |

**Label:**
No newer label was found. The Brandt website only provides the August 1, 2018 version or older.

| Found? | Direct Link or Page URL                   | Document Date                  | Suggested File Name              |
| ------ | ----------------------------------------- | ------------------------------ | -------------------------------- |
| No     | https://brandt.co/lines/brandt-sequestar/ | November 12, 2018 (last known) | Sequestar13Mn_SDS_2018-11-12.pdf |

**SDS:**
No newer SDS was found. The Brandt website and trusted portals only provide the November 12, 2018 version or older.

**Summary:**
No updated Label or SDS documents (newer than those provided) could be found from official manufacturer or trusted sources.

Citations:
[1] https://labelsds.com/images/user_uploads/Pendulum%202G%20SDS%204-3-23.pdf
[2] https://betterturf.basf.us/products/pendulum--2g-herbicide.html
[3] https://www.trianglecc.com/wp-content/uploads/2022/08/Pendulum-2G-Label.pdf
[4] https://labelsds.com/images/user_uploads/Pendulum%202G%20Label%205-1-08.pdf
[5] https://betterplants.basf.us/products/pendulum--2g-herbicide.html
[6] https://spsonline.com/wp-content/uploads/2024/10/Pendulum-AquaCap-SDS.pdf
[7] https://www.epa.gov/ingredients-used-pesticide-products/how-search-information-about-pesticide-ingredients-and-labels
[8] https://apps.cdpr.ca.gov/docs/label/labelque.cfm
[9] https://www.epa.gov/pesticide-registration/prn-92-4-material-safety-data-sheets-pesticide-labeling
[10] https://www.epa.gov/pesticide-registration/prn-2012-1-material-safety-data-sheets-pesticide-labeling

---

Answer from Perplexity: pplx.ai/share

## 2. Microsoft Copilot AI (Free Model) Response:

Here’s what I found regarding the latest Label and SDS documents for **Sequestar 13% Mn**:

### **Label Document**

| Found? | Direct Link or Page URL                                       | Document Date | Suggested File Name             |
| ------ | ------------------------------------------------------------- | ------------- | ------------------------------- |
| Yes    | https://brandt.co/media/7662/brandt-sequestar-13-mn-label.pdf | August 2018   | Sequestar13Mn_Label_2018-08.pdf |

### **SDS Document**

| Found? | Direct Link or Page URL                                     | Document Date     | Suggested File Name              |
| ------ | ----------------------------------------------------------- | ----------------- | -------------------------------- |
| Yes    | https://brandt.co/media/8288/brandt-sequestar-13-mn-sds.pdf | November 12, 2018 | Sequestar13Mn_SDS_2018-11-12.pdf |

It looks like the label document matches the last known date, and the SDS document is the same as the last known version. Let me know if you need further assistance!

## 3. Google Gemini AI (Free Model - 2.0 Flash Model) Response:

Okay, I will find the most up-to-date Label and SDS for Sequestar 13% Mn, avoiding links from labelsds.com and presenting the results in a table.

**Label Search Results:**

| Found? | Direct Link or Page URL                                                                                                                                                                                                                    | Document Date  | Suggested File Name                |
| :----- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------- | :--------------------------------- |
| Yes    | [https://www.google.com/search?q=https://brandt.co/wp-content/uploads/2020/01/Sequestar-13-Mn-Label-08.01.18-REV.pdf](https://www.google.com/search?q=https://brandt.co/wp-content/uploads/2020/01/Sequestar-13-Mn-Label-08.01.18-REV.pdf) | August 1, 2018 | Sequestar13Mn_Label_2018-08-01.pdf |

**SDS Search Results:**

| Found? | Direct Link or Page URL                                                                                                                                                                                                                | Document Date     | Suggested File Name              |
| :----- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------- | :------------------------------- |
| Yes    | [https://www.google.com/search?q=https://brandt.co/wp-content/uploads/2020/01/Sequestar-13-Mn-SDS-11.12.18-REV.pdf](https://www.google.com/search?q=https://brandt.co/wp-content/uploads/2020/01/Sequestar-13-Mn-SDS-11.12.18-REV.pdf) | November 12, 2018 | Sequestar13Mn_SDS_2018-11-12.pdf |

I did not find any newer Label or SDS documents than the ones provided.

## 4. OpenAI ChatGPT AI (Free Model - 4o Model) Response:

Here are the most up-to-date documents available for **Sequestar 13% Mn** by **Brandt**:

---

### Label Document

| Found? | Direct Link or Page URL                                       | Document Date  | Suggested File Name                |
| ------ | ------------------------------------------------------------- | -------------- | ---------------------------------- |
| Yes    | https://brandt.co/media/7662/brandt-sequestar-13-mn-label.pdf | August 1, 2018 | Sequestar13Mn_Label_2018-08-01.pdf |

---

### Safety Data Sheet (SDS)

| Found? | Direct Link or Page URL                                     | Document Date     | Suggested File Name              |
| ------ | ----------------------------------------------------------- | ----------------- | -------------------------------- |
| Yes    | https://brandt.co/media/8288/brandt-sequestar-13-mn-sds.pdf | November 12, 2018 | Sequestar13Mn_SDS_2018-11-12.pdf |

---

**Summary:**

- **Label:** The most recent label available is dated **August 1, 2018**, which matches the last known label date.

- **SDS:** The latest Safety Data Sheet is dated **November 12, 2018**, aligning with the last known SDS date.

For further information or updates, you may refer to the [Brandt Sequestar product page](https://brandt.co/lines/brandt-sequestar/).

## Result Summary - TEST 5

| Rank | Service       | Reason                                                                |
| ---- | ------------- | --------------------------------------------------------------------- |
| 🥇 1 | ChatGPT (4o)  | Perfect execution — full direct links, correct dates, clean tables    |
| 🥈 2 | Copilot       | Matches ChatGPT in links and accuracy, slightly weaker formatting     |
| 🥉 3 | Perplexity AI | Accurate, but returned only page link, not PDFs; cluttered citations  |
| ❌ 4 | Gemini        | Returned Google search URLs; breaks prompt rules; not automation-safe |

# AI Prompt 6

You are a web research assistant. Your task is to search the internet and find the most up-to-date Label and SDS (Safety Data Sheet) documents for a pesticide or chemical product.

Focus on:

- Searching official manufacturer websites, EPA databases, and trusted agricultural product portals.
- Returning direct **plain PDF URLs** to the Label and SDS documents if possible.
- Do not embed links in text — show the full URL directly.
- **Do not return any links from https://labelsds.com/**. We already track our own database, so ignore anything hosted there.
- If direct links are unavailable, return the most relevant page URL where the document can be downloaded manually.
- Prioritize files that mention a newer revision date than the ones provided.
- For SDS documents, look for “Revision Date,” “Revised,” or “Updated” on the document (not “Printed” date).
- If a newer document is found, suggest a filename in the format: ProductName_Label_YYYY-MM-DD.pdf or ProductName_SDS_YYYY-MM-DD.pdf

Return the results in **table format** for each document type (Label and SDS) with the following columns:
| Found? | Direct Link or Page URL | Document Date | Suggested File Name | Is Newer than Last Known? |

If nothing is found or the document is outdated, say so clearly.

⸻
**DATA:**

- **Product Name:** Sniper LFR
- **Manufacturer:** Loveland Products
- **EPA Registration #:** 34704-1089
- **Last Known Label Date:** September 17, 2018
- **Last Known SDS Date:** October 26, 2018
- **Reference Page (if needed):** https://www.lovelandproducts.com/content/loveland/us/en/products/crop-protection/insecticide/sniper-lfr.html

# Results 6

## 1. Perplexity AI (Free Model) Response:

### Label

| Found? | Direct Link or Page URL                                                                                      | Document Date                   | Suggested File Name            | Is Newer than Last Known? |
| ------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------- | ------------------------------ | ------------------------- |
| No     | https://www.lovelandproducts.com/content/loveland/us/en/products/crop-protection/insecticide/sniper-lfr.html | September 17, 2018 (last known) | SniperLFR_Label_2018-09-17.pdf | No                        |

### SDS

| Found? | Direct Link or Page URL                                                                                      | Document Date                 | Suggested File Name          | Is Newer than Last Known? |
| ------ | ------------------------------------------------------------------------------------------------------------ | ----------------------------- | ---------------------------- | ------------------------- |
| No     | https://www.lovelandproducts.com/content/loveland/us/en/products/crop-protection/insecticide/sniper-lfr.html | October 26, 2018 (last known) | SniperLFR_SDS_2018-10-26.pdf | No                        |

**No newer Label or SDS for Sniper LFR was found. The most current documents available remain the September 17, 2018 label and the October 26, 2018 SDS.**

Citations:
[1] https://brandt.co/media/8288/brandt-sequestar-13-mn-sds.pdf
[2] https://brandt.allsystemsgo.net/media/1449/brandt-sequestar-13-mn-sds.pdf
[3] https://brandt.co/media/7662/brandt-sequestar-13-mn-label.pdf
[4] https://veseris.com/default/t-o-vegetation/fertilizers-plant-nutrients/sequestar-13-mn
[5] https://www.target-specialty.com/sequestar-13-manganese-5lb
[6] http://portlandcleanair.org/files/merge/msds/SEQUESTAR_13_MANGANESE_CHELATE.PDF
[7] https://www.golfventures.com/assets/1/6/brandt-sequestar-5-mn-sds.pdf
[8] https://brandt.co/lines/brandt-sequestar/

---

Answer from Perplexity: pplx.ai/share

## 2. Microsoft Copilot AI (Free Model) Response:

Here’s what I found regarding the latest Label and SDS documents for **Sniper LFR**:

### **Label Document**

| Found? | Direct Link or Page URL                                                                             | Document Date      | Suggested File Name            | Is Newer than Last Known? |
| ------ | --------------------------------------------------------------------------------------------------- | ------------------ | ------------------------------ | ------------------------- |
| No     | [EPA Label Page](https://iaspub.epa.gov/apex/pesticides/f?p=PPLS:102:::NO::P102_REG_NUM:34704-1089) | September 17, 2018 | SniperLFR_Label_2018-09-17.pdf | No                        |

### **SDS Document**

| Found? | Direct Link or Page URL | Document Date | Suggested File Name | Is Newer than Last Known? |
| ------ | ----------------------- | ------------- | ------------------- | ------------------------- |
| No     | No updated SDS found    | N/A           | N/A                 | No                        |

It looks like the label remains unchanged since the last known version, and I couldn't find a newer SDS document. Let me know if you need further assistance!

## 3. Google Gemini AI (Free Model - 2.0 Flash Model) Response:

Okay, I will find the most up-to-date Label and SDS for Sniper LFR, avoiding links from labelsds.com and presenting the results in a table with an additional column indicating if the found document is newer than the last known one.

**Label Search Results:**

| Found? | Direct Link or Page URL                                                                                                                                                                                                  | Document Date | Suggested File Name            | Is Newer than Last Known? |
| :----- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------ | :----------------------------- | :------------------------ |
| Yes    | [https://www.google.com/search?q=https://www3.epa.gov/pesticides/chem_search/ppls/034704-01089-20220303.pdf](https://www.google.com/search?q=https://www3.epa.gov/pesticides/chem_search/ppls/034704-01089-20220303.pdf) | March 3, 2022 | SniperLFR_Label_2022-03-03.pdf | Yes                       |

**SDS Search Results:**

| Found? | Direct Link or Page URL                                                                                                                          | Document Date            | Suggested File Name          | Is Newer than Last Known? |
| :----- | :----------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------- | :--------------------------- | :------------------------ |
| Yes    | [https://www.google.com/search?q=https://www.cdms.net/ldat/mp0BX000.pdf](https://www.google.com/search?q=https://www.cdms.net/ldat/mp0BX000.pdf) | **Revised:** May 1, 2024 | SniperLFR_SDS_2024-05-01.pdf | Yes                       |

I found a newer Label dated March 3, 2022, and a newer SDS with a revision date of May 1, 2024, compared to the last known dates provided.

## 4. OpenAI ChatGPT AI (Free Model - 4o Model) Response:

Here are the most up-to-date documents available for **Sniper LFR** (EPA Reg. No. 34704-1089) by **Loveland Products**:

---

### Label Document

| Found? | Direct Link or Page URL                                                    | Document Date      | Suggested File Name            | Is Newer than Last Known? |
| ------ | -------------------------------------------------------------------------- | ------------------ | ------------------------------ | ------------------------- |
| Yes    | https://www3.epa.gov/pesticides/chem_search/ppls/034704-01089-20180917.pdf | September 17, 2018 | SniperLFR_Label_2018-09-17.pdf | No                        |

---

### Safety Data Sheet (SDS)

| Found? | Direct Link or Page URL                                               | Document Date    | Suggested File Name          | Is Newer than Last Known? |
| ------ | --------------------------------------------------------------------- | ---------------- | ---------------------------- | ------------------------- |
| Yes    | https://assets.greenbook.net/18-31-32-21-02-2019-Sniper_LFR_MSDS3.pdf | October 26, 2018 | SniperLFR_SDS_2018-10-26.pdf | No                        |

---

**Summary:**

- **Label:** The most recent label available is dated **September 17, 2018**, which matches the last known label date.

- **SDS:** The latest Safety Data Sheet is dated **October 26, 2018**, aligning with the last known SDS date.

For further information or updates, you may refer to the [Loveland Products Sniper LFR product page](https://www.lovelandproducts.com/content/loveland/us/en/products/crop-protection/insecticide/sniper-lfr.html).

## Result Summary - TEST 6

| Rank | Service       | Reason                                                                                          |
| ---- | ------------- | ----------------------------------------------------------------------------------------------- |
| 🥇 1 | ChatGPT (4o)  | Found valid, correct direct links for both label and SDS; best formatting and prompt compliance |
| 🥈 2 | Perplexity AI | Only reached product page, not direct PDFs; clean format but didn't dig deep enough             |
| 🥉 3 | Copilot       | Just linked EPA landing page, no direct PDF, and failed to find SDS                             |
| ❌ 4 | Gemini        | Returned non-working search and broken links; failed formatting and accuracy                    |

# AI Prompt 7

You are a web research assistant. Your task is to search the internet and find the most up-to-date Label and SDS (Safety Data Sheet) documents for a pesticide or chemical product.

Focus on:

- Searching official manufacturer websites, EPA databases, and trusted agricultural product portals.
- Returning direct **plain PDF URLs** to the Label and SDS documents if possible.
- Do not embed links in text — show the full URL directly.
- **Do not return any links from https://labelsds.com/**. We already track our own database, so ignore anything hosted there.
- If direct links are unavailable, return the most relevant page URL where the document can be downloaded manually.
- Prioritize files that mention a newer revision date than the ones provided.
- For SDS documents, look for “Revision Date,” “Revised,” or “Updated” on the document (not “Printed” date).
- If a newer document is found, suggest a filename in the format: ProductName_Label_YYYY-MM-DD.pdf or ProductName_SDS_YYYY-MM-DD.pdf

Return the results in **table format** for each document type (Label and SDS) with the following columns:
| Found? | Direct Link or Page URL | Document Date | Suggested File Name | Is Newer than Last Known? |

If nothing is found or the document is outdated, say so clearly.

⸻
**DATA:**

- **Product Name:** Oatey Plumbers Putty
- **Manufacturer:** Oatey
- **EPA Registration #:** None
- **Last Known Label Date:** None
- **Last Known SDS Date:** May 11, 2023
- **Reference Page (if needed):** https://www.oatey.com/products/oatey-plumbers-putty--1165995750?upc=038753311661

# Results 7

## 1. Perplexity AI (Free Model) Response:

### Label

| Found? | Direct Link or Page URL                                                          | Document Date | Suggested File Name               | Is Newer than Last Known? |
| ------ | -------------------------------------------------------------------------------- | ------------- | --------------------------------- | ------------------------- |
| No     | https://www.oatey.com/products/oatey-plumbers-putty--1165995750?upc=038753311661 | Not listed    | OateyPlumbersPutty_Label_NONE.pdf | No                        |

### SDS

| Found? | Direct Link or Page URL                                                          | Document Date | Suggested File Name                   | Is Newer than Last Known? |
| ------ | -------------------------------------------------------------------------------- | ------------- | ------------------------------------- | ------------------------- |
| No     | https://www.oatey.com/products/oatey-plumbers-putty--1165995750?upc=038753311661 | May 11, 2023  | OateyPlumbersPutty_SDS_2023-05-11.pdf | No                        |

**Summary:**  
No newer Label or SDS for Oatey Plumbers Putty was found. The most current SDS remains the May 11, 2023 version, and no official product label document is available from the manufacturer or trusted sources.

Citations:
[1] https://assets.greenbook.net/18-31-32-21-02-2019-Sniper_LFR_MSDS3.pdf
[2] https://labelsds.com/view-product?product=2047&company_uuid=2ef23451-6554-4145-8fd5-587cae6bc8d6&hide_nav=1
[3] https://labelsds.com/chemical-label-list?company_code=6046875d6c440&product_page=14&product_search=
[4] https://www.lovelandproducts.com/content/loveland/us/en/products/crop-protection/insecticide/sniper-lfr.html
[5] https://sdsviewer.fmc.com/SDS_DOCS/50000395_SDS_US_EN.PDF
[6] https://s3-us-west-1.amazonaws.com/agrian-cg-fs1-production/pdfs/Sniper_MSDS6.pdf
[7] https://www3.epa.gov/pesticides/chem_search/ppls/034704-01089-20180917.pdf
[8] https://kernred.co.kern.ca.us/kern-agcomm/products/SNIPER.pdf

---

Answer from Perplexity: pplx.ai/share

## 2. Microsoft Copilot AI (Free Model) Response:

Here’s what I found regarding the latest Label and SDS documents for **Oatey Plumbers Putty**:

### **Label Document**

| Found? | Direct Link or Page URL | Document Date | Suggested File Name | Is Newer than Last Known? |
| ------ | ----------------------- | ------------- | ------------------- | ------------------------- |
| No     | No label document found | N/A           | N/A                 | N/A                       |

### **SDS Document**

| Found? | Direct Link or Page URL                                                                          | Document Date | Suggested File Name                   | Is Newer than Last Known? |
| ------ | ------------------------------------------------------------------------------------------------ | ------------- | ------------------------------------- | ------------------------- |
| Yes    | https://www.shop.msdscatalogservice.com/system/files/raw_04_Oatey_PlumbersPutty_SDS_00395643.pdf | May 11, 2023  | OateyPlumbersPutty_SDS_2023-05-11.pdf | No                        |

It looks like the SDS document matches the last known date, and I couldn't find a label document for this product. Let me know if you need further assistance!

## 3. Google Gemini AI (Free Model - 2.0 Flash Model) Response:

Okay, I will find the most up-to-date Label and SDS for Oatey Plumbers Putty, avoiding links from labelsds.com and presenting the results in a table with an additional column indicating if the found document is newer than the last known one.

**Label Search Results:**

| Found? | Direct Link or Page URL | Document Date | Suggested File Name | Is Newer than Last Known? |
| :----- | :---------------------- | :------------ | :------------------ | :------------------------ |
| No     | None                    | None          | None                | N/A                       |
|        |                         |               |                     |                           |

**SDS Search Results:**

| Found? | Direct Link or Page URL                                                                                                                                                                                                            | Document Date               | Suggested File Name                   | Is Newer than Last Known? |
| :----- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------- | :------------------------------------ | :------------------------ |
| Yes    | [https://www.google.com/search?q=https://www.oatey.com/ASSETS/DOCUMENTS/ENGLISH/Oatey_Plumbers_Putty_SDS_ENG.pdf](https://www.google.com/search?q=https://www.oatey.com/ASSETS/DOCUMENTS/ENGLISH/Oatey_Plumbers_Putty_SDS_ENG.pdf) | **Revised:** April 28, 2025 | OateyPlumbersPutty_SDS_2025-04-28.pdf | Yes                       |

I was unable to locate a specific label document with a date for Oatey Plumbers Putty. However, I found a Safety Data Sheet with a revision date of April 28, 2025, which is newer than the last known SDS date.

## 4. OpenAI ChatGPT AI (Free Model - 4o Model) Response:

Here are the most up-to-date Label and Safety Data Sheet (SDS) documents for **Oatey Plumber's Putty**:

---

### Label Document

| Found? | Direct Link or Page URL | Document Date | Suggested File Name | Is Newer than Last Known? |
| ------ | ----------------------- | ------------- | ------------------- | ------------------------- |
| No     | Not available           | N/A           | N/A                 | N/A                       |

---

### Safety Data Sheet (SDS)

| Found? | Direct Link or Page URL                                                                  | Document Date | Suggested File Name                   | Is Newer than Last Known? |
| ------ | ---------------------------------------------------------------------------------------- | ------------- | ------------------------------------- | ------------------------- |
| Yes    | https://pdf.lowes.com/productdocuments/4ff3bf9d-70ee-4a52-93d8-1f4e85385ae3/63984677.pdf | May 11, 2023  | OateyPlumbersPutty_SDS_2023-05-11.pdf | No                        |

---

**Summary:**

- **Label:** No label document was found.

- **SDS:** The most recent Safety Data Sheet available is dated **May 11, 2023**, which matches the last known SDS date.

For further information or updates, you may refer to the [Oatey Plumber's Putty product page](https://www.oatey.com/products/oatey-plumbers-putty--1165995750).

## Result Summary - TEST 7

| Rank | Service       | Reason                                                                    |
| ---- | ------------- | ------------------------------------------------------------------------- |
| 🥇 1 | ChatGPT (4o)  | Found correct SDS PDF; clean formatting; full prompt compliance           |
| 🥈 2 | Copilot       | Found correct SDS as well; slightly weaker format                         |
| 🥉 3 | Perplexity AI | Only linked product page; missed downloadable SDS                         |
| ❌ 4 | Gemini        | Gave search link instead of real PDF; claimed 2025 revision with no proof |

# AI Prompt 8

You are a web research assistant. Your task is to search the internet and find the most up-to-date Label and SDS (Safety Data Sheet) documents for a pesticide or chemical product.

Focus on:

- Searching official manufacturer websites, EPA databases, and trusted agricultural product portals.
- Returning direct **plain PDF URLs** to the Label and SDS documents if possible.
- Do not embed links in text — show the full URL directly.
- **Do not return any links from https://labelsds.com/**. We already track our own database, so ignore anything hosted there.
- **Do not return Google search result links.** Only include real, functional PDF file URLs or official product page links where the file can be downloaded manually.
- If direct links are unavailable, return the most relevant official webpage where the document can be accessed.
- Prioritize files that mention a newer revision date than the ones provided.
- For SDS documents, look for “Revision Date,” “Revised,” or “Updated” on the document (not “Printed” date).
- If a newer document is found, suggest a filename in the format: ProductName_Label_YYYY-MM-DD.pdf or ProductName_SDS_YYYY-MM-DD.pdf

Return the results in **table format** for each document type (Label and SDS) with the following columns:
| Found? | Direct Link or Page URL | Document Date | Suggested File Name | Is Newer than Last Known? |

If nothing is found or the document is outdated, say so clearly.

⸻
**DATA:**

- **Product Name:** Crew Specialty Herbicide
- **Manufacturer:** Corteva
- **EPA Registration #:** 62719-742
- **Last Known Label Date:** April 3, 2023
- **Last Known SDS Date:** April 29, 2022
- **Reference Page (if needed):** https://www.corteva.us/products-and-solutions/turf-and-ornamental/crew.html

# Results 8

## 1. Perplexity AI (Free Model) Response:

### Label

| Found? | Direct Link or Page URL                                                     | Document Date              | Suggested File Name                         | Is Newer than Last Known? |
| ------ | --------------------------------------------------------------------------- | -------------------------- | ------------------------------------------- | ------------------------- |
| No     | https://www.corteva.us/products-and-solutions/turf-and-ornamental/crew.html | April 3, 2023 (last known) | CrewSpecialtyHerbicide_Label_2023-04-03.pdf | No                        |

### SDS

| Found? | Direct Link or Page URL                                                     | Document Date               | Suggested File Name                       | Is Newer than Last Known? |
| ------ | --------------------------------------------------------------------------- | --------------------------- | ----------------------------------------- | ------------------------- |
| No     | https://www.corteva.us/products-and-solutions/turf-and-ornamental/crew.html | April 29, 2022 (last known) | CrewSpecialtyHerbicide_SDS_2022-04-29.pdf | No                        |

**No newer Label or SDS for Crew Specialty Herbicide was found. The most current documents remain the April 3, 2023 label and the April 29, 2022 SDS, available via the official Corteva product page.**

Citations:
[1] https://www.rksplumbing.com/MSDS/PDFS/Oatey%20Plumber's%20Putty%20SDS.pdf
[2] https://www.oatey.com/products/oatey-plumbers-putty--1165995750
[3] https://media.distributordatasolutions.com/oatey/2018q4/0c05fef0843167c56af9ed48d36832a7d9064127.pdf
[4] https://www.oatey.com/products/oatey-stainfree-plumbers-putty--934748176
[5] https://www.thepartworks.com/core/media/media.nl?id=6574425&c=4086386&h=PbzoL6mHZyzWWKoqRbu-2hirLzQFSGis4sh6J2DAxfOh6NKA&_xt=.pdf
[6] https://www.whatsinproducts.com/types/type_detail/1/3488/standard/span%20style=%22color:
[7] https://www.whatsinproducts.com/types/type_detail/1/21700/standard/div%20id=%22cke_pastebin%22%3EOatey,%20Stain-Free%20Plumbers%20Putty,%2031177-04/22/2015/div%3E/15-001-100
[8] https://www.oatey.com/document/search

---

Answer from Perplexity: pplx.ai/share

## 2. Microsoft Copilot AI (Free Model) Response:

Here’s what I found regarding the latest Label and SDS documents for **Crew Specialty Herbicide**:

### **Label Document**

| Found? | Direct Link or Page URL                                                                            | Document Date | Suggested File Name                         | Is Newer than Last Known? |
| ------ | -------------------------------------------------------------------------------------------------- | ------------- | ------------------------------------------- | ------------------------- |
| Yes    | [EPA Label Page](https://iaspub.epa.gov/apex/pesticides/f?p=PPLS:102:::NO::P102_REG_NUM:62719-742) | April 3, 2023 | CrewSpecialtyHerbicide_Label_2023-04-03.pdf | No                        |

### **SDS Document**

| Found? | Direct Link or Page URL | Document Date | Suggested File Name | Is Newer than Last Known? |
| ------ | ----------------------- | ------------- | ------------------- | ------------------------- |
| No     | No updated SDS found    | N/A           | N/A                 | No                        |

It looks like the label remains unchanged since the last known version, and I couldn't find a newer SDS document. Let me know if you need further assistance!

## 3. Google Gemini AI (Free Model - 2.0 Flash Model) Response:

Okay, I will find the most up-to-date Label and SDS for Crew Specialty Herbicide, adhering to all the specified constraints, and present the results in a table format.

**Label Search Results:**

| Found? | Direct Link or Page URL                                                                                                                                                                                                                                                                                                                    | Document Date | Suggested File Name                | Is Newer than Last Known? |
| :----- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------ | :--------------------------------- | :------------------------ |
| Yes    | [https://www.google.com/search?q=https://www.corteva.us/content/dam/dpagco/corteva/na/us/en/products/herbicide/crew/pdfs/crew-specialty-herbicide-label-04-03-23.pdf](https://www.google.com/search?q=https://www.corteva.us/content/dam/dpagco/corteva/na/us/en/products/herbicide/crew/pdfs/crew-specialty-herbicide-label-04-03-23.pdf) | April 3, 2023 | CrewSpecialty_Label_2023-04-03.pdf | No                        |

**SDS Search Results:**

| Found? | Direct Link or Page URL                                                                                                                                                                                                                                                                                                                | Document Date  | Suggested File Name              | Is Newer than Last Known? |
| :----- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------- | :------------------------------- | :------------------------ |
| Yes    | [https://www.google.com/search?q=https://www.corteva.us/content/dam/dpagco/corteva/na/us/en/products/herbicide/crew/pdfs/crew-specialty-herbicide-sds-04-29-22.pdf](https://www.google.com/search?q=https://www.corteva.us/content/dam/dpagco/corteva/na/us/en/products/herbicide/crew/pdfs/crew-specialty-herbicide-sds-04-29-22.pdf) | April 29, 2022 | CrewSpecialty_SDS_2022-04-29.pdf | No                        |

I found the Label and SDS on the manufacturer's website. Neither document appears to be newer than the last known dates provided.

## 4. OpenAI ChatGPT AI (Free Model - 4o Model) Response:

Here are the most up-to-date Label and Safety Data Sheet (SDS) documents for Crew Specialty Herbicide (EPA Reg. No. 62719-742) by Corteva:

---

### Label Document

| Found? | Direct Link or Page URL                                                    | Document Date   | Suggested File Name                         | Is Newer than Last Known? |
| ------ | -------------------------------------------------------------------------- | --------------- | ------------------------------------------- | ------------------------- |
| Yes    | https://www3.epa.gov/pesticides/chem_search/ppls/062719-00742-20191008.pdf | October 8, 2019 | CrewSpecialtyHerbicide_Label_2019-10-08.pdf | No                        |

---

### Safety Data Sheet (SDS)

| Found? | Direct Link or Page URL                                         | Document Date  | Suggested File Name                       | Is Newer than Last Known? |
| ------ | --------------------------------------------------------------- | -------------- | ----------------------------------------- | ------------------------- |
| Yes    | https://assets.greenbook.net/21-52-33-16-09-2022-Crew_-_sds.pdf | April 29, 2022 | CrewSpecialtyHerbicide_SDS_2022-04-29.pdf | No                        |

---

**Summary:**

- **Label:** The most recent label available is dated **October 8, 2019**, which is older than the last known label date of **April 3, 2023**.
- **SDS:** The latest Safety Data Sheet is dated **April 29, 2022**, matching the last known SDS date.

For further information or updates, you may refer to the Corteva Crew Specialty Herbicide product page.

## Result Summary - TEST 8

| Rank | Service       | Reason                                                                   |
| ---- | ------------- | ------------------------------------------------------------------------ |
| 🥇 1 | ChatGPT (4o)  | Found valid direct links to label (2019) and SDS (2022); best formatting |
| 🥈 2 | Perplexity AI | Linked official Corteva page, but didn’t extract direct PDFs             |
| 🥉 3 | Copilot       | Found label (2023) via EPA page but no PDF or SDS link                   |
| ❌ 4 | Gemini        | Returned Google search result links — disqualified per updated prompt    |

# AI Prompt 9

You are a web research assistant. Your task is to search the internet and find the most up-to-date Label and SDS (Safety Data Sheet) documents for a pesticide or chemical product.

Focus on:

- Searching official manufacturer websites, EPA databases, and trusted agricultural product portals.
- Returning direct **plain PDF URLs** to the Label and SDS documents if possible.
- Do not embed links in text — show the full URL directly.
- **Do not return any links from https://labelsds.com/**. We already track our own database, so ignore anything hosted there.
- **Do not return Google search result links.** Only include real, functional PDF file URLs or official product page links where the file can be downloaded manually.
- If direct links are unavailable, return the most relevant official webpage where the document can be accessed.
- Prioritize files that mention a newer revision date than the ones provided.
- For SDS documents, look for “Revision Date,” “Revised,” or “Updated” on the document (not “Printed” date).
- If a newer document is found, suggest a filename in the format: ProductName_Label_YYYY-MM-DD.pdf or ProductName_SDS_YYYY-MM-DD.pdf

Return the results in **table format** for each document type (Label and SDS) with the following columns:
| Found? | Direct Link or Page URL | Document Date | Suggested File Name | Is Newer than Last Known? |

If nothing is found or the document is outdated, say so clearly.

⸻
**DATA:**

- **Product Name:** Hormodin 3
- **Manufacturer:** OHP
- **EPA Registration #:** 59807-3
- **Last Known Label Date:** June 26, 2006
- **Last Known SDS Date:** May 22, 2015
- **Reference Page (if needed):** https://www.ohp.com/Products/hormodin.php

# Results 9

## 1. Perplexity AI (Free Model) Response:

### Label

| Found? | Direct Link or Page URL                   | Document Date              | Suggested File Name            | Is Newer than Last Known? |
| ------ | ----------------------------------------- | -------------------------- | ------------------------------ | ------------------------- |
| No     | https://www.ohp.com/Products/hormodin.php | June 26, 2006 (last known) | Hormodin3_Label_2006-06-26.pdf | No                        |

### SDS

| Found? | Direct Link or Page URL                   | Document Date             | Suggested File Name          | Is Newer than Last Known? |
| ------ | ----------------------------------------- | ------------------------- | ---------------------------- | ------------------------- |
| No     | https://www.ohp.com/Products/hormodin.php | May 22, 2015 (last known) | Hormodin3_SDS_2015-05-22.pdf | No                        |

**No newer Label or SDS for Hormodin 3 was found. The most current documents remain the June 26, 2006 label and the May 22, 2015 SDS, available via the official OHP product page.**

Citations:
[1] https://www.oatey.com/products/oatey-plumbers-putty--1165995750
[2] https://ruizfoods-ca.safepersonnelsds.com/document/repo/97c69720-55d2-4243-9a45-e3d804a1b437
[3] https://www.rksplumbing.com/MSDS/PDFS/Oatey%20Plumber's%20Putty%20SDS.pdf
[4] https://www.oatey.com/products/oatey-stainfree-plumbers-putty--934748176
[5] https://www.oatey.ca/products/oatey-plumbers-putty--1165995750
[6] https://images.thdstatic.com/catalog/pdfImages/0c/0c774982-d426-4c42-bc33-868667049e04.pdf
[7] https://www2.pcad.edu/Facilities/health_safety/SDS/Maintenance/Oatey/plumber's%20putty.pdf
[8] https://media.distributordatasolutions.com/oatey/2018q4/0c05fef0843167c56af9ed48d36832a7d9064127.pdf
[9] https://www.thepartworks.com/core/media/media.nl?id=6574425&c=4086386&h=PbzoL6mHZyzWWKoqRbu-2hirLzQFSGis4sh6J2DAxfOh6NKA&_xt=.pdf

---

Answer from Perplexity: pplx.ai/share

## 2. Microsoft Copilot AI (Free Model) Response:

Here’s what I found regarding the latest Label and SDS documents for **Hormodin 3**:

### **Label Document**

| Found? | Direct Link or Page URL                                                    | Document Date | Suggested File Name            | Is Newer than Last Known? |
| ------ | -------------------------------------------------------------------------- | ------------- | ------------------------------ | ------------------------- |
| Yes    | [Hormodin 3 Label](http://www.ohp.com/Labels_MSDS/PDF/hormodin3_label.pdf) | March 6, 2018 | Hormodin3_Label_2018-03-06.pdf | Yes                       |

### **SDS Document**

| Found? | Direct Link or Page URL                                              | Document Date         | Suggested File Name | Is Newer than Last Known? |
| ------ | -------------------------------------------------------------------- | --------------------- | ------------------- | ------------------------- |
| Yes    | [Hormodin SDS](https://www.ohp.com/Labels_MSDS/PDF/hormodin_sds.pdf) | Not explicitly stated | Hormodin3_SDS.pdf   | Unknown                   |

It looks like the label has been updated since the last known version, but the SDS document does not clearly indicate a revision date. Let me know if you need further assistance!

## 3. Google Gemini AI (Free Model - 2.0 Flash Model) Response:

Okay, I will find the most up-to-date Label and SDS for Hormodin 3, following all instructions, and present the results in a table format.

**Label Search Results:**

| Found? | Direct Link or Page URL  
| Found? | Direct Link or Page URL | Document Date | Suggested File Name | Is Newer than Last Known? |
| :----- | :---------------------- | :-------------- | :-------------------- | :------------------------ |
| Yes | [https://www.google.com/search?q=https://www.ohp.com/PDFs/Hormodin3Label.pdf](https://www.google.com/search?q=https://www.ohp.com/PDFs/Hormodin3Label.pdf) | June 26, 2006 | Hormodin3_Label_2006-06-26.pdf | No |

**SDS Search Results:**

| Found? | Direct Link or Page URL

## 4. OpenAI ChatGPT AI (Free Model - 4o Model) Response:

Here are the most up-to-date Label and Safety Data Sheet (SDS) documents for Hormodin 3 (EPA Reg. No. 59807-3) by OHP:

---

### Label Document

| Found? | Direct Link or Page URL                                                    | Document Date | Suggested File Name            | Is Newer than Last Known? |
| ------ | -------------------------------------------------------------------------- | ------------- | ------------------------------ | ------------------------- |
| Yes    | https://www3.epa.gov/pesticides/chem_search/ppls/059807-00003-20180306.pdf | March 6, 2018 | Hormodin3_Label_2018-03-06.pdf | Yes                       |

---

### Safety Data Sheet (SDS)

| Found? | Direct Link or Page URL                              | Document Date | Suggested File Name          | Is Newer than Last Known? |
| ------ | ---------------------------------------------------- | ------------- | ---------------------------- | ------------------------- |
| Yes    | https://www.ohp.com/Labels_MSDS/PDF/hormodin_sds.pdf | May 22, 2015  | Hormodin3_SDS_2015-05-22.pdf | No                        |

---

**Summary:**

- **Label:** A newer label dated **March 6, 2018**, has been found, which is more recent than the last known label date of **June 26, 2006**.
- **SDS:** The latest Safety Data Sheet is dated **May 22, 2015**, which matches the last known SDS date.

For further information or updates, you may refer to the OHP Hormodin product page. ([PDF] OHP Hormodin #1, #2, #3 - Log in)

## Result Summary - TEST 9

| Rank | Service       | Reason                                                                 |
| ---- | ------------- | ---------------------------------------------------------------------- |
| 🥇 1 | ChatGPT (4o)  | Found both updated label + SDS; perfect direct links; prompt-compliant |
| 🥈 2 | Copilot       | Same data as ChatGPT but weaker link formatting and unclear SDS date   |
| 🥉 3 | Perplexity AI | Missed updated label and SDS; just linked to product page              |
| ❌ 4 | Gemini        | Google search link + no SDS = disqualified                             |

# AI Prompt 10

You are a web research assistant. Your task is to search the internet and find the most up-to-date Label and SDS (Safety Data Sheet) documents for a pesticide or chemical product.

Focus on:

- Searching official manufacturer websites, EPA databases, and trusted agricultural product portals.
- Returning direct **plain PDF URLs** to the Label and SDS documents if possible.
- Do not embed links in text — show the full URL directly.
- **Do not return any links from https://labelsds.com/**. We already track our own database, so ignore anything hosted there.
- **Do not return Google search result links.** Only include real, functional PDF file URLs or official product page links where the file can be downloaded manually.
- If direct links are unavailable, return the most relevant official webpage where the document can be accessed.
- Prioritize files that mention a newer revision date than the ones provided.
- For SDS documents, look for “Revision Date,” “Revised,” or “Updated” on the document (not “Printed” date).
- If a newer document is found, suggest a filename in the format: ProductName_Label_YYYY-MM-DD.pdf or ProductName_SDS_YYYY-MM-DD.pdf

Return the results in **table format** for each document type (Label and SDS) with the following columns:
| Found? | Direct Link or Page URL | Document Date | Suggested File Name | Is Newer than Last Known? |

If nothing is found or the document is outdated, say so clearly.

⸻
**DATA:**

- **Product Name:** Nibor D Insecticide Foam + IGR
- **Manufacturer:** Nisus
- **EPA Registration #:** 64405-37
- **Last Known Label Date:** December 1, 2021
- **Last Known SDS Date:** November 7, 2023
- **Reference Page (if needed):** https://nisuscorp.com/product/nibor-digr#single-resources

# Results 10

## 1. Perplexity AI (Free Model - Free PRO Search) Response:

Here are the most up-to-date Label and Safety Data Sheet (SDS) documents for Nibor-D Insecticide Foam + IGR (EPA Reg. No. 64405-37) by Nisus Corporation:

### Label Document

| Found? | Direct Link or Page URL                                                    | Document Date | Suggested File Name                           | Is Newer than Last Known? |
| ------ | -------------------------------------------------------------------------- | ------------- | --------------------------------------------- | ------------------------- |
| Yes    | https://www3.epa.gov/pesticides/chem_search/ppls/064405-00037-20231107.pdf | 2023-11-07    | NiborDInsecticideFoamIGR_Label_2023-11-07.pdf | Yes                       |

---

### Safety Data Sheet (SDS)

| Found? | Direct Link or Page URL                                                                              | Document Date | Suggested File Name                         | Is Newer than Last Known? |
| ------ | ---------------------------------------------------------------------------------------------------- | ------------- | ------------------------------------------- | ------------------------- |
| Yes    | https://nisuscorp.com/wp-content/uploads/download-manager-files/NIBOR-D-INSECTICIDE-FOAM-IGR_SDS.pdf | 2023-11-07    | NiborDInsecticideFoamIGR_SDS_2023-11-07.pdf | No (Same as Last Known)   |

**Summary:**

- The most current label is dated November 7, 2023, which is newer than the last known label date (December 1, 2021)[2][4].
- The most current SDS is also dated November 7, 2023, which matches the last known SDS date[1]. No newer SDS is available.

Citations:
[1] https://nisuscorp.com/wp-content/uploads/download-manager-files/NIBOR-D-INSECTICIDE-FOAM-IGR_SDS.pdf
[2] https://www3.epa.gov/pesticides/chem_search/ppls/064405-00037-20231107.pdf
[3] https://nisuscorp.com/wp-content/uploads/download-manager-files/Nibor-DIGR_Label.pdf
[4] https://ordspub.epa.gov/ords/pesticides/f?p=PPLS%3A102%3A%3A%3ANO%3A%3AP102_REG_NUM%3A64405-37
[5] https://labelsds.com/images/user_uploads/Nibor%20D%20IGR%20Foam%20SDS%203-3-22.pdf
[6] https://nisuscorp.com/product/nibor-d
[7] https://nisuscorp.com/wp-content/uploads/download-manager-files/Garbage_Chute_Protocol.pdf
[8] https://diypestcontrol.com/nibor-d-insecticide-foam-plus-igr
[9] https://www.rosepestcontrol.com/wp-content/uploads/2022/02/Nibor-D-SDS.pdf
[10] https://www.domyown.com/nibor-insecticide-foam-plus-igr-p-25121.html
[11] https://nisuscorp.com/product/nibor-digr
[12] https://nisuscorp.com/wp-content/uploads/download-manager-files/NiborD_IGR_Q_and_A_BP_20221104.pdf
[13] https://nisuscorp.com/wp-content/uploads/download-manager-files/Small-Fly-and-Cockroach-Control-Protocol_0323.pdf
[14] https://nisuscorp.com/wp-content/uploads/download-manager-files/Nibor-DIGR-Product-Flyer_0822.pdf
[15] https://nisuscorp.com/wp-content/uploads/download-manager-files/Fly-Control-ID_booklet_online-version-0323.pdf
[16] https://nisuscorp.com/wp-content/uploads/download-manager-files/Nisus_Product_Booklet.pdf
[17] https://labelsds.com/images/user_uploads/Nibor%20D%20IGR%20Foam%20Label%205-6-21.pdf
[18] https://www.solutionsstores.com/nibor-d-insecticide-foam-and-igr
[19] https://www.bugmanrochester.com/index.cfm?Page=Labels-SDS-Sheets
[20] https://www3.epa.gov/pesticides/chem_search/ppls/064405-00002-20150205.pdf

---

Answer from Perplexity: pplx.ai/share

## 2. Microsoft Copilot AI (Free Model) Response:

Here’s what I found regarding the latest Label and SDS documents for **Nibor D Insecticide Foam + IGR**:

### **Label Document**

| Found? | Direct Link or Page URL                                                                           | Document Date    | Suggested File Name         | Is Newer than Last Known? |
| ------ | ------------------------------------------------------------------------------------------------- | ---------------- | --------------------------- | ------------------------- |
| Yes    | [EPA Label Page](https://iaspub.epa.gov/apex/pesticides/f?p=PPLS:102:::NO::P102_Reg_Num:64405-37) | November 7, 2023 | NiborD_Label_2023-11-07.pdf | Yes                       |

### **SDS Document**

| Found? | Direct Link or Page URL                                                                                              | Document Date    | Suggested File Name       | Is Newer than Last Known? |
| ------ | -------------------------------------------------------------------------------------------------------------------- | ---------------- | ------------------------- | ------------------------- |
| No     | [SDS Document](https://nisuscorp.com/wp-content/uploads/download-manager-files/NIBOR-D-INSECTICIDE-FOAM-IGR_SDS.pdf) | November 7, 2023 | NiborD_SDS_2023-11-07.pdf | No                        |

It looks like the label has been updated since the last known version, but the SDS remains unchanged. Let me know if you need further assistance!

## 3. Google Gemini AI (Free Model - 2.5 Pro Model) Response:

Okay, I will search for the latest Label and SDS documents for Nibor D Insecticide Foam + IGR.

**Label Document Search**
Okay, here are the results of the search for the Label and SDS documents for Nibor D Insecticide Foam + IGR (EPA Reg \# 64405-37).

**Label Document**

| Found? | Direct Link or Page URL                                                                                                                                                      | Document Date | Suggested File Name                           | Is Newer than Last Known? (Dec 1, 2021) |
| :----- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------ | :-------------------------------------------- | :-------------------------------------- |
| Yes    | [https://nisuscorp.com/wp-content/uploads/download-manager-files/Nibor-DIGR_Label.pdf](https://nisuscorp.com/wp-content/uploads/download-manager-files/Nibor-DIGR_Label.pdf) | February 2024 | NiborDInsecticideFoamIGR_Label_2024-02-29.pdf | Yes                                     |

**SDS Document**

| Found? | Direct Link or Page URL                                                                                                                                                                                              | Document Date    | Suggested File Name | Is Newer than Last Known? (Nov 7, 2023) |
| :----- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------- | :------------------ | :-------------------------------------- |
| Yes    | [https://www.google.com/search?q=https://nisuscorp.com/images/uploads/products/Nibor-D_IGR_SDS_110723.pdf](https://www.google.com/search?q=https://nisuscorp.com/images/uploads/products/Nibor-D_IGR_SDS_110723.pdf) | November 7, 2023 | None                | No                                      |

## 4. OpenAI ChatGPT AI (Paid Model - o4-mini-high Model) Response:

A newer label for **Nibor D Insecticide Foam + IGR** was located on the EPA Pesticide Product Label system with a Notification date of November 7, 2023 ([[PDF] Nibor-D Insecticide Foam + IGR](https://www3.epa.gov/pesticides/chem_search/ppls/064405-00037-20231107.pdf?utm_source=chatgpt.com)). The Safety Data Sheet was retrieved from the official Nisus website and shows a Revision Date of November 7, 2023, matching the user’s last known SDS date ([[PDF] Nibor-D® Insecticide Foam + IGR Safety Data Sheet - Nisus Corp](https://nisuscorp.com/wp-content/uploads/download-manager-files/NIBOR-D-INSECTICIDE-FOAM-IGR_SDS.pdf?srsltid=AfmBOoqP9YFm2k-BdCkcPy8Olxiu8sDYQstyc6_fVcDo7c6870x2gGWi&utm_source=chatgpt.com)). No additional labels or SDS versions were found on the manufacturer site or in trusted third-party registries beyond these documents ([Nibor-D®+IGR - Nisus Corp](https://nisuscorp.com/product/nibor-digr?srsltid=AfmBOoppOMzutiBkEUKqCMScSLpaltZsrrHDPL_ONN6JLJRqd8LhJ9uT&utm_source=chatgpt.com), [new-nibor-d-label.pdf - American Pest](https://americanpest.net/media/ma0euf3e/new-nibor-d-label.pdf?utm_source=chatgpt.com)).

### Label Document

| Found? | Direct Link or Page URL                                                    | Document Date    | Suggested File Name                           | Is Newer than Last Known? |
| ------ | -------------------------------------------------------------------------- | ---------------- | --------------------------------------------- | ------------------------- |
| Yes    | https://www3.epa.gov/pesticides/chem_search/ppls/064405-00037-20231107.pdf | November 7, 2023 | NiborDInsecticideFoamIGR_Label_2023-11-07.pdf | Yes                       |

- **Found?** Yes ([[PDF] Nibor-D Insecticide Foam + IGR](https://www3.epa.gov/pesticides/chem_search/ppls/064405-00037-20231107.pdf?utm_source=chatgpt.com))
- **Document Date:** November 7, 2023
- **Is Newer than Last Known?** Yes

### Safety Data Sheet (SDS) Document

| Found? | Direct Link or Page URL                                                                              | Document Date    | Suggested File Name                         | Is Newer than Last Known? |
| ------ | ---------------------------------------------------------------------------------------------------- | ---------------- | ------------------------------------------- | ------------------------- |
| Yes    | https://nisuscorp.com/wp-content/uploads/download-manager-files/NIBOR-D-INSECTICIDE-FOAM-IGR_SDS.pdf | November 7, 2023 | NiborDInsecticideFoamIGR_SDS_2023-11-07.pdf | No                        |

- **Found?** Yes ([[PDF] Nibor-D® Insecticide Foam + IGR Safety Data Sheet - Nisus Corp](https://nisuscorp.com/wp-content/uploads/download-manager-files/NIBOR-D-INSECTICIDE-FOAM-IGR_SDS.pdf?srsltid=AfmBOoqP9YFm2k-BdCkcPy8Olxiu8sDYQstyc6_fVcDo7c6870x2gGWi&utm_source=chatgpt.com))
- **Document Date:** November 7, 2023
- **Is Newer than Last Known?** No

## Result Summary - TEST 10

| Rank | Service                | Reason                                                              |
| ---- | ---------------------- | ------------------------------------------------------------------- |
| 🥇 1 | ChatGPT (o4-mini-high) | Accurate, updated label + SDS; clean formatting and link compliance |
| 🥈 2 | Perplexity (Free PRO)  | Same data, great accuracy, just slightly looser format              |
| 🥉 3 | Copilot                | Found same files, but used embedded links and markdown gaps         |
| ❌ 4 | Gemini                 | Used Google search link for SDS; disqualified per prompt            |
