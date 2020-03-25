---
title: Расширения Майкрософт
ms.date: 11/04/2016
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
ms.openlocfilehash: a2d0846e55122f177b4868c2e80c4f1d27267f5e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179410"
---
# <a name="microsoft-extensions"></a>Расширения Майкрософт

*ASM-оператор*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__asm***инструкции сборки* **;** <sub>неявное согласие</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__asm {** *Assembly-инструкции-List* **};** <sub>неявное согласие</sub>

*список инструкций сборки*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*инструкции сборки* **;** <sub>неявное согласие</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*инструкции сборки* **;** *список инструкций сборки* **;** <sub>неявное согласие</sub>

*MS-модификатор-List*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*MS-модификатор* *MS-Modifiers-List*<sub>OPT</sub>

*Модификатор MS*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__cdecl**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__fastcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__stdcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__syscall** (зарезервировано для будущих реализаций)<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__oldcall** (зарезервировано для будущих реализаций)<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__unaligned** (зарезервировано для будущих реализаций)<br/>
Модификатор &nbsp;&nbsp;&nbsp;*на основе* &nbsp;

*Модификатор на основе*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__based (** *на основе типа* **)**

*тип на основе*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*имя*
