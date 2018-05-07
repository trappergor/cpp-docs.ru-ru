---
title: Ошибка компилятора C2755 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2755
dev_langs:
- C++
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a018554de91003b54ffc403f1527ca07f2d4a75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2755"></a>Ошибка компилятора C2755
«параметр»: параметр частичной специализации не являющийся типом должен быть простым идентификатором  
  
 Параметр не является типом должен быть простым идентификатором, то, что компилятор может разрешить во время компиляции один идентификатор или значение константы.  
  
 Следующий пример приводит к возникновению ошибки C2755:  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```