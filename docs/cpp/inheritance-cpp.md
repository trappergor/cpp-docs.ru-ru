---
title: "Наследование (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- derived classes
- derived classes, about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
caps.latest.revision: 7
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
ms.openlocfilehash: dba45acbc602465db876038e83cb0cd496b2337e
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="inheritance--c"></a>Наследование (C++)
В этом разделе рассматривается использование производных классов для создания расширяемых программ.  
  
## <a name="overview"></a>Обзор  
 Новые классы могут наследоваться от существующих классов с помощью механизма «наследования» (см. сведения начиная в [одиночное наследование](../cpp/single-inheritance.md)). Классы, используемые для наследования, называются "базовыми классами" определенного производного класса. Производный класс объявляется с помощью следующего синтаксиса:  
  
```  
 class Derived : [virtual] [access-specifier] Base  
{  
   // member list  
};  
 class Derived : [virtual] [access-specifier] Base1,  
 [virtual] [access-specifier] Base2, . . .  
{  
   // member list  
};  
```  
  
 После тега (имени) класса следует двоеточие и список базовых спецификаций.  Названные таким образом базовые классы, вероятно, были объявлены ранее.  Базовые спецификации могут содержать описатель доступа, которое является одним из ключевых слов **открытый**, `protected` или `private`.  Эти описатели доступа отображаются перед именем базового класса и применяются только к базовому классу.  Эти описатели контролируют разрешение производного класса на использование членов базового класса.  В разделе [управления доступом к членам](../cpp/member-access-control-cpp.md) сведения о доступе к членам базового класса.  Если описатель доступа пропущен, доступ к базе считается `private`.  Базовые спецификации могут содержать ключевое слово **виртуальных** для указания виртуальное наследование.  Это ключевое слово может отображаться до или после описателя доступа, если таковые имеются.  Если используется виртуальное наследование, базовый класс называется виртуальным базовым классом.  
  
 Можно определить несколько базовых классов, разделив их запятыми.  Если указан один базовый класс, модель наследования является [единый наследования](../cpp/single-inheritance.md). Если указано более одного базового класса, модель наследования называется [множественное наследование](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca),  
  
 В раздел входят следующие темы:  
  
-   [Одиночное наследование](../cpp/single-inheritance.md)  
  
-   [Множественное наследование](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca)  
  
-   [Несколько базовых классов](../cpp/multiple-base-classes.md)  
  
-   [Виртуальные функции](../cpp/virtual-functions.md)  
  
-   [Явные переопределения](../cpp/explicit-overrides-cpp.md)  
  
-   [Абстрактные классы](../cpp/abstract-classes-cpp.md)  
  
-   [Сводка правил области](../cpp/summary-of-scope-rules.md)  
  
 [__Super](../cpp/super.md) и [__interface](../cpp/interface.md) в этом разделе описаны ключевые слова.  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку C++](../cpp/cpp-language-reference.md)
