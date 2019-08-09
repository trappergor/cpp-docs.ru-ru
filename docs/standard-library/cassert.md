---
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: 58ebd91fb4fa32cf31d2c49429d0445b92fe0c82
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449910"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

Включает заголовок \<стандартной библиотеки C Assert. h > и добавляет связанные имена `std` в пространство имен. Включение этого заголовка гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C `std` , объявляются в пространстве имен.

> [!NOTE]
> \<Assert. h > не определяет `static_assert` макрос.

## <a name="syntax"></a>Синтаксис

```cpp
#include <cassert>
```

## <a name="macros"></a>Макросы

```cpp
#define assert(E)
```

### <a name="remarks"></a>Примечания

`assert(E)`является константой, если NDEBUG определен, где `assert` является последним определением или переопределением, или *E* , преобразованное в bool, вычисляется как **true**.

## <a name="see-also"></a>См. также

[Макрос assert, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)\
[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
