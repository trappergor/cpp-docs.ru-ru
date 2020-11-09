---
title: Анализ
description: Справочник по функции Analyze пакета SDK Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5e593b690231adf6f04161f9c3ff6aef3217f9ef
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920324"
---
# <a name="analyze"></a>Анализ

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `Analyze` используется для анализа трассировки событий Windows (ETW), полученной из MSVC при трассировке сборки C++. События в трассировке ETW передаются последовательно в группу анализатора, предоставленную вызывающим объектом. Эта функция поддерживает многопроходный анализ, который позволяет передавать поток событий в группу анализатора несколько раз в одной строке.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const char*                                   inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const wchar_t*                                inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>Параметры

*TAnalyzerGroupMembers*\
Этот параметр выводится во всех случаях.

*inputLogFile*\
Входная трассировка ETW, из которой нужно считать события.

*numberOfPasses*\
Количество проходов анализа для выполнения во входной трассировке. Трассировка передается через предоставленную группу анализатора один раз для каждого выполнения анализа.

*analyzerGroup*\
Группа анализатора, используемая для анализа. Вызовите [MakeStaticAnalyzerGroup](make-static-analyzer-group.md), чтобы создать группу анализатора. Чтобы использовать группу динамического анализатора, полученную из [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md), сначала необходимо инкапсулировать ее в статическую группу анализатора, передав ее адрес в `MakeStaticAnalyzerGroup`.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md).

::: moniker-end
