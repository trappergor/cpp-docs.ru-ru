---
title: "class (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "class_cpp"
  - "class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class - ключевое слово [C++]"
  - "типы классов, операторы class"
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# class (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключевое слово `class` объявляет тип класса или определяет объект типа класса.  
  
## Синтаксис  
  
```  
  
      [template-spec]  
       class [ms-decl-spec] [tag [: base-list ]]  
{  
   member-list  
} [declarators];  
[ class ] tag declarators;  
```  
  
#### Параметры  
 `template-spec`  
 Необязательные спецификации шаблона.  Дополнительные сведения см. в разделе [Спецификации шаблонов](../Topic/Template%20Specifications.md).  
  
 `class`  
 Ключевое слово `class`.  
  
 `ms-decl-spec`  
 Необязательная спецификация класса хранения.  Дополнительные сведения см. в разделе с описанием ключевого слова [\_\_declspec](../cpp/declspec.md).  
  
 `tag`  
 Имя типа, присваиваемое классу.  Этот параметр tag становится зарезервированным ключевым словом в области класса.  Тег является необязательным.  Если он опущен, определяется анонимный класс.  Дополнительные сведения см. в разделе [Типы анонимных классов](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Необязательный список классов или структур, от которых этот класс будет наследовать члены.  Дополнительные сведения см. в разделе [Базовые классы](../cpp/base-classes.md).  Каждому имени базового класса или структуры может предшествовать спецификатор доступа \([public](../cpp/public-cpp.md), [private](../Topic/private%20\(C++\).md), [protected](../Topic/protected%20\(C++\).md)\) и ключевое слово [virtual](../cpp/virtual-cpp.md).  Дополнительные сведения см. в таблице членского доступа в разделе [Управление доступом к членам класса](../misc/controlling-access-to-class-members.md).  
  
 `member-list`  
 Список членов класса.  Дополнительные сведения см. в разделе [Обзор членов класса](../Topic/Class%20Member%20Overview.md).  
  
 `declarators`  
 Список деклараторов, в котором указываются имена одного или нескольких экземпляров типа класса.  Деклараторы могут содержать списки инициализаторов, если все данные\-члены класса являются открытыми \(`public`\).  Это чаще используется не в классах, а в структурах, чьи данные\-члены имеют видимость по умолчанию `public`.  Дополнительные сведения см. в разделе [Общие сведения о деклараторах](../cpp/overview-of-declarators.md).  
  
## Заметки  
 Дополнительные сведения о классах в целом см. в следующих разделах:  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [union](../cpp/unions.md)  
  
-   [\_\_multiple\_inheritance](../cpp/inheritance-keywords.md)  
  
-   [\_\_single\_inheritance](../cpp/inheritance-keywords.md)  
  
-   [\_\_virtual\_inheritance](../cpp/inheritance-keywords.md)  
  
 Сведения об управляемых классах и структурах см. в разделе [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).  
  
## Пример  
  
```  
// class.cpp  
// compile with: /EHsc  
// Example of the class keyword  
// Exhibits polymorphism/virtual functions.  
  
#include <iostream>  
#include <string>  
#define TRUE = 1  
using namespace std;  
  
class dog  
{  
public:  
   dog()  
   {  
      _legs = 4;  
      _bark = true;  
   }  
  
   void setDogSize(string dogSize)  
   {  
      _dogSize = dogSize;  
   }  
   virtual void setEars(string type)      // virtual function  
   {  
      _earType = type;  
   }  
  
private:  
   string _dogSize, _earType;  
   int _legs;  
   bool _bark;  
  
};  
  
class breed : public dog  
{  
public:  
   breed( string color, string size)  
   {  
      _color = color;  
      setDogSize(size);  
   }  
  
   string getColor()  
   {  
      return _color;  
   }  
  
   // virtual function redefined  
   void setEars(string length, string type)  
   {  
      _earLength = length;  
      _earType = type;  
   }  
  
protected:  
   string _color, _earLength, _earType;  
};  
  
int main()  
{  
   dog mongrel;  
   breed labrador("yellow", "large");  
   mongrel.setEars("pointy");  
   labrador.setEars("long", "floppy");  
   cout << "Cody is a " << labrador.getColor() << " labrador" << endl;  
}  
```  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Классы и структуры](../Topic/Classes%20and%20Structs%20\(C++\).md)