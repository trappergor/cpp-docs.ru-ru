---
title: Расширения Microsoft | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5699ce82a6e8537f12da50fdcb8288da167ecca3
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752243"
---
# <a name="microsoft-extensions"></a>Расширения Майкрософт

*оператор ASM*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__asm***инструкции ассемблера* **;** <sub>opt  </sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__asm {***списка для инструкций сборки***};** <sub>opt    </sub>

*список сборок инструкция*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*инструкции ассемблера* **;** <sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*инструкции ассемблера* **;** *списка для инструкций сборки* **;** <sub>opt</sub>

*Список MS модификатор*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*MS модификатор* *список ms модификатор*<sub>opt</sub>

*MS модификатор*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__cdecl**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__fastcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__stdcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__syscall** (зарезервировано для будущих реализаций)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__oldcall** (зарезервировано для будущих реализаций)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__unaligned** (зарезервировано для будущих реализаций)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*на основе модификатор*

*на основе модификатор*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__based (** *на основе типа* **)**

*на основе типа*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Имя*