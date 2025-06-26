# ✨ Tổng hợp dịch vụ deploy web miễn phí - chi tiết nhất

Dưới đây là danh sách đầy đủ và chi tiết nhất về các dịch vụ deploy web tĩnh / động đã được đề cập trong cuộc hội thoại. Bao gồm thông tin về:

* Miễn phí hay không
* Kết nối được GitHub repo không
* Hỗ trợ CDN không
* Loại trang web hỗ trợ (HTML, backend, fullstack...)
* Base path (/) hay /repo-name/
* Domain hostname dùng `endsWith()` trong JS
* Đánh giá nên dùng hay không
* Ghi chú chi tiết
* Tốc độ tải, hỗ trợ custom domain, khả năng SEO

## 1. Bảng tổng hợp

| Dịch vụ          | Free | GitHub  | CDN | Dạng web          | Base Path | Domain `endsWith`           | Nên dùng?    | Custom Domain | SEO Friendly | Tốc độ tải    | Ghi chú                    |
| ---------------- | ---- | ------- | --- | ----------------- | --------- | --------------------------- | ------------ | ------------- | ------------ | ------------- | -------------------------- |
| GitHub Pages     | ✅    | ✅       | ✅   | Tĩnh              | /repo/, / | .github.io                  | ✅ Rất nên    | ✅             | ✅            | 🟢 Nhanh      | Cực ổn định                |
| Netlify          | ✅    | ✅       | ✅   | Tĩnh/JAMstack     | /         | .netlify.app                | ✅ Nên        | ✅             | ✅            | 🟢 Rất nhanh  | Auto deploy GitHub         |
| Vercel           | ✅    | ✅       | ✅   | Tĩnh + Serverless | /         | .vercel.app                 | ✅ Nên        | ✅             | ✅            | 🟢 Rất nhanh  | Redirect từ now\.sh        |
| Cloudflare Pages | ✅    | ✅       | ✅   | Tĩnh              | /         | .pages.dev                  | ✅ Nên        | ✅             | ✅            | 🟢 Nhanh nhất | CDN mạnh                   |
| Firebase Hosting | ✅    | ⚫️      | ✅   | Tĩnh/động         | /         | .web.app / .firebaseapp.com | ✅ Nên        | ✅             | ✅            | 🟡 Trung bình | Dùng .web.app là chính     |
| Render           | ✅    | ✅       | ⚫️  | Fullstack         | /         | .onrender.com               | ✅ Dùng tốt   | ✅             | ✅            | 🟡 Trung bình | Có sleep trong free tier   |
| Surge.sh         | ✅    | ❌ (CLI) | ❌   | Tĩnh              | /         | .surge.sh                   | ✅ OK         | ✅             | 🟡 Không rõ  | 🟡 TB         | Rất nhẹ, không cần đăng ký |
| Glitch           | ✅    | ⚫️      | ❌   | Fullstack         | /         | .glitch.me                  | ❌ Hạn chế    | ❌             | ❌            | 🔴 Chậm       | Hay lỗi, đợi lâu           |
| Replit           | ✅    | ❌       | ❌   | Tĩnh + fullstack  | /         | .repl.co                    | ❌ Không nên  | ✅             | ❌            | 🔴 Chậm       | App sleep, giới hạn        |
| Railway          | ✅    | ✅       | ⚫️  | Fullstack         | /         | .up.railway.app             | ⚫️ Tạm được  | ✅             | ✅            | 🟡 Trung bình | Tốt backend, có sleep      |
| Fleek            | ✅    | ✅       | ✅   | Tĩnh + IPFS       | /         | .on.fleek.co                | ⚫️ Mới       | ✅             | 🟡 Giới hạn  | 🟡 TB         | Hỗ trợ Web3                |
| CodeSandbox      | ✅    | ✅       | ✅   | Dev/preview       | /         | .csb.app                    | ⚫️ Dùng tạm  | ❌             | ❌            | 🟡 TB         | Preview nhanh, không SEO   |
| InfinityFree     | ✅    | ❌       | ❌   | PHP               | /         | .epizy.com / .rf.gd         | ❌ Kém        | ✅             | ❌            | 🔴 Rất chậm   | Hay downtime               |
| 000Webhost       | ✅    | ❌       | ❌   | PHP               | /         | .000webhostapp.com          | ❌ Không nên  | ✅             | ❌            | 🔴 Rất chậm   | Tự xóa site, ẩn rủi ro     |
| Neocities        | ✅    | ❌       | ❌   | Tĩnh              | /         | .neocities.org              | ✅ Ổn cá nhân | ✅             | 🟡 Cơ bản    | 🟡 TB         | Phong cách retro, cổ điển  |

## 2. ✨ Top dịch vụ đề xuất theo mục đích

### Web tĩnh, site cá nhân, CV, blog

* ✅ GitHub Pages
* ✅ Netlify
* ✅ Cloudflare Pages
* ✅ Vercel

### App backend (Node, Flask...)

* ✅ Render
* ✅ Railway
* ✅ Vercel (Serverless function)

### Web nhanh, CDN mạnh

* ✅ Cloudflare Pages
* ✅ Netlify
* ✅ Vercel

### PHP, MySQL test nhanh

* ⚫️ InfinityFree
* ⚫️ 000Webhost

### Web tĩnh giản lược, offline

* ✅ Neocities
* ✅ Surge.sh

### Demo nhanh, chia sẻ preview

* ⚫️ Glitch
* ⚫️ CodeSandbox

### Kết hợp Web3, IPFS

* ⚫️ Fleek

## 3. Gợi ý hostname `endsWith()` ánh xạ trong JS (dùng trong base path)

```js
const baseConfig = new Map([
  ["github.io", "/repo-name/"],
  ["netlify.app", "/"],
  ["vercel.app", "/"],
  ["pages.dev", "/"],
  ["web.app", "/"],
  ["firebaseapp.com", "/"],
  ["onrender.com", "/"],
  ["surge.sh", "/"],
  ["glitch.me", "/"],
  ["repl.co", "/"],
  ["up.railway.app", "/"],
  ["on.fleek.co", "/"],
  ["csb.app", "/"],
  ["codesandbox.io", "/"],
  ["epizy.com", "/"],
  ["rf.gd", "/"],
  ["000webhostapp.com", "/"],
  ["neocities.org", "/"]
]);
```

---

Bạn có thể copy toàn bộ bảng này vào Notion, Google Sheet hoặc Markdown doc.

Nếu muốn mình giúp bạn tạo file chia sẻ (để in, chia sẻ team, publish), hãy bảo mình nhé!
