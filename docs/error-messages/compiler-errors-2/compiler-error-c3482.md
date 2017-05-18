---
title: "Ошибка компилятора C3482 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3482
dev_langs:
- C++
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
caps.latest.revision: 7
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
ms.openlocfilehash: ca80df6224311db87c4c5f1425d825cbada2116c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3482"></a>Ошибка компилятора C3482
"this" может быть использован в качестве передаваемого параметра в лямбда-выражении только с нестатической функцией-членом  
  
 Нельзя передавать `this` в список передаваемых параметров лямбда-выражения, объявленного в статическом методе или в глобальной функции.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Преобразуйте включающую функцию в нестатический метод или  
  
-   удалите указатель `this` из списка передаваемых параметров лямбда-выражения.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению предупреждения C3482:  
  
```  
// C3482.cpp  
// compile with: /c  
  
class C  
{  
public:  
   static void staticMethod()  
   {  
      [this] {}(); // C3482  
   }  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
