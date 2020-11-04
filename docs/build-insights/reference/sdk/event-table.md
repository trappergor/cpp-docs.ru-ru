---
title: 'Пакет SDK Аналитики сборок C++: таблица событий'
description: Справочник по событиям для пакета SDK Аналитики сборок C++ для Visual Studio
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Events
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2a6270e8e166bb38754314fcb308b86232dbb68b
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922913"
---
# <a name="c-build-insights-sdk-event-table"></a>Пакет SDK Аналитики сборок C++: таблица событий

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

## <a name="compiler-events"></a>События компилятора

[COMPILER](#compiler)\
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

## <a name="compiler-back-end-events"></a>События внутренней части компилятора

[C2_DLL](#c2-dll)\
[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis)\
[TOP_DOWN](#top-down)\
[BOTTOM_UP](#bottom-up)\
[CODE_GENERATION](#code-generation)\
[THREAD](#thread)\
[FUNCTION](#function)\
[FORCE_INLINEE](#force-inlinee)

## <a name="linker-events"></a>События компоновщика

[LINKER](#linker)\
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

| Событие | Свойство | Описание: |
|--|--|--|
| <a name="back-end-pass"></a> BACK_END_PASS | Тип | Действие |
|  | Parents | [COMPILER](#compiler) |
|  | Дети | [C2_DLL](#c2-dll) |
|  | Свойства | — Абсолютный путь к входному исходному файлу<br/>— Абсолютный путь к результирующему объектному файлу |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[BackEndPass](cpp-event-data-types/back-end-pass.md) |
|  | Описание | Возникает при запуске и окончании прохода внутренней части компилятора. Этот проход отвечает за оптимизацию проанализированного исходного кода C/C++ и его преобразование в машинный код. |
| <a name="bottom-up"></a> BOTTOM_UP | Тип | Действие |
|  | Parents | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Дети | None |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[BottomUp](cpp-event-data-types/bottom-up.md) |
|  | Описание | Возникает при запуске и окончании этапа анализа всей программы снизу вверх. |
| <a name="c1-dll"></a> C1_DLL | Тип | Действие |
|  | Parents | [FRONT_END_PASS](#front-end-pass) |
|  | Дети | [FRONT_END_FILE](#front-end-file)<br/>[SYMBOL_NAME](#symbol-name)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[C1DLL](cpp-event-data-types/c1-dll.md) |
|  | Описание | Возникает при запуске и окончании вызова *c1.dll* или *c1xx.dll*. Эти библиотеки DLL являются внешним интерфейсом компилятора для C и C++. Они вызываются только драйвером компилятора ( *cl.exe* ). |
| <a name="c2-dll"></a> C2_DLL | Тип | Действие |
|  | Parents | [BACK_END_PASS](#back-end-pass)<br/>[LTCG](#ltcg) |
|  | Дети | [CODE_GENERATION](#code-generation)<br/>[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[C2DLL](cpp-event-data-types/c2-dll.md) |
|  | Описание | Возникает при запуске и окончании вызова *c2.dll*. Эта библиотека DLL является внутренней частью компилятора. Она вызывается драйвером компилятора ( *cl.exe* ). Также она вызывается компоновщиком ( *link.exe* ), если используется создание кода во время компоновки. |
| <a name="code-generation"></a> CODE_GENERATION | Тип | Действие |
|  | Parents | [C2_DLL](#c2-dll) |
|  | Дети | [FUNCTION](#function)<br/>[THREAD](#thread) |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[CodeGeneration](cpp-event-data-types/code-generation.md) |
|  | Описание | Возникает при запуске и прекращении этапа создания кода в серверной части. |
| <a name="command-line"></a> COMMAND_LINE | Тип | Простое событие |
|  | Parents | [COMPILER](#compiler)<br/>[LINKER](#linker) |
|  | Дети | None |
|  | Свойства | — Командная строка, которая использовалась для вызова *cl.dll* или *link.dll*. |
|  | Классы фиксации | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[CommandLine](cpp-event-data-types/command-line.md) |
|  | Описание | Возникает, когда компилятор и компоновщик завершают анализ командной строки. Проанализированная командная строка включает все параметры *cl.dll* или *link.dll* , передаваемые через файл ответов. Она также включает параметры *cl.dll* или *link.dll* , переданные через переменные среды, как, например, CL, \_CL\_, LINK и \_LINK\_. |
| <a name="compiler"></a> COMPILER | Тип | Действие |
|  | Parents | None |
|  | Дети | [BACK_END_PASS](#back-end-pass)<br/>[COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[FILE_INPUT](#file-input)<br/>[OBJ_OUTPUT](#obj-output)<br/>[FRONT_END_PASS](#front-end-pass) |
|  | Свойства | — Версия компилятора<br/>— Рабочий каталог<br/>— Абсолютный путь к вызываемому файлу *cl.exe* |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[Вызов](cpp-event-data-types/invocation.md)<br/>[Компилятор](cpp-event-data-types/compiler.md) |
|  | Описание | Возникает при запуске и окончании вызова *cl.exe*. |
| <a name="environment-variable"></a> ENVIRONMENT_VARIABLE | Тип | Простое событие |
|  | Parents | [COMPILER](#compiler)<br/>[LINKER](#linker) |
|  | Дети | None |
|  | Свойства | — Имя переменной среды.<br/>— Значение переменной среды. |
|  | Классы фиксации | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[EnvironmentVariable](cpp-event-data-types/environment-variable.md) |
|  | Описание | Возникает один раз для каждой существующей переменной среды в момент вызова *cl.dll* или *link.dll*. |
| <a name="executable-image-output"></a> EXECUTABLE_IMAGE_OUTPUT | Тип | Простое событие |
|  | Parents | [LINKER](#linker) |
|  | Дети | None |
|  | Свойства | — Абсолютный путь к выходному файлу библиотеки DLL или исполняемого файла. |
|  | Классы фиксации | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ExecutableImageOutput](cpp-event-data-types/executable-image-output.md) |
|  | Описание | Возникает, когда на вход компоновщика поступает библиотека DLL или исполняемый файл образа. |
| <a name="exp-output"></a> EXP_OUTPUT | Тип | Простое событие |
|  | Parents | [LINKER](#linker) |
|  | Дети | None |
|  | Свойства | — Абсолютный путь к выходному файлу *.exp*. |
|  | Классы фиксации | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ExpOutput](cpp-event-data-types/exp-output.md) |
|  | Описание | Возникает, когда в качестве выхода компоновщику предлагается файл *.exp*. |
| <a name="file-input"></a> FILE_INPUT | Тип | Простое событие |
|  | Parents | [COMPILER](#compiler)<br/>[LINKER](#linker) |
|  | Дети | None |
|  | Свойства | — Абсолютный путь к входному файлу<br/>— Тип входного файла |
|  | Классы фиксации | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileInput](cpp-event-data-types/file-input.md) |
|  | Описание | Возникает, чтобы объявить входные данные для *cl.dll* или *link.dll*. |
| <a name="force-inlinee"></a> FORCE_INLINEE | Тип | Простое событие |
|  | Parents | [FUNCTION](#function) |
|  | Дети | None |
|  | Свойства | — Имя принудительно встраиваемой функции.<br/>— Размер принудительно встраиваемой функции, выраженный в числе инструкций промежуточного языка. |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[ForceInlinee](cpp-event-data-types/force-inlinee.md) |
|  | Описание | Возникает, когда функция принудительно встраивается в другую функцию с помощью ключевого слова **`__forceinline`** . |
| <a name="front-end-file"></a> FRONT_END_FILE | Тип | Действие |
|  | Parents | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file) |
|  | Дети | [FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Свойства | — Абсолютный путь к файлу. |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[FrontEndFile](cpp-event-data-types/front-end-file.md) |
|  | Описание | Возникает при запуске и остановке обработки файла внешним интерфейсом компилятора. Это событие является рекурсивным. Рекурсия происходит, когда внешний интерфейс анализирует включенные файлы. |
| <a name="front-end-pass"></a> FRONT_END_PASS | Тип | Действие |
|  | Parents | [COMPILER](#compiler) |
|  | Дети | [C1_DLL](#c1-dll) |
|  | Свойства | — Абсолютный путь к входному исходному файлу<br/>— Абсолютный путь к результирующему объектному файлу |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[FrontEndPass](cpp-event-data-types/front-end-pass.md) |
|  | Описание | Возникает при запуске и окончании этапа внешнего интерфейса компилятора. Этот этап включает анализ исходного кода C или C++ и его преобразование в промежуточный язык. |
| <a name="function"></a> FUNCTION | Тип | Действие |
|  | Parents | [CODE_GENERATION](#code-generation)<br/>[THREAD](#thread)<br/>[TOP_DOWN](#top-down) |
|  | Дети | [FORCE_INLINEE](#force-inlinee) |
|  | Свойства | — Имя функции. |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[Компонент](cpp-event-data-types/function.md) |
|  | Описание | Возникает при запуске и завершении создания кода для функции. |
| <a name="imp-lib-output"></a> IMP_LIB_OUTPUT | Тип | Простое событие |
|  | Parents | [LINKER](#linker) |
|  | Дети | None |
|  | Свойства | — Абсолютный путь к выходному файлу библиотеки импорта. |
|  | Классы фиксации | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ImpLibOutput](cpp-event-data-types/imp-lib-output.md) |
|  | Описание | Возникает, когда в качестве выхода компоновщику предлагается библиотека импорта. |
| <a name="lib-output"></a> LIB_OUTPUT | Тип | Простое событие |
|  | Parents | [LINKER](#linker) |
|  | Дети | None |
|  | Свойства | — Абсолютный путь к выходному файлу статической библиотеки. |
|  | Классы фиксации | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[LibOutput](cpp-event-data-types/lib-output.md) |
|  | Описание | Возникает, когда в качестве выхода компоновщику предлагается статическая библиотека. |
| <a name="linker"></a> LINKER | Тип | Действие |
|  | Parents | None |
|  | Дети | [COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)<br/>[EXP_OUTPUT](#exp-output)<br/>[FILE_INPUT](#file-input)<br/>[IMP_LIB_OUTPUT](#imp-lib-output)<br/>[LIB_OUTPUT](#lib-output)<br/>[PASS1](#pass1)<br/>[PASS2](#pass2) |
|  | Свойства | — Версия компоновщика<br/>— Рабочий каталог<br/>— Абсолютный путь к вызываемому файлу *link.exe* |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[Вызов](cpp-event-data-types/invocation.md)<br/>[Компоновщик](cpp-event-data-types/linker.md) |
|  | Описание | Возникает при запуске и окончании вызова *link.exe*. |
| <a name="ltcg"></a> LTCG | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Дети | [C2_DLL](#c2-dll) |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[LTCG](cpp-event-data-types/ltcg.md) |
|  | Описание | Возникает при запуске и окончании этапа создания кода во время компоновки. |
| <a name="obj-output"></a> OBJ_OUTPUT | Тип | Простое событие |
|  | Parents | [COMPILER](#compiler) |
|  | Дети | None |
|  | Свойства | — Абсолютный путь к выходному файлу *.obj*. |
|  | Классы фиксации | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ObjOutput](cpp-event-data-types/obj-output.md) |
|  | Описание | Возникает один раз для каждого выходного файла *.obj* , создаваемого *cl.exe*. |
| <a name="opt-icf"></a> OPT_ICF | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Дети | None |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[OptICF](cpp-event-data-types/opt-icf.md) |
|  | Описание | Возникает при запуске и завершении этапа оптимизации компоновщика для удаления идентичных COMDAT (/OPT:ICF). |
| <a name="opt-lbr"></a> OPT_LBR | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Дети | None |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[OptLBR](cpp-event-data-types/opt-lbr.md) |
|  | Описание | Возникает при запуске и окончании этапа оптимизации компоновщика для длинной ветви (/OPT:LBR). |
| <a name="opt-ref"></a> OPT_REF | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Дети | None |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[OptRef](cpp-event-data-types/opt-ref.md) |
|  | Описание | Возникает при запуске и окончании этапа оптимизации компоновщика для удаления функций и данных без ссылок на них (/OPT:REF). |
| <a name="pass1"></a> PASS1 | Тип | Действие |
|  | Parents | [LINKER](#linker) |
|  | Дети | [LTCG](#ltcg)<br/>[OPT_ICF](#opt-icf)<br/>[OPT_LBR](#opt-lbr)<br/>[OPT_REF](#opt-ref) |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[Pass1](cpp-event-data-types/pass1.md) |
|  | Описание | Возникает при запуске и окончании первого этапа компоновщика. |
| <a name="pass2"></a> PASS2 | Тип | Действие |
|  | Parents | [LINKER](#linker) |
|  | Дети | None |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[Pass2](cpp-event-data-types/pass2.md) |
|  | Описание | Возникает при запуске и окончании второго этапа компоновщика. |
| <a name="pre-ltcg-opt-ref"></a> PRE_LTCG_OPT_REF | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Дети | None |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[PreLTCGOptRef](cpp-event-data-types/pre-ltcg-opt-ref.md) |
|  | Описание | Возникает при запуске и окончании этапа оптимизации компоновщика, который удаляет функции и данные без ссылок на них (/OPT:REF). Это происходит до создания кода во время компоновки. |
| <a name="symbol-name"></a> SYMBOL_NAME | Тип | Простое событие |
|  | Parents | [C1_DLL](#c1-dll) |
|  | Дети | None |
|  | Свойства | — Ключ типа<br/> — Имя типа |
|  | Классы фиксации | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[SymbolName](cpp-event-data-types/symbol-name.md) |
|  | Описание | Возникает в конце первого этапа внешнего интерфейса, по одному разу для каждого типа, участвующего в создании экземпляров шаблона. Этот ключ является числовым идентификатором типа, а имя — его текстовым представлением. Ключи типа уникальны в пределах анализируемой трассировки. Но разные ключи, созданные на разных этапах внешнего интерфейса компилятора, могут указывать на один и тот же тип. Чтобы сравнивать типы, полученные на разных этапах внешнего интерфейса компилятора, нужно использовать их имена. События SYMBOL_NAME возникают в конце этапа внешнего интерфейса компилятора, после создания всех экземпляров шаблонов. |
| <a name="template-instantiation"></a> TEMPLATE_INSTANTIATION | Тип | Действие |
|  | Parents | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Дети | [TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Свойства | — Ключ для специализированного типа<br/>— Ключ для типа первичного шаблона<br/>— Тип шаблона, экземпляр которого был создан |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[TemplateInstantiation](cpp-event-data-types/template-instantiation.md) |
|  | Описание | Возникает в начале и в конце этапа создания экземпляра шаблона. Создается экземпляр основного типа шаблона (например, `vector`), что приводит к созданию специализированного типа (например, `std::vector<int>`). Предоставляются ключи для обоих типов. Используйте событие [SYMBOL_NAME](#symbol-name), чтобы преобразовать ключ в имя типа. Ключи типа уникальны в пределах анализируемой трассировки. Но разные ключи, созданные на разных этапах внешнего интерфейса компилятора, могут указывать на один и тот же тип. Чтобы сравнивать типы, полученные на разных этапах внешнего интерфейса компилятора, нужно использовать символические имена. Это событие является рекурсивным. Рекурсия происходит, когда внешний интерфейс создает экземпляр шаблона с вложением. |
| <a name="thread"></a> THREAD | Тип | Действие |
|  | Parents | [CODE_GENERATION](#code-generation)<br/>[TOP_DOWN](#top-down) |
|  | Дети | [FUNCTION](#function) |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[Поток](cpp-event-data-types/thread.md) |
|  | Описание | Возникает в начале и в конце этапа выполнения потока внутренней части компилятора. Приостанавливаемый поток считается завершаемым. Пробуждаемый поток считается запускаемым. |
| <a name="top-down"></a> TOP_DOWN | Тип | Действие |
|  | Parents | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Дети | [FUNCTION](#function)<br/>[THREAD](#thread) |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[TopDown](cpp-event-data-types/top-down.md) |
|  | Описание | Возникает при запуске и окончании этапа анализа всей программы сверху вниз. |
| <a name="whole-program-analysis"></a> WHOLE_PROGRAM_ANALYSIS | Тип | Действие |
|  | Parents | [C2_DLL](#c2-dll) |
|  | Дети | [BOTTOM_UP](#bottom-up)<br/>[TOP_DOWN](#top-down) |
|  | Свойства | None |
|  | Классы фиксации | [Действие](cpp-event-data-types/activity.md)<br/>[WholeProgramAnalysis](cpp-event-data-types/whole-program-analysis.md) |
|  | Описание | Возникает при запуске и окончании этапа анализа всей программы при создании кода во время компоновки. |

::: moniker-end
