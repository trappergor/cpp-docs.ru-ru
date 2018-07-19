---
title: Предупреждение (уровень 1) C4677 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4677
dev_langs:
- C++
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3511ad3100bf695cec5df97703b39e5926c71c11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281698"
---
# <a name="compiler-warning-level-1-c4677"></a>Предупреждение компилятора (уровень 1) C4677
«функция»: подпись не частного члена содержит частный тип сборки «private_type»  
  
 Тип, открытым вне сборки использует тип, имеющий доступ к закрытому за пределами сборки. Компонент, ссылающийся на открытый тип сборки нельзя будет использовать член типа или элементы, которые ссылаются на частный тип сборки.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4677.  
  
```  
// C4677.cpp  
// compile with: /clr /c /W1  
delegate void TestDel();  
public delegate void TestDel2();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;   // C4677  
   static event TestDel2^ MyClass_Event2;   // OK  
};  
```