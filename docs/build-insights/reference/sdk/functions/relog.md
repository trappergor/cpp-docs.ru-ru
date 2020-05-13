---
title: Релог
description: Ссылка на функцию SDK Relog в сборке СЗ.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Relog
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 28b290d2bf2880ce2f534fa1cd91750890e2fead
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323780"
---
# <a name="relog"></a>Релог

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `Relog` используется для чтения событий MSVC из трассировки событий для отслеживания Windows (ETW) и записывания их в новый, измененный след ETW.

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

*TAnalyzerGroupЧлены*\
Этот параметр всегда выводится.

*TReloggerGroupЧлены*\
Этот параметр всегда выводится.

*вхотливыйLogFile*\
Входный след ETW, из которого вы хотите прочитать события.

*выходНопок*\
Файл, в котором можно написать новые события.

*numberOfAnalysisPasses*\
Количество анализов проходит для выполнения на входе следа. След проходит через предоставленную группу анализаторов один раз за анализ.

*системаСобытияУтУдержаниеФлаги*\
Битовая маска, которая определяет, какая система ETW событий держать в перелогированных след. Для получения дополнительной информации см [RELOG_RETENTION_SYSTEM_EVENT_FLAGS.](../other-types/relog-retention-system-event-flags-constants.md)

*анализаторГруппа*\
Группа анализаторов, используемая для фазы анализа сеанса перезаписи. Позвоните [MakeStaticAnalyzerGroup,](make-static-analyzer-group.md) чтобы создать группу анализаторов. Чтобы использовать группу динамического анализатора, полученную от [MakeDynamicAnalyzerGroup,](make-dynamic-analyzer-group.md)сначала инкапсулируют `MakeStaticAnalyzerGroup`его внутри группы статического анализатора, передав его адрес .

*reloggerGroup*\
Группа перелогов, которая переобораживает события в файл трассировки, указанный в *outputLogFile.* Позвоните [MakeStaticReloggerGroup,](make-static-relogger-group.md) чтобы создать группу перелогов. Чтобы использовать динамическую группу релоггеров, полученную от [MakeDynamicReloggerGroup,](make-dynamic-relogger-group.md)сначала инкапсулируйте его `MakeStaticReloggerGroup`внутри статической группы релоггеров, передав свой адрес.

### <a name="return-value"></a>Возвращаемое значение

Код результата из [RESULT_CODE](../other-types/result-code-enum.md) enum.

### <a name="remark"></a>Комментарий

Вхотовый след проходит через номер группы *анализатораOfAnalysisPasses* раз. Аналогичной опции для перезаписи пропусков нет. След передается корыта relogger группы только один раз, после того, как все анализ проходит завершены.

Повторная запись системных событий, таких как образцы процессора из класса relogger, не поддерживается. Используйте параметр *systemEventsRetentionFlags,* чтобы решить, какие события системы следует держать в выходном следе.

::: moniker-end
