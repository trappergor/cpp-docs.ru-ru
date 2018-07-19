---
title: Ошибка компилятора C2801 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2801
dev_langs:
- C++
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f68b3f575fcb8b909f58ac2ffbcaca26580279da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237096"
---
# <a name="compiler-error-c2801"></a>Ошибка компилятора C2801
«оператор» должен быть статическим членом  
  
 Следующие операторы могут перегружаться только как нестатические члены:  
  
-   Назначение `=`  
  
-   Доступ к членам класса `->`  
  
-   Подписи пропущена `[]`  
  
-   Вызов функции `()`  
  
 Возможные причины C2801.  
  
-   Перегруженный оператор не класса, структуры или члена объединения.  
  
-   Перегруженный оператор объявлен `static`.  
  
-   Следующий пример приводит к возникновению ошибки C2801:  
  
```  
// C2801.cpp  
// compile with: /c  
operator[]();   // C2801 not a member  
class A {  
   static operator->();   // C2801 static  
   operator()();   // OK  
};  
```