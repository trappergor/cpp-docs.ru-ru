---
title: 'Справочник: команды vcperf'
description: Справка по программе командной строки vcperf.exe.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 42ca422e11824bdbdad4e42e7b55950317095703
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922209"
---
# <a name="reference-vcperf-commands"></a>Справочник: команды vcperf

::: moniker range="<=msvc-150"

Средства C++ Build Insights доступны в Visual Studio 2019. Чтобы отобразилась документация для этой версии, установите в этой статье селектор **Версия** Visual Studio в положение "Visual Studio 2019". Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range="msvc-160"

В этой статье приводятся и описываются команды, доступные в *vcperf.exe* , а также способы их использования.

## <a name="commands-to-start-and-stop-traces"></a>Команды для запуска и остановки трассировок

*ВАЖНО! Все приведенные ниже команды требуют прав администратора.*

| Параметр           | Аргументы и описание |
|------------------|---------------------------|
| `/start`         | `[/nocpusampling]` `<sessionName>` |
|                  | Указывает *vcperf.exe* запустить трассировку в сеансе с определенным именем. На отдельном компьютере одновременно можно запустить только один сеанс за раз. <br/><br/> Если указан параметр `/nocpusampling`, *vcperf.exe* не собирает выборку ЦП. Это предотвращает использование представления "Использование ЦП (с выборкой)" в Windows Performance Analyzer, но уменьшает размер собранных трассировок. <br/><br/> После запуска трассировки *vcperf.exe* немедленно возвращает результат. События собираются во всей системе для всех процессов, выполняющихся на компьютере. Это означает, что вам не нужно выполнять сборку проекта из той же командной строки, из которой вы выполнили *vcperf.exe*. Например, вы можете выполнить сборку проекта из Visual Studio. |
| `/stop`          | `<sessionName>` `<outputFile.etl>` |
|                  | Отвечает за остановку трассировки, определенную указанным именем сеанса. Отвечает за постобработку для трассировки с целью создания файла для просмотра в Windows Performance Analyzer (WPA). Для оптимального просмотра используйте версию WPA с надстройкой C++ Build Insights. Дополнительные сведения см. в статье [Начало работы с C++ Build Insights](../get-started-with-cpp-build-insights.md). Параметр `<outputFile.etl>` указывает расположение для сохранения выходного файла. |
| `/stopnoanalyze` | `<sessionName>` `<rawOutputFile.etl>` |
|                  | Остановите трассировку, определенную заданным именем сеанса, при которой необработанные данные записываются в указанный выходной файл. Полученный файл не предназначен для просмотра в WPA. <br/><br/> Процесс постобработки, выполняемый командой `/stop`, иногда занимает достаточно много времени. Вы можете воспользоваться командой `/stopnoanalyze`, чтобы отложить этот шаг. Выполните команду `/analyze`, если все готово к созданию файла для просмотра в Windows Performance Analyzer. |

## <a name="miscellaneous-commands"></a>Разные команды

| Параметр     | Аргументы и описание |
|------------|---------------------------|
| `/analyze` | `<rawInputFile.etl> <outputFile.etl>` |
|            | Принимает необработанный файл трассировки, созданный с помощью команды `/stopnoanalyze`. Отвечает за постобработку для трассировки с целью создания файла для просмотра в Windows Performance Analyzer. Для оптимального просмотра используйте версию WPA с надстройкой C++ Build Insights. Дополнительные сведения см. в статье [Начало работы с C++ Build Insights](../get-started-with-cpp-build-insights.md). |

## <a name="see-also"></a>См. также раздел

[Начало работы с аналитикой сборки C++](../get-started-with-cpp-build-insights.md)\
[Руководство. Основы использования Windows Performance Analyzer](../tutorials/wpa-basics.md)\
[Общие сведения Представления Windows Performance Analyzer](wpa-views.md)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
