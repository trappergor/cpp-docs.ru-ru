---
title: "Перегрузка оператора &lt;&lt; для пользовательских классов | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operator<<, overloading for your own classes
- operator <<, overloading for your own classes
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
caps.latest.revision: 12
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 22eb3fbef373c2e80989c49887cfa8b3c9eadc61
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="overloading-the-ltlt-operator-for-your-own-classes"></a>Перегрузка оператора &lt;&lt; для собственных классов
Потоки ввода используют оператор вставки (`<<`) для стандартных типов. Оператор `<<` для собственных классов можно перегрузить.  
  
## <a name="example"></a>Пример  
 Пример функции `write` показывает использование структуры `Date`. Даты хорошо подходят для класса C++, в котором члены данных (месяц, день и год) скрыты от просмотра. Поток вывода является логическим местом назначения для отображения такой структуры. Этот код отображает дату с помощью объекта `cout`:  
  
```  
Date dt(1, 2, 92);

cout <<dt;  
```  
  
 Чтобы `cout` принимал объект `Date` после оператора вставки, перегрузите оператор вставки для распознавания объектов `ostream` слева и `Date` справа. Перегруженная функция оператора `<<` затем должна быть объявлена как друг класса `Date`, он может получить доступ к личных данных в пределах `Date` объекта.  
  
```  
// overload_date.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
class Date  
{  
    int mo, da, yr;  
public:  
    Date(int m, int d, int y)  
    {  
        mo = m; da = d; yr = y;  
    }  
    friend ostream& operator<<(ostream& os, const Date& dt);  
};  
  
ostream& operator<<(ostream& os, const Date& dt)  
{  
    os << dt.mo << '/' << dt.da << '/' << dt.yr;  
    return os;  
}  
  
int main()  
{  
    Date dt(5, 6, 92);  
    cout << dt;  
}  
```  
  
```Output  
5/6/92  
```  
  
## <a name="remarks"></a>Примечания  
 Перегруженный оператор возвращает ссылку на исходный объект `ostream`, то есть вставки можно объединить:  
  
```  
cout <<"The date is" <<dt <<flush;  
```  
  
## <a name="see-also"></a>См. также  
 [Потоки вывода](../standard-library/output-streams.md)


