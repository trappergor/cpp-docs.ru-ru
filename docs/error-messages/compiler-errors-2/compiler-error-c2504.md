---
title: "Ошибка компилятора C2504 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2504
dev_langs:
- C++
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b7843d69b7238bedb58d0232d64ff2d0a826d07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2504"></a>Ошибка компилятора C2504
«класс»: базовый класс не определен  
  
 Базовый класс объявлен, но никогда не определен.  Возможные причины:  
  
1.  Пропущен включаемый файл.  
  
2.  Внешний базовый класс объявлен без [extern](../../cpp/using-extern-to-specify-linkage.md).  
  
 Следующий пример приводит к возникновению ошибки C2504:  
  
```  
// C2504.cpp  
// compile with: /c  
class A;  
class B : public A {};   // C2504  
```  
  
 ХОРОШО  
  
```  
class C{};  
class D : public C {};  
```