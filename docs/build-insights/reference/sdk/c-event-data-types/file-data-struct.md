---
title: структура FILE_DATA
description: Ссылка на структуру SDK Build Insights sDK FILE_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6b7b0129c54fa4b1d5285bafb38761da45bab4e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325591"
---
# <a name="file_data-structure"></a>структура FILE_DATA

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `FILE_DATA` описывает ввод файла или вывод.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct FILE_DATA_TAG
{
    const wchar_t*      Path;
    int                 TypeCode;

} FILE_DATA;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `Path` | Абсолютный путь файла |
| `TypeCode` | Код, описывающий тип файла. Для получения дополнительной информации см [FILE_TYPE_CODE.](file-type-code-enum.md) |

::: moniker-end
