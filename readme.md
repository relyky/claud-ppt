# Mastering Claude Code in 30 minutes 筆記
這是隨手筆記。時間有限。

# Tips
> Tip #1:   
> use codebase Q&A as a way to dip your feet into Claude Code   
> 使用「程式碼庫問答」作為入門方式，讓自己先試水溫了解 Claude Code。

> Tip #2:   
> practice prompting, and start to understand what Claude Code "gets" immediately vs. what needs more specific instructions   
> 練習撰寫提示語，並開始理解哪些內容 Claude Code 能立即理解、哪些需要更具體的指示。

> Tip #3:   
> teach Claude to use your tools   
> 教會 Claude 如何使用你的工具。

> Tip #4:   
> tailor the workflow to the task   
> 根據任務來調整工作流程。

> Tip #5:   
> the more context you give Claude, the smarter it will be   
> 你提供給 Claude 的上下文越多，它就會變得越聰明。

> Tip #6:   
> take time to tune context   
> 花時間調整上下文（context tuning）。   
> *Is it for you or your team? Do you want to add it automatically or lazily?*   
> *想想這是為你自己還是你的團隊使用？你希望它是自動添加還是延遲載入？*

> Tip #7:   
> configure CLAUDE.md, MCP servers, permissions, and slash commands for your team, and check them into git   
> 為你的團隊設定好 CLAUDE.md、MCP 伺服器、權限與斜線指令，並將它們提交到 Git 版本庫中。

# Common workflows
就是 prompt 怎麼下比較好。 
總之就是：在編寫代碼前先制定計劃，就這樣。
在編寫代碼前，在開始做一點探索、做一點規劃，

### 註：個人心得   
總之俱體就是：   
(1) 在編寫代碼前一開始做相關探索，  
(2) 然後下需求或問題 → 叫AI先思考(頭腦風暴)再給予計劃或建議方案 → 在執行前先批準。   
 
> Explore > plan > confirm > code > commit
```
> Figure out the root cause for issue #983, then propose a few fixes. Let me choose an approach before you code. ultrathink.
> 找出第 983 號問題的根本原因，然後提出幾個修復方案。在你開始撰寫程式碼之前，讓我先選擇要採用的方法。請深入思考。
```

> Write tests > commit > code > iterate > commit
```
> Write test for @utils/markdown.ts to make sure links render properly (note the tests wan't pass yet, since links aren't yet implemented). Then commit. Then update the code to make the tests pass.
> 撰寫 @utils/markdown.ts 的測試，以確保連結能正確渲染（注意：測試目前尚不會通過，因為連結功能尚未實作）。接著提交（commit）變更，然後更新程式碼，使測試通過。
```

> Write code > screenshot result > iterate
```
> Implement [mock.png]. Then screenshot it with Puppeteer and iterate till it looks like the mock.
> 實作 [mock.png] 的設計。然後使用 Puppeteer 截圖，並不斷調整，直到畫面與設計稿相符。
``` 
※ Puppeteer 是一款由Google 開發的Node.js 函式庫，提供JavaScript API 來控制Chrome 或Chromium 瀏覽器。

# Give Claude context
>
> **More context = better performance**
>

`CLAUDE.md` 一言難盡啊！   

There are a number of ways to give Claude more context:
 - CLAUDE.md
   - CLAUDE.local.md
 - Slash commands
   - `/help`
 - At-mentioning filenames
   - `@filename1 @filename2 ...`
 - (coming soon: MCP resources)
 
## Give Claude more context

 - `/<enterprise root>/CLAUDE.md`
 - `~/.claude/CLAUDE.md`
 - `project-root/`   
   * `CLAUDE.md`   
   * `CLAUDE.local.md`	 

## Give Claude more context (commands & settings.json)
 - `~/.claude/commands/foo.md`
 - `project-root/`
   - `.claude/commands/foo.md`
   - `a/`
     - `commands/foo.md`
	 - `CLAUDE.md`
	 - `foo.py`
 
