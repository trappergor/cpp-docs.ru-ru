---
title: Освобождение ресурсов
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
ms.openlocfilehash: b172695044057f58771af0f4cfcb5ca869b36678
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229055"
---
# <a name="cleaning-up-resources"></a>Освобождение ресурсов

Во время выполнения обработчика завершения не всегда известно, какие ресурсы фактически выделены, прежде чем не будет вызван обработчик завершения. Возможно, блок оператора **__try** был прерван до выделения всех ресурсов, так что не все ресурсы были открыты.

Таким образом, в целях безопасности прежде чем продолжить очистку обработки завершения, необходимо проверить, какие ресурсы фактически открыты. Ниже описана рекомендованная процедура.

1. Инициализируйте дескрипторы со значением null.

1. В блоке инструкций **__try** выделите ресурсы. Для дескрипторов устанавливается положительные значения по мере распределения ресурсов.

1. В **`__finally`** блоке инструкций выпустите каждый ресурс, соответствующий маркер или переменная флага которого не равны нулю или не имеют значение null.

## <a name="example"></a>Пример

Например, в следующем коде обработчик завершения используется для закрытия трех файлов и блока памяти, выделенного в блоке инструкций **__try** . Перед очисткой ресурса код сначала проверяет, был ли ресурс распределен.

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

## <a name="see-also"></a>См. также статью

[Написание обработчика завершения](../cpp/writing-a-termination-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
