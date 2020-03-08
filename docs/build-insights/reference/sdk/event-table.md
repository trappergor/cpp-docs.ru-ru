---
title: 'C++Пакет SDK для Build Insights: таблица событий'
description: Справочник по событиям для пакета C++ SDK для Visual Studio Build Insights
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Events
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2ccc8a4ef707942963b85edc6db9e21e05610b54
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78857021"
---
# <a name="c-build-insights-sdk-event-table"></a>C++Пакет SDK для Build Insights: таблица событий

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

## <a name="compiler-events"></a>События компилятора

\ [компилятора](#compiler)
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[OBJ_OUTPUT](#obj-output)\
[FRONT_END_PASS](#front-end-pass)\
[BACK_END_PASS](#back-end-pass)

## <a name="compiler-front-end-events"></a>События внешнего интерфейса компилятора

[C1_DLL](#c1-dll)\
[FRONT_END_FILE](#front-end-file)\
[TEMPLATE_INSTANTIATION](#template-instantiation)\
[SYMBOL_NAME](#symbol-name)

## <a name="compiler-back-end-events"></a>События серверной части компилятора

[C2_DLL](#c2-dll)\
[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis)\
[TOP_DOWN](#top-down)\
[BOTTOM_UP](#bottom-up)\
[CODE_GENERATION](#code-generation)\
\ [потоков](#thread)
\ [функции](#function)
[FORCE_INLINEE](#force-inlinee)

## <a name="linker-events"></a>События компоновщика

\ [компоновщика](#linker)
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)\
[EXP_OUTPUT](#exp-output)\
[IMP_LIB_OUTPUT](#imp-lib-output)\
[LIB_OUTPUT](#lib-output)\
[PASS1](#pass1)\
[PRE_LTCG_OPT_REF](#pre-ltcg-opt-ref)\
[LTCG](#ltcg)\
[OPT_REF](#opt-ref)\
[OPT_ICF](#opt-icf)\
[OPT_LBR](#opt-lbr)\
[PASS2](#pass2)

## <a name="event-table"></a>Таблица событий

| Событие | Свойство | Описание |
|--|--|--|
| <a name="back-end-pass"></a>BACK_END_PASS | Тип | Действие |
|  | Parents | [КОМПИЛЯТОРА](#compiler) |
|  | Children | [C2_DLL](#c2-dll) |
|  | Свойства | — Абсолютный путь к входному исходному файлу<br/>-Абсолютный путь к выходному файлу объекта |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[компилерпасс](cpp-event-data-types/compiler-pass.md)<br/>[баккендпасс](cpp-event-data-types/back-end-pass.md) |
|  | Описание | Возникает при запуске и окончании этапа серверной части компилятора. Этот проход отвечает за оптимизацию проанализированного кода C/C++ Source и его преобразование в машинный код. |
| <a name="bottom-up"></a>BOTTOM_UP | Тип | Действие |
|  | Parents | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Children | Нет |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[боттомуп](cpp-event-data-types/bottom-up.md) |
|  | Описание | Происходит при запуске и окончании прохода "на весь анализ программы". |
| <a name="c1-dll"></a>C1_DLL | Тип | Действие |
|  | Parents | [FRONT_END_PASS](#front-end-pass) |
|  | Children | [FRONT_END_FILE](#front-end-file)<br/>[SYMBOL_NAME](#symbol-name)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[C1DLL](cpp-event-data-types/c1-dll.md) |
|  | Описание | Происходит при запуске и окончании вызова *C1. dll* или *c1xx. dll* . Эти библиотеки DLL являются C и C++ внешним интерфейсом компилятора. Они вызываются только драйвером компилятора (*CL. exe*). |
| <a name="c2-dll"></a>C2_DLL | Тип | Действие |
|  | Parents | [BACK_END_PASS](#back-end-pass)<br/>[LTCG](#ltcg) |
|  | Children | [CODE_GENERATION](#code-generation)<br/>[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[C2DLL](cpp-event-data-types/c2-dll.md) |
|  | Описание | Происходит при запуске и окончании вызова *C2. dll* . Эта библиотека DLL является серверной частью компилятора. Он вызывается драйвером компилятора (*CL. exe*). Он также вызывается компоновщиком (*Link. exe*) при использовании создания кода во время компоновки. |
| <a name="code-generation"></a>CODE_GENERATION | Тип | Действие |
|  | Parents | [C2_DLL](#c2-dll) |
|  | Children | [FUNCTION](#function)<br/>[ПОТОК](#thread) |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[Стратегию](cpp-event-data-types/code-generation.md) |
|  | Описание | Происходит при запуске и прекращении этапа формирования кода серверной части. |
| <a name="command-line"></a>COMMAND_LINE | Тип | Простое событие |
|  | Parents | [КОМПИЛЯТОРА](#compiler)<br/>[КОМПОНОВЩИКА](#linker) |
|  | Children | Нет |
|  | Свойства | — Командная строка, которая использовалась для вызова *CL. exe* или *Link. exe.* |
|  | Классы отслеживания | [симпливент](cpp-event-data-types/simple-event.md)<br/>[Команд](cpp-event-data-types/command-line.md) |
|  | Описание | Происходит, когда компилятор и компоновщик выполняются для вычисления командной строки. Вычисленная Командная строка включает все параметры *CL. exe* и *Link. exe* , переданные через файл ответов. Он также включает параметры для *CL. exe* и *Link. exe* , переданные через переменные среды, такие как cl, \_CL\_, link и \_Link\_. |
| <a name="compiler"></a>КОМПИЛЯТОРА | Тип | Действие |
|  | Parents | Нет |
|  | Children | [BACK_END_PASS](#back-end-pass)<br/>[COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[FILE_INPUT](#file-input)<br/>[OBJ_OUTPUT](#obj-output)<br/>[FRONT_END_PASS](#front-end-pass) |
|  | Свойства | — Версия компилятора<br/>— Рабочий каталог<br/>— Абсолютный путь к вызываемому файлу *CL. exe* |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[Вызов](cpp-event-data-types/invocation.md)<br/>[Компилятора](cpp-event-data-types/compiler.md) |
|  | Описание | Происходит при запуске и остановкой вызова *CL. exe* . |
| <a name="environment-variable"></a>ENVIRONMENT_VARIABLE | Тип | Простое событие |
|  | Parents | [КОМПИЛЯТОРА](#compiler)<br/>[КОМПОНОВЩИКА](#linker) |
|  | Children | Нет |
|  | Свойства | — Имя переменной среды;<br/>— Значение переменной среды. |
|  | Классы отслеживания | [симпливент](cpp-event-data-types/simple-event.md)<br/>[EnvironmentVariable](cpp-event-data-types/environment-variable.md) |
|  | Описание | Происходит один раз для каждой существующей переменной среды во время вызова *CL. exe* или *Link. exe* . |
| <a name="executable-image-output"></a>EXECUTABLE_IMAGE_OUTPUT | Тип | Простое событие |
|  | Parents | [КОМПОНОВЩИКА](#linker) |
|  | Children | Нет |
|  | Свойства | — Абсолютный путь к DLL или исполняемому файлу. |
|  | Классы отслеживания | [симпливент](cpp-event-data-types/simple-event.md)<br/>[филеаутпут](cpp-event-data-types/file-output.md)<br/>[ексекутаблеимажеаутпут](cpp-event-data-types/executable-image-output.md) |
|  | Описание | Происходит, когда один из входных данных компоновщика является библиотекой DLL или исполняемым файлом образа. |
| <a name="exp-output"></a>EXP_OUTPUT | Тип | Простое событие |
|  | Parents | [КОМПОНОВЩИКА](#linker) |
|  | Children | Нет |
|  | Свойства | — Абсолютный путь к выходному файлу *. exp* . |
|  | Классы отслеживания | [симпливент](cpp-event-data-types/simple-event.md)<br/>[филеаутпут](cpp-event-data-types/file-output.md)<br/>[експаутпут](cpp-event-data-types/exp-output.md) |
|  | Описание | Происходит, когда один из выходных данных компоновщика является *exp* -файлом. |
| <a name="file-input"></a>FILE_INPUT | Тип | Простое событие |
|  | Parents | [КОМПИЛЯТОРА](#compiler)<br/>[КОМПОНОВЩИКА](#linker) |
|  | Children | Нет |
|  | Свойства | — Абсолютный путь к входному файлу;<br/>— Тип входного файла. |
|  | Классы отслеживания | [симпливент](cpp-event-data-types/simple-event.md)<br/>[филеинпут](cpp-event-data-types/file-input.md) |
|  | Описание | Возникает, чтобы объявить входные данные *CL. exe* или *Link. exe* . |
| <a name="force-inlinee"></a>FORCE_INLINEE | Тип | Простое событие |
|  | Parents | [FUNCTION](#function) |
|  | Children | Нет |
|  | Свойства | — Имя функции принудительного встраивания.<br/>— Размер встроенной функции Force, представленной в виде промежуточного числа инструкций. |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[форцеинлини](cpp-event-data-types/force-inlinee.md) |
|  | Описание | Возникает, когда функция принудительно встроена в другую функцию с помощью ключевого слова `__forceinline`. |
| <a name="front-end-file"></a>FRONT_END_FILE | Тип | Действие |
|  | Parents | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file) |
|  | Children | [FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Свойства | — Абсолютный путь к файлу. |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[фронтендфиле](cpp-event-data-types/front-end-file.md) |
|  | Описание | Происходит при запуске и остановке обработки файла внешним интерфейсом компилятора. Это событие является рекурсивным. Рекурсия происходит, когда внешний интерфейс анализирует включенные файлы. |
| <a name="front-end-pass"></a>FRONT_END_PASS | Тип | Действие |
|  | Parents | [КОМПИЛЯТОРА](#compiler) |
|  | Children | [C1_DLL](#c1-dll) |
|  | Свойства | — Абсолютный путь к входному исходному файлу<br/>-Абсолютный путь к выходному файлу объекта |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[компилерпасс](cpp-event-data-types/compiler-pass.md)<br/>[фронтендпасс](cpp-event-data-types/front-end-pass.md) |
|  | Описание | Происходит при запуске и окончании прохода внешнего интерфейса компилятора. Этот проход отвечает за анализ исходного кода C/C++ и его преобразование в промежуточный язык. |
| <a name="function"></a>ФУНКЦИЙ | Тип | Действие |
|  | Parents | [CODE_GENERATION](#code-generation)<br/>[ПОТОК](#thread)<br/>[TOP_DOWN](#top-down) |
|  | Children | [FORCE_INLINEE](#force-inlinee) |
|  | Свойства | — Имя функции. |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[Компонент](cpp-event-data-types/function.md) |
|  | Описание | Происходит при запуске и завершении создания кода для функции. |
| <a name="imp-lib-output"></a>IMP_LIB_OUTPUT | Тип | Простое событие |
|  | Parents | [КОМПОНОВЩИКА](#linker) |
|  | Children | Нет |
|  | Свойства | — Абсолютный путь к выходному файлу библиотеки импорта. |
|  | Классы отслеживания | [симпливент](cpp-event-data-types/simple-event.md)<br/>[филеаутпут](cpp-event-data-types/file-output.md)<br/>[имплибаутпут](cpp-event-data-types/imp-lib-output.md) |
|  | Описание | Происходит, когда один из выходных данных компоновщика является библиотекой импорта. |
| <a name="lib-output"></a>LIB_OUTPUT | Тип | Простое событие |
|  | Parents | [КОМПОНОВЩИКА](#linker) |
|  | Children | Нет |
|  | Свойства | — Абсолютный путь к выходному файлу статической библиотеки. |
|  | Классы отслеживания | [симпливент](cpp-event-data-types/simple-event.md)<br/>[филеаутпут](cpp-event-data-types/file-output.md)<br/>[либаутпут](cpp-event-data-types/lib-output.md) |
|  | Описание | Происходит, когда один из выходных данных компоновщика является статической библиотекой. |
| <a name="linker"></a>КОМПОНОВЩИКА | Тип | Действие |
|  | Parents | Нет |
|  | Children | [COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)<br/>[EXP_OUTPUT](#exp-output)<br/>[FILE_INPUT](#file-input)<br/>[IMP_LIB_OUTPUT](#imp-lib-output)<br/>[LIB_OUTPUT](#lib-output)<br/>[PASS1](#pass1)<br/>[PASS2](#pass2) |
|  | Свойства | -Версия компоновщика<br/>— Рабочий каталог<br/>— Абсолютный путь к вызываемому *Link. exe* |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[Вызов](cpp-event-data-types/invocation.md)<br/>[Компоновщик](cpp-event-data-types/linker.md) |
|  | Описание | Происходит при запуске и остановкой вызова *Link. exe* . |
| <a name="ltcg"></a>LTCG | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Children | [C2_DLL](#c2-dll) |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[LTCG](cpp-event-data-types/ltcg.md) |
|  | Описание | Происходит при запуске и окончании создания кода во время компоновки. |
| <a name="obj-output"></a>OBJ_OUTPUT | Тип | Простое событие |
|  | Parents | [КОМПИЛЯТОРА](#compiler) |
|  | Children | Нет |
|  | Свойства | — Абсолютный путь к выходному файлу *obj.* |
|  | Классы отслеживания | [симпливент](cpp-event-data-types/simple-event.md)<br/>[филеаутпут](cpp-event-data-types/file-output.md)<br/>[обжаутпут](cpp-event-data-types/obj-output.md) |
|  | Описание | Происходит один раз для каждого вывода *obj* -файла, созданного *CL. exe*. |
| <a name="opt-icf"></a>OPT_ICF | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Children | Нет |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[оптикф](cpp-event-data-types/opt-icf.md) |
|  | Описание | Происходит при запуске и отмене идентичной оптимизации компоновщика COMDAT (/OPT: ICF). |
| <a name="opt-lbr"></a>OPT_LBR | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Children | Нет |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[оптлбр](cpp-event-data-types/opt-lbr.md) |
|  | Описание | Происходит при запуске и окончании оптимизации компоновщика длинной ветви (/OPT: ЛБР). |
| <a name="opt-ref"></a>OPT_REF | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Children | Нет |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[оптреф](cpp-event-data-types/opt-ref.md) |
|  | Описание | Происходит при запуске и окончании оптимизации компоновщика нессылочных функций и исключения данных (/OPT: REF). |
| <a name="pass1"></a>PASS1 | Тип | Действие |
|  | Parents | [КОМПОНОВЩИКА](#linker) |
|  | Children | [LTCG](#ltcg)<br/>[OPT_ICF](#opt-icf)<br/>[OPT_LBR](#opt-lbr)<br/>[OPT_REF](#opt-ref) |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[Pass1](cpp-event-data-types/pass1.md) |
|  | Описание | Происходит при запуске и окончании прохода компоновщика 1. |
| <a name="pass2"></a>PASS2 | Тип | Действие |
|  | Parents | [КОМПОНОВЩИКА](#linker) |
|  | Children | Нет |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[Pass2](cpp-event-data-types/pass2.md) |
|  | Описание | Происходит при запуске и окончании прохода компоновщика 2. |
| <a name="pre-ltcg-opt-ref"></a>PRE_LTCG_OPT_REF | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Children | Нет |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[прелткгоптреф](cpp-event-data-types/pre-ltcg-opt-ref.md) |
|  | Описание | Происходит при запуске и окончании этапа оптимизации компоновщика, который исключает функции и данные без ссылок (/OPT: REF). Это делается до создания кода во время компоновки. |
| <a name="symbol-name"></a>SYMBOL_NAME | Тип | Простое событие |
|  | Parents | [C1_DLL](#c1-dll) |
|  | Children | Нет |
|  | Свойства | — Ключ типа<br/> — Имя типа; |
|  | Классы отслеживания | [симпливент](cpp-event-data-types/simple-event.md)<br/>[симболнаме](cpp-event-data-types/symbol-name.md) |
|  | Описание | Происходит в конце первого этапа передачи: один раз для каждого типа, вовлеченного в создание экземпляров шаблона. Ключ является числовым идентификатором для типа, а имя — его текстовым представлением. Ключи типа уникальны в анализируемой трассировке. Однако разные ключи, поступающие из разных интерфейсных проходов компилятора, могут указывать на один и тот же тип. Сравнение типов между разными проходами внешнего интерфейса компилятора требует использования их имен. SYMBOL_NAME события выдаются в конце внешнего прохода компилятора, после того, как все экземпляры шаблонов созданы. |
| <a name="template-instantiation"></a>TEMPLATE_INSTANTIATION | Тип | Действие |
|  | Parents | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Children | [TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Свойства | — Ключ для специализированного типа<br/>— Ключ для типа первичного шаблона;<br/>— Тип шаблона, экземпляр которого был создан |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[темплатеинстантиатион](cpp-event-data-types/template-instantiation.md) |
|  | Описание | Происходит в начале и в конце создания экземпляра шаблона. Создается экземпляр основного типа шаблона (например, `vector`), что приводит к созданию специализированного типа (например, `std::vector<int>`). Ключ предоставляется для обоих типов. Используйте событие [SYMBOL_NAME](#symbol-name) для преобразования ключа в имя типа. Ключи типа уникальны в анализируемой трассировке. Однако разные ключи, поступающие из разных интерфейсных проходов компилятора, могут указывать на один и тот же тип. Для сравнения типов между различными интерфейсными передачами компилятора требуется использовать имена символов. Это событие является рекурсивным. Рекурсия происходит в некоторых случаях, когда внешний интерфейс создает экземпляр вложенных шаблонов. |
| <a name="thread"></a>ПОТОК | Тип | Действие |
|  | Parents | [CODE_GENERATION](#code-generation)<br/>[TOP_DOWN](#top-down) |
|  | Children | [FUNCTION](#function) |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[Поток](cpp-event-data-types/thread.md) |
|  | Описание | Происходит в начале и в конце выполнения серверного потока компилятора. Приостановленный поток считается завершенным. Пробуждении поток считается запущенным. |
| <a name="top-down"></a>TOP_DOWN | Тип | Действие |
|  | Parents | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Children | [FUNCTION](#function)<br/>[ПОТОК](#thread) |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[топдовн](cpp-event-data-types/top-down.md) |
|  | Описание | Происходит при запуске и окончании прохода по всему анализу программы. |
| <a name="whole-program-analysis"></a>WHOLE_PROGRAM_ANALYSIS | Тип | Действие |
|  | Parents | [C2_DLL](#c2-dll) |
|  | Children | [BOTTOM_UP](#bottom-up)<br/>[TOP_DOWN](#top-down) |
|  | Свойства | Нет |
|  | Классы отслеживания | [Действие](cpp-event-data-types/activity.md)<br/>[вхолепрограманалисис](cpp-event-data-types/whole-program-analysis.md) |
|  | Описание | Происходит при запуске и окончании фазы анализа всей программы при создании кода во время компоновки. |

::: moniker-end
