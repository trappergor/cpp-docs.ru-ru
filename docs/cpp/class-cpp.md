---
title: class (C++)
ms.date: 11/04/2016
f1_keywords:
- class_cpp
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
ms.openlocfilehash: c1b9d8f6510dfe15644f0e47cad7e0aecbac36c9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180980"
---
# <a name="class-c"></a>class (C++)

Ключевое слово **Class** объявляет тип класса или определяет объект типа класса.

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

*Спецификация шаблона*<br/>
Необязательные спецификации шаблона. Дополнительные сведения см. в разделе [шаблоны](templates-cpp.md).

*class*<br/>
Ключевое слово **Class** .

*MS-decl-Spec*<br/>
Необязательная спецификация класса хранения. Дополнительные сведения см. в разделе ключевое слово [__declspec](../cpp/declspec.md) .

*тегами*<br/>
Имя типа, присваиваемое классу. Этот параметр tag становится зарезервированным ключевым словом в области класса. Тег является необязательным. Если он опущен, определяется анонимный класс. Дополнительные сведения см. в разделе [типы анонимных классов](../cpp/anonymous-class-types.md).

*base-list*<br/>
Необязательный список классов или структур, от которых этот класс будет наследовать члены. Дополнительные сведения см. в разделе [базовые классы](../cpp/base-classes.md) . Каждому базовому классу или имени структуры может предшествовать спецификатор доступа ([открытый](../cpp/public-cpp.md), [частный](../cpp/private-cpp.md), [защищенный](../cpp/protected-cpp.md)) и ключевое слово [Virtual](../cpp/virtual-cpp.md) . Дополнительные сведения см. в таблице доступ к элементам в разделе [Управление доступом к членам класса](member-access-control-cpp.md) .

*Список участников*<br/>
Список членов класса. Дополнительные сведения см. в разделе [Обзор членов класса](../cpp/class-member-overview.md) .

*declarators*<br/>
Список деклараторов, в котором указываются имена одного или нескольких экземпляров типа класса. Деклараторы могут включать списки инициализаторов, если все элементы данных класса являются **открытыми**. Это более распространено в структурах, члены данных которых по умолчанию являются **открытыми** , чем в классах. Дополнительные сведения см. в разделе [Общие сведения об деклараторах](../cpp/overview-of-declarators.md) .

## <a name="remarks"></a>Remarks

Дополнительные сведения о классах в целом см. в следующих разделах:

- [struct](../cpp/struct-cpp.md)

- [union](../cpp/unions.md)

- [__multiple_inheritance](../cpp/inheritance-keywords.md)

- [__single_inheritance](../cpp/inheritance-keywords.md)

- [__virtual_inheritance](../cpp/inheritance-keywords.md)

Сведения об управляемых классах и структурах в C++/CLI и C++/CX см. в разделе [классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md) .

## <a name="example"></a>Пример

```cpp
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

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Классы и структуры](../cpp/classes-and-structs-cpp.md)
