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
ms.openlocfilehash: 70b1e0e6ef1294ff23952816db6f468022609f4f
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408379"
---
# <a name="microsoft-extensions"></a>Расширения Майкрософт
*оператор ASM*:  
 **__asm***инструкции ассемблера* **;** OPT    
  
 **__asm {***списка для инструкций сборки***};** OPT      
  
 *список сборок инструкция*:  
 *инструкции ассемблера* **;** OPT  
  
 *инструкции ассемблера* **;** *списка для инструкций сборки* **;** OPT  
  
 *Список MS модификатор*:  
 *MS модификатор ms модификатор list*opt  
  
 *MS модификатор*:  
 **__cdecl**  
  
 **__fastcall**  
  
 **__stdcall**  
  
 **__syscall** (зарезервировано для будущих реализаций)  
  
 **__oldcall** (зарезервировано для будущих реализаций)  
  
 **__unaligned** (зарезервировано для будущих реализаций)  
  
 *на основе модификатор*  
  
 *на основе модификатор*:  
 **__based (** *на основе типа* **)**  
  
 *на основе типа*:  
 *name*  