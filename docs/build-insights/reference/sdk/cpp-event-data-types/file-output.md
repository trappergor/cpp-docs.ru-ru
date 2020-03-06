---
title: Класс Филеаутпут
description: Справочник C++ по классу SDK для Build Insights филеаутпут.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1c4053d0378ddb9d5dd061bbc9889c454dc9b52c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334844"
---
# <a name="fileoutput-class"></a>Класс Филеаутпут

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `FileOutput` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output), [EXP_OUTPUT](../event-table.md#exp-output), [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output), [LIB_OUTPUT](../event-table.md#lib-output)или [OBJ_OUTPUT](../event-table.md#obj-output) события.

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

Вместе с наследуемыми членами из своего базового класса [симпливент](simple-event.md) класс `FileOutput` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[филеаутпут](#file-output)

### <a name="functions"></a>Функции

[Тип](#type)
[пути](#path)

## <a name="file-output"></a>филеаутпут

```cpp
FileOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output), [EXP_OUTPUT](../event-table.md#exp-output), [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output), [LIB_OUTPUT](../event-table.md#lib-output)или [OBJ_OUTPUT](../event-table.md#obj-output) .

## <a name="path"></a> Path

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к выходному файлу.

## <a name="type"></a>Тип

```cpp
Type Type() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, описывающий тип выходного файла.

::: moniker-end
