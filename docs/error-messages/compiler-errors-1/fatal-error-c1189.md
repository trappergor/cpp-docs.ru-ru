---
title: Неустранимая ошибка C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 06d42316a0109ac063bba43cefebd9aab71c2e72
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229063"
---
# <a name="fatal-error-c1189"></a>Неустранимая ошибка C1189

> **\#Ошибка:** *указанное пользователем сообщение*

## <a name="remarks"></a>Примечания

Ошибка C1189 создается `#error` директива. Разработчик, коды директива задает текст сообщения об ошибке. Дополнительные сведения см. в разделе [директива #error (C/C++)](../../preprocessor/hash-error-directive-c-cpp.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C1189. В этом примере разработчик задал пользовательское сообщение об ошибке, поскольку `_WIN32` идентификатор не определен:

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>См. также

[Директива #define (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)