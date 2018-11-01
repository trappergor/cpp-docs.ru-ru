---
title: Определения типов &lt;system_error&gt;
ms.date: 11/04/2016
f1_keywords:
- system_error/std::generic_errno
ms.assetid: 28cf9f7d-9c28-4baa-a297-67c8260b07fb
ms.openlocfilehash: 95b2cb22d4fbff4f92cf28041e70ae599c318cbc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531066"
---
# <a name="ltsystemerrorgt-typedefs"></a>Определения типов &lt;system_error&gt;

||
|-|
|[generic_errno](#generic_errno)|

## <a name="generic_errno"></a>  generic_errno

Тип, который представляет перечисление, предоставляющее символьные имена для всех макросов с ошибками в коде, определяемых Posix в `<errno.h>`.

```cpp
typedef errc generic_error;
```

### <a name="remarks"></a>Примечания

Тип является синонимом [errc](../standard-library/system-error-enums.md#errc).

## <a name="see-also"></a>См. также

[<system_error>](../standard-library/system-error.md)<br/>
