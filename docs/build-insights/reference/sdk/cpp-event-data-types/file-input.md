---
title: Класс FileInput
description: Справочник по классу FileInput пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileInput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6e12336c10347f00ea2663116f2f308658775e0d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920688"
---
# <a name="fileinput-class"></a>Класс FileInput

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `FileInput` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [FILE_INPUT](../event-table.md#file-input).

## <a name="syntax"></a>Синтаксис

```cpp
class FileInput : public SimpleEvent
{
public:
    enum class Type
    {
        OTHER               = FILE_TYPE_CODE_OTHER,
        OBJ                 = FILE_TYPE_CODE_OBJ,
        EXECUTABLE_IMAGE    = FILE_TYPE_CODE_EXECUTABLE_IMAGE,
        LIB                 = FILE_TYPE_CODE_LIB,
        IMP_LIB             = FILE_TYPE_CODE_IMP_LIB,
        EXP                 = FILE_TYPE_CODE_EXP
    };

    FileInput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [SimpleEvent](simple-event.md) класс `FileInput` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[FileInput](#file-input)

### <a name="functions"></a>Функции

[Path](#path)
[Type](#type)

## <a name="fileinput"></a><a name="file-input"></a> FileInput

```cpp
FileInput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [FILE_INPUT](../event-table.md#file-input).

## <a name="path"></a><a name="path"></a> Path

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к входному файлу.

## <a name="type"></a>Тип <a name="type"></a>

```cpp
Type Type() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, описывающий тип входного файла.

::: moniker-end
