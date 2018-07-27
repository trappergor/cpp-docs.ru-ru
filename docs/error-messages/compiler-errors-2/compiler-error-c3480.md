---
title: Ошибка компилятора C3480 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3480
dev_langs:
- C++
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 673eff58b09fe1f2bbfe8a7629594399e8ca6b22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33259143"
---
# <a name="compiler-error-c3480"></a>Ошибка компилятора C3480
"переменная": передаваемая переменная в лямбда-выражении должна быть из внешней области видимости функции  
  
 Передаваемая переменная в лямбда-выражении не относится к внешней области видимости функции.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите переменную из списка передаваемых параметров в лямбда-выражении.  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример вызывает ошибку C3480, так как переменная `global` не относится к внешней области видимости функции.  
  
```  
// C3480a.cpp  
  
int global = 0;  
int main()  
{  
   [&global] { global = 5; }(); // C3480  
}  
```  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере ошибка C3480 устраняется путем удаления переменной `global` из списка передачи лямбда-выражения.  
  
```  
// C3480b.cpp  
  
int global = 0;  
int main()  
{  
   [] { global = 5; }();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)