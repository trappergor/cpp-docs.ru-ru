---
title: класс (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- class_cpp
dev_langs:
- CPP
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e5807b529ca56613cfe0021762a0191e4038df0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118743"
---
# <a name="class-c"></a>class (C++)

**Класс** ключевое слово объявляет тип класса или определяет объект типа класса.

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

*шаблон спецификации*<br/>
Необязательные спецификации шаблона. Дополнительные сведения см. [шаблоны](templates-cpp.md).

*class*<br/>
**Класс** ключевое слово.

*MS-decl-spec*<br/>
Необязательная спецификация класса хранения. Дополнительные сведения см. [__declspec](../cpp/declspec.md) ключевое слово.

*Тег*<br/>
Имя типа, присваиваемое классу. Этот параметр tag становится зарезервированным ключевым словом в области класса. Тег является необязательным. Если он опущен, определяется анонимный класс. Дополнительные сведения см. в разделе [типы анонимных классов](../cpp/anonymous-class-types.md).

*базовый список*<br/>
Необязательный список классов или структур, от которых этот класс будет наследовать члены. См. в разделе [базовых классов](../cpp/base-classes.md) Дополнительные сведения. Каждый базовое имя класса или структуры может предшествовать спецификатор доступа ([открытый](../cpp/public-cpp.md), [частного](../cpp/private-cpp.md), [защищенные](../cpp/protected-cpp.md)) и [виртуального](../cpp/virtual-cpp.md) Ключевое слово. См. в таблице доступа к членам в [управление доступом к членам класса](member-access-control-cpp.md) Дополнительные сведения.

*Список членов*<br/>
Список членов класса. Ссылаться на [Обзор членов класса](../cpp/class-member-overview.md) Дополнительные сведения.

*деклараторы*<br/>
Список деклараторов, в котором указываются имена одного или нескольких экземпляров типа класса. Деклараторы могут содержать списки инициализаторов, если все данные-члены класса являются **открытый**. Это более типично в структурах, чьи данные-члены являются **открытый** по умолчанию, чем в классы. См. в разделе [Обзор из деклараторы](../cpp/overview-of-declarators.md) Дополнительные сведения.

## <a name="remarks"></a>Примечания

Дополнительные сведения о классах в целом см. в следующих разделах:

- [struct](../cpp/struct-cpp.md)

- [объединение](../cpp/unions.md)

- [__multiple_inheritance](../cpp/inheritance-keywords.md)

- [__single_inheritance](../cpp/inheritance-keywords.md)

- [__virtual_inheritance](../cpp/inheritance-keywords.md)

Сведения об управляемых классах и структурах см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)

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

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Классы и структуры](../cpp/classes-and-structs-cpp.md)