---
title: Перебор элементов коллекции стандартной библиотеки C++ с использованием цикла for each | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- DTL collections, iterating over
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 92934e3f00bb34e6adfe101b0fea7abbe03600c2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383200"
---
# <a name="iterating-over-c-standard-library-collection-by-using-for-each"></a>Перебор элементов коллекции стандартной библиотеки C++ с использованием цикла for each

`for each` Ключевое слово может использоваться для прохода по коллекции стандартной библиотеки C++.

## <a name="all-platforms"></a>Все платформы

Коллекция стандартной библиотеки C++ также называется *контейнера*. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

## <a name="examples"></a>Примеры

В следующем примере кода используется `for each` для выполнения итерации по [ \<map >](../standard-library/map.md).

```cpp
// for_each_stl.cpp
// compile with: /EHsc
#include <map>
#include <iostream>
#include <string>
using namespace std;

int main() {
   int retval  = 0;
   map<string, int> months;

   months["january"] = 31;
   months["february"] = 28;
   months["march"] = 31;
   months["april"] = 30;
   months["may"] = 31;
   months["june"] = 30;
   months["july"] = 31;
   months["august"] = 31;
   months["september"] = 30;
   months["october"] = 31;
   months["november"] = 30;
   months["december"] = 31;

   map<string, int> months_30;

   for each( pair<string, int> c in months )
      if ( c.second == 30 )
         months_30[c.first] = c.second;

   for each( pair<string, int> c in months_30 )
      retval++;

   cout << "Months with 30 days = " << retval << endl;
}
```

### <a name="output"></a>Вывод

```Output
Months with 30 days = 4
```

## <a name="example"></a>Пример

В следующем примере кода используется ссылка const (`const&`) для переменной итерации с контейнерами стандартной библиотеки C++. Можно использовать ссылку (`&`) как переменная итерации в любой коллекции типа, который может быть объявлено как *T*`&`.

```cpp
// for_each_stl_2.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
using namespace std;

int main() {
   int retval = 0;

   vector<int> col(3);
   col[0] = 10;
   col[1] = 20;
   col[2] = 30;

   for each( const int& c in col )
      retval += c;

   cout << "retval: " << retval << endl;
}
```

### <a name="output"></a>Вывод

```Output
retval: 60
```

## <a name="windows-runtime"></a>Среда выполнения Windows

Отсутствуют платформы комментарии об этой функции.

### <a name="requirements"></a>Требования

Параметр компилятора: **/ZW**

## <a name="common-language-runtime"></a>Среда CLR

Отсутствуют платформы комментарии об этой функции.

### <a name="requirements"></a>Требования

Параметр компилятора: **/clr**

## <a name="see-also"></a>См. также

[for each, in](../dotnet/for-each-in.md)<br/>
[Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)