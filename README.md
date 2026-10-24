# Student Social Media Usage & Wellbeing Dashboard

I built this Power BI dashboard to see how much time students spend on social media each day, and how that connects to their sleep, mental health and studies. The data covers 705 students.

The question I wanted to answer: **how does daily social media use relate to students' sleep, mental health and studies, and where should a wellness team start?**

## Preview

![Executive Overview](screenshots/01-executive-overview.png)

The dashboard has 6 pages:

| Page | What it shows |
|---|---|
| 1. Executive Overview | Main numbers, sleep by daily usage, usage by age, addiction score by academic level |
| 2. Mental Health & Lifestyle | Students by country and health band, addiction vs mental health, sleep by age |
| 3. Academic Impact | Usage by academic level, and how many students say it affects their studies, by platform |
| 4. Relationships & Conflicts | Relationship status, conflict level, addiction score for each student |
| 5. Interactive Story View | Buttons to switch between a gender view and an academic level view |
| 6. Student Profile | A drill-through page with the details of one student |

You can find all the screenshots in the `screenshots` folder.

## About the data

- 705 students, aged 18 to 24, from 110 countries (353 female, 352 male)
- By level: 353 undergraduate, 325 graduate, 27 high school
- The Excel file `data/Students Social Media Addiction.xlsx` has two sheets:
  - **Student_Details**: age, gender, academic level, country, sleep hours, mental health score, relationship status, conflicts over social media, addicted score
  - **Platform_Details**: daily usage hours, most used platform, and whether it affects academic performance (Yes/No)
- I linked the two tables 1:1 using `Student_ID`.

## What I found

- Students use social media about **4.9 hours a day** and sleep about **6.9 hours** a night.
- **64.3%** of students say social media affects their studies.
- **28.2%** (199 students) have an addicted score above 7.

I also split students into three groups by daily use:

| Daily use | Students | Avg sleep | Avg mental health score | Say it affects studies |
|---|---|---|---|---|
| Up to 3 hours | 49 | 8.2 h | 7.9 | 0% |
| 3 to 6 hours | 513 | 7.1 h | 6.4 | 60.4% |
| Over 6 hours | 143 | 5.7 h | 4.9 | 100% |

The more hours students spend online, the less they sleep and the lower their mental health score. Both relationships are fairly strong (correlation of about -0.8).

By platform, WhatsApp users spend the most time (about 6.5 hours a day, 54 students, all of them say it affects their studies). TikTok comes next (about 5.4 hours, 154 students, 93.5% affected). LinkedIn users spend the least (about 2.5 hours, 21 students, none affected).

## What I would suggest

These are ideas based on the patterns above, not proven results.

- Start awareness sessions with students who use social media more than 6 hours a day. That is 143 students, about 20% of the group.
- Focus first on heavy users of chat and short-video apps like WhatsApp and TikTok.

## What's inside the project

- **Model:** 2 tables linked 1:1 on `Student_ID`
- **Measures:** Total Students, Avg Sleep Hours, Avg Usage Hours, % Affected Academically, Addicted Student Count (addicted score above 7), % Addicted Students
- **Calculated columns:** Health Band, Conflict Level, Usage Band
- **Report features:** slicers, bookmarks and buttons, drill-through, and short insight boxes

## Data checks

- No missing values and no duplicate Student_IDs
- Both tables have 705 rows and every Student_ID matches
- All values are in realistic ranges (usage 1.5 to 8.5 hours, sleep 3.8 to 9.6 hours, mental health score 4 to 9)
- The main measures match the raw data (705 students, 64.3% affected, 199 addicted students)

## Things to keep in mind

- The data has no dates, so I could not look at trends over time.
- The numbers move together, but that does not prove that social media causes the change in sleep or mental health.
- Some groups are small (LinkedIn has 21 students, high school has 27), so treat those as patterns to watch.
- The Health Band "Poor" group is empty because the lowest mental health score is 4.
- The Conflict Level "High" group is empty because it needs more than 5 conflicts, and the highest value in the data is 5.

## How to open it

1. Install Power BI Desktop (it is free).
2. Download this repo and open `Social_Media_Addiction_GitHub.pbix`.
3. If Power BI can't find the data, go to **Transform data > Data source settings > Change source** and pick `data/Students Social Media Addiction.xlsx`.

## Tools used

Power BI, DAX, Power Query, Excel
