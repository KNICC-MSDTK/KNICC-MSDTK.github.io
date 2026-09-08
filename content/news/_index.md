---
title: 'NEWS'
date: 2026-08-24
type: landing

sections:
  - block: markdown
    id: list
    content:
      title: NEWS
      subtitle: 'BOARD'
      text: |-
        <div id="nb-root">
          <div class="nb-filter">
            <span class="nb-filter-label">Category</span>
            <label><input type="checkbox" class="nb-cat" data-cat="all" checked> All</label>
            <label><input type="checkbox" class="nb-cat" data-cat="Activities" checked> Activities</label>
            <label><input type="checkbox" class="nb-cat" data-cat="Admissions &amp; Graduation" checked> Admissions &amp; Graduation</label>
            <label><input type="checkbox" class="nb-cat" data-cat="Conferences &amp; Awards" checked> Conferences &amp; Awards</label>
            <label><input type="checkbox" class="nb-cat" data-cat="Projects" checked> Projects</label>
          </div>

          <div id="nb-list"></div>

          <div class="nb-bottom">
            <input type="text" id="nb-search" placeholder="Search">
            <div class="nb-pagination" id="nb-pagination"></div>
          </div>
        </div>

        <style>
          #nb-root {
            font-family: inherit; margin-top: 8px;
            width: min(88vw, 1000px); max-width: 1000px;
            position: relative; left: 50%; transform: translateX(-50%);
          }
          .nb-filter {
            display: flex; flex-wrap: wrap; align-items: center; gap: 18px;
            background: #10182b; color: #fff; border-radius: 10px;
            padding: 16px 20px; margin-bottom: 4px; font-size: 14px;
          }
          .nb-filter-label {
            background: #fff; color: #10182b; font-weight: 700;
            font-size: 12px; padding: 4px 10px; border-radius: 6px;
          }
          .nb-filter label { display: flex; align-items: center; gap: 6px; cursor: pointer; }
          .nb-filter input { accent-color: #4f6df5; cursor: pointer; }
          #nb-list { border-top: 2px solid #10182b; min-height: 520px; }
          .nb-row {
            display: flex; gap: 28px; align-items: flex-start;
            padding: 20px 6px; border-bottom: 1px solid #e5e5e5;
            transition: background-color .15s ease;
          }
          .nb-row:hover { background-color: rgba(0,0,0,0.03); }
          .nb-date {
            width: 100px; flex-shrink: 0; color: #666; font-size: 14px; padding-top: 3px;
          }
          .nb-body { flex: 1; min-width: 0; }
          .nb-title {
            font-weight: 700; font-size: 17px; margin-bottom: 6px; color: #10182b;
          }
          .nb-summary {
            color: #555; font-size: 14px; line-height: 1.55;
            display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical;
            overflow: hidden;
          }
          .nb-more {
            flex-shrink: 0; align-self: center;
            background: #eef0f7; color: #333; font-size: 13px; font-weight: 600;
            padding: 8px 16px; border-radius: 999px; white-space: nowrap;
          }
          .nb-more:hover { background: #dde1f0; }
          .nb-empty { padding: 40px 6px; text-align: center; color: #888; }
          .nb-bottom {
            display: flex; justify-content: space-between; align-items: center;
            margin-top: 72px; flex-wrap: wrap; gap: 12px;
          }
          #nb-search {
            border: 1px solid #ccc; border-radius: 6px; padding: 8px 12px;
            font-size: 14px; min-width: 220px;
          }
          .nb-pagination { display: flex; gap: 6px; align-items: center; }
          .nb-pagination button {
            border: 1px solid #ddd; background: #fff; border-radius: 6px;
            padding: 6px 11px; font-size: 13px; cursor: pointer; color: #333;
          }
          .nb-pagination button.active { background: #10182b; color: #fff; border-color: #10182b; }
          .nb-pagination button:disabled { opacity: 0.4; cursor: default; }
        </style>

        <script>
        (function () {
          // 새 소식을 추가하려면: 1) content/news/새폴더/index.md 생성 2) 아래 배열에 한 줄 추가
          var NB_ITEMS = [
            { date: '2026-08-17', category: 'Conferences & Awards', title: '(예시) 산업인공지능 제조혁신 해커톤 대회 수상', summary: '연구실 세부 팀들이 해커톤 대회에 참가하여 수상한 소식입니다. 실제 소식 내용으로 교체해 주세요.', link: '/news/hackathon-award/' },
            { date: '2026-08-17', category: 'Activities', title: '(예시) 연구실 워크숍 진행', summary: '구성원 간 소통을 위한 워크숍 소식입니다. 실제 소식 내용으로 교체해 주세요.', link: '/news/inspiration-day/' },
            { date: '2026-07-15', category: 'Conferences & Awards', title: '(예시) 학술대회 수상 소식', summary: '학술대회 참가 및 수상 소식입니다. 실제 소식 내용으로 교체해 주세요.', link: '/news/best-paper-award/' }
          ];
          var PAGE_SIZE = 10;
          var state = { page: 1, search: '', cats: new Set(['Activities', 'Admissions & Graduation', 'Conferences & Awards', 'Projects']) };

          function filtered() {
            var q = state.search.trim().toLowerCase();
            return NB_ITEMS.filter(function (it) {
              if (!state.cats.has(it.category)) return false;
              if (q && (it.title + ' ' + it.summary).toLowerCase().indexOf(q) === -1) return false;
              return true;
            });
          }

          function render() {
            var listEl = document.getElementById('nb-list');
            var items = filtered();
            var totalPages = Math.max(1, Math.ceil(items.length / PAGE_SIZE));
            if (state.page > totalPages) state.page = totalPages;
            var start = (state.page - 1) * PAGE_SIZE;
            var pageItems = items.slice(start, start + PAGE_SIZE);

            if (pageItems.length === 0) {
              listEl.innerHTML = '<div class="nb-empty">해당하는 소식이 없습니다.</div>';
            } else {
              listEl.innerHTML = pageItems.map(function (it) {
                return '<div class="nb-row">' +
                  '<div class="nb-date">' + it.date.replace(/-/g, '.') + '</div>' +
                  '<div class="nb-body"><div class="nb-title">' + it.title + '</div>' +
                  '<div class="nb-summary">' + it.summary + '</div></div>' +
                  '<a class="nb-more" href="' + it.link + '">Read More</a>' +
                  '</div>';
              }).join('');
            }

            var pagEl = document.getElementById('nb-pagination');
            var html = '<button ' + (state.page <= 1 ? 'disabled' : '') + ' data-page="' + (state.page - 1) + '">‹</button>';
            for (var p = 1; p <= totalPages; p++) {
              html += '<button class="' + (p === state.page ? 'active' : '') + '" data-page="' + p + '">' + p + '</button>';
            }
            html += '<button ' + (state.page >= totalPages ? 'disabled' : '') + ' data-page="' + (state.page + 1) + '">›</button>';
            pagEl.innerHTML = html;
            Array.prototype.forEach.call(pagEl.querySelectorAll('button'), function (btn) {
              btn.addEventListener('click', function () {
                state.page = parseInt(btn.getAttribute('data-page'), 10);
                render();
              });
            });
          }

          document.querySelectorAll('.nb-cat').forEach(function (box) {
            box.addEventListener('change', function () {
              if (box.getAttribute('data-cat') === 'all') {
                document.querySelectorAll('.nb-cat').forEach(function (b) { b.checked = box.checked; });
                state.cats = box.checked
                  ? new Set(['Activities', 'Admissions & Graduation', 'Conferences & Awards', 'Projects'])
                  : new Set();
              } else {
                if (box.checked) state.cats.add(box.getAttribute('data-cat'));
                else state.cats.delete(box.getAttribute('data-cat'));
                var allBox = document.querySelector('.nb-cat[data-cat="all"]');
                var others = document.querySelectorAll('.nb-cat:not([data-cat="all"])');
                allBox.checked = Array.prototype.every.call(others, function (b) { return b.checked; });
              }
              state.page = 1;
              render();
            });
          });

          document.getElementById('nb-search').addEventListener('input', function (e) {
            state.search = e.target.value;
            state.page = 1;
            render();
          });

          render();
        })();
        </script>
    design:
      columns: '1'
---
