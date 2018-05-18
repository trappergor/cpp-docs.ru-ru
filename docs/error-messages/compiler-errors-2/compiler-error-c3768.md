---
title: Ошибка компилятора C3768 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3768
dev_langs:
- C++
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3634ecf3eb1417095cce144706838113b5ad2a0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3768"></a>Ошибка компилятора C3768
не удается получить адрес виртуальной функции vararg в чистом управляемом коде  
  
 **/CLR: pure** рекомендуется использовать параметр компилятора в Visual Studio 2015.  
  
 При компиляции с параметром `/clr:pure`, невозможно получить адрес виртуальной `vararg` функции.  
  
## <a name="example"></a>Пример  

 Следующий пример приводит к возникновению ошибки C3768:  
  
```  
// C3768.cpp  
// compile with: /clr:pure  
struct A  
{  
   virtual void f(...);  
};  
  
int main()  
{  
   &(A::f);   // C3768  
}  
```