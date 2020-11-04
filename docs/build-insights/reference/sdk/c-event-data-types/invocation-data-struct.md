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
ms.openlocfilehash: 98ac234b702ef2c73a5c8d90ee6bf4dc59349ed6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920974"
---
# <a name="invocation_data-structure"></a>Структура INVOCATION_DATA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

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
