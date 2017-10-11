---
title: "Ошибка компилятора C3771 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3771
dev_langs:
- C++
helpviewer_keywords:
- C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: dc3e9639fa83524e797c22edd771c847046f0e3c
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3771"></a>Ошибка компилятора C3771
"идентификатор": в ближайшей области пространства имен не удалось найти дружественное объявление  
  
Объявление шаблона класса для указанного шаблона *идентификатор* не удалось найти в текущем пространстве имен.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что объявление шаблона класса для идентификатора шаблона задается в текущем пространстве имен или что идентификатор шаблона является полным именем.  
  
## <a name="example"></a>Пример  
Следующий пример кода объявляет шаблон класса и функцию в пространстве имен `NA`, но пытается объявить шаблон дружественной функции в пространстве имен `NB`.  
  
```cpp  
// C3771.cpp   
// compile with: /c  
  
namespace NA {  
template<class T> class A {  
    void aFunction(T t) {};  
    };  
}  
// using namespace NA;  
namespace NB {  
    class X {  
        template<class T> friend void A<T>::aFunction(T); // C3771  
// try the following line instead  
//      template<class T> friend void NA::A<T>::aFunction(T);  
// or try "using namespace NA;" instead.  
    };  
}  
```  
  
## <a name="see-also"></a>См. также  
[Шаблоны](../../cpp/templates-cpp.md)  
