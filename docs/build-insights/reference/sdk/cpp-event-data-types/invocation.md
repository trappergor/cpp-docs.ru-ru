---
title: Класс Invocation
description: Справочник по классу Invocation пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Invocation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dfd463c7b9ca72dc14ad74b3759fdd1e3730d5a9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923138"
---
# <a name="invocation-class"></a>Класс Invocation

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `Invocation` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [COMPILER](../event-table.md#compiler) или [LINKER](../event-table.md#linker).

## <a name="syntax"></a>Синтаксис

```cpp
class Invocation : public Activity
{
    const INVOCATION_DATA* data_;

public:
    enum class Type
    {
        CL      = MSVC_TOOL_CODE_CL,
        LINK    = MSVC_TOOL_CODE_LINK
    };

    Invocation(const RawEvent& event);

    Type             Type() const;
    const char*      ToolVersionString() const;
    const wchar_t*   WorkingDirectory() const;
    const wchar_t*   ToolPath() const;

    const INVOCATION_VERSION_DATA& ToolVersion() const;
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `Invocation` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[Вызов](#invocation)

### <a name="functions"></a>Функции

[ToolPath](#tool-path)
[ToolVersion](#tool-version)
[ToolVersionString](#tool-version-string)
[Type](#type)
[WorkingDirectory](#working-directory)

## <a name="invocation"></a><a name="invocation"></a> Invocation

```cpp
Invocation(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [COMPILER](../event-table.md#compiler) или [LINKER](../event-table.md#linker).

## <a name="toolpath"></a><a name="tool-path"></a> ToolPath

```cpp
const wchar_t* ToolPath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к вызываемому средству.

## <a name="toolversion"></a><a name="tool-version"></a> ToolVersion

```cpp
const INVOCATION_VERSION_DATA& ToolVersion() const;
```

### <a name="return-value"></a>Возвращаемое значение

Версия средства, которая была вызвана как ссылка [INVOCATION_VERSION_DATA](../c-event-data-types/invocation-version-data-struct.md).

## <a name="toolversionstring"></a><a name="tool-version-string"></a> ToolVersionString

```cpp
const char* ToolVersionString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Версия вызванного средства в виде строки ANSI.

## <a name="type"></a>Тип <a name="type"></a>

```cpp
Type Type() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, указывающий на вызванное средство.

## <a name="workingdirectory"></a><a name="working-directory"></a> WorkingDirectory

```cpp
const wchar_t* WorkingDirectory() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к каталогу, в котором было вызвано средство.

::: moniker-end
