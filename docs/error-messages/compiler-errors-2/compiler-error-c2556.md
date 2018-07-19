---
title: Ошибка компилятора C2556 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2556
dev_langs:
- C++
helpviewer_keywords:
- C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb090b932daa93c2c680d4ec871b36c78f09a7c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228242"
---
# <a name="compiler-error-c2556"></a>Ошибка компилятора C2556
«Идентификатор»: перегруженная функция отличается только возвращаемым типом  
  
 Перегруженные функции имеют различные возвращаемые типы, но такой же список параметров. Каждая перегруженная функция должна иметь список формальных параметров.  
  
 В следующем примере возникает ошибка C2556:  
  
```  
// C2556.cpp  
// compile with: /c  
class C {  
   int func();  
   double func();   // C2556  
   int func(int i);   // ok parameter lists differ  
};  
```