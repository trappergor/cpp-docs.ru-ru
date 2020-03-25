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
ms.openlocfilehash: f42a4e2af46ab7690d6f4bc9641c09f3757eb6b6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160558"
---
# <a name="unhandled-c-exceptions"></a>Необработанные исключения C++

Если для текущего исключения не удается найти соответствующий обработчик (или обработчик **catch** с многоточием), то вызывается предопределенная `terminate` функция времени выполнения. (Можно также явно вызвать `terminate` в любом из обработчиков.) Действием `terminate` по умолчанию является вызов `abort`. Если вам необходимо, чтобы перед выходом из приложения функция `terminate` в вашей программе вызывала какую-то другую функцию, вызовите функцию `set_terminate`, указав в качестве ее единственного аргумента ту функцию, которую нужно вызвать. Функцию `set_terminate` можно вызвать из любого места программы. `terminate` подпрограммы всегда вызывает последнюю функцию, заданную в качестве аргумента для `set_terminate`.

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

## <a name="see-also"></a>См. также раздел

[Современные C++ рекомендации по исключениям и обработке ошибок](../cpp/errors-and-exception-handling-modern-cpp.md)
