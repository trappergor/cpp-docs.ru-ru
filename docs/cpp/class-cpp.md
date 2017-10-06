---
title: "класс (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- class_cpp
dev_langs:
- C++
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
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
ms.openlocfilehash: 7cdd7b7cefcd9f3826cfe426008bdf1eefde82f6
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="class-c"></a>class (C++)
Ключевое слово `class` объявляет тип класса или определяет объект типа класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [template-spec]  
       class [ms-decl-spec] [tag [: base-list ]]  
{  
   member-list  
} [declarators];  
[ class ] tag declarators;  
```  
  
#### <a name="parameters"></a>Параметры  
 `template-spec`  
 Необязательные спецификации шаблона. Дополнительные сведения см. в [шаблоны](templates-cpp.md).  
  
 `class`  
 Ключевое слово `class`.  
  
 `ms-decl-spec`  
 Необязательная спецификация класса хранения. Дополнительные сведения см. в [__declspec](../cpp/declspec.md) ключевое слово.  
  
 `tag`  
 Имя типа, присваиваемое классу. Этот параметр tag становится зарезервированным ключевым словом в области класса. Тег является необязательным. Если он опущен, определяется анонимный класс. Дополнительные сведения см. в разделе [типы анонимных классов](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Необязательный список классов или структур, от которых этот класс будет наследовать члены. В разделе [базовые классы](../cpp/base-classes.md) для получения дополнительной информации. Каждый базовое имя класса или структуры может предшествовать спецификатор доступа ([открытый](../cpp/public-cpp.md), [закрытый](../cpp/private-cpp.md), [защищенных](../cpp/protected-cpp.md)) и [виртуальный](../cpp/virtual-cpp.md) Ключевое слово. См. в таблице доступа к членам [управление доступом к членам класса](member-access-control-cpp.md) для получения дополнительной информации.  
  
 `member-list`  
 Список членов класса. Ссылаться на [Общие сведения о членах класса](../cpp/class-member-overview.md) для получения дополнительной информации.  
  
 `declarators`  
 Список деклараторов, в котором указываются имена одного или нескольких экземпляров типа класса. Деклараторы могут содержать списки инициализаторов, если все данные-члены класса являются открытыми (`public`). Это чаще используется не в классах, а в структурах, чьи данные-члены имеют видимость по умолчанию `public`. В разделе [Обзор деклараторы](../cpp/overview-of-declarators.md) для получения дополнительной информации.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о классах в целом см. в следующих разделах:  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [объединение](../cpp/unions.md)  
  
-   [__multiple_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__single_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__virtual_inheritance](../cpp/inheritance-keywords.md)  
  
 Сведения об управляемых классах и структурах см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Классы и структуры](../cpp/classes-and-structs-cpp.md)
