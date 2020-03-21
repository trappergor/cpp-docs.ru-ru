---
title: '&lt;ctime&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ctime>
- std::<ctime>
helpviewer_keywords:
- ctime header
ms.assetid: c1f7d4a4-4bfe-4e35-92cb-f63dbd3c39a8
ms.openlocfilehash: 2b3f31ba48ca831b2d2d8cd460b60549c4debe83
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076622"
---
# <a name="ltctimegt"></a>&lt;ctime&gt;

Включает заголовок \<time.h> стандартной библиотеки C и добавляет связанные имена в пространство имен `std`.

## <a name="syntax"></a>Синтаксис

```cpp
#include <ctime>
```

## <a name="remarks"></a>Примечания

Включение этого заголовка гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C, объявляются в пространстве имен `std`.

## <a name="constants"></a>Константы

```cpp
#define NULL
#define CLOCKS_PER_SEC
#define TIME_UTC

namespace std {
    using size_t = see below;
    using clock_t = see below ;
    using time_t = see below ;
}
```

## <a name="structures"></a>Структуры

```cpp
struct timespec;
struct tm;
```

## <a name="functions"></a>Функции

```cpp
clock_t clock();
double difftime(time_t time1, time_t time0);
time_t mktime(struct tm* timeptr);
time_t time(time_t* timer);
int timespec_get(timespec* ts, int base);
char* asctime(const struct tm* timeptr);
char* ctime(const time_t* timer);
struct tm* gmtime(const time_t* timer);
struct tm* localtime(const time_t* timer);
size_t strftime(char* s, size_t maxsize, const char* format, const struct tm* timeptr);
```

## <a name="see-also"></a>См. также:

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
