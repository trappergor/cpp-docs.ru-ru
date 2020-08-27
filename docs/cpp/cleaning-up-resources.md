---
title: Освобождение ресурсов
description: Как освободить ресурсы во время обработчика завершения для структурированной обработки исключений.
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
ms.openlocfilehash: dae92a515db25b9985a890d7d08cc213f88ecfea
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898432"
---
# <a name="cleaning-up-resources"></a>Освобождение ресурсов

Во время выполнения обработчика завершения может быть неизвестно, какие ресурсы были получены до вызова обработчика завершения. Возможно, **`__try`** блок инструкций был прерван до получения всех ресурсов, так что не все ресурсы были открыты.

Чтобы быть в безопасности, перед продолжением очистки для обработки завершения следует проверить, какие ресурсы открыты. Ниже описана рекомендованная процедура.

1. Инициализируйте дескрипторы со значением null.

1. В **`__try`** блоке инструкций получите ресурсы. Для дескрипторов задаются положительные значения при получении ресурса.

1. В **`__finally`** блоке инструкций выпустите каждый ресурс, соответствующий маркер или переменная флага которого не равны нулю или не имеют значение null.

## <a name="example"></a>Пример

Например, в следующем коде обработчик завершения используется для закрытия трех файлов и освобождения блока памяти. Эти ресурсы были получены в **`__try`** блоке инструкций. Перед очисткой ресурса код сначала проверяет, был ли получен ресурс.

```cpp
// exceptions_Cleaning_up_Resources.cpp
#include <stdlib.h>
#include <malloc.h>
#include <stdio.h>
#include <windows.h>

void fileOps() {
   FILE  *fp1 = NULL,
         *fp2 = NULL,
         *fp3 = NULL;
   LPVOID lpvoid = NULL;
   errno_t err;

   __try {
      lpvoid = malloc( BUFSIZ );

      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );
      err = fopen_s(&fp3, "CARS.DAT", "w+" );
   }
   __finally {
      if ( fp1 )
         fclose( fp1 );
      if ( fp2 )
         fclose( fp2 );
      if ( fp3 )
         fclose( fp3 );
      if ( lpvoid )
         free( lpvoid );
   }
}

int main() {
   fileOps();
}
```

## <a name="see-also"></a>См. также

[Написание обработчика завершения](../cpp/writing-a-termination-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
