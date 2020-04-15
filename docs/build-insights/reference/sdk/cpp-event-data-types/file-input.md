---
title: Класс FileInput
description: Ссылка на класс SDK FileInput.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileInput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 642236d3e67465ed38508cb24c8cd698ae880065
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324797"
---
# <a name="fileinput-class"></a>Класс FileInput

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `FileInput` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [FILE_INPUT](../event-table.md#file-input) событию.

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

## <a name="members"></a>Участники

Наряду с унаследованных членов из `FileInput` своего базового класса [SimpleEvent,](simple-event.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[FileInput](#file-input)

### <a name="functions"></a>Функции

[Path](#path)
[Тип](#type) пути

## <a name="fileinput"></a><a name="file-input"></a>FileInput

```cpp
FileInput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
[Событие FILE_INPUT.](../event-table.md#file-input)

## <a name="path"></a><a name="path"></a>Путь

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к файлу ввода.

## <a name="type"></a>Тип <a name="type"></a>

```cpp
Type Type() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, описывающий тип ввода файла.

::: moniker-end
