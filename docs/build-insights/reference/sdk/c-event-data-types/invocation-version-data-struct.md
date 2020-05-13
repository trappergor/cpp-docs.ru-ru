---
title: структура INVOCATION_VERSION_DATA
description: Ссылка на структуру SDK Build Insights sDK INVOCATION_VERSION_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1211b4eb999fd63767af71c6884d7d20d6920df0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325469"
---
# <a name="invocation_version_data-structure"></a>структура INVOCATION_VERSION_DATA

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `INVOCATION_VERSION_DATA` описывает номер версии как группу интегральных значений.

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

|  |  |
|--|--|
| `VersionMajor` | Основной номер версии. |
| `VersionMinor` | Незначительный номер версии. |
| `BuildNumberMajor` | Основное число сборки. |
| `BuildNumberMinor` | Незначительное число сборки. |

::: moniker-end
