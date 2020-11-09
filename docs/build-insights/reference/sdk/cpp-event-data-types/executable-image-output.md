---
title: Класс ExecutableImageOutput
description: Справочник по классу ExecutableImageOutput пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExecutableImageOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bf6bb9790dabc39d1ed6baa417d5dc3bf72ed5e6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920727"
---
# <a name="executableimageoutput-class"></a>Класс ExecutableImageOutput

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `ExecutableImageOutput` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output).

## <a name="syntax"></a>Синтаксис

```cpp
class ExecutableImageOutput : public FileOutput
{
public:
    ExecutableImageOutput(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [FileOutput](file-output.md) класс `ExecutableImageOutput` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[ExecutableImageOutput](#executable-image-output)

## <a name="executableimageoutput"></a><a name="executable-image-output"></a> ExecutableImageOutput

```cpp
ExecutableImageOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output).

::: moniker-end
