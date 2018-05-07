---
title: Ошибка компилятора C2394 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2394
dev_langs:
- C++
helpviewer_keywords:
- C2394
ms.assetid: 653fa9a0-29b3-48aa-bc01-82f98f717a2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a31a43e50a19765d7d5a07ca61f3195099793ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2394"></a>Ошибка компилятора C2394
'your_type:: operator'op'»: среда CLR или WinRToperator не является допустимым. Хотя бы один параметр должен быть следующих типов: "T^", "T^%", "T^&", где T = ваш тип  
  
 Оператор в управляемом типе или типе среды выполнения Windows не содержал по крайней мере один параметр, тип которого совпадает с типом значения, возвращаемого оператором.  
  
 Следующий пример приводит к возникновению ошибки C2394:  
  
```  
// C2394.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y^ operator -(int i, char c);   // C2394  
  
   // OK  
   static Y^ operator -(Y^ hY, char c);  
   // or  
   static Y^ operator -(int i, Y^& rhY);  
};  
```