---
title: "Структура (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- struct_cpp
dev_langs:
- C++
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
caps.latest.revision: 9
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
ms.openlocfilehash: 4918adb779a620afd4a0c1e4ef64ef9892de1ba8
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="struct-c"></a>struct (C++)
Ключевое слово `struct` указывает тип структуры или переменную типа структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[template-spec] struct[ms-decl-spec] [tag [: base-list ]]  
{   
   member-list   
} [declarators];  
[struct] tag declarators;  
```  
  
#### <a name="parameters"></a>Параметры  
 `template-spec`  
 Необязательные спецификации шаблона. Дополнительные сведения см. в [спецификации шаблона](templates-cpp.md).  
  
 `struct`  
 Ключевое слово `struct`.  
  
 `ms-decl-spec`  
 Необязательная спецификация класса хранения. Дополнительные сведения см. в [__declspec](../cpp/declspec.md) ключевое слово.  
  
 `tag`  
 Имя типа, присваиваемое структуре. Тег становится зарезервированным ключевым словом в области структуры. Тег является необязательным. Если он опущен, определяется анонимная структура. Дополнительные сведения см. в разделе [типы анонимных классов](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Необязательный список классов или структур, из которых эта структура будет наследовать члены. В разделе [базовые классы](../cpp/base-classes.md) для получения дополнительной информации. Каждый базовое имя класса или структуры может предшествовать спецификатор доступа ([открытый](../cpp/public-cpp.md), [закрытый](../cpp/private-cpp.md), [защищенных](../cpp/protected-cpp.md)) и [виртуальный](../cpp/virtual-cpp.md) Ключевое слово. См. в таблице доступа к членам [управление доступом к членам класса](member-access-control-cpp.md) для получения дополнительной информации.  
  
 `member-list`  
 Список членов структуры. Ссылаться на [Общие сведения о членах класса](../cpp/class-member-overview.md) для получения дополнительной информации. Единственное отличие заключается в том, что вместо ключевого слова `struct` используется ключевое слово `class`.  
  
 `declarators`  
 Список деклараторов с указанием имен класса. В списках деклараторов объявляются один или несколько экземпляров типа структуры. Деклараторы могут содержать списки инициализаторов, если все данные-члены класса являются открытыми (`public`). Списки инициализаторов распространены в структурах, поскольку по умолчанию данные-члены открыты (`public`).  В разделе [Обзор деклараторы](../cpp/overview-of-declarators.md) для получения дополнительной информации.  
  
## <a name="remarks"></a>Примечания  
 Тип структуры — это пользовательский составной тип. Он состоит из полей или членов, которые могут иметь разные типы.  
  
 В C++ структура совпадает с классом, за исключением того, что по умолчанию ее члены являются открытыми (`public`).  
  
 Сведения об управляемых классах и структурах см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).  
  
## <a name="using-a-structure"></a>Использование структуры  
 В C для объявления структуры необходимо явно использовать ключевое слово `struct`. В C++ нет необходимости использовать ключевое слово `struct` после определения типа.  
  
 Если тип структуры определен путем размещения одной или нескольких разделенных запятыми имен переменных между закрывающей фигурной скобкой и точкой с запятой, имеется возможность объявления переменных.  
  
 Переменные структуры можно инициализировать. Инициализация каждой переменной должна быть заключена в скобки.  
  
 Дополнительные сведения см. в разделе [класса](../cpp/class-cpp.md), [объединение](../cpp/unions.md), и [перечисления](../cpp/enumerations-cpp.md).  
  
## <a name="example"></a>Пример  
  
```  
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
  

