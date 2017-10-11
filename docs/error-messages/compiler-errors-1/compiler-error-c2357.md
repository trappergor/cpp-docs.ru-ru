---
title: "Ошибка компилятора C2357 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2357
dev_langs:
- C++
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b3804f0ee55284aabcd46b0f45c557ccc79cbb8a
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2357"></a>Ошибка компилятора C2357
«Идентификатор»: должна быть функцией типа «тип»  
  
 Коде объявляется версия `atexit` функции, которая соответствует версии внутренне объявленной компилятором. Объявите `atexit` следующим образом:  
  
```  
int __cdecl atexit(void (__cdecl *)());  
```  
  
 Дополнительные сведения см. в разделе [init_seg](../../preprocessor/init-seg.md).  
  
 Следующий пример приводит к возникновению ошибки C2357:  
  
```  
// C2357.cpp  
// compile with: /c  
// C2357 expected  
#pragma warning(disable : 4075)  
// Uncomment the following line to resolve.  
// int __cdecl myexit(void (__cdecl *)());  
#pragma init_seg(".mine$m",myexit)  
```
