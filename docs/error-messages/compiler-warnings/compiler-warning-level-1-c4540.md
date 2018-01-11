---
title: "Предупреждение (уровень 1) C4540 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4540
dev_langs: C++
helpviewer_keywords: C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aaaef1edaa6af093ae03fe69231a9686e3d087a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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