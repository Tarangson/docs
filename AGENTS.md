# Tarangson Documentation — Project Instructions

## About this project

- Documentation site for **Tarangson** (ระบบจัดตารางสอนอัจฉริยะ) — a Thai school timetable scheduling app
- Built on [Mintlify](https://mintlify.com) with MDX pages and YAML frontmatter
- Configuration lives in `docs.json`
- Bilingual: Thai (default, root) and English (`en/` prefix)
- Run `mint dev` to preview locally
- Run `mint broken-links` to check links

## Terminology

| Thai | English | Usage notes |
|------|---------|-------------|
| ตารางสอน | Timetable | Use "timetable" not "schedule" for the main product |
| คาบเรียน | Period | A single time slot in the timetable |
| ผู้สอน / ครู | Teacher | Use "ครู" or "ผู้สอน" interchangeably in Thai docs |
| นักเรียน / ห้องเรียน | Student / Class | "นักเรียน" refers to a class group, not individual students |
| ห้อง | Room | Physical classroom |
| วิชา | Subject | Academic subject/course |
| แฟ้มตาราง | Timetable file | A saved timetable configuration |
| ลาก-วาง | Drag-and-drop | For scheduling interactions |
| ความขัดแย้ง | Conflict | Schedule conflicts (teacher/student/room double-booking) |
| ปักหมุด | Pin/Lock | Locking a schedule entry so it can't be moved |
| Wizard | Wizard | Keep in English in Thai docs |
| Setup Wizard | Setup Wizard | Keep in English in Thai docs |

## Style preferences

### Thai pages (root)
- Use active voice and second person ("คุณ")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: คลิก **บันทึก**
- Code formatting for technical terms: `Firebase`, `Excel`
- Use Kanit font (configured in docs.json)
- Technical terms stay in English: Firebase, OAuth, Excel, drag-and-drop

### English pages (`en/` folder)
- Use active voice and second person ("you")
- Same formatting rules as Thai
- Include Thai UI labels in parentheses where helpful: Click **Save** (บันทึก)
- Thai-specific features (address autocomplete, prefix options) should include context for international readers

### Both languages
- Use Mintlify components: Steps, Step, Card, Callout, Tabs, Tab, CodeGroup, Columns
- Include practical step-by-step instructions
- Reference actual app behavior (verified against source code)

## Project structure

```
docs/
├── docs.json              # Mintlify configuration + i18n + navigation
├── index.mdx              # Home page (Thai)
├── getting-started/       # Registration, setup wizard, dashboard
├── settings/              # Academic defaults, school profile, account
├── roster/                # Teachers, students, rooms, subjects, Excel
├── timetable/             # Create, wizard, editing, viewing, printing, files
├── dev/                   # Developer guide (architecture, schema, types, etc.)
├── en/                    # English translations (mirrors root structure)
│   ├── index.mdx
│   ├── getting-started/
│   ├── settings/
│   ├── roster/
│   ├── timetable/
│   └── dev/
├── images/                # Logos and images
└── logo/                  # Light/dark logo variants
```

## Content boundaries

- Document all user-facing features of the Tarangson web app
- Developer guide covers architecture, data model, and contribution guidelines
- Do NOT document internal admin panels or billing backend
- Do NOT include API keys, secrets, or Firebase credentials in docs
- Screenshots should not contain real student/teacher data

## Source code reference

The main application source code is at a separate repository:
- `app/lib/types.ts` — TypeScript interfaces (Teacher, Student, Room, Subject, etc.)
- `app/lib/firestore.ts` — Firestore database functions
- `app/lib/excel.ts` — Excel import/export utilities
- `app/context/AuthContext.tsx` — Authentication context
- `app/timetable/page.tsx` — Main timetable editor
