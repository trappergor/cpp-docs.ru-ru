---
title: "Ошибка компилятора C2535 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2535
dev_langs: C++
helpviewer_keywords: C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2cdcd4aa00f0b96e0995e7589a8bbe4d1b990c74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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