---
title: Класс Ексекутаблеимажеаутпут
description: Справочник C++ по классу SDK для Build Insights ексекутаблеимажеаутпут.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExecutableImageOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5a2e417a7dd976f257b4dd5a3aabfdf440c604fc
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334880"
---
# <a name="executableimageoutput-class"></a>Класс Ексекутаблеимажеаутпут

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `ExecutableImageOutput` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) .

## <a name="syntax"></a>Синтаксис

```cpp
class ExecutableImageOutput : public FileOutput
{
public:
    ExecutableImageOutput(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Вместе с наследуемыми членами из своего базового класса [филеаутпут](file-output.md) класс `ExecutableImageOutput` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[ексекутаблеимажеаутпут](#executable-image-output)

## <a name="executable-image-output"></a>ексекутаблеимажеаутпут

```cpp
ExecutableImageOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) .

::: moniker-end
