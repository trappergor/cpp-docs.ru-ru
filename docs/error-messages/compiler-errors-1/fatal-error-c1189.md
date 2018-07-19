---
title: Неустранимая ошибка C1189 | Документы Microsoft
ms.custom: ''
ms.date: 04/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 051b7eb965526d12311dfacaeae7a00e4fbe4e75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199798"
---
# <a name="fatal-error-c1189"></a>Неустранимая ошибка C1189

> **\#Ошибка:** *сообщение об ошибке указанное пользователем*

## <a name="remarks"></a>Примечания

Ошибка C1189 создается `#error` директивы. Разработчик, коды директива задает текст сообщения об ошибке. Дополнительные сведения см. в разделе [(C/C++) директива #error](../../preprocessor/hash-error-directive-c-cpp.md).

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