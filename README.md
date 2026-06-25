# 教練課程管理系統

## 📁 檔案說明
```
coach-app/
├── public/
│   └── index.html     ← 主程式（所有功能都在這一個檔案）
├── vercel.json        ← Vercel 路由設定
├── package.json
├── 部署說明.md
└── README.md
```

---

## 🚀 部署步驟（約 15 分鐘）

### 第一步：設定 Firebase

1. 前往 https://console.firebase.google.com
2. 點「新增專案」→ 輸入名稱（例如 `coach-management`）→ 建立
3. 左側選單點「Firestore Database」→「建立資料庫」→ 選「測試模式」→ 選 `asia-east1`
4. 點左上角齒輪圖示 →「專案設定」
5. 往下找「您的應用程式」→ 點 `</>` 網頁圖示 → 輸入任意暱稱 →「註冊」
6. 複製 `firebaseConfig` 裡的所有內容

### 第二步：填入設定

打開 `public/index.html`，找到這段（約第 230 行）：

```js
const firebaseConfig = {
  apiKey: "填入你的apiKey",
  authDomain: "填入你的authDomain",
  projectId: "填入你的projectId",
  storageBucket: "填入你的storageBucket",
  messagingSenderId: "填入你的messagingSenderId",
  appId: "填入你的appId"
};
```

把每個引號裡的文字換成你從 Firebase 複製的值。

### 第三步：上傳到 GitHub

1. 前往 https://github.com → 登入或註冊
2. 點右上角「+」→「New repository」
3. Repository name 輸入 `coach-app`，點「Create repository」
4. 按照 GitHub 頁面上「upload an existing file」的指示，把整個 `coach-app` 資料夾上傳

### 第四步：部署到 Vercel

1. 前往 https://vercel.com → 用 GitHub 帳號登入
2. 點「Add New Project」→ 選剛才建立的 `coach-app` repo
3. 直接點「Deploy」（不需要改任何設定）
4. 等待約 1 分鐘，完成後會看到你的網址：`https://coach-app-xxx.vercel.app`

---

## 🔑 預設帳號

| 角色 | 帳號 | 密碼 |
|------|------|------|
| 總教練 | admin | admin123 |
| 陳教練 | coach1 | coach123 |
| 林教練 | coach2 | coach456 |

> 登入後可在「教練管理」頁面修改帳號密碼，或新增更多教練

---

## ✨ 功能說明

- **總覽**：統計數字、即將用完警示、最近上課紀錄
- **學員管理**：新增/編輯/刪除學員，顯示堂數進度條
- **登記上課**：選學員 → 選時間 → 確認，自動 -1 堂；支援取消還原
- **繳費記錄**：記錄繳費金額與堂數，自動增加學員總堂數
- **教練管理**（總教練專屬）：管理教練帳號密碼

---

## 🔒 後續安全設定（可選）

正式使用前，建議在 Firebase Console → Firestore → 規則 設定更嚴格的存取規則。
