---
title: 'СЗ Сборка Исследования SDK: таблица событий'
description: Ссылка на события для Визуальной студии СЗ Построить Исследования SDK
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Events
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 932b78347e05d313e7962da2fdff8c3454dec963
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324146"
---
# <a name="c-build-insights-sdk-event-table"></a>СЗ Сборка Исследования SDK: таблица событий

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

## <a name="compiler-events"></a>Мероприятия компилятора

[Компилятора](#compiler)\
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[OBJ_OUTPUT](#obj-output)\
[FRONT_END_PASS](#front-end-pass)\
[BACK_END_PASS](#back-end-pass)

## <a name="compiler-front-end-events"></a>Компилятор фронт-энд событий

[C1_DLL](#c1-dll)\
[FRONT_END_FILE](#front-end-file)\
[TEMPLATE_INSTANTIATION](#template-instantiation)\
[SYMBOL_NAME](#symbol-name)

## <a name="compiler-back-end-events"></a>События компилятора бэк-энда

[C2_DLL](#c2-dll)\
[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis)\
[TOP_DOWN](#top-down)\
[BOTTOM_UP](#bottom-up)\
[CODE_GENERATION](#code-generation)\
[Поток](#thread)\
[Функции](#function)\
[FORCE_INLINEE](#force-inlinee)

## <a name="linker-events"></a>События Linker

[Компоновщик](#linker)\
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
|  | Parents | [Компилятора](#compiler) |
|  | Дети | [C2_DLL](#c2-dll) |
|  | Свойства | - Абсолютный путь к исходным файлам ввода<br/>- Абсолютный путь к файлу объекта вывода |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[BackEndPass](cpp-event-data-types/back-end-pass.md) |
|  | Описание | Происходит в начале и остановке компилятора бэк-энд проход. Этот пропуск отвечает за оптимизацию разображенный исходный код C/C и преобразование его в машинный код. |
| <a name="bottom-up"></a>BOTTOM_UP | Тип | Действие |
|  | Parents | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Дети | Отсутствуют |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[БоттомАп](cpp-event-data-types/bottom-up.md) |
|  | Описание | Происходит в начале и остановке прохода снизу вверх всего программного анализа. |
| <a name="c1-dll"></a>C1_DLL | Тип | Действие |
|  | Parents | [FRONT_END_PASS](#front-end-pass) |
|  | Дети | [FRONT_END_FILE](#front-end-file)<br/>[SYMBOL_NAME](#symbol-name)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[C1DLL](cpp-event-data-types/c1-dll.md) |
|  | Описание | Происходит в начале и остановке *c1.dll* или *c1xx.dll* вызова. Эти DLL являются передней оконечной передней частью компилятора C и C.'. Они вызываются исключительно драйвером компилятора *(cl.exe*). |
| <a name="c2-dll"></a>C2_DLL | Тип | Действие |
|  | Parents | [BACK_END_PASS](#back-end-pass)<br/>[LTCG](#ltcg) |
|  | Дети | [CODE_GENERATION](#code-generation)<br/>[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[C2DLL](cpp-event-data-types/c2-dll.md) |
|  | Описание | Происходит в начале и остановке *вызова c2.dll.* Этот DLL является задней частью компилятора. Это называется драйвером компилятора *(cl.exe*). Он также вызывается linker *(link.exe*), когда используется генерация кода времени ссылки. |
| <a name="code-generation"></a>CODE_GENERATION | Тип | Действие |
|  | Parents | [C2_DLL](#c2-dll) |
|  | Дети | [Функции](#function)<br/>[Поток](#thread) |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[CodeGeneration](cpp-event-data-types/code-generation.md) |
|  | Описание | Происходит в начале и остановке фазы генерации кода задней части. |
| <a name="command-line"></a>COMMAND_LINE | Тип | Простое событие |
|  | Parents | [Компилятора](#compiler)<br/>[Компоновщик](#linker) |
|  | Дети | Отсутствуют |
|  | Свойства | - Командная строка, которая использовалась для ссылки *cl.exe* или *link.exe* |
|  | Классы захвата | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Командный пункт](cpp-event-data-types/command-line.md) |
|  | Описание | Происходит, когда компилятор и связующий выполняются оценки командной строки. Оцененная командная строка включает в себя все параметры *cl.exe* и *link.exe,* передаваемые через файл ответа. Она также включает в себя параметры *cl.exe* и *link.exe* \_передается через переменные среды, такие как CL, CL\_, LINK, и \_LINK\_. |
| <a name="compiler"></a>Компилятора | Тип | Действие |
|  | Parents | Отсутствуют |
|  | Дети | [BACK_END_PASS](#back-end-pass)<br/>[COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[FILE_INPUT](#file-input)<br/>[OBJ_OUTPUT](#obj-output)<br/>[FRONT_END_PASS](#front-end-pass) |
|  | Свойства | - Вариант компилятора<br/>- Рабочий каталог<br/>- Абсолютный путь к вызываемому *cl.exe* |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[Вызов](cpp-event-data-types/invocation.md)<br/>[Компилятор](cpp-event-data-types/compiler.md) |
|  | Описание | Происходит в начале и остановке *вызова cl.exe.* |
| <a name="environment-variable"></a>ENVIRONMENT_VARIABLE | Тип | Простое событие |
|  | Parents | [Компилятора](#compiler)<br/>[Компоновщик](#linker) |
|  | Дети | Отсутствуют |
|  | Свойства | - Название переменной среды<br/>- Значение переменной среды. |
|  | Классы захвата | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[EnvironmentVariable](cpp-event-data-types/environment-variable.md) |
|  | Описание | Происходит один раз для каждой существующей переменной среды в момент вызова *cl.exe* или *link.exe.* |
| <a name="executable-image-output"></a>EXECUTABLE_IMAGE_OUTPUT | Тип | Простое событие |
|  | Parents | [Компоновщик](#linker) |
|  | Дети | Отсутствуют |
|  | Свойства | - Абсолютный путь к DLL или исполняемый выходный файл. |
|  | Классы захвата | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[ФайлВыход](cpp-event-data-types/file-output.md)<br/>[ИсполняемыйИзображениеВыход](cpp-event-data-types/executable-image-output.md) |
|  | Описание | Происходит, когда одним из входов ссылок является DLL или исполняемый файл изображения. |
| <a name="exp-output"></a>EXP_OUTPUT | Тип | Простое событие |
|  | Parents | [Компоновщик](#linker) |
|  | Дети | Отсутствуют |
|  | Свойства | - Абсолютный путь к выходу файла *.exp.* |
|  | Классы захвата | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[ФайлВыход](cpp-event-data-types/file-output.md)<br/>[ExpOutput](cpp-event-data-types/exp-output.md) |
|  | Описание | Происходит, когда один из выходов связующим звеном является файлом *.exp.* |
| <a name="file-input"></a>FILE_INPUT | Тип | Простое событие |
|  | Parents | [Компилятора](#compiler)<br/>[Компоновщик](#linker) |
|  | Дети | Отсутствуют |
|  | Свойства | - Абсолютный путь к вхотвому файлу<br/>- Тип ввода файла |
|  | Классы захвата | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileInput](cpp-event-data-types/file-input.md) |
|  | Описание | Происходит объявление *о ввода cl.exe* или *link.exe.* |
| <a name="force-inlinee"></a>FORCE_INLINEE | Тип | Простое событие |
|  | Parents | [Функции](#function) |
|  | Дети | Отсутствуют |
|  | Свойства | - Название силовой функции.<br/>- Размер функции, подстеженной силой, представленкакой промежуточным подсчетом инструкций. |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[ForceInlinee](cpp-event-data-types/force-inlinee.md) |
|  | Описание | Происходит, когда функция в настоящее время силой встроены в другую функцию с помощью `__forceinline` ключевого слова. |
| <a name="front-end-file"></a>FRONT_END_FILE | Тип | Действие |
|  | Parents | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file) |
|  | Дети | [FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Свойства | - Абсолютный путь к файлу. |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[FrontEndFile](cpp-event-data-types/front-end-file.md) |
|  | Описание | Происходит, когда передний конец компилятора запускается и останавливает обработку файла. Это событие является рекурсивным. Рекурсия происходит, когда передний конец разбора включены файлы. |
| <a name="front-end-pass"></a>FRONT_END_PASS | Тип | Действие |
|  | Parents | [Компилятора](#compiler) |
|  | Дети | [C1_DLL](#c1-dll) |
|  | Свойства | - Абсолютный путь к исходным файлам ввода<br/>- Абсолютный путь к файлу объекта вывода |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[FrontEndPass](cpp-event-data-types/front-end-pass.md) |
|  | Описание | Происходит в начале и остановке переднего прохода компилятора. Этот пропуск отвечает за разбор исходного кода C/C и преобразование его на промежуточный язык. |
| <a name="function"></a>Функции | Тип | Действие |
|  | Parents | [CODE_GENERATION](#code-generation)<br/>[Поток](#thread)<br/>[TOP_DOWN](#top-down) |
|  | Дети | [FORCE_INLINEE](#force-inlinee) |
|  | Свойства | - Название функции |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[Функция](cpp-event-data-types/function.md) |
|  | Описание | Происходит при запуске и завершении генерации кода для функции. |
| <a name="imp-lib-output"></a>IMP_LIB_OUTPUT | Тип | Простое событие |
|  | Parents | [Компоновщик](#linker) |
|  | Дети | Отсутствуют |
|  | Свойства | - Абсолютный путь к файлу вывода библиотеки импорта. |
|  | Классы захвата | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[ФайлВыход](cpp-event-data-types/file-output.md)<br/>[ImpLibOutput](cpp-event-data-types/imp-lib-output.md) |
|  | Описание | Происходит, когда один из выходов linker является библиотекой импорта. |
| <a name="lib-output"></a>LIB_OUTPUT | Тип | Простое событие |
|  | Parents | [Компоновщик](#linker) |
|  | Дети | Отсутствуют |
|  | Свойства | - Абсолютный путь к статическому файлу вывода библиотеки. |
|  | Классы захвата | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[ФайлВыход](cpp-event-data-types/file-output.md)<br/>[LibOutput](cpp-event-data-types/lib-output.md) |
|  | Описание | Происходит, когда один из выходов связующим является статической библиотекой. |
| <a name="linker"></a>Компоновщик | Тип | Действие |
|  | Parents | Отсутствуют |
|  | Дети | [COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)<br/>[EXP_OUTPUT](#exp-output)<br/>[FILE_INPUT](#file-input)<br/>[IMP_LIB_OUTPUT](#imp-lib-output)<br/>[LIB_OUTPUT](#lib-output)<br/>[PASS1](#pass1)<br/>[PASS2](#pass2) |
|  | Свойства | - Ссылка версия<br/>- Рабочий каталог<br/>- Абсолютный путь к вызываемым *link.exe* |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[Вызов](cpp-event-data-types/invocation.md)<br/>[Компоновщик](cpp-event-data-types/linker.md) |
|  | Описание | Происходит в начале и остановке *link.exe* вызова. |
| <a name="ltcg"></a>LTCG | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Дети | [C2_DLL](#c2-dll) |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[LTCG](cpp-event-data-types/ltcg.md) |
|  | Описание | Происходит в начале и остановке генерации кода времени ссылки. |
| <a name="obj-output"></a>OBJ_OUTPUT | Тип | Простое событие |
|  | Parents | [Компилятора](#compiler) |
|  | Дети | Отсутствуют |
|  | Свойства | - Абсолютный путь к выходу *файла .obj* |
|  | Классы захвата | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[ФайлВыход](cpp-event-data-types/file-output.md)<br/>[ObjOutput](cpp-event-data-types/obj-output.md) |
|  | Описание | Происходит один раз для каждого *выхода .obj* произведенного *cl.exe*. |
| <a name="opt-icf"></a>OPT_ICF | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Дети | Отсутствуют |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[OptICF](cpp-event-data-types/opt-icf.md) |
|  | Описание | Происходит в начале и остановке идентичной оптимизации связующего соединения COMDAT (/OPT:ICF). |
| <a name="opt-lbr"></a>OPT_LBR | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Дети | Отсутствуют |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[OptLBR](cpp-event-data-types/opt-lbr.md) |
|  | Описание | Происходит в начале и остановке длинной ветки (/OPT:LBR) оптимизация связующим звеном. |
| <a name="opt-ref"></a>OPT_REF | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Дети | Отсутствуют |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[OptRef](cpp-event-data-types/opt-ref.md) |
|  | Описание | Происходит в начале и остановке неоплачиваемых функций и устранения данных (/OPT:REF) оптимизация связующим звеном. |
| <a name="pass1"></a>PASS1 | Тип | Действие |
|  | Parents | [Компоновщик](#linker) |
|  | Дети | [LTCG](#ltcg)<br/>[OPT_ICF](#opt-icf)<br/>[OPT_LBR](#opt-lbr)<br/>[OPT_REF](#opt-ref) |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[Pass1](cpp-event-data-types/pass1.md) |
|  | Описание | Происходит в начале и остановке прохода связующее 1. |
| <a name="pass2"></a>PASS2 | Тип | Действие |
|  | Parents | [Компоновщик](#linker) |
|  | Дети | Отсутствуют |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[Pass2](cpp-event-data-types/pass2.md) |
|  | Описание | Происходит в начале и остановке прохода связующее 2. |
| <a name="pre-ltcg-opt-ref"></a>PRE_LTCG_OPT_REF | Тип | Действие |
|  | Parents | [PASS1](#pass1) |
|  | Дети | Отсутствуют |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[ПреЛТКГОпреф](cpp-event-data-types/pre-ltcg-opt-ref.md) |
|  | Описание | Происходит в начале и остановке пропуска оптимизации связующее звено, который устраняет неотъемлимые функции и данные (/OPT:REF). Это делается до генерации кода времени ссылки. |
| <a name="symbol-name"></a>SYMBOL_NAME | Тип | Простое событие |
|  | Parents | [C1_DLL](#c1-dll) |
|  | Дети | Отсутствуют |
|  | Свойства | - Тип ключа<br/> - Имя типа |
|  | Классы захвата | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[СимволИ](cpp-event-data-types/symbol-name.md) |
|  | Описание | Происходит в конце переднего конца прохода: один раз для каждого типа, участвующих в шаблон моментов. Ключ является числовым идентификатором для типа, в то время как имя является его текстовым представлением. Введите ключи являются уникальными в пределах трассировки. Тем не менее, различные клавиши, поступающие из различных компилятор передний конец проходит может указывать на тот же тип. Сравнение типов между различными передними проходами компилятора требует использования их имен. SYMBOL_NAME события излучаются в конце переднего прохода компилятора, после того, как все моментгности шаблона имели место. |
| <a name="template-instantiation"></a>TEMPLATE_INSTANTIATION | Тип | Действие |
|  | Parents | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Дети | [TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Свойства | - Ключ для специализированного типа<br/>- Ключ для типа первичного шаблона<br/>- Вид шаблона, который был мгновенно |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[ШаблонМеймикция](cpp-event-data-types/template-instantiation.md) |
|  | Описание | Происходит в начале и конце мгновенного шаблона. Основной тип шаблона `vector`(например, ) мгновенно, в результате `std::vector<int>`чего специализированный тип (например, ). Ключ дается для обоих типов. Используйте [событие SYMBOL_NAME](#symbol-name) для преобразования ключа в имя типа. Введите ключи являются уникальными в пределах трассировки. Тем не менее, различные клавиши, поступающие из различных компилятор передний конец проходит может указывать на тот же тип. Сравнение типов между различными передними проходами компилятора требует использования имен символов. Это событие является рекурсивным. Рекурсия происходит в некоторых случаях, когда передний конец мгновенно вложенных шаблонов. |
| <a name="thread"></a>Поток | Тип | Действие |
|  | Parents | [CODE_GENERATION](#code-generation)<br/>[TOP_DOWN](#top-down) |
|  | Дети | [Функции](#function) |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[Поток](cpp-event-data-types/thread.md) |
|  | Описание | Происходит в начале и конце выполнения обратного потока компилятора. Приостановленный поток считается завершенным. Просевшаяся поток считается запущенной. |
| <a name="top-down"></a>TOP_DOWN | Тип | Действие |
|  | Parents | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Дети | [Функции](#function)<br/>[Поток](#thread) |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[ТопДаун](cpp-event-data-types/top-down.md) |
|  | Описание | Происходит в начале и остановке пропуска сверху вниз всего анализа программы. |
| <a name="whole-program-analysis"></a>WHOLE_PROGRAM_ANALYSIS | Тип | Действие |
|  | Parents | [C2_DLL](#c2-dll) |
|  | Дети | [BOTTOM_UP](#bottom-up)<br/>[TOP_DOWN](#top-down) |
|  | Свойства | Отсутствуют |
|  | Классы захвата | [Действие](cpp-event-data-types/activity.md)<br/>[ЦельПрограммноеАнализ](cpp-event-data-types/whole-program-analysis.md) |
|  | Описание | Происходит в начале и остановке фазы анализа всей программы генерации кода времени ссылки. |

::: moniker-end
