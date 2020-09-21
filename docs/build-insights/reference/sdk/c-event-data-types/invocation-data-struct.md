---
title: Структура INVOCATION_DATA
description: Справочник по структуре INVOCATION_DATA из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 48b4c28d3c01d61a31343894312a54ba2ab17a70
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041644"
---
# <a name="invocation_data-structure"></a>Структура INVOCATION_DATA

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

В структуре `INVOCATION_DATA` описывается вызов компилятора и компоновщика.

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

| Имя | Описание |
|--|--|
| `MSVCToolCode` | Код, определяющий тип вызова. Подробнее см. в статье о [MSVC_TOOL_CODE](msvc-tool-code-enum.md). |
| `ToolVersion` | Объект, хранящий версию вызываемого средства в виде группы целочисленных значений. |
| `ToolVersionString` | Описывает версию вызванного средства в текстовой форме. |
| `WorkingDirectory` | Каталог, из которого был сделан вызов. |
| `ToolPath` | Абсолютный путь к вызываемому средству. |

::: moniker-end
