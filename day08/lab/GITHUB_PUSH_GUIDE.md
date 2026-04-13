# HƯỚNG DẪN PUSH LÊN GITHUB

## Phân công: 4 Sprints → 5 người

> **Sprint 3 chia cho 2 người**: Sơn (Retrieval variants) + Tín (Query Transform)

---

## THỨ TỰ PUSH (BẮT BUỘC)

```
1. TÀI   → Core indexing + baseline
2. SƠN   → Retrieval variants  
3. TÍN   → Query transform (sau khi Sơn push xong)
4. QUANG → Evaluation
5. NGỌC  → Documentation + Group report
```

---

## 1. TÀI (Tech Lead) - Sprint 1, 2

### Files:
```
index.py
.env.example
requirements.txt
reports/individual/tai.md
```

### Commands:
```bash
git add index.py .env.example requirements.txt reports/individual/tai.md
git commit -m "[Tai] Sprint 1-2: Indexing pipeline and baseline RAG"
git push origin main
```

---

## 2. SƠN (Retrieval Owner) - Sprint 1, 3a

### Files:
```
rag_answer.py (phần retrieval: retrieve_sparse, retrieve_hybrid, rerank_with_llm)
reports/individual/son.md
```

### Commands:
```bash
git pull origin main
git add rag_answer.py reports/individual/son.md
git commit -m "[Son] Sprint 3a: Retrieval variants (Hybrid, BM25, Rerank)"
git push origin main
```

---

## 3. TÍN (Query Transform) - Sprint 3b

> ⚠️ **QUAN TRỌNG**: Phải đợi Sơn push xong rồi mới pull và add code!

### Files:
```
rag_answer.py (thêm phần query transform: transform_query, rag_answer_with_query_transform)
reports/individual/tin.md
```

### Commands:
```bash
git pull origin main  # Lấy code của Sơn
# Thêm functions query transform vào rag_answer.py
git add rag_answer.py reports/individual/tin.md
git commit -m "[Tin] Sprint 3b: Query transformation (Expansion, HyDE)"
git push origin main
```

---

## 4. QUANG (Eval Owner) - Sprint 4

### Files:
```
eval.py
results/scorecard_baseline.md
results/scorecard_variant.md
results/ab_comparison.csv
reports/individual/quang.md
```

### Commands:
```bash
git pull origin main
git add eval.py results/ reports/individual/quang.md
git commit -m "[Quang] Sprint 4: Evaluation and A/B comparison"
git push origin main
```

---

## 5. NGỌC (Documentation Owner) - Sprint 4

### Files:
```
docs/architecture.md
docs/tuning-log.md
reports/group_report.md
reports/individual/ngoc.md
GITHUB_PUSH_GUIDE.md
.gitignore
```

### Commands:
```bash
git pull origin main
git add docs/ reports/group_report.md reports/individual/ngoc.md GITHUB_PUSH_GUIDE.md .gitignore
git commit -m "[Ngoc] Sprint 4: Documentation and group report"
git push origin main
```

---

## CHECKLIST TRƯỚC KHI PUSH

- [ ] File `.env` KHÔNG được push (chứa API key)
- [ ] Thư mục `chroma_db/` KHÔNG push (data local)
- [ ] Thư mục `__pycache__/` KHÔNG push
- [ ] Đã test code chạy được trước khi push
- [ ] Đã `git pull` trước khi push

---

## .gitignore

```
.env
chroma_db/
__pycache__/
*.pyc
.DS_Store
```

---

## NẾU BỊ CONFLICT

```bash
git pull origin main
# Resolve conflict trong VSCode
git add .
git commit -m "Resolve conflict"
git push origin main
```

---

## TỔNG KẾT PHÂN CÔNG

| Sprint | Người | Nội dung |
|--------|-------|----------|
| 1 | Tài + Sơn (chunking) | Build Index |
| 2 | Tài | Baseline RAG |
| 3a | Sơn | Hybrid, BM25, Rerank |
| 3b | Tín | Query Transform |
| 4 | Quang + Ngọc | Evaluation + Documentation |

---

*Liên hệ Tài hoặc Ngọc nếu gặp vấn đề với Git.*
