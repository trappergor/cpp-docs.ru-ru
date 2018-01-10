---
title: "Классы и структуры (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- Visual C++, classes
- structures, C++ classes
- user-defined types
- classes [C++]
- user-defined types, C++ classes
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ac15db222aed3abad980f4e1a0c715c099e2019c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="classes-and-structs-c"></a>Классы и структуры (C++)
В этом разделе приводится информация о классах и структурах C++. В C++ эти конструкции идентичны, за исключением того факта, что структуры по умолчанию открыты для доступа, а классы — закрыты.  
  
 Классы и структуры являются конструкциями, в которых пользователь определяет собственные типы. Классы и структуры могут включать данные-члены и функции-члены, позволяющие описывать состояние и поведение данного типа.  
  
 В раздел входят следующие темы:  
  
-   [class](../cpp/class-cpp.md)  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [Обзор членов класса](../cpp/class-member-overview.md)  
  
-   [Управление доступом к членам](../cpp/member-access-control-cpp.md)  
  
-   [Наследование](../cpp/inheritance-cpp.md)  
  
-   [Статические члены](../cpp/static-members-cpp.md)  
  
-   [Заданные пользователем преобразования типов](../cpp/user-defined-type-conversions-cpp.md)  
  
-   [Изменяемые члены данных (изменяемый спецификатор)](../cpp/mutable-data-members-cpp.md)  
  
-   [Объявления вложенных классов](../cpp/nested-class-declarations.md)  
  
-   [Типы анонимных классов](../cpp/anonymous-class-types.md)  
  
-   [Указатели на члены](../cpp/pointers-to-members.md)  
  
-   [Указатель this](../cpp/this-pointer.md)  
  
-   [Битовые поля в C++](../cpp/cpp-bit-fields.md)  
  
 Существует три типа классов: структура, класс и объединение. Они объявляются с помощью [структуры](../cpp/struct-cpp.md), [класса](../cpp/class-cpp.md), и [объединение](../cpp/unions.md) ключевые слова (см. [определение типов классов](http://msdn.microsoft.com/en-us/e8c65425-0f3a-4dca-afc2-418c3b1e57da)). В следующей таблице показаны различия между этими тремя типами классов.  
  
 Дополнительные сведения об объединениях см. в разделе [объединения](../cpp/unions.md). Сведения об управляемых классах и структурах см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).  
  
### <a name="access-control-and-constraints-of-structures-classes-and-unions"></a>Управление доступом и ограничения для структур, классов и объединений  
  
|Структуры|Классы|Объединения|  
|----------------|-------------|------------|  
|Ключевое слово для класса: `struct`|ключ класса **класса**|ключ класса **объединения**|  
|Доступ по умолчанию: public (открытый).|Доступ по умолчанию: private (закрытый).|Доступ по умолчанию: public (открытый).|  
|Нет ограничений на использование|Нет ограничений на использование|Используется только один член за один раз|  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку C++](../cpp/cpp-language-reference.md)