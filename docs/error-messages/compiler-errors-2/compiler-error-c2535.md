---
title: Ошибка компилятора C2535 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2535
dev_langs:
- C++
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1dc791cd7782cc758aa51b0c61d87a79570c13c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2535"></a>Ошибка компилятора C2535
«Идентификатор»: функция-член уже определена или объявлена  
  
 Причиной этой ошибки может с помощью того же списка формальных параметров в более одного определения или объявления перегруженной функции.  
  
 Если C2535 получить из-за функции Dispose, см. раздел [деструкторы и методы завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) для получения дополнительной информации.  
  
 При компиляции проекта ATL, см. в статье базы знаний Q241852.  
  
 Следующий пример приводит к возникновению ошибки C2535:  
  
```  
// C2535.cpp  
// compile with: /c  
class C {  
public:  
   void func();   // forward declaration  
   void func() {}   // C2535  
};  
```