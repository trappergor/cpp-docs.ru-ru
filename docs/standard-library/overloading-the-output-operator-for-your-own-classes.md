---
title: Перегрузка оператора &lt;&lt; для пользовательских классов | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operator<<, overloading for your own classes
- operator <<, overloading for your own classes
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5f5129be6ebf7cac336373f00c7f9e989c23489
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852537"
---
# <a name="overloading-the-ltlt-operator-for-your-own-classes"></a>Перегрузка оператора &lt;&lt; для собственных классов

Потоки ввода используют оператор вставки (`<<`) для стандартных типов. Оператор `<<` для собственных классов можно перегрузить.

## <a name="example"></a>Пример

Пример функции `write` показывает использование структуры `Date`. Даты хорошо подходят для класса C++, в котором члены данных (месяц, день и год) скрыты от просмотра. Поток вывода является логическим местом назначения для отображения такой структуры. Этот код отображает дату с помощью объекта `cout`:

```cpp
Date dt(1, 2, 92);

cout <<dt;
```

Чтобы `cout` принимал объект `Date` после оператора вставки, перегрузите оператор вставки для распознавания объектов `ostream` слева и `Date` справа. Перегруженная функция оператора `<<` затем должна быть объявлена как друг класса `Date`, он может получить доступ к личных данных в пределах `Date` объекта.

```cpp
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

```cpp
cout <<"The date is" <<dt <<flush;
```

## <a name="see-also"></a>См. также

[Потоки вывода](../standard-library/output-streams.md)<br/>
