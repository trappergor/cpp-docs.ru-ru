---
title: "Ошибка компилятора C2356 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2356
dev_langs: C++
helpviewer_keywords: C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 99f29fb1e651c8182c8aa4dc037fc8cd6af6c6cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2356"></a>Ошибка компилятора C2356
сегмент инициализации не должен изменяться во время записи преобразования  
  
 Возможные причины:  
  
-   `#pragma init_seg`предшествует код инициализации сегмента  
  
-   `#pragma init_seg`предшествует другая директива`#pragma init_seg`  
  
 Чтобы решить, переместите код инициализации сегмента в начало модуля. Если необходимо инициализировать несколько областей, переместите их в разные модули.  
  
 Следующий пример приводит к возникновению ошибки C2356:  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```