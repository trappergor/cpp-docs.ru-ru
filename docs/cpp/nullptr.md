---
title: "nullptr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- nullptr_cpp
dev_langs:
- C++
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 16bbbc38c61b2b6ff0539b2c71a0457b38465acb
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="nullptr"></a>nullptr
Обозначает константу-указатель NULL типа `std::nullptr_t`, которая может быть преобразована к любому типу необработанного указателя.  Хотя ключевое слово `nullptr` можно использовать без включения каких-либо заголовков, но если в коде используется тип `std::nullptr_t`, необходимо определить его, включив заголовок `<cstddef>`.  
  
> [!NOTE]
>  Ключевое слово `nullptr` также определено в языке C++/CLI для приложений управляемого кода, и оно не взаимозаменяемо с ключевым словом языка C++ стандарта ISO. Если ваш код может компилироваться с помощью [/CLR](../build/reference/clr-common-language-runtime-compilation.md) параметр компилятора, который нацелен на управляемый код, затем с помощью `__nullptr` в любой строке кода, где необходимо обеспечить, чтобы компилятор использовал собственную интерпретацию C++. Дополнительные сведения см. в разделе [nullptr](../windows/nullptr-cpp-component-extensions.md).  
  
## <a name="remarks"></a>Примечания  
 Не следует использовать значение `NULL` или ноль (`0`) в качестве константы-указателя null; ключевое слово `nullptr` менее уязвимо для неправильного использования и лучше работает в большинстве случаев.  Например, если для функции `func(std::pair<const char *, double>)` произвести вызов `func(std::make_pair(NULL, 3.14))`, возникнет ошибка компилятора.  Макрос NULL разворачивается в `0`, поэтому вызов `std::make_pair(0, 3.14)` возвращает значение `std::pair<int, double>`, которое невозможно преобразовать к типу параметра `std::pair<const char *, double>` функции func().  Вызов `func(std::make_pair(nullptr, 3.14))` успешно компилируется, поскольку `std::make_pair(nullptr, 3.14)` возвращает значение `std::pair<std::nullptr_t, double>`, которое допускает преобразование в тип `std::pair<const char *, double>`.  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)
