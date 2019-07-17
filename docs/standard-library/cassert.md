---
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: 14dda03e835ec411013b2d827bd1ccaa77f8982e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245019"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

Включает C стандартный заголовок библиотеки \<assert.h > и добавляет связанные имена в `std` пространства имен. Включение этого заголовка гарантирует, что имена, объявленные с внешней компоновкой в заголовке библиотеки C Standard, объявляются в `std` пространства имен.

> [!NOTE]
> \<Assert.h > не определяет `static_assert` макрос.

## <a name="syntax"></a>Синтаксис

```cpp
#include <cassert>
```

## <a name="macros"></a>Макросы

```cpp
#define assert(E)
```

### <a name="remarks"></a>Примечания

`assert(E)` только является константой, если определен NDEBUG где `assert` последнего определяются или переопределяются, или *E* преобразуется в логическое значение, результатом которого является **true**.

## <a name="see-also"></a>См. также

[Макрос assert, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
