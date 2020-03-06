---
title: Загрузить
description: Справочник C++ по функции Relog для Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Relog
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1ce09101deebd957de4b9305762dc37f38b53f4e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334286"
---
# <a name="relog"></a>Загрузить

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `Relog` используется для чтения событий КОМПИЛЯТОРОМ MSVC из трассировки трассировки событий Windows (ETW) и записи их в новую, измененную трассировку ETW.

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

*Танализерграупмемберс*\
Этот параметр всегда выводится.

*Трелогжерграупмемберс*\
Этот параметр всегда выводится.

*инпутлогфиле*\
Входная трассировка ETW, из которой требуется считать события.

*аутпутлогфиле*\
Файл, в который записываются новые события.

*нумберофаналисиспассес*\
Количество проходов анализа для выполнения во входной трассировке. Трассировка передается через предоставленную группу анализаторов один раз для каждого этапа анализа.

*системевентсретентионфлагс*\
Битовая маска, указывающая системные события ETW, которые должны оставаться в журнале трассировки. Дополнительные сведения см. в разделе [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md).

*анализерграуп*\
Группа анализатора, используемая для фазы анализа сеанса повторного ведения журнала. Вызовите [макестатиканализерграуп](make-static-analyzer-group.md) , чтобы создать группу анализатора. Чтобы использовать группу динамического анализатора, полученную из [макединамиканализерграуп](make-dynamic-analyzer-group.md), сначала необходимо инкапсулировать ее в статическую группу анализатора, передав ее адрес в `MakeStaticAnalyzerGroup`.

*релогжерграуп*\
Группа переведения журнала, которая выполняет перезапись событий в файл трассировки, указанный в *аутпутлогфиле*. Вызовите [макестатикрелогжерграуп](make-static-relogger-group.md) , чтобы создать группу повторного ведения журнала. Чтобы использовать группу "Динамическая переведение журнала", полученную из [макединамикрелогжерграуп](make-dynamic-relogger-group.md), сначала необходимо инкапсулировать ее в группу "статическая регистрация", передав ее адрес в `MakeStaticReloggerGroup`.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md) .

### <a name="remark"></a>Комментарий

Входная трассировка передается через группу анализатора *нумберофаналисиспассес* раз. Для проходов перезаписи не существует аналогичного варианта. Трассировка передается траугх только один раз после завершения всех этапов анализа.

Перезапись системных событий, таких как примеры ЦП, из класса, переданного в журнал, не поддерживается. Используйте параметр *системевентсретентионфлагс* , чтобы решить, какие системные события следует отслеживать в выходной трассировке.

::: moniker-end
