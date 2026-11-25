# Data

The notebook expects this folder at `MyDrive/StudyMate_v2/data/` in Google Drive (see the main README).

| Folder / file | What it is | Where it comes from | In the repo? |
|---|---|---|---|
| `raw/ml_lessons.csv` | Our **50 core ML lessons** in 10 topics. Columns: `lesson_id, topic, title, content, difficulty, simple_explanation, real_world_example, technical_explanation, python_example, practice_exercise, next_lesson` | Written by our team, using the scikit-learn documentation and Google's Machine Learning Crash Course as references | ✅ Included (needed to run the notebook) |
| `raw/ai_dictionary_raw.csv` | Untouched copy of the **AI Dictionary of Terms** (211 terms, 7 columns, 8 categories) | Downloaded by Cell 2 from Hugging Face `alexnubla/ai-dictionary-terms` (MIT license) | Created at runtime |
| `processed/lessons_v2.csv` | The **66-lesson library** StudyMate searches (50 core + 16 dictionary terms). Columns: `lesson_id, title, topic, source, simple_explanation, short_detail, detailed_explanation, real_world_example, related_terms, extra_simple, search_text` | Built by Cell 3 | ✅ Included (a sample of the processed data that feeds the assistant) |
| `processed/data_quality_before_after.csv` | Quality numbers before vs after cleaning | Cell 3b | Created at runtime |
| `evaluation/dev_questions.csv` | 50 practice questions (46 ML + 4 off-topic) used to choose settings | Cell 6 (drafted with AI help, reviewed by our team) | Created at runtime |
| `evaluation/dev_option_results.csv` | Dev scores for the 3 search options | Cell 7 | Created at runtime |
| `evaluation/feature_importance.csv` | Each search signal alone vs combined | Cell 7b | Created at runtime |
| `evaluation/holdout_to_label.csv` | 120 real questions with 5 suggested lessons each, ready to label | Cell 8, from Hugging Face `mgp123/datascience-stackexchange-with-similar-questions` (CC BY-SA) | Created at runtime |
| `evaluation/lesson_titles.csv` | The 66 lesson titles and topics (the label list) | Cell 8 | ✅ Included |
| `evaluation/holdout_labeled.csv` | **Our labels** for the 120 real questions: `expected_lesson` (or `skip`) and `also_acceptable` | Labeled by our team in Google Sheets (first-pass labels drafted with AI help, then reviewed and corrected) | ✅ Needed for Cells 9–10 |
| `evaluation/final_exam_results.csv`, `final_exam_summary.csv` | Final exam results, question by question and summary | Cell 10 | Created at runtime |

**Label notes:** 53 questions have a lesson label and 67 are `skip` (outside our library). Cell 9 fixes the one typo in the file ("Embeeding" → "Embedding") and checks that every label matches a real lesson title.
