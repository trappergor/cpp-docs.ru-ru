---
title: "Ссылки (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], referencing
- references [C++]
- references, to pointers
- declarations, references
- references, declaring
- referencing objects, declarator syntax
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
caps.latest.revision: 12
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
ms.openlocfilehash: fb208f61d2da9e7daa7a53ac68fdcdfcdf1acab4
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="references-c"></a>Ссылки (C++)
В ссылке, как и в указателе, хранится адрес объекта, расположенного в другой области памяти. В отличие от указателя, после инициализации ссылку нельзя перенаправить на другой объект или присвоить ей нулевое значение. Существует два типа ссылок: ссылки lvalue, указывающие именованный переменной и ссылки rvalue, указывающие [временный объект](../cpp/temporary-objects.md). Оператором & обозначаются ссылки lvalue, а оператором &&, в зависимости от контекста, — ссылки rvalue или универсальные ссылки (как rvalue, так и lvalue).  
  
 Ссылки могут объявляться с помощью следующего синтаксиса.  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator [= expression];  
```  
  
 Можно использовать любой допустимый декларатор, задающий ссылку. Следующий упрощенный синтаксис применяется всегда, кроме случаев, когда ссылка является ссылкой на функцию или тип массива.  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [& or &&]   
[cv-qualifiers] identifier [= expression];  
```  
  
 Ссылки объявляются с использованием следующей последовательности.  
  
 1. Спецификаторы объявления:  
  
-   Необязательный спецификатор класса хранения.  
  
-   Необязательный **const** и/или `volatile` квалификаторы.  
  
-   Спецификатор типа: имя типа.  
  
-   2. Декларатор:  
  
-   Необязательный модификатор, используемый в системах Microsoft. Дополнительные сведения см. в разделе [модификаторы, используемые Microsoft](../cpp/microsoft-specific-modifiers.md).  
  
-   Оператор & или &&.  
  
-   Необязательный **const** и/или `volatile` квалификаторы.  
  
-   Идентификатор.  
  
 3. Необязательный инициализатор.  
  
 Более сложные формы декларатора указатели на массивы и функции также применяются к ссылкам на массивы и функции, см. в разделе [указатели](../cpp/pointers-cpp.md) и [деклараторы](http://msdn.microsoft.com/en-us/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).  
  
 Несколько деклараторов и инициализаторов могут отображаться в разделенном запятыми списке после отдельного спецификатора объявления. Пример:  
  
```  
int &i;   
int &i, &j;   
```  
  
 Ссылки, указатели и объекты могут быть объявлены вместе.  
  
```  
int &ref, *ptr, k;   
```  
  
 Ссылка содержит адрес объекта, однако с синтаксической точки зрения ведет себя как объект.  
  
 В следующей программе обратите внимание, что имя объекта, `Today` и ссылка на объект, `TodayRef`, могут использоваться идентично в следующих программах.  
  
## <a name="example"></a>Пример  
  
```  
// references.cpp  
#include <stdio.h>  
struct S {  
   short i;  
};  
  
int main() {  
   S  s;   // Declare the object.  
   S& SRef = s;   // Declare the reference.  
   s.i = 3;  
  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
  
   SRef.i = 4;  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
}  
```  
  
```Output  
3  
3  
4  
4  
```  
  
## <a name="comment"></a>Комментарий  
 Подразделы в этом разделе:  
  
-   [Аргументы функции ссылочного типа](../cpp/reference-type-function-arguments.md)  
  
-   [Возвращаемые значения функции ссылочного типа](../cpp/reference-type-function-returns.md)  
  
-   [Ссылки на указатели](../cpp/references-to-pointers.md)  
  

