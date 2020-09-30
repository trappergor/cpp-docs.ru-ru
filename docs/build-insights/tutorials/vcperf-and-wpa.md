---
title: Руководство. Средство vcperf и Windows Performance Analyzer
description: Руководство по использованию vcperf и WPA для анализа трассировок сборки C++.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b82c1f7105b3fd03d8c21dd79617dbc66f3e090c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507769"
---
# <a name="tutorial-vcperf-and-windows-performance-analyzer"></a>Руководство. Средство vcperf и Windows Performance Analyzer

::: moniker range="<=vs-2017"

Средства C++ Build Insights доступны в Visual Studio 2019. Чтобы отобразилась документация для этой версии, установите в этой статье селектор **Версия** Visual Studio в положение "Visual Studio 2019". Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range="vs-2019"

В этом руководстве описано, как использовать *vcperf.exe* для сбора трассировки сборки C++. Вы также узнаете, как просматривать эту трассировку в Windows Performance Analyzer.

## <a name="step-1-install-and-configure-windows-performance-analyzer"></a>Шаг 1. Установка и настройка Windows Performance Analyzer

Windows Performance Analyzer (WPA) — это средство просмотра трассировки из Комплекта средств для развертывания и оценки Windows (ADK). Это отдельная служебная программа. Она не входит в число компонентов, которые можно установить с помощью установщика Visual Studio.

