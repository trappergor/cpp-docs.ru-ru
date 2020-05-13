---
title: АнализW
description: Ссылка на функцию SDK AnalyseW в отношении сборки.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalyzeW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 64d68e4c10c0b77c3e6b08b1ec23735e38a377a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324159"
---
# <a name="analyzew"></a>АнализW

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `AnalyzeW` используется для анализа событий MSVC, считываемых из отслеживания событий ввода для отслеживания Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE AnalyzeW(
    const wchar_t*             inputLogFile,
    const ANALYSIS_DESCRIPTOR* analysisDescriptor);
```

### <a name="parameters"></a>Параметры

*вхотливыйLogFile*\
Входный след ETW, из которого вы хотите прочитать события.

*анализДескриптор*\
Указатель на [ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) объект. Используйте этот объект для настройки анализа.

### <a name="return-value"></a>Возвращаемое значение

Код результата из [RESULT_CODE](../other-types/result-code-enum.md) enum.

::: moniker-end
