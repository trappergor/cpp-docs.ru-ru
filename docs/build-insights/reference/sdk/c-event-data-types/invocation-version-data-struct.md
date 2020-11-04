---
title: Структура INVOCATION_VERSION_DATA
description: Справочник по структуре INVOCATION_VERSION_DATA из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ebed659ade4610b50ae06f2a32851522073a58d8
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923558"
---
# <a name="invocation_version_data-structure"></a>Структура INVOCATION_VERSION_DATA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

В структуре `INVOCATION_VERSION_DATA` описывается номер версии в виде группы целочисленных значений.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct INVOCATION_VERSION_DATA_TAG
{
    unsigned short VersionMajor;
    unsigned short VersionMinor;
    unsigned short BuildNumberMajor;
    unsigned short BuildNumberMinor;

} INVOCATION_VERSION_DATA;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `VersionMajor` | Основной номер версии. |
| `VersionMinor` | Дополнительный номер версии. |
| `BuildNumberMajor` | Основной номер сборки. |
| `BuildNumberMinor` | Дополнительный номер сборки. |

::: moniker-end
