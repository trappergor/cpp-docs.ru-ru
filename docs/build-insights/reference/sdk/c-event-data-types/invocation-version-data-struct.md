---
title: Структура INVOCATION_VERSION_DATA
description: В C++ пакете SDK для аналитики сборки INVOCATION_VERSION_DATA ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 040b0f90b14133ec2b25f7a12d35b88d382c4f7a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335132"
---
# <a name="invocation_version_data-structure"></a>Структура INVOCATION_VERSION_DATA

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `INVOCATION_VERSION_DATA` описывает номер версии в виде группы целочисленных значений.

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

## <a name="members"></a>Члены

|  |  |
|--|--|
| `VersionMajor` | Основной номер версии. |
| `VersionMinor` | Дополнительный номер версии. |
| `BuildNumberMajor` | Основной номер сборки. |
| `BuildNumberMinor` | Дополнительный номер сборки. |

::: moniker-end
