---
title: Класс FileOutput
description: Ссылка на класс SDK FileOutput.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 37823da8a4aaac0ce4094583b8aee8ac1eb04aaa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324805"
---
# <a name="fileoutput-class"></a>Класс FileOutput

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `FileOutput` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его, чтобы соответствовать [EXECUTABLE_IMAGE_OUTPUT,](../event-table.md#executable-image-output) [EXP_OUTPUT,](../event-table.md#exp-output) [IMP_LIB_OUTPUT,](../event-table.md#imp-lib-output) [LIB_OUTPUT,](../event-table.md#lib-output)или [OBJ_OUTPUT](../event-table.md#obj-output) событию.

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

## <a name="members"></a>Участники

Наряду с унаследованных членов из `FileOutput` своего базового класса [SimpleEvent,](simple-event.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[ФайлВыход](#file-output)

### <a name="functions"></a>Функции

[Path](#path)
[Тип](#type) пути

## <a name="fileoutput"></a><a name="file-output"></a>ФайлВыход

```cpp
FileOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
[Событие EXECUTABLE_IMAGE_OUTPUT,](../event-table.md#executable-image-output) [EXP_OUTPUT,](../event-table.md#exp-output) [IMP_LIB_OUTPUT,](../event-table.md#imp-lib-output) [LIB_OUTPUT](../event-table.md#lib-output)или [OBJ_OUTPUT.](../event-table.md#obj-output)

## <a name="path"></a><a name="path"></a>Путь

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к файлу вывода.

## <a name="type"></a>Тип <a name="type"></a>

```cpp
Type Type() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, описывающий тип вывода файла.

::: moniker-end
