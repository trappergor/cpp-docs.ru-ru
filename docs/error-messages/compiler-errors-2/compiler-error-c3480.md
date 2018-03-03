---
title: "Ошибка компилятора C3480 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3480
dev_langs:
- C++
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 344e76f5d146e6bc715619bce7e68c80ffda211f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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