---
title: Класс FrontEndFile
description: Справочник по классу FrontEndFile пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFile
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7715a153df538eab94b8de5281a91d4f6b439ff9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920662"
---
# <a name="frontendfile-class"></a>Класс FrontEndFile

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `FrontEndFile` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [FRONT_END_FILE](../event-table.md#front-end-file).

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

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `FrontEndFile` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[FrontEndFile](#front-end-file)

### <a name="functions"></a>Функции

[Путь](#path)

## <a name="frontendfile"></a><a name="front-end-file"></a> FrontEndFile

```cpp
FrontEndFile(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [FRONT_END_FILE_DATA](../event-table.md#front-end-file).

## <a name="path"></a><a name="path"></a> Path

```cpp
const char* Path() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к файлу в кодировке UTF-8.

::: moniker-end
