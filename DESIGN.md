# DESIGN.md

## 1. TOKENS
```css
--bg: #0a0a0a;
--bg-elev: #141414;
--fg: #f0f0f0;
--fg-muted: #a0a0a0;
--border: #2a2a2a;
--accent: #f97316;
--accent-fg: #0a0a0a;
--font-sans: system-ui, -apple-system, "Segoe UI", sans-serif;
--font-mono: ui-monospace, "SF Mono", Consolas, monospace;
--radius: 4px;
--fs-base: 15px;
```

## 2. COMPONENT OVERRIDES
```css
.thesis { border-radius: 0; border-left-width: 6px; }
.case-table th { background: var(--accent); color: var(--accent-fg); }
.toc a.active { font-weight: 700; }
```

## 3. QUY TẮC CẤM
- Không dùng border-radius > 12px.
- Cỡ chữ tối thiểu 14px.
- Bắt buộc hỗ trợ dark mode.
- Không dùng font ngoài; chỉ system font.
- Không animation quá 200ms.

## 4. GHI CHÚ THÊM
Giao diện ưu tiên đọc sâu, tương phản cao, cấu trúc rõ ràng, tối ưu màn hình máy tính nhưng responsive trên điện thoại. Giữ nguyên tiếng Việt cho mọi nhãn UI.
