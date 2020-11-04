---
title: Структура CL_PASS_DATA
description: Справочник по структуре CL_PASS_DATA из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 24e524b802a124f38043f3b69afed7f1aa9cd156
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923647"
---
# <a name="cl_pass_data-structure"></a>Структура CL_PASS_DATA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

В структуре `CL_PASS_DATA` описывается проход компиляции.

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

| Имя | Описание |
|--|--|
| `TranslationUnitPassCode` | Код, идентифицирующий выполняемый проход компиляции. Дополнительные сведения см. в статье о [TRANSLATION_UNIT_PASS_CODE](translation-unit-pass-code-enum.md). |
| `InputSourcePath` | Исходный файл C или C++, в котором выполняется этот проход компиляции. |
| `OutputObjectPath` | Объектный файл, создаваемый компилятором. |

::: moniker-end
