---
title: Предупреждение (уровень 1) C4540 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4540
dev_langs:
- C++
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3939ad2bbcba1ab3b492d83bdbb8f7076c2c5f2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283066"
---
# <a name="compiler-warning-level-1-c4540"></a>Предупреждение компилятора (уровень 1) C4540
приведение dynamic_cast использовано для преобразования к недоступной или неоднозначной базе; Проверка во время выполнения не удастся («тип1» в «тип2»)  
  
 Вы использовали `dynamic_cast` для преобразования из одного типа в другой. Компилятору определить, что приведения невозможно (вернуть **NULL**), так как базовый класс недоступен (`private`, например) или является неоднозначным (более одного раза в иерархии классов для экземпляра).  
  
 Ниже показан пример этого предупреждения. Класс **B** является производным от класса **A**. Программа использует `dynamic_cast` приведение от класса **B** (производный класс) класс **A**, который всегда будут завершаться ошибкой из-за класс **B** — `private` и, следовательно, Нет доступа. Изменения доступа к **A** для **открытый** устранить предупреждение.  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```