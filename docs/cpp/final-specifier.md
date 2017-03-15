---
title: "Спецификатор final | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "final"
  - "final_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "final - идентификатор"
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Спецификатор final
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключевое слово `final` можно использовать для назначения виртуальных функций, которые невозможно переопределить в производном классе.  Можно также использовать это ключевое слово для назначения классов, которые невозможно наследовать.  
  
## Синтаксис  
  
```  
  
function-declaration final;  
```  
  
```  
  
class class-name final base-classes  
```  
  
## Заметки  
 Ключевое слово `final` зависит от контекста и имеет специальное значение, только если используется после объявления функции или имени класса; в противном случае оно не является зарезервированным ключевым словом.  
  
 Если `final` используется в объявлениях класса, `base-classes` является необязательной частью объявления.  
  
## Пример  
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
  
 Дополнительные сведения о том, как указать, что функции\-члены можно переопределить, см. в разделе [Спецификатор override](../cpp/override-specifier.md).  
  
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
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) C\+\+ Type Names](http://msdn.microsoft.com/ru-ru/b53ba470-e583-4e5c-b634-6018f6110674)   
 [Спецификатор override](../cpp/override-specifier.md)