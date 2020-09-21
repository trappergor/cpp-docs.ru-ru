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
ms.openlocfilehash: ec54c560dd408dc3beecbc20eaac69d389c7ec37
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041563"
---
# <a name="invocation_version_data-structure"></a>Структура INVOCATION_VERSION_DATA

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

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
