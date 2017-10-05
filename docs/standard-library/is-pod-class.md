---
title: "Класс is_pod | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_pod
dev_langs:
- C++
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: efe54ef10c8ab8102e17efdbf8e38f217ec2e0df
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="ispod-class"></a>Класс is_pod
Проверяет, является ли тип типом POD.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>
struct is_pod;
```  
  
#### <a name="parameters"></a>Параметры  
*T*  
Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
`is_pod<T>::value` — это `true`, если тип *T* — POD. В противном случае — `false`.  
  
К типам POD относятся арифметические типы, типы перечисления, типы указателей и указатели на типы-члены.  
  
Квалифицированная версия типа POD также обладает типом POD.  
  
Массив данных типа POD также имеет тип POD.  
  
Структура или объединение, все нестатические данные-члены которого имеют типа POD, также обладает типом POD при соблюдении следующих условий:  
  
-   Нет объявленных пользователем конструкторов.  
  
-   Нет закрытых или защищенных нестатических данных-членов.  
  
-   Отсутствие базовых классов.  
  
-   Нет виртуальных функций.  
  
-   Нет нестатических данных-членов ссылочного типа.  
  
-   Нет определяемого пользователем оператора присвоения копирования.  
  
-   Нет определяемого пользователем деструктора.  
  
Таким образом, можно рекурсивно создавать структуры POD и массивы, содержащие структуры и массивы POD.  
  
## <a name="example"></a>Пример  
  
```cpp  
// std__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial {   
    int val;   
};   
  
struct throws {   
    throws() {}  // User-declared ctor, so not POD
  
    int val;   
};   
  
int main() {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
is_pod<trivial> == true  
is_pod<int> == true  
is_pod<throws> == false  
```  
  
## <a name="requirements"></a>Требования  
**Заголовок:** \<type_traits>  
  
**Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
[<type_traits>](../standard-library/type-traits.md)




