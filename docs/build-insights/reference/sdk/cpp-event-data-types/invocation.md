---
title: Класс вызова
description: Справочник C++ по классу вызова SDK для аналитики сборки.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Invocation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 0c4698300a3eeaf77210ad74f84b0c0cd219b457
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334748"
---
# <a name="invocation-class"></a>Класс вызова

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Invocation` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с [компилятором](../event-table.md#compiler) или событием [компоновщика](../event-table.md#linker) .

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

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `Invocation` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Вызов](#invocation)

### <a name="functions"></a>Функции

[ToolPath](#tool-path)
[тулверсион](#tool-version)
[тулверсионстринг](#tool-version-string)
[тип](#type)
[WorkingDirectory](#working-directory)

## <a name="invocation"></a>Вызова

```cpp
Invocation(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
[Компилятор](../event-table.md#compiler) или событие [компоновщика](../event-table.md#linker) .

## <a name="tool-path"></a>ToolPath

```cpp
const wchar_t* ToolPath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к вызываемому средству.

## <a name="tool-version"></a>тулверсион

```cpp
const INVOCATION_VERSION_DATA& ToolVersion() const;
```

### <a name="return-value"></a>Возвращаемое значение

Версия средства, которая была вызвана, как ссылка на [INVOCATION_VERSION_DATA](../c-event-data-types/invocation-version-data-struct.md) .

## <a name="tool-version-string"></a>тулверсионстринг

```cpp
const char* ToolVersionString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Версия вызываемого инструмента в виде строки ANSI.

## <a name="type"></a>Тип

```cpp
Type Type() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, указывающий на вызванное средство.

## <a name="working-directory"></a>WorkingDirectory

```cpp
const wchar_t* WorkingDirectory() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к каталогу, в котором был вызван инструмент.

::: moniker-end
