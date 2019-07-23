---
title: Эффекты буферизации
ms.date: 11/04/2016
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
ms.openlocfilehash: 23e241794455a92f9e3628a786d75a6d4c7b037e
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376315"
---
# <a name="effects-of-buffering"></a>Эффекты буферизации

В следующем примере демонстрируются эффекты буферизации. Вы могли ожидать, что программа выведет `please wait`, подождет 5 секунд и затем продолжит выполнение. Однако такое поведение необязательно, так как выходные данные помещаются в буфер.

```cpp
// effects_buffering.cpp
// compile with: /EHsc
#include <iostream>
#include <time.h>
using namespace std;

int main( )
{
   time_t tm = time( NULL ) + 5;
   cout << "Please wait...";
   while ( time( NULL ) < tm )
      ;
   cout << "\nAll done" << endl;
}
```

Чтобы программа работала логично, объект `cout` должен опустошать себя перед выводом сообщения. Чтобы сохранить объект `ostream` , отправьте ему манипулятор `flush` :

```cpp
cout <<"Please wait..." <<flush;
```

Это действие сохраняет буфер, гарантируя вывод сообщения до ожидания. Можно также использовать `endl` манипулятор, который очищает буфер и выводит символ перевода строки возврата каретки или можно `cin` использовать объект. Этот объект (с объектами `cerr` или `clog` ) обычно привязывается к объекту `cout` . Таким образом, любое использование `cin` (или объектов `cerr` или `clog` ) сохраняет объект `cout` .

## <a name="see-also"></a>См. также

[Потоки вывода](../standard-library/output-streams.md)<br/>
