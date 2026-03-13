.. _sec-it:

IT
==

.. contents::
   :local:
   :depth: 4

Why Mips fall
-------------

有人說arm mips是授權費的不同

MIPS的定價策略是核授權很貴，而架構授權很便宜。有能力的公司都可以使用MIPS指令集開發自己的CPU，併且可以對指令集進行擴展，而不受限製。這種模式在短期內造成了百花齊放的效果，但從長期而言，由於允許自行擴充指令，導緻生態碎片化，相互不兼容，從而影響了開發者和使用者的熱情，這是MIPS沒落的主要原因。

與MIPS相反，ARM則是核授權很便宜，架構授權很貴(據說大約每5年1億美圜)，以及每顆芯片賣出後的版稅(約售價的1~2%)。這樣即使沒有能力自己開發CPU核的公司，也能通過購買核授權來快速推出CPU產品，即使有研發能力的公司，使用現成的 ARM IP 來集成CPU，也可以大幅度降低產品開發成本和縮短開發週期。ARM 的商業模式漸漸驅逐了MIPS，併開闢和佔領了更多市場，畢竟低成本的快速的產品方案可以提高市場競爭力，MIPS因此舉步為艱 [#license]_。

擴展私有指令就走向mips的老路了,但差別是riscv是open source hardware，the supported software will grow fast!

Mips在網路家電類的embedded electronic devices活的很好，但在cell phone, pc這種大量生命周期長的主市場就被arm, intel緊抓住，進不了 [#miss-cellphone]_ 。

Riscv open source hardware會先改幹掉mips, 至於cell phone...只能自己猜了。

以上私人想法。


AI時代
------

有人說：

對於寫程式的人來說

現在真的很適合引用雙城記開頭那段話

這是一個最好的時代，這是一個最壞的時代；

這是一個智慧的年代，這是一個愚蠢的年代；

這是一個信仰的時期，這是一個懷疑的時期；

這是一個光明的季節，這是一個黑暗的季節；

這是希望之春，這是失望之冬；

我們面前應有盡有，我們面前一無所有；

我們都將直上天堂，我們都將直下地獄。


未來 UI 開發會被 AI 程式產生器取代嗎？
--------------------------------------

一個值得思考的歷史對比是：DOS 時代與 Windows GUI 時代的演進。

● DOS 時代：UI Generator

在 DOS PC 時代（1980s–early 1990s），其實已經有很多 **程式產生器 (program generator)** 或 UI 設計工具，可以透過拖拉方式設計畫面並自動產生程式碼，例如：

- Turbo Vision
- dBASE form generator
- FoxPro screen builder

典型的開發模式是：

::

   Design UI
        ↓
   Generate code
        ↓
   Developer modify

但這種模式很快遇到幾個問題：

- 產生的程式碼難以維護
- 客製化能力有限
- UI abstraction 層級太低

因此 UI generator 並沒有取代 UI 程式設計師。

● Windows GUI 時代：OS Framework

當 Windows / Mac GUI 作業系統出現後，情況發生很大的改變。

作業系統提供完整的 GUI framework，例如：

- Win32 API
- MFC
- .NET / WPF
- Cocoa (macOS)

開發模式變成：

::

   OS GUI Framework
         ↓
   IDE (Visual Studio / Xcode)
         ↓
   Developer writes logic

IDE 仍然提供 UI designer，但主要只是輔助工具，核心程式邏輯仍然由工程師撰寫。

因此 UI generator 並沒有取代 UI 開發者。

● Web 時代：更高層的 UI abstraction

Web UI framework 又把 abstraction 提升了一層，例如：

- React
- Angular
- Vue

UI 開發逐漸變成 **component-based architecture**。

例如：

::

   <Button onClick={submit}>Submit</Button>

工程師主要負責：

- state management
- interaction logic
- application architecture

真正困難的部分已經不是畫 UI，而是 **系統設計與狀態管理**。

● AI Code Generator 的限制

現在的 AI coding 工具，例如：

- Copilot
- ChatGPT
- Cursor
- Devin

其實更接近 **code assistant**。

AI 擅長的事情包括：

- 產生 boilerplate code
- 生成 UI layout
- 寫 CRUD 程式

但在以下方面仍然有限：

- 大型系統 architecture
- 跨模組 interaction
- performance tuning
- 長期 maintainability

真正困難的通常是 **abstraction design**。

● 未來可能的方向：AI-aware OS / Framework

未來的發展不一定是「Cloud AI 自動生成整個程式」。

另一種可能是 **OS 或 framework 直接內建 AI 能力**。

例如 OS 可能提供 AI-aware API：

::

   create_ui_from_spec(json)
   generate_animation(style)
   generate_layout(intent)

開發者只需要描述 UI intent，例如：

- login screen
- corporate style
- mobile friendly

framework 或 OS 再利用 AI 生成 layout 與 UI component。

這其實和現在的 **Declarative UI** 很接近，例如：

- SwiftUI
- Jetpack Compose
- Flutter

● 未來 UI stack 的可能架構

未來 UI 系統可能演變為：

::

   Application logic
          ↓
   Intent UI description
          ↓
   Framework / OS
          ↓
   AI layout / rendering
          ↓
   GPU

也就是說 **AI 可能存在於 framework layer，而不是完全取代 developer**。

這樣的設計有幾個好處：

- 行為較 deterministic
- security 較好
- 可以 version control
- 系統架構更容易維護

軟體工程的長期趨勢

如果從軟體工程歷史來看，其實一直在做同一件事情：

::

   Assembly
     ↓
   C
     ↓
   GUI framework
     ↓
   Web framework
     ↓
   Declarative UI
     ↓
   AI-assisted development

每一次都是在 **提升 abstraction level**。

工程師並沒有消失，只是工作層次不斷往上移。


.. [#license] http://bbs.creaders.net/education/bbsviewer.php?trd_id=1446940&language=big5

.. [#miss-cellphone] 错失智能手机时代，无力回天 https://zhuanlan.zhihu.com/p/29983481
