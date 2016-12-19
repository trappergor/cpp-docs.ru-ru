---
title: "Расширения Microsoft | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "расширения Microsoft в C/C++"
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Расширения Microsoft
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*оператор\-сборки*:  
 **\_\_asm**  *инструкция\-сборки* **;** необ  
  
 **\_\_asm {**  *список\-инструкций\-по\-сборке*  **};** необ  
  
 *список\-инструкций\-по\-сборке*:  
 *инструкция\-по\-сборке* **;** необ  
  
 *инструкция\-по\-сборке* **;** *список\-инструкций\-по\-сборке* **;** необ  
  
 *список\-модификаторов\-ms*:  
 *модификатор\-ms список\-модификаторов\-ms* необ  
  
 *модификатор\-ms*:  
 **\_\_cdecl**  
  
 **\_\_fastcall**  
  
 **\_\_stdcall**  
  
 **\_\_syscall** \(зарезервировано для будущих реализаций\)  
  
 **\_\_oldcall** \(зарезервировано для будущих реализаций\)  
  
 **\_\_unaligned** \(зарезервировано для будущих реализаций\)  
  
 *базовый\-модификатор*  
  
 *базовый\-модификатор*:  
 **\_\_based \(** *базовый\-тип* **\)**  
  
 *базовый\-тип*:  
 *имя*  
  
## См. также  
 [Сводка по грамматике](../misc/grammar-summary-cpp.md)