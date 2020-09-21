---
title: Структура SYMBOL_NAME_DATA
description: Справочник по структуре SYMBOL_NAME_DATA из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SYMBOL_NAME_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d234c6c225eff87a0eecd98fa5ff60bf92db97f5
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041917"
---
# <a name="symbol_name_data-structure"></a>Структура SYMBOL_NAME_DATA

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

В структуре `SYMBOL_NAME_DATA` описывается символ внешнего интерфейса компилятора.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct SYMBOL_NAME_DATA_TAG
{
    unsigned long long  Key;
    const char*         Name;

} SYMBOL_NAME_DATA;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `Key` | Ключ символа. Это значение уникально в пределах анализируемой трассировки. |
| `Name` | Имя символа. |

## <a name="remarks"></a>Remarks

Символы, созданные на двух разных этапах внешнего интерфейса компилятора, могут уметь одинаковое имя но разные ключи. В этом случае используйте имена символов, чтобы определить, являются ли два типа идентичными.

::: moniker-end
