---
title: CL_PASS_DATA структура
description: Ссылка на структуру SDK Build Insights sDK CL_PASS_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b0a41e59068ade285f1ffa1a9ce13734ef5f1f32
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325700"
---
# <a name="cl_pass_data-structure"></a>CL_PASS_DATA структура

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `CL_PASS_DATA` описывает компиляционный проход.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct CL_PASS_DATA_TAG
{
    int                         TranslationUnitPassCode;
    const wchar_t*              InputSourcePath;
    const wchar_t*              OutputObjectPath;

} CL_PASS_DATA;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `TranslationUnitPassCode` | Код, определяющий выполняемый компиляционный пропуск. Для получения дополнительной информации см [TRANSLATION_UNIT_PASS_CODE.](translation-unit-pass-code-enum.md) |
| `InputSourcePath` | Исходный файл C или C', на котором выполняется этот компиляционный пропуск. |
| `OutputObjectPath` | Файл объекта, производимый компилятором. |

::: moniker-end
