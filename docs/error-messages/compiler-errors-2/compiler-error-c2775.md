---
title: Ошибка компилятора C2775 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2775
dev_langs:
- C++
helpviewer_keywords:
- C2775
ms.assetid: 9c488508-ade0-48f1-b94f-d538d15f807a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29db1a183af3c19a21cb1ea6ca677c3741a67ddf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2775"></a>Ошибка компилятора C2775
«Идентификатор»: нет метод «get» связан с этим свойством  
  
 Элемент данных объявлен с [свойство](../../cpp/property-cpp.md) расширенный атрибут не имеет `get` функция определена, но выражение пытается извлечь его значение.  
  
 Следующий пример приводит к возникновению ошибки C2775:  
  
```  
// C2775.cpp  
struct A {  
   __declspec(property(put=PutProp2, get=GetProp2)) int prop2;  
   int GetProp2(){return 0;}  
   void PutProp2(int){}  
  
   __declspec(property(put=PutProp)) int prop;  
   int PutProp(void){}  
  
};  
  
int main() {  
   A* pa = new A;  
   int x;  
   x = pa->prop;   // C2775  
   x = pa->prop2;  
}  
```