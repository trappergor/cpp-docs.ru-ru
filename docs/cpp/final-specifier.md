---
title: "Спецификатор final | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- final_CPP
dev_langs:
- C++
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a3f7c5afd4010983ea943193b7abfb99f22eda38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="final-specifier"></a>Спецификатор final
Ключевое слово `final` можно использовать для назначения виртуальных функций, которые невозможно переопределить в производном классе. Можно также использовать это ключевое слово для назначения классов, которые невозможно наследовать.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
function-declaration final;  
```  
  
```  
  
class class-name final base-classes  
```  
  
## <a name="remarks"></a>Примечания  
 Ключевое слово `final` зависит от контекста и имеет специальное значение, только если используется после объявления функции или имени класса; в противном случае оно не является зарезервированным ключевым словом.  
  
 Если `final` используется в объявлениях класса, `base-classes` является необязательной частью объявления.  
  
## <a name="example"></a>Пример  
 В следующем примере ключевое слово `final` используется для указания невозможности переопределения виртуальной функции.  
  
```cpp  
class BaseClass  
{  
    virtual void func() final;  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void func(); // compiler error: attempting to   
                         // override a final function  
};  
```  
  
 Сведения о том, как указать, что функции-члены могут быть переопределены см. в разделе [спецификатор переопределения](../cpp/override-specifier.md).  
  
 В следующем примере ключевое слово `final` используется для указания невозможности наследования класса.  
  
```cpp  
class BaseClass final   
{  
};  
  
class DerivedClass: public BaseClass // compiler error: BaseClass is   
                                     // marked as non-inheritable  
{  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Описатель override](../cpp/override-specifier.md)