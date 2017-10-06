---
title: "Возвращаемые значения функции ссылочного типа | Документы Microsoft"
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
- function return types [C++], reference type
- data types [C++], function return types
- functions [C++], return types
ms.assetid: 5b73be1d-2dc7-41df-ab0a-adcba36f2ad1
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
ms.openlocfilehash: 1cadf01b1af0bac4fb76d0146a51b789b5ddc6e5
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="reference-type-function-returns"></a>Возвращаемые значения функции ссылочного типа
Функции можно объявить, чтобы они возвращали ссылочный тип. Существует две причины создания такого объявления.  
  
-   Возвращаемая информация представляет собой настолько крупный объект, что возврат ссылки является более эффективным, чем возврат копии.  
  
-   Тип функции должен представлять собой l-значение.  
  
-   Объект, на который указывает ссылка, не выйдет из области видимости при возврате управления функцией.  
  
 Точно так же, как можно более эффективно передавать крупные объекты *для* функции по ссылке, она может быть более эффективным, возвращать крупные объекты *из* функции по ссылке. Протокол возврата ссылок устраняет необходимость копировать объект во временное хранилище перед возвратом.  
  
 Типы возврата ссылок также могут оказаться полезными, если результатом функции должно быть l-значение. Большинство перегруженных операторов относятся к этой категории, в частности оператор присваивания. Перегруженные операторы описаны в [перегруженные операторы](../cpp/operator-overloading.md).  
  
## <a name="example"></a>Пример  
 Рассмотрим пример `Point`.  
  
```  
// refType_function_returns.cpp  
// compile with: /EHsc  
  
#include <iostream>  
using namespace std;  
  
class Point  
{  
public:  
// Define "accessor" functions as  
//  reference types.  
unsigned& x();  
unsigned& y();  
private:  
// Note that these are declared at class scope:  
unsigned obj_x;   
unsigned obj_y;   
};  
  
unsigned& Point :: x()  
{  
return obj_x;  
}  
unsigned& Point :: y()  
{  
return obj_y;  
}  
  
int main()  
{  
Point ThePoint;  
// Use x() and y() as l-values.  
ThePoint.x() = 7;  
ThePoint.y() = 9;  
  
// Use x() and y() as r-values.  
cout << "x = " << ThePoint.x() << "\n"  
<< "y = " << ThePoint.y() << "\n";  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
x = 7  
y = 9  
```  
  
 Обратите внимание, что функции `x` и `y` объявляются как типы возвращаемых ссылок. Эти функции можно использовать на любой стороне оператора присваивания.  
  
 Также обратите внимание, что в функции main объект ThePoint остается в области видимости, поэтому его ссылочные элементы продолжают действовать, и к ним можно получить безопасный доступ.  
  
 Объявления ссылочных типов должны содержать инициализаторы. Исключение составляют следующие случаи.  
  
-   Явное объявление `extern`  
  
-   Объявление члена класса  
  
-   Объявление в классе  
  
-   Объявление аргумента в адрес функции или возвращаемого типа для функции  
  
## <a name="caution-returning-address-of-local"></a>Предупреждение при возвращении адреса локальной переменной  
 Если объект объявляется в локальной области видимости, он будет уничтожен, когда функция вернет ссылку. Возвращенная этому объекту ссылка может нарушить доступ в среде выполнения, поскольку вызывающий объект попытается использовать пустую ссылку.  
  
```  
// C4172 means Don’t do this!!!  
Foo& GetFoo()  
{  
    Foo f;  
    ...  
    return f;  
} // f is destroyed here  
```  
  
 Компилятор выдает предупреждение, в данном случае: `warning C4172: returning address of local variable or temporary`. В простых программах доступ может случайно сохраниться, если ссылка будет использована вызывающим объектом до перезаписи соответствующей области памяти. Однако это чистая случайность. Обратите внимание на предупреждение.  
  
## <a name="see-also"></a>См. также  
 [Ссылки](../cpp/references-cpp.md)
