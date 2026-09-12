# 个人主页

极简静态个人主页，纯 HTML + CSS，无框架、无构建、无 JS。

```
index.html       整站（内容 + 样式都在这一个文件里）
cv.pdf           CV，从 ../CV_zhd_HCI/cv_hcai.pdf 复制而来
photo.jpg        头像，512x512，已裁剪压缩并清除 EXIF
photo-formal.jpg 备用头像（正式证件照风格），想换就把 index.html 里的 src 改掉
*.JPG            手机/相机原图，已在 .gitignore 里，不会被发布
```

## 本地预览

直接双击 `index.html` 用浏览器打开即可。或者：

```bash
python3 -m http.server 8000    # 然后访问 http://localhost:8000
```

## 部署到 GitHub Pages（免费，自带 HTTPS）

1. 在 GitHub 新建仓库，名字必须是 `<你的用户名>.github.io`（你的是 `zihanding.github.io`）。
   这样网址就是 `https://<用户名>.github.io`，不带子路径。
2. 在本目录执行：

```bash
git init
git add .
git commit -m "Initial personal website"
git branch -M main
git remote add origin git@github.com:ZihanDing/zihanding.github.io.git
git push -u origin main
```

3. 仓库 Settings → Pages → Source 选 `Deploy from a branch`，分支选 `main` / `(root)`，保存。
4. 等 1–2 分钟，访问 `https://<用户名>.github.io`。

之后每次改完 `index.html`，`git add . && git commit -m "update" && git push` 就会自动重新发布。

## 更新 CV

CV 改完重新编译后，把 PDF 同步过来再推送：

```bash
cp ../CV_zhd_HCI/cv_hcai.pdf cv.pdf
git add cv.pdf && git commit -m "Update CV" && git push
```
