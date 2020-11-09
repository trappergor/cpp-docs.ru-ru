---
title: Relog
description: Справочник по классу Relog пакета SDK Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Relog
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 628f60042a10cf80c0b077d28387ed75466e925b
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922756"
---
# <a name="relog"></a>Relog

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `Relog` используется для чтения событий MSVC из трассировки событий Windows (ETW) и записи этих событий в новую, измененную трассировку ETW.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const char*                                   inputLogFile,
    const char*                                   outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const wchar_t*                                inputLogFile,
    const wchar_t*                                outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>Параметры

*TAnalyzerGroupMembers*\
Этот параметр выводится во всех случаях.

*TReloggerGroupMembers*\
Этот параметр выводится во всех случаях.

*inputLogFile*\
Входная трассировка ETW, из которой нужно считать события.

*outputLogFile*\
Файл, в который записываются новые события.

*numberOfAnalysisPasses*\
Количество проходов анализа для выполнения во входной трассировке. Трассировка передается через предоставленную группу анализатора один раз для каждого выполнения анализа.

*systemEventsRetentionFlags*\
Битовая маска, указывающая, какие системные события трассировки событий Windows следует сохранить в повторно записанных трассировках. Дополнительные сведения см. в статье [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md).

*analyzerGroup*\
Группа анализатора, используемая для анализа сеанса повторной записи. Вызовите [MakeStaticAnalyzerGroup](make-static-analyzer-group.md), чтобы создать группу анализатора. Чтобы использовать группу динамического анализатора, полученную из [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md), сначала необходимо инкапсулировать ее в статическую группу анализатора, передав ее адрес в `MakeStaticAnalyzerGroup`.

*reloggerGroup*\
Группа перезаписи, которая выполняет перезапись событий в файл трассировки, указанный в *outputLogFile*. Вызовите [MakeStaticReloggerGroup](make-static-relogger-group.md), чтобы создать группу перезаписи. Чтобы использовать группу динамической перезаписи, полученную из [MakeDynamicReloggerGroup](make-dynamic-relogger-group.md), сначала нужно инкапсулировать ее в группу динамической перезаписи, передав ее адрес в `MakeStaticReloggerGroup`.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md).

### <a name="remark"></a>Комментарий

Входная трассировка передается через группу анализатора значения времени *numberOfAnalysisPasses* раз. Для проходов перезаписи не существует аналогичного параметра. Трассировка передается через группу перезаписи только один раз после завершения всех этапов анализа.

Повторная запись системных событий, таких как примеры ЦП, из класса перезаписи не поддерживается. Используйте параметр *systemEventsRetentionFlags* , чтобы решить, какие системные события следует хранить в выходной трассировке.

::: moniker-end
