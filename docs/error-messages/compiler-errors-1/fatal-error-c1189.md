---
title: Неустранимая ошибка C1189 | Документы Microsoft
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b49f227b5fda20ab0ba202d3d7eca99492509b35
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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