---
title: Класс призыва
description: Ссылка на класс SDK Invocation.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Invocation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fcb087d46ea445251b0108f811545a44c26f421e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324643"
---
# <a name="invocation-class"></a>Класс призыва

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Invocation` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его, чтобы соответствовать событию [COMPILER](../event-table.md#compiler) или [LINKER.](../event-table.md#linker)

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

Наряду с унаследованные члены `Invocation` из своего базового класса [деятельности,](activity.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Вызов](#invocation)

### <a name="functions"></a>Функции

[ToolPath](#tool-path)
[ToolVersion](#tool-version)
[ToolVersionString](#tool-version-string)
[Тип](#type)
[WorkingDirectory](#working-directory)

## <a name="invocation"></a><a name="invocation"></a>Вызова

```cpp
Invocation(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [COMPILER](../event-table.md#compiler) или [LINKER.](../event-table.md#linker)

## <a name="toolpath"></a><a name="tool-path"></a>ИнструментПат

```cpp
const wchar_t* ToolPath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к инструменту, который был вызван.

## <a name="toolversion"></a><a name="tool-version"></a>ToolVersion

```cpp
const INVOCATION_VERSION_DATA& ToolVersion() const;
```

### <a name="return-value"></a>Возвращаемое значение

Версия инструмента, которая была вызвана, в качестве [INVOCATION_VERSION_DATA](../c-event-data-types/invocation-version-data-struct.md) ссылки.

## <a name="toolversionstring"></a><a name="tool-version-string"></a>ToolVersionString

```cpp
const char* ToolVersionString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Версия инструмента, который был вызван, как строка ANSI.

## <a name="type"></a>Тип <a name="type"></a>

```cpp
Type Type() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, указывающий на инструмент, который был вызван.

## <a name="workingdirectory"></a><a name="working-directory"></a>Workingdirectory

```cpp
const wchar_t* WorkingDirectory() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к каталогу, в котором был вызван инструмент.

::: moniker-end
