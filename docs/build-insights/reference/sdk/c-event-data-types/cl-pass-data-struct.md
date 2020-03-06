---
title: Структура CL_PASS_DATA
description: В C++ пакете SDK для аналитики сборки CL_PASS_DATA ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3df5b5bc1cddbadc4a4d432ae021dd8b338c532e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335258"
---
# <a name="cl_pass_data-structure"></a>Структура CL_PASS_DATA

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `CL_PASS_DATA` описывает этап компиляции.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct CL_PASS_DATA_TAG
{
    int                         TranslationUnitPassCode;
    const wchar_t*              InputSourcePath;
    const wchar_t*              OutputObjectPath;

} CL_PASS_DATA;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `TranslationUnitPassCode` | Код, идентифицирующий выполняемый этап компиляции. Дополнительные сведения см. в разделе [TRANSLATION_UNIT_PASS_CODE](translation-unit-pass-code-enum.md). |
| `InputSourcePath` | Исходный файл C C++ или, на котором выполняется этот этап компиляции. |
| `OutputObjectPath` | Объектный файл, создаваемый компилятором. |

::: moniker-end
