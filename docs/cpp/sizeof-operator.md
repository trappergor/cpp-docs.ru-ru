---
title: "Оператор sizeof | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: sizeof_cpp
dev_langs: C++
helpviewer_keywords: sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f6cb6e9755b1a9a02c87fa713a9774945856b461
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="sizeof-operator"></a>Оператор sizeof
Возвращает размер своего операнда относительно размера типа `char`.  
  
> [!NOTE]
>  Сведения о `sizeof ...` оператор, в разделе [многоточия и шаблоны с переменным числом аргументов](../cpp/ellipses-and-variadic-templates.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
sizeof unary-expression  
sizeof  ( type-name )  
```  
  
## <a name="remarks"></a>Примечания  
 Результат оператора `sizeof` имеет тип `size_t`, целочисленный тип, определенный во включаемом файле STDDEF.H. Этот оператор позволяет избежать задания зависимых от компьютера размера данных в программах.  
  
 Оператор `sizeof` может иметь один из следующих операндов.  
  
-   Имя типа. Если оператор `sizeof` используется с именем типа, оно должно быть заключено в скобки.  
  
-   Выражения. Если оператор `sizeof` используется с выражением, его можно определять как со скобками, так и без них. Значение выражения не вычисляется.  
  
 Если оператор `sizeof` применяется к объекту типа `char`, он дает результат 1. Если оператор `sizeof` применяется к массиву, то результатом является не размер указателя, представленного идентификатором массива, а общее количество байтов в этом массиве. Чтобы получить размер указателя, представленного идентификатором массива, передайте его в качестве параметра в функцию, в которой используется оператор `sizeof`. Пример:  
  
## <a name="example"></a>Пример  
  
```  
#include <iostream>  
using namespace std;  
  
size_t getPtrSize( char *ptr )  
{  
   return sizeof( ptr );  
}  
  
int main()  
{  
   char szHello[] = "Hello, world!";  
  
   cout  << "The size of a char is: "  
         << sizeof( char )  
         << "\nThe length of " << szHello << " is: "  
         << sizeof szHello  
         << "\nThe size of the pointer is "  
         << getPtrSize( szHello ) << endl;  
}  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
The size of a char is: 1  
The length of Hello, world! is: 14  
The size of the pointer is 4  
```  
  
 Если оператор `sizeof` применяется к объекту типа `class`, `struct` или `union`, то результатом будет число байт в объекте этого типа, плюс любое заполнение, которое добавляется для выравнивания членов в границах слова. Результат не обязательно должен соответствовать размеру, вычисляемому путем добавления требований к хранению отдельных членов. [/Zp](../build/reference/zp-struct-member-alignment.md) параметр компилятора и [пакет](../preprocessor/pack.md) pragma влияют на границы выравнивания для членов.  
  
 Оператор `sizeof` никогда не создает результат 0, даже для пустого класса.  
  
 Оператор `sizeof` не может использоваться со следующими операндами.  
  
-   Функции. (Однако оператор `sizeof` можно применять к указателям на функции.)  
  
-   Битовые поля.  
  
-   Неопределенные классы.  
  
-   Тип `void`.  
  
-   Динамически создаваемые массивы.  
  
-   Внешние массивы.  
  
-   Неполные типы.  
  
-   Заключенные в скобки имена неполных типов.  
  
 Если оператор `sizeof` применяется к ссылке, он создает такой же результат, как если бы `sizeof` был применен к самому объекту.  
  
 Если безразмерный массив является последним элементом структуры, оператор `sizeof` возвращает размер структуры без массива.  
  
 Оператор `sizeof` часто используется для вычисления количества элементов в массиве с помощью выражения следующего вида.  
  
```  
sizeof array / sizeof array[0]  
```  
  
## <a name="see-also"></a>См. также  
 [Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)