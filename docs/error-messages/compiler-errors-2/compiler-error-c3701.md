---
title: Ошибка компилятора C3701 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3701
dev_langs:
- C++
helpviewer_keywords:
- C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: efcf451729ef9ffd869d9fecdc122615e4b40e54
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3701"></a>Ошибка компилятора C3701
«функция»: event_source не имеет событий  
  
 Предпринята попытка использования [event_source](../../windows/event-source.md) для класса, не имеющего методов событий. Чтобы устранить эту ошибку, добавьте в класс одно или несколько событий.  
  
 Следующий пример приводит к возникновению ошибки C3701:  
  
```  
// C3701.cpp  
[ event_source(native) ]  
class CEventSrc {  
public:  
   // uncomment the following line to resolve this C3701  
   // __event void fireEvent(int i);  
};   // C3701  
  
int main() {  
}  
```