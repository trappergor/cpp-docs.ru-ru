---
title: Оператор sizeof | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- sizeof_cpp
dev_langs:
- C++
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58724d2e17947c69d1aaf2ed0af66137fe20cc74
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944256"
---
# <a name="sizeof-operator"></a>Оператор sizeof
Возвращает размер своего операнда относительно размера типа **char**.  
  
> [!NOTE]
>  Сведения о `sizeof ...` оператора, см. в разделе [многоточия и шаблоны с переменным числом аргументов](../cpp/ellipses-and-variadic-templates.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
sizeof unary-expression  
sizeof  ( type-name )  
```  
  
## <a name="remarks"></a>Примечания  
 Результат **sizeof** оператор имеет тип `size_t`, целочисленный тип, определенный во включаемом файле \<stddef.h >. Этот оператор позволяет избежать задания зависимых от компьютера размера данных в программах.  
  
 Операнд **sizeof** может принимать одно из следующих:  
  
-   Имя типа. Чтобы использовать **sizeof** с именем типа, имя должно быть заключено в круглые скобки.  
  
-   Выражения. При использовании с помощью выражения, **sizeof** можно указать с или без скобок. Значение выражения не вычисляется.  
  
 Когда **sizeof** оператор применяется к объекту типа **char**, он дает результат 1. Когда **sizeof** оператор применяется к массиву, то результатом является общее число байтов в этом массиве, а не размер указателя, представленного идентификатором массива. Чтобы получить размер указателя, представленного идентификатором массива, передайте его в качестве параметра для функции, которая использует **sizeof**. Пример:  
  
## <a name="example"></a>Пример  
  
```cpp 
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
  
```Output  
The size of a char is: 1  
The length of Hello, world! is: 14  
The size of the pointer is 4  
```  
  
 Когда **sizeof** оператор применяется к **класс**, **структуры**, или **объединение** тип, результат — число байтов в объект, тип, а также любое заполнение, которое добавляется выравнивания членов в границах слова. Результат не обязательно должен соответствовать размеру, вычисляемому путем добавления требований к хранению отдельных членов. [/Zp](../build/reference/zp-struct-member-alignment.md) параметр компилятора и [пакет](../preprocessor/pack.md) pragma влияют на границы выравнивания для членов.  
  
 **Sizeof** оператор никогда не возвращает 0, даже для пустого класса.  
  
 **Sizeof** оператор не может использоваться со следующими операндами:  
  
-   Функции. (Однако **sizeof** можно применять к указателям на функции.)  
  
-   Битовые поля.  
  
-   Неопределенные классы.  
  
-   Тип **void**.  
  
-   Динамически создаваемые массивы.  
  
-   Внешние массивы.  
  
-   Неполные типы.  
  
-   Заключенные в скобки имена неполных типов.  
  
 Когда **sizeof** оператор применяется к ссылке, результат будет такой же так, как если **sizeof** применен к самому объекту.  
  
 Если безразмерный массив является последним элементом структуры, **sizeof** оператор возвращает размер структуры без массива.  
  
 **Sizeof** оператор часто используется для вычисления числа элементов в массиве, с помощью выражения вида:  
  
```cpp 
sizeof array / sizeof array[0]  
```  
  
## <a name="see-also"></a>См. также  
 [Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)