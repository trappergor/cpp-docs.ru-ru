---
title: '&lt;cstdarg&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdarg>
helpviewer_keywords:
- cstdarg header
ms.assetid: 639b4ef7-8408-4640-9343-41631f0ab663
ms.openlocfilehash: f8d2d3b886cfa46905e8f17f1e13b51881b80191
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244486"
---
# <a name="ltcstdarggt"></a>&lt;cstdarg&gt;

Включает C стандартный заголовок библиотеки \<stdarg.h > и добавляет связанные имена в `std` пространства имен. Включение этого заголовка гарантирует, что имена, объявленные с внешней компоновкой в заголовке библиотеки C Standard, объявляются в `std` пространства имен.

## <a name="syntax"></a>Синтаксис

```cpp
#include <cstdarg>
```

## <a name="namespace-and-macros"></a>Пространство имен и макросы

```cpp
namespace std {
    using va_list = see below;
}

#define va_arg(V, P)
#define va_copy(VDST, VSRC)
#define va_end(V)
#define va_start(V, P)
```

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
