---
title: Структура INVOCATION_DATA
description: В C++ пакете SDK для аналитики сборки INVOCATION_DATA ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b2e8ddcf79201d8bcbbb8eb298b96b5c7680f90e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335144"
---
# <a name="invocation_data-structure"></a>Структура INVOCATION_DATA

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `INVOCATION_DATA` описывает вызов компилятора или компоновщика.

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

## <a name="members"></a>Члены

|  |  |
|--|--|
| `MSVCToolCode` | Код, определяющий тип вызова. Дополнительные сведения см. в разделе [MSVC_TOOL_CODE](msvc-tool-code-enum.md). |
| `ToolVersion` | Объект, хранящий версию вызываемого инструмента в виде группы целочисленных значений. |
| `ToolVersionString` | Описывает версию вызванного средства в текстовом виде. |
| `WorkingDirectory` | Каталог, из которого был сделан вызов. |
| `ToolPath` | Абсолютный путь вызываемого инструмента. |

::: moniker-end
