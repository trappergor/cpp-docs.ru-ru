---
title: "Pimpl для инкапсуляции времени компиляции (современный C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a109015f3d30b04eaf89e769e1265c49663599f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Pimpl для инкапсуляции времени компиляции (современный C++)
*Pimpl идиому* методика современный C++ для скрытия реализацию, чтобы свести к минимуму взаимозависимости and для разделения интерфейсов. Pimpl — сокращение для «указатель на реализацию.» Уже могут быть знакомы с концепцией, но он известен, другие имена, как брандмауэр компилятора или как Чеширский Кот идиому.  
  
## <a name="why-use-pimpl"></a>Зачем использовать pimpl?  
 Вот, как pimpl идиому можно улучшить жизненного цикла разработки программного обеспечения.  
  
-   Минимизация зависимостей компиляции.  
  
-   Разделение интерфейс и реализацию.  
  
-   Переносимость.  
  
## <a name="pimpl-header"></a>Pimpl заголовок  
  
```cpp  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
  
```  
  
 Pimpl идиому предотвращает каскадные перестроения и макеты негибкие объекта. Оно хорошо подходит для (транзитивно) популярных типов.  
  
## <a name="pimpl-implementation"></a>Реализация Pimpl  
 Определение `impl` класса в CPP-файле.  
  
```cpp  
// my_class.cpp  
class my_class::impl {  // defined privately here  
  // ... all private data and functions: all of these  
  //     can now change without recompiling callers ...  
};  
my_class::my_class(): pimpl( new impl )  
{  
  // ... set impl values ...   
}  
```  
  
## <a name="best-practices"></a>Рекомендации  
 Рассмотрите возможность добавления поддержки для специализации не создающие замены.  
  
## <a name="see-also"></a>См. также  
 [Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Справочник по языку C++](../cpp/cpp-language-reference.md)   
 [Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)