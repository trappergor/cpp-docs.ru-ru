---
title: "Ошибка компилятора C3532 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3532
dev_langs: C++
helpviewer_keywords: C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e78db21d00ea93378358a1147163276fb12bdfd5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3532"></a>Ошибка компилятора C3532
«Тип»: Неправильное использование «auto»  
  
 Указанный тип не может объявляться с `auto` ключевое слово. Например, нельзя использовать `auto` ключевое слово для объявления массива или метод тип возвращаемого значения.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что выражение инициализации возвращает допустимый тип.  
  
2.  Убедитесь, что не объявления массива или тип возвращаемого значения метода.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3532, поскольку `auto` ключевое слово не может объявить тип возвращаемого значения метода.  
  
```  
// C3532a.cpp  
// Compile with /Zc:auto  
auto f(){}   // C3532  
```  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3532, поскольку `auto` ключевое слово не может объявить массив.  
  
```  
// C3532b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int x[5];  
   auto a[5];            // C3532  
   auto b[1][2];         // C3532  
   auto y[5] = x;        // C3532  
   auto z[] = {1, 2, 3}; // C3532  
   auto w[] = x;         // C3532  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово auto](../../cpp/auto-keyword.md)