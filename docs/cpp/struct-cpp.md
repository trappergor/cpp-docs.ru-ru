---
title: "struct (C++) | Microsoft Docs"
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
  - "struct"
  - "struct_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "конструкторы структур"
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# struct (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключевое слово `struct` указывает тип структуры или переменную типа структуры.  
  
## Синтаксис  
  
```  
[template-spec] struct [ms-decl-spec] [tag [: base-list ]]  
{   
   member-list   
} [declarators];  
[struct] tag declarators;  
```  
  
#### Параметры  
 `template-spec`  
 Необязательные спецификации шаблона.  Дополнительные сведения см. в разделе [Спецификации шаблонов](../Topic/Template%20Specifications.md).  
  
 `struct`  
 Ключевое слово `struct`.  
  
 `ms-decl-spec`  
 Необязательная спецификация класса хранения.  Дополнительные сведения см. в разделе с описанием ключевого слова [\_\_declspec](../cpp/declspec.md).  
  
 `tag`  
 Имя типа, присваиваемое структуре.  Тег становится зарезервированным ключевым словом в области структуры.  Тег является необязательным.  Если он опущен, определяется анонимная структура.  Дополнительные сведения см. в разделе [Типы анонимных классов](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Необязательный список классов или структур, из которых эта структура будет наследовать члены.  Дополнительные сведения см. в разделе [Базовые классы](../cpp/base-classes.md).  Каждому имени базового класса или структуры может предшествовать спецификатор доступа \([public](../cpp/public-cpp.md), [private](../Topic/private%20\(C++\).md), [protected](../Topic/protected%20\(C++\).md)\) и ключевое слово [virtual](../cpp/virtual-cpp.md).  Дополнительные сведения см. в таблице членского доступа в разделе [Управление доступом к членам класса](../misc/controlling-access-to-class-members.md).  
  
 `member-list`  
 Список членов структуры.  Дополнительные сведения см. в разделе [Обзор членов класса](../Topic/Class%20Member%20Overview.md).  Единственное отличие заключается в том, что вместо ключевого слова `class` используется ключевое слово `struct`.  
  
 `declarators`  
 Список деклараторов с указанием имен класса.  В списках деклараторов объявляются один или несколько экземпляров типа структуры.  Деклараторы могут содержать списки инициализаторов, если все данные\-члены класса являются открытыми \(`public`\).  Списки инициализаторов распространены в структурах, поскольку по умолчанию данные\-члены открыты \(`public`\).  Дополнительные сведения см. в разделе [Общие сведения о деклараторах](../cpp/overview-of-declarators.md).  
  
## Заметки  
 Тип структуры — это пользовательский составной тип.  Он состоит из полей или членов, которые могут иметь разные типы.  
  
 В C\+\+ структура совпадает с классом, за исключением того, что по умолчанию ее члены являются открытыми \(`public`\).  
  
 Сведения об управляемых классах и структурах см. в разделе [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).  
  
## Использование структуры  
 В C для объявления структуры необходимо явно использовать ключевое слово `struct`.  В C\+\+ нет необходимости использовать ключевое слово `struct` после определения типа.  
  
 Если тип структуры определен путем размещения одной или нескольких разделенных запятыми имен переменных между закрывающей фигурной скобкой и точкой с запятой, имеется возможность объявления переменных.  
  
 Переменные структуры можно инициализировать.  Инициализация каждой переменной должна быть заключена в скобки.  
  
 Дополнительные сведения см. в разделах [class](../cpp/class-cpp.md), [union](../cpp/unions.md) и [enum](../cpp/enumerations-cpp.md).  
  
## Пример  
  
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
  
## См. также  
 [Определение типов классов](http://msdn.microsoft.com/ru-ru/e8c65425-0f3a-4dca-afc2-418c3b1e57da)