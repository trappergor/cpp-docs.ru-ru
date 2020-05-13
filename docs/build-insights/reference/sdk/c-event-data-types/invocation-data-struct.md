---
title: структура INVOCATION_DATA
description: Ссылка на структуру SDK Build Insights sDK INVOCATION_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4e1f428facac413d7a4a5c059452dd8cdb07be4c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325488"
---
# <a name="invocation_data-structure"></a>структура INVOCATION_DATA

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `INVOCATION_DATA` описывает вызов компилятора или ссылки.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct INVOCATION_DATA_TAG
{
    int                         MSVCToolCode;

    INVOCATION_VERSION_DATA     ToolVersion;

    const char*                 ToolVersionString;
    const wchar_t*              WorkingDirectory;
    const wchar_t*              ToolPath;

} INVOCATION_DATA;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `MSVCToolCode` | Код, идентифицирующие тип вызова. Для получения дополнительной информации см [MSVC_TOOL_CODE.](msvc-tool-code-enum.md) |
| `ToolVersion` | Объект, который хранит вызываемую версию инструмента как группу интегральных значений. |
| `ToolVersionString` | Описывает версию вызываемого инструмента в текстовой форме. |
| `WorkingDirectory` | Каталог, из которого был сделан призыв. |
| `ToolPath` | Абсолютный путь вызываемого инструмента. |

::: moniker-end
