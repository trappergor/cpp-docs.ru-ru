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
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b5b061112501cad028e8ca05f50b93651d2a11e6
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3480"></a>Ошибка компилятора C3480
"переменная": передаваемая переменная в лямбда-выражении должна быть из внешней области видимости функции  
  
 Передаваемая переменная в лямбда-выражении не относится к внешней области видимости функции.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите переменную из списка передачи лямбда-выражения.  
  
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
