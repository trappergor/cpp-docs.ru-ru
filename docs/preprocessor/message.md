---
title: сообщение
ms.date: 11/04/2016
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
ms.openlocfilehash: e9383238fd308ec59a9767f56af1c07fc3cfcf07
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030210"
---
# <a name="message"></a>сообщение
Отправляет строковый литерал в стандартный вывод, не завершая компиляцию.

## <a name="syntax"></a>Синтаксис

```
#pragma message( messagestring )
```

## <a name="remarks"></a>Примечания

Типичное применение **сообщение** pragma — Отображать информационные сообщения во время компиляции.

*Messagestring* параметр может быть макросом, который развертывается в строковый литерал, и можно сцепить эти макросы со строковыми литералами в любой комбинации.

При использовании предопределенного макроса в **сообщение** pragma, макрос должен вернуть строку, в противном случае вам придется преобразовать вывод макроса в строку.

В следующем фрагменте кода используется **сообщение** директивы pragma, для отображения сообщений во время компиляции:

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

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)