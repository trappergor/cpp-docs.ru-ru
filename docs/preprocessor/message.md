---
title: Прагма message
ms.date: 08/29/2019
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
ms.openlocfilehash: 48605fbef3b6d81c140e663e950429cd3dcf9b19
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218792"
---
# <a name="message-pragma"></a>Прагма message

Отправляет строковый литерал в стандартный вывод, не завершая компиляцию.

## <a name="syntax"></a>Синтаксис

> **сообщение #pragma (** *Строка сообщения* **)**

## <a name="remarks"></a>Примечания

Обычно директива pragma **сообщения** используется для вывода информационных сообщений во время компиляции.

Параметр *строки сообщения* может быть макросом, который расширяется до строкового литерала, и можно объединить такие макросы с строковыми литералами в любом сочетании.

При использовании предопределенного макроса в директиве pragma **сообщения** макрос должен возвращать строку. В противном случае необходимо преобразовать выходные данные макроса в строку.

В следующем фрагменте кода используется директива pragma **Message** для вывода сообщений во время компиляции:

```cpp
// pragma_directives_message1.cpp
// compile with: /LD
#if _M_IX86 >= 500
#pragma message("_M_IX86 >= 500")
#endif

#pragma message("")

#pragma message( "Compiling " __FILE__ )
#pragma message( "Last modified on " __TIMESTAMP__ )

#pragma message("")

// with line number
#define STRING2(x) #x
#define STRING(x) STRING2(x)

#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")

#pragma message("")
```

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