Версия WPA, которая поддерживает C++ Build Insights, в настоящее время доступна только в Windows ADK Insider Preview. Для получения доступа к этой предварительной версии необходимо зарегистрироваться в [программе предварительной оценки Windows](https://insider.windows.com). Чтобы получить предварительную версию Windows ADK, не нужно устанавливать операционную систему Windows 10 Insider Preview. Вам нужно только зарегистрировать учетную запись Майкрософт в программе предварительной оценки Windows.

### <a name="to-download-and-install-wpa"></a>Скачивание и установка WPA

Примечание. Для установки Windows Performance Analyzer требуется Windows 8 или более поздней версии.

1. Перейдите на [страницу для скачивания](/windows-hardware/get-started/adk-install) Windows ADK.

1. Скачайте и установите последнюю версию Windows ADK.

1. При появлении запроса на выбор компонентов, которые нужно установить, выберите **Windows Performance Toolkit**. При желании можете выбрать другие компоненты, но они не нужны для установки WPA.

   ![Экран выбора компонентов установщика Windows Performance Analyzer](media/wpa-installation.png)

### <a name="to-configure-wpa"></a><a name="configuration-steps"></a> Настройка WPA

Для просмотра трассировок C++ Build Insights в WPA требуется специальная надстройка. Чтобы установить ее, выполните следующие действия:

1. Получите надстройку, скачав один из приведенных ниже компонентов. Достаточно одного из них. Выберите тот, который вам удобнее.
    1. [Visual Studio 2019 версии 16.6 и выше](https://visualstudio.microsoft.com/downloads/);
    1. [пакет NuGet для C++ Build Insights](https://www.nuget.org/packages/Microsoft.Cpp.BuildInsights/).

1. Скопируйте файл `perf_msvcbuildinsights.dll` и вставьте в каталог установки WPA.
    1. В Visual Studio 2019 версии 16.6 и выше этот файл находится здесь: `C:\Program Files (x86)\Microsoft Visual Studio\2019\{Edition}\VC\Tools\MSVC\{Version}\bin\Host{Architecture}\{Architecture}`.
    1. В пакете NuGet для C++ Build Insights этот файл расположен здесь: `wpa\{Architecture}`.
    1. В приведенных выше путях замените переменные, заключенные в фигурные скобки, следующим образом:
        1. `{Edition}` — это используемый вами выпуск Visual Studio 2019 (Community, Professional или Enterprise).
        1. `{Version}` — это версия MSVC. Выберите самую последнюю из доступных.
        1. `{Architecture}`: выберите `x64`, если вы используете 64-разрядную версию Windows. В противном случае выберите `x86`.
    1. Как правило, каталог установки WPA размещен здесь: `C:\Program Files (x86)\Windows Kits\10\Windows Performance Toolkit`.

1. В каталоге установки WPA откройте файл `perfcore.ini` и добавьте запись для `perf_msvcbuildinsights.dll`.

## <a name="step-2-trace-your-build-with-vcperfexe"></a>Шаг 2. Трассировка сборки с помощью vcperf.exe

Чтобы просмотреть данные C++ Build Insights, сначала соберите их в файл трассировки, выполнив следующие действия:

1. Откройте **командную строку Native Tools x86** или **x64 для VS 2019** в режиме администратора. (Щелкните правой кнопкой мыши пункт меню "Пуск" и выберите **Еще** > **Запуск от имени администратора**.)
    1. Выберите **x64**, если вы используете 64-разрядную версию Windows. В противном случае выберите **x86**.

1. В окне командной строки введите следующую команду:

   **vcperf.exe /start _SessionName_**

   Вместо *SessionName* выберите понятное имя сеанса.

1. Выполните сборку проекта обычным образом. Для сборки не обязательно использовать то же окно командной строки.

1. В окне командной строки введите следующую команду:

   **vcperf.exe /stop _SessionName_ _traceFile.etl_**

   Используйте то же имя сеанса, которое выбрали для *SessionName*. Выберите подходящее имя для файла трассировки *traceFile.etl*.

Вот как выглядит типичная последовательность команд *vcperf.exe* в окне командной строки разработчика:

![Простой сценарий использования vcperf.exe](media/vcperf-simple-usage.png)

### <a name="important-notes-about-vcperfexe"></a>Важные примечания о vcperf.exe

- Для запуска и остановки трассировки *vcperf.exe* требуются права администратора. Используйте окно командной строки разработчика, которое открывается с помощью команды **Запуск от имени администратора**.

- На компьютере может выполняться только один сеанс трассировки.

- Обязательно запомните имя сеанса, использованное вами для запуска трассировки. Остановить сеанс, имя которого неизвестно, может быть сложно.

- Так же, как *cl.exe* и *link.exe*, служебная программа командной строки *vcperf.exe* включена в комплект установки MSVC. Для получения этого компонента никаких дополнительных действий не требуется.

- *vcperf.exe* собирает сведения о всех инструментах MSVC, запущенных в системе. Поэтому вам не обязательно запускать процесс сборки с помощью той же командной строки, которая использовалась для сбора трассировки. Сборку проекта можно выполнить из другой командной строки или даже в Visual Studio.

### <a name="vcperfexe-is-open-source"></a>vcperf.exe — программа с открытым кодом

Если вы хотите выполнить сборку собственной версии *vcperf.exe* и использовать ее, клонируйте эту программу из [репозитория GitHub vcperf](https://github.com/microsoft/vcperf).

## <a name="step-3-view-your-trace-in-windows-performance-analyzer"></a>Шаг 3. Просмотр трассировки в Windows Performance Analyzer

Запустите WPA и откройте журнал только что собранной трассировки. WPA должен распознать ее как трассировку C++ Build Insights. На панели обозревателя графов слева должны отображаться следующие представления:

- Обозреватель сборок
- Файлы
- Функции
- Создание экземпляров шаблонов

Если эти представления не отображаются, убедитесь, что WPA настроен правильно, как описано на [шаге 1](#configuration-steps). Вы можете просмотреть данные сборок, перетащив представления в пустое окно анализа справа, как показано ниже:

![Просмотр трассировки C++ Build Insights в Windows Performance Analyzer](media/wpa-viewing-trace.gif)

Другие представления доступны на панели обозревателя графов. Перетащите их в окно "Анализ", чтобы подробнее изучить информацию, которую они содержат. Полезным является представление CPU (Sampled) (ЦП, выборка), в котором показана загрузка ЦП во время сборки.

## <a name="more-information"></a>Дополнительные сведения

[Учебник. Основы использования Windows Performance Analyzer](wpa-basics.md)\
Сведения об распространенных операциях WPA, которые могут помочь при анализе трассировок сборки.

[Справочник: команды vcperf](../reference/vcperf-commands.md)\
В справочнике по командам *vcperf.exe* перечислены все доступные параметры команд.

[Общие сведения Представления Windows Performance Analyzer](../reference/wpa-views.md)\
В этой статье приведены подробные сведения о представлениях C++ Build Insights в WPA.

[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)\
Официальный сайт документации по WPA.

::: moniker-end
