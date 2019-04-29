---
title: struct (C++)
ms.date: 11/04/2016
f1_keywords:
- struct_cpp
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
ms.openlocfilehash: e9ffd30dd0017e912fd7c196e2d3f0e987fb0810
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330587"
---
# <a name="struct-c"></a>struct (C++)

**Структуры** ключевое слово определяет тип структуры или переменную типа структуры.

## <a name="syntax"></a>Синтаксис

```
[template-spec] struct [ms-decl-spec] [tag [: base-list ]]
{
   member-list
} [declarators];
[struct] tag declarators;
```

#### <a name="parameters"></a>Параметры

*шаблон спецификации*<br/>
Необязательные спецификации шаблона. Дополнительные сведения см. [спецификации шаблона](templates-cpp.md).

*struct*<br/>
**Структуры** ключевое слово.

*ms-decl-spec*<br/>
Необязательная спецификация класса хранения. Дополнительные сведения см. [__declspec](../cpp/declspec.md) ключевое слово.

*Тег*<br/>
Имя типа, присваиваемое структуре. Тег становится зарезервированным ключевым словом в области структуры. Тег является необязательным. Если он опущен, определяется анонимная структура. Дополнительные сведения см. в разделе [типы анонимных классов](../cpp/anonymous-class-types.md).

*базовый список*<br/>
Необязательный список классов или структур, из которых эта структура будет наследовать члены. См. в разделе [базовых классов](../cpp/base-classes.md) Дополнительные сведения. Каждый базовое имя класса или структуры может предшествовать спецификатор доступа ([открытый](../cpp/public-cpp.md), [частного](../cpp/private-cpp.md), [защищенные](../cpp/protected-cpp.md)) и [виртуального](../cpp/virtual-cpp.md) Ключевое слово. См. в таблице доступа к членам в [управление доступом к членам класса](member-access-control-cpp.md) Дополнительные сведения.

*Список членов*<br/>
Список членов структуры. Ссылаться на [Обзор членов класса](../cpp/class-member-overview.md) Дополнительные сведения. Единственное отличие заключается в том, **структуры** используется вместо **класс**.

*деклараторы*<br/>
Список деклараторов с указанием имени структуры. В списках деклараторов объявляются один или несколько экземпляров типа структуры. Деклараторы могут содержать списки инициализаторов, если все данные-члены структуры являются **открытый**. Списки инициализаторов распространены в структурах, так как данные-члены являются **открытый** по умолчанию.  См. в разделе [Обзор из деклараторы](../cpp/overview-of-declarators.md) Дополнительные сведения.

## <a name="remarks"></a>Примечания

Тип структуры — это пользовательский составной тип. Он состоит из полей или членов, которые могут иметь разные типы.

В C++ структура совпадает со значением класса за исключением того, что ее члены являются открытыми **открытый** по умолчанию.

Сведения об управляемых классах и структурах в C++выполняет, см. в разделе [классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="using-a-structure"></a>Использование структуры

В C, необходимо явно использовать **структуры** ключевого слова для объявления структуры. В C++, вам не обязательно должны использовать **структуры** ключевое слово после определения типа.

Если тип структуры определен путем размещения одной или нескольких разделенных запятыми имен переменных между закрывающей фигурной скобкой и точкой с запятой, имеется возможность объявления переменных.

Переменные структуры можно инициализировать. Инициализация каждой переменной должна быть заключена в скобки.

Дополнительные сведения см. в разделе [класс](../cpp/class-cpp.md), [объединение](../cpp/unions.md), и [перечисления](../cpp/enumerations-cpp.md).

## <a name="example"></a>Пример

```cpp
#include <iostream>
using namespace std;

struct PERSON {   // Declare PERSON struct type
    int age;   // Declare member types
    long ss;
    float weight;
    char name[25];
} family_member;   // Define object of type PERSON

struct CELL {   // Declare CELL bit field
    unsigned short character  : 8;  // 00000000 ????????
    unsigned short foreground : 3;  // 00000??? 00000000
    unsigned short intensity  : 1;  // 0000?000 00000000
    unsigned short background : 3;  // 0???0000 00000000
    unsigned short blink      : 1;  // ?0000000 00000000
} screen[25][80];       // Array of bit fields

int main() {
    struct PERSON sister;   // C style structure declaration
    PERSON brother;   // C++ style structure declaration
    sister.age = 13;   // assign values to members
    brother.age = 7;
    cout << "sister.age = " << sister.age << '\n';
    cout << "brother.age = " << brother.age << '\n';

    CELL my_cell;
    my_cell.character = 1;
    cout << "my_cell.character = " << my_cell.character;
}
// Output:
// sister.age = 13
// brother.age = 7
// my_cell.character = 1
```