``` 
1 .claude
2 ├── commands
3 │   ├── create-release-pr.md
4 │   ├── fix-github-issue.md
5 │   ├── get-feedback.md
6 │   ├── label-github-issues.md
7 │   └── lint.md
8 ├── settings.json
9 └── settings.local.json 
``` 

# 參考來源
- bilibili [Anthropic内部员工2天快速入职的秘诀？官方创建者揭秘Claude Code终极用法](https://www.bilibili.com/video/BV1c5JDzyEH7/?spm_id_from=333.788.videopod.sections&vd_source=c0cbb7db1f35153d8ef998e4cbecdbe7)   
- youtube [Mastering Claude Code in 30 minutes](https://www.youtube.com/watch?v=6eBSHbLKuN0)  

# 演講投影片
![2025-10-30-10-13-48-1](2025-10-30-10-13-48-1.webp)
![2025-10-30-10-13-49-1](2025-10-30-10-13-49-1.webp)
![2025-10-30-10-13-49-2](2025-10-30-10-13-49-2.webp)
![2025-10-30-10-13-49-3](2025-10-30-10-13-49-3.webp)
![2025-10-30-10-13-49-4](2025-10-30-10-13-49-4.webp)
![2025-10-30-10-13-49-5](2025-10-30-10-13-49-5.webp)
![2025-10-30-10-13-50-1](2025-10-30-10-13-50-1.webp)
![2025-10-30-10-13-50-2](2025-10-30-10-13-50-2.webp)
![2025-10-30-10-13-50-3](2025-10-30-10-13-50-3.webp)
![2025-10-30-10-13-50-4](2025-10-30-10-13-50-4.webp)
![2025-10-30-10-13-51-1](2025-10-30-10-13-51-1.webp)
![2025-10-30-10-13-51-2](2025-10-30-10-13-51-2.webp)
![2025-10-30-10-13-51-3](2025-10-30-10-13-51-3.webp)
![2025-10-30-10-13-51-4](2025-10-30-10-13-51-4.webp)
![2025-10-30-10-13-52-1](2025-10-30-10-13-52-1.webp)
![2025-10-30-10-13-52-2](2025-10-30-10-13-52-2.webp)
![2025-10-30-10-13-52-3](2025-10-30-10-13-52-3.webp)
![2025-10-30-10-13-52-4](2025-10-30-10-13-52-4.webp)
![2025-10-30-10-13-53-1](2025-10-30-10-13-53-1.webp)
![2025-10-30-10-13-53-2](2025-10-30-10-13-53-2.webp)
![2025-10-30-10-13-53-3](2025-10-30-10-13-53-3.webp)
![2025-10-30-10-13-53-4](2025-10-30-10-13-53-4.webp)
![2025-10-30-10-13-53-5](2025-10-30-10-13-53-5.webp)
![2025-10-30-10-13-54-1](2025-10-30-10-13-54-1.webp)
![2025-10-30-10-13-54-2](2025-10-30-10-13-54-2.webp)
![2025-10-30-10-13-54-3](2025-10-30-10-13-54-3.webp)
![2025-10-30-10-13-54-4](2025-10-30-10-13-54-4.webp)
![2025-10-30-10-13-55-1](2025-10-30-10-13-55-1.webp)
![2025-10-30-10-13-55-2](2025-10-30-10-13-55-2.webp)
![2025-10-30-10-13-55-3](2025-10-30-10-13-55-3.webp)
![2025-10-30-10-13-55-4](2025-10-30-10-13-55-4.webp)
![2025-10-30-10-13-55-5](2025-10-30-10-13-55-5.webp)
![2025-10-30-10-13-56-1](2025-10-30-10-13-56-1.webp)
![2025-10-30-10-13-56-2](2025-10-30-10-13-56-2.webp)
![2025-10-30-10-13-56-3](2025-10-30-10-13-56-3.webp)