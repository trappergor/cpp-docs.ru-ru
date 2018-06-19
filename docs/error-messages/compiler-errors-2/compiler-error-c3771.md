---
title: Ошибка компилятора C3771 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3771
dev_langs:
- C++
helpviewer_keywords:
- C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8adfdb1562cc9efbe208bd7c887b7c4aa77ddd82
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272549"
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