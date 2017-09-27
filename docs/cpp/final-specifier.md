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
- final
- final_CPP
dev_langs:
- C++
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
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
ms.openlocfilehash: c9f0a638707466778e75a3eabfe838c84b0355d7
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

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
