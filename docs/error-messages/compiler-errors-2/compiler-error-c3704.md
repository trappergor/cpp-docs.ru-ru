---
title: Ошибка компилятора C3704 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3704
dev_langs:
- C++
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b3b1f255852def5e04d75751b0a902fb7072545
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264146"
---
# <a name="compiler-error-c3704"></a>Ошибка компилятора C3704
«функция»: метод vararg не может порождать события  
  
 Предпринята попытка использования [__event](../../cpp/event.md) в методе с переменным количеством аргументов. Чтобы устранить эту ошибку, замените `fireEvent(int i, ...)` вызов с `fireEvent(int i)` вызова, как показано в следующем образце кода.  
  
 Следующий пример приводит к возникновению ошибки C3704:  
  
```  
// C3704.cpp  
[ event_source(native) ]  
class CEventSrc {  
   public:  
      __event void fireEvent(int i, ...);   // C3704  
      // try the following line instead:  
      // __event void fireEvent(int i);  
};  
  
int main() {  
}  
```