# DoF Feasibility Index

**Why “more degrees of freedom” does not mean “easier to scale.”**

A quantitative framework for assessing the **engineering scalability** of electromechanical and robotic products — not market size, intelligence, or peak demo performance.

- **Author:** Rongzhong Li · Petoi LLC  
- **Version:** 0.9 — September 2026  
- **Live page:** open [`index.html`](./index.html) in a browser (Cloudflare Pages / GitHub Pages will serve it at the site root).

---

## What this is

The **DoF Feasibility Index \(F\)** combines four structural ideas into one index:

| Idea | Role in \(F\) |
|------|----------------|
| **Capability** | Equivalent functional DoF vs. task-necessary DoF \((D_e / D_t)^\alpha\) |
| **Reliability** | Series-system survival \(e^{-T \cdot D_a / \mathrm{MTBF}}\) |
| **Complexity** | Polynomial penalty \(1 + c \cdot D_a^\beta\) |
| **Calibration** | Constant \(K\) so a reference product (air conditioner) has \(F = 1\) |

Core formula:

\[
F = \frac{K \cdot \left[1 + \left(\dfrac{D_e}{D_t}\right)^{\alpha}\right] \cdot e^{-T \cdot D_a / MTBF_{DoF}}}{1 + c \cdot D_a^{\beta}}
\]

**Interpretation bands (engineering scalability, not sales):**

| Range | Meaning |
|-------|---------|
| \(F \ge 0.9\) | High scalability |
| \(0.5 \le F < 0.9\) | Scalable / developing |
| \(0.35 \le F < 0.5\) | Constrained scalability |
| \(F < 0.35\) | High complexity / hard to scale |

The page also discusses **structure reuse \(S = D_e / D_a\)**, an optional **extra-structural term \(E\)** (institutional or emotional / life-like value), and product cases from appliances and cars to vacuums, drones, 3D printers, arms, and quadrupeds.

> This is a **thinking framework**. The specific algebraic form can be redefined as long as rankings still match reality and the model does not overfit.

---

## How to use the webpage

1. **Open the HTML**  
   Double-click `index.html`, or serve the folder locally, e.g.  
   `python3 -m http.server 8080`  
   then visit `http://localhost:8080/index.html`.  
   Internet access is required (Tailwind, KaTeX, Plotly, fonts load from CDNs).

2. **Language**  
   Use the **EN / 中** toggle in the sidebar or mobile header.

3. **Read the article**  
   Sections cover background, the formula and variables, derivation, product validation, evolutionary cases (e.g. fans, shavers, 3D printers), structure reuse \(S\), non-structural \(E\), and implications for high-DoF systems.

4. **Interactive calculator**  
   In the validation section, adjust \(D_a\), \(S\), \(D_t\), MTBF, usage window \(T\), etc., and see \(F\) update live. Click a **product row** in the table to load that product’s parameters into the calculator.

5. **Charts**  
   DoF–feasibility curves and related Plotly charts illustrate how \(F\) changes with design choices.

6. **Markdown companion**  
   [`dof_feasibility_index.md`](./dof_feasibility_index.md) is a text/math source for reading or citation. Interactive UI and charts live only in the HTML.

---

## Repository contents

| File | Purpose |
|------|---------|
| `index.html` | Full interactive article (site root for static hosting) |
| `dof_feasibility_index.md` | Markdown write-up of the same framework |
| `README.md` | This file |

No build step, no npm install. Static hosting only.

---

## License / contact

This work is licensed under **[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)**  
(Attribution–NonCommercial). See [`LICENSE`](./LICENSE).

Framework, calibrations, and product assessments by Rongzhong Li (Petoi LLC).  
Site: [petoi.com](https://www.petoi.com) · Support: support@petoi.com

---

# 自由度可行性指数

**为什么「自由度越多」不等于「越容易规模化」。**

用于评估机电与机器人产品**工程可规模性**的定量框架——不是市场规模、智能水平或演示峰值。

- **作者：** 李荣仲 · Petoi LLC  
- **版本：** 0.9 — 2026年9月  
- **在线阅读：** 用浏览器打开 [`index.html`](./index.html)（Cloudflare / GitHub Pages 会将其作为站点根页面）。

---

## 这是什么

**自由度可行性指数 \(F\)** 把四类结构因素收成一个指数：

| 思路 | 在 \(F\) 中的作用 |
|------|-------------------|
| **能力** | 等效功能自由度相对任务必要自由度 \((D_e / D_t)^\alpha\) |
| **可靠性** | 串联系统存活概率 \(e^{-T \cdot D_a / \mathrm{MTBF}}\) |
| **复杂度** | 多项式惩罚 \(1 + c \cdot D_a^\beta\) |
| **标定** | 常数 \(K\)，使基准产品（空调）\(F = 1\) |

核心公式：

\[
F = \frac{K \cdot \left[1 + \left(\dfrac{D_e}{D_t}\right)^{\alpha}\right] \cdot e^{-T \cdot D_a / MTBF_{DoF}}}{1 + c \cdot D_a^{\beta}}
\]

**判定区间（工程可规模性，不是销量）：**

| 范围 | 含义 |
|------|------|
| \(F \ge 0.9\) | 高可规模性 |
| \(0.5 \le F < 0.9\) | 可规模化 / 发展中 |
| \(0.35 \le F < 0.5\) | 受限可规模性 |
| \(F < 0.35\) | 高复杂度 / 难以规模化 |

页面还讨论**结构复用 \(S = D_e / D_a\)**、可选的**非结构附加项 \(E\)**（制度支持或情绪 / 生命感），以及从家电、汽车到扫地机、无人机、3D 打印机、机械臂、四足等产品对照。

> 这是一种**思考维度**。具体代数形式可以重定义，只要排序仍贴合现实、且不过拟合即可。

---

## 网页怎么用

1. **打开 HTML**  
   直接打开 `index.html`，或在目录下运行  
   `python3 -m http.server 8080`，  
   访问 `http://localhost:8080/index.html`。  
   需要能访问外网（Tailwind、KaTeX、Plotly、字体走 CDN）。

2. **语言**  
   侧栏或手机顶栏的 **EN / 中** 切换中英文。

3. **阅读正文**  
   含问题背景、公式与变量、推导、产品验证、演化案例（电扇、剃须刀、3D 打印机等）、结构复用 \(S\)、非结构项 \(E\)，以及对高自由度系统的启示。

4. **交互计算器**  
   在验证一节调节 \(D_a\)、\(S\)、\(D_t\)、MTBF、可靠性窗口 \(T\) 等，实时看 \(F\)。点击产品表中的一行，可把该产品参数载入计算器。

5. **图表**  
   自由度–可行性等 Plotly 图帮助观察设计选择如何影响 \(F\)。

6. **Markdown 版本**  
   [`dof_feasibility_index.md`](./dof_feasibility_index.md) 便于阅读与引用；交互界面与图表仅在 HTML 中。

---

## 仓库内容

| 文件 | 用途 |
|------|------|
| `index.html` | 完整交互文章（静态托管的站点根页面） |
| `dof_feasibility_index.md` | 同一框架的 Markdown 文稿 |
| `README.md` | 本说明 |

无需构建、无需安装依赖，纯静态托管即可。

---

## 许可 / 联系

本作品采用 **[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)**  
（署名–非商业性使用）许可。详见 [`LICENSE`](./LICENSE)。

框架、标定与产品评估由李荣仲（Petoi LLC）提出。  
官网：[petoi.com](https://www.petoi.com) · 支持邮箱：support@petoi.com
