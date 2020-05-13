---
title: Класс FrontEndFile
description: Ссылка на класс SDK FrontEndFile.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFile
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c40137724279ea2fd615729db39f0ac5c907b79e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324765"
---
# <a name="frontendfile-class"></a>Класс FrontEndFile

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `FrontEndFile` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [FRONT_END_FILE](../event-table.md#front-end-file) событию.

## <a name="syntax"></a>Синтаксис

```cpp
class FrontEndFile : public Activity
{
public:
    FrontEndFile(const RawEvent& event);

    const char* Path() const;
};
```

## <a name="members"></a>Участники

Наряду с унаследованные члены `FrontEndFile` из своего базового класса [деятельности,](activity.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[FrontEndFile](#front-end-file)

### <a name="functions"></a>Функции

[Путь](#path)

## <a name="frontendfile"></a><a name="front-end-file"></a>FrontEndFile

```cpp
FrontEndFile(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
[Событие FRONT_END_FILE.](../event-table.md#front-end-file)

## <a name="path"></a><a name="path"></a>Путь

```cpp
const char* Path() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к файлу, закодированный в UTF-8.

::: moniker-end
