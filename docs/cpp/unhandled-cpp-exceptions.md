---
title: Необработанные исключения C++
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], unhandled exceptions
- catch keyword [C++], handler not found
- exceptions [C++], unhandled
- C++ exception handling, unhandled exceptions
- unhandled exceptions [C++]
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
ms.openlocfilehash: 48b417c48a3cbb903f3fabaf31b1423e79a1a414
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233591"
---
# <a name="unhandled-c-exceptions"></a>Необработанные исключения C++

Если **`catch`** для текущего исключения не удается найти соответствующий обработчик (или обработчик многоточия), вызывается предопределенная `terminate` функция времени выполнения. (Вы также можете явно вызвать `terminate` в любом обработчике.) Действие по умолчанию `terminate` — вызвать `abort` . Если вам необходимо, чтобы перед выходом из приложения функция `terminate` в вашей программе вызывала какую-то другую функцию, вызовите функцию `set_terminate`, указав в качестве ее единственного аргумента ту функцию, которую нужно вызвать. Функцию `set_terminate` можно вызвать из любого места программы. `terminate`Подпрограммы всегда вызывают последнюю функцию, заданную в качестве аргумента для `set_terminate` .

## <a name="example"></a>Пример

В следующем примере создается исключение типа `char *`, однако в нем нет обработчика, предназначенного для перехвата исключений `char *`. Вызов `set_terminate` содержит инструкцию, согласно которой `terminate` вызывает функцию `term_func`.

```cpp
// exceptions_Unhandled_Exceptions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
void term_func() {
   cout << "term_func was called by terminate." << endl;
   exit( -1 );
}
int main() {
   try
   {
      set_terminate( term_func );
      throw "Out of memory!"; // No catch handler for this exception
   }
   catch( int )
   {
      cout << "Integer exception raised." << endl;
   }
   return 0;
}
```

## <a name="output"></a>Выходные данные

```Output
term_func was called by terminate.
```

Функция `term_func` должна завершать программу или текущий поток (желательно путем вызова функции `exit`). Если вместо этого она возвращает управление вызвавшему объекту, то вызывается функция `abort`.

## <a name="see-also"></a>См. также статью

[Современные рекомендации по C++ для исключений и обработки ошибок](../cpp/errors-and-exception-handling-modern-cpp.md)
