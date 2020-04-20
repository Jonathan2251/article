.. _sec-gpu:

Why Mips fall
=============

.. contents::
   :local:
   :depth: 4

有人說arm mips是授權費的不同

MIPS的定價策略是核授權很貴，而架構授權很便宜。有能力的公司都可以使用MIPS指令集開發自己的CPU，併且可以對指令集進行擴展，而不受限製。這種模式在短期內造成了百花齊放的效果，但從長期而言，由於允許自行擴充指令，導緻生態碎片化，相互不兼容，從而影響了開發者和使用者的熱情，這是MIPS沒落的主要原因。

與MIPS相反，ARM則是核授權很便宜，架構授權很貴(據說大約每5年1億美圜)，以及每顆芯片賣出後的版稅(約售價的1~2%)。這樣即使沒有能力自己開發CPU核的公司，也能通過購買核授權來快速推出CPU產品，即使有研發能力的公司，使用現成的 ARM IP 來集成CPU，也可以大幅度降低產品開發成本和縮短開發週期。ARM 的商業模式漸漸驅逐了MIPS，併開闢和佔領了更多市場，畢竟低成本的快速的產品方案可以提高市場競爭力，MIPS因此舉步為艱。

擴展私有指令就走向mips的老路了,但差別是riscv是open source hardware，the supported software will grow fast!

Mips在網路家電類的embedded electronic devices活的很好，但在cell phone, pc這種大量生命周期長的主市場就被arm, intel緊抓住，進不了。

Riscv open source hardware會先改幹掉mips, 至於cell phone...只能自己猜了。

以上私人想法。

[#license] http://bbs.creaders.net/education/bbsviewer.php?trd_id=1446940&language=big5

