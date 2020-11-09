---
title: Класс FileOutput
description: Справочник по классу FileOutput пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 65e23715d8ac47a8653215e8bd3ee7a43bbe80a3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923247"
---
# <a name="fileoutput-class"></a>Класс FileOutput

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `FileOutput` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления событий [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output), [EXP_OUTPUT](../event-table.md#exp-output), [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output), [LIB_OUTPUT](../event-table.md#lib-output) или [OBJ_OUTPUT](../event-table.md#obj-output).

## <a name="syntax"></a>Синтаксис

```cpp
class FileOutput : public SimpleEvent
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

    FileOutput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [SimpleEvent](simple-event.md) класс `FileOutput` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[FileOutput](#file-output)

### <a name="functions"></a>Функции

[Path](#path)
[Type](#type)

## <a name="fileoutput"></a><a name="file-output"></a> FileOutput

```cpp
FileOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
События [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output), [EXP_OUTPUT](../event-table.md#exp-output), [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output), [LIB_OUTPUT](../event-table.md#lib-output) или [OBJ_OUTPUT](../event-table.md#obj-output).

## <a name="path"></a><a name="path"></a> Path

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к выходному файлу.

## <a name="type"></a>Тип <a name="type"></a>

```cpp
Type Type() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, описывающий тип выходного файла.

::: moniker-end
