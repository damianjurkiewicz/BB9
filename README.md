# Traceability Graph

```mermaid
flowchart TD
  REQ[Requirement]
  TASK[Jira Task]
  BRANCH[Git Branch]
  SCRIPT[Python Script]
  CSV[CSV Export]
  PR[Pull Request]
  MERGE[Merge to Main]

  REQ --> TASK --> BRANCH --> SCRIPT --> CSV --> PR --> MERGE
```

---

### 📁 Repo Structure

```
cnc-machine-plm/
├── README.md                   ← główna mapa: stack, traceability, struktura
│
├── plc/                        ← kod PLC (Structured Text, SFC)
│   ├── main.st
│   └── motion_axis_x.st
│
├── fusion/                     ← dane eksportowane z Fusion 360
│   ├── bom_2025-07-10.csv      ← BOM: struktura, ilości, masa
│   ├── sketch_areas.csv        ← powierzchnie i momenty bezwładności
│   └── sensor_locations.csv    ← lokalizacje czujników itp. (opcjonalnie)
│
├── requirements/               ← wymagania inżynierskie (.md)
│   ├── CTX_TABLE_R5.md
│   └── EQ_FRAME_BASE.md
│
├── mermaid/                    ← diagramy architektury i traceability
│   ├── system_overview.md      ← np. BOM → Jira → kod
│   └── motion_interfaces.mmd
│
├── scripts/                    ← automatyczne eksporty i analizy
│   ├── export_sketch_area.py
│   └── export_bom.py
│
├── io/                         ← tabela mapowań sygnałów IO
│   ├── io_mapping.csv          ← tabela: %I / %Q ↔ komponenty
│   └── io_links.md             ← opisy połączeń z CAD i wymaganiami
│
└── docs/                       ← opcjonalne PDF schematów, opisy fizyczne
    ├── electrical_layout.pdf   ← schemat zewnętrznej firmy
    └── actuator_specs.pdf
```
