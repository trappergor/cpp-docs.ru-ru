---
title: Параметры компилятора в алфавитном порядке | Документы Microsoft
ms.custom: ''
ms.date: 02/22/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- compiler options, C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 259958d789ed189c38b75fe708034fb0d76fc35c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-options-listed-alphabetically"></a>Параметры компилятора в алфавитном порядке

Ниже приведен полный список параметров компилятора в алфавитном порядке. Список, в разделе [параметры компилятора, упорядоченные по категориям](compiler-options-listed-by-category.md).

|Параметр|Цель|
|------------|-------------|
|[@](at-specify-a-compiler-response-file.md)|Указывает файл ответа.|
|[/?](help-compiler-command-line-help.md)|Отображает список параметров компилятора.|
|[/AI](ai-specify-metadata-directories.md)|Указывает каталог поиска для разрешения ссылок на файлы, указанные в директиве [#using](../../preprocessor/hash-using-directive-cpp.md) .|
|[/ analyze](analyze-code-analysis.md)|Включение анализа кода.|
|[/ arch](arch-minimum-cpu-architecture.md)|Задает архитектуру для создания кода.|
|[/ await](await-enable-coroutine-support.md)|Включите расширения сопрограммы (возобновляемые функции).|
|[/ bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md)|Увеличивает число адресуемых секций в OBJ-файле.|
|[/C](c-preserve-comments-during-preprocessing.md)|Сохраняет комментарии на этапе предварительной обработки.|
|[/c](c-compile-without-linking.md)|Задает компиляцию без компоновки.|
|[/ cgthreads](cgthreads-code-generation-threads.md)|Задает число потоков cl.exe, используемых для оптимизации и создания кода.|
|[/clr](clr-common-language-runtime-compilation.md)|Создает выходной файл, предназначенный для выполнения в среде CLR.|
|[/constexpr](constexpr-control-constexpr-evaluation.md)|Вычисление constexpr элемента управления во время компиляции.|
|[/D](d-preprocessor-definitions.md)|Определяет константы и макросы.|
|[/Diagnostics](diagnostics-compiler-diagnostic-options.md)|Определяет формат диагностических сообщений.|
|[/doc](doc-process-documentation-comments-c-cpp.md)|Сведение документирующих комментариев в XML-файл.|
|[/E](e-preprocess-to-stdout.md)|Копирует выходные данные препроцессора в стандартный вывод.|
|[/EH](eh-exception-handling-model.md)|Задает модель обработки исключений.|
|[/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Копирует выходные данные препроцессора в стандартный вывод.|
|[/ ERRORREPORT](errorreport-report-internal-compiler-errors.md)|Разрешает передавать данные о внутренних ошибках компилятора (ICE) непосредственно в группу Visual C++.|
|[/ Execution-CharSet](execution-charset-set-execution-character-set.md)|Набор символов исполнения набора.|
|[/F](f-set-stack-size.md)|Задает размер стека.|
|[/ favor](favor-optimize-for-architecture-specifics.md)|Формирует код, оптимизированный для конкретной архитектуры [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] или для специфики микроархитектур в архитектурах AMD64 и EM64T.|
|[/FA](fa-fa-listing-file.md)|Создает файл листинга.|
|[/FA](fa-fa-listing-file.md)|Задает имя файла листинга.|
|[/FC](fc-full-path-of-source-code-file-in-diagnostics.md)|Вывод полного пути файлов исходного кода, переданных программе cl.exe, в диагностическом тексте.|
|[/Fd](fd-program-database-file-name.md)|Переименовывает файл базы данных программы.|
|[/FE](fe-name-exe-file.md)|Переименовывает исполняемый файл.|
|[/FI](fi-name-forced-include-file.md)|Выполняет предварительную обработку указанного включаемого файла.|
|[/Fi](fi-preprocess-output-file-name.md)|Задает предобработанное имя выходного файла.|
|[Параметр /FM](fm-name-mapfile.md)|Создает файл сопоставления.|
|[/FO](fo-object-file-name.md)|Создает объектный файл.|
|[/fp](fp-specify-floating-point-behavior.md)|Задает поведение чисел с плавающей запятой.|
|[/Fp](fp-name-dot-pch-file.md)|Задает имя файла предкомпилированного заголовка.|
|[/FR](fr-fr-create-dot-sbr-file.md)<br /><br /> [/Fr](fr-fr-create-dot-sbr-file.md)|Создает файлы браузера. **/Fr** не рекомендуется к использованию.|
|[/FS](fs-force-synchronous-pdb-writes.md)|Обеспечивает принудительную сериализацию записей в файл базы данных программы (PDB) с помощью MSPDBSRV.EXE.|
|[/FU](fu-name-forced-hash-using-file.md)|Принудительное использование имени файла, как если бы оно было указано в директиве [#using](../../preprocessor/hash-using-directive-cpp.md) .|
|[/Fx](fx-merge-injected-code.md)|Включает введенный код в исходный файл.|
|[/GA](ga-optimize-for-windows-application.md)|Выполняет оптимизацию кода для приложений Windows.|
|[/Gd](gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__cdecl` (только архитектура x86).|
|[/Ge](ge-enable-stack-probes.md)|Не рекомендуется. Включает стековые зонды.|
|[/GF](gf-eliminate-duplicate-strings.md)|Включает объединение строк.|
|[/GH](gh-enable-pexit-hook-function.md)|Вызывает функцию-обработчик `_pexit`.|
|[/Gh](gh-enable-penter-hook-function.md)|Вызывает функцию-обработчик `_penter`.|
|[/GL](gl-whole-program-optimization.md)|Включает оптимизацию всей программы.|
|[/GM](gm-enable-minimal-rebuild.md)|Включает минимальное перепостроение.|
|[/GR](gr-enable-run-time-type-information.md)|Включает информацию о типах во время выполнения (RTTI).|
|[/Gr](gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__fastcall` (только архитектура x86).|
|[/GS](gs-buffer-security-check.md)|Буферизует проверку безопасности.|
|[/Gs](gs-control-stack-checking-calls.md)|Управляет стековыми зондами.|
|[/GT](gt-support-fiber-safe-thread-local-storage.md)|Поддерживает безопасность относительно волокон для данных, размещаемых с помощью статической локальной памяти потока.|
|[/ Guard: CF](guard-enable-control-flow-guard.md)|Добавление проверок безопасности для защиты потока управления.|
|[/Gv](gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__vectorcall` . (только x86 и x64)|
|[/Gw](gw-optimize-global-data.md)|Включает глобальную оптимизацию данных всей программы.|
|[/GX](gx-enable-exception-handling.md)|Не рекомендуется. Включает синхронную обработку исключений. Используйте [/EH](eh-exception-handling-model.md) вместо него.|
|[/Gy](gy-enable-function-level-linking.md)|Включает компоновку на уровне функций.|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Не рекомендуется. То же, что [/RTC1](rtc-run-time-error-checks.md).|
|[/GZ](gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__stdcall` (только архитектура x86).|
|[/H](h-restrict-length-of-external-names.md)|Не рекомендуется. Ограничивает длину внешних (открытых) имен.|
|[/ HELP](help-compiler-command-line-help.md)|Отображает список параметров компилятора.|
|[/ homeparams](homeparams-copy-register-parameters-to-stack.md)|Принудительная запись параметров, переданных в регистрах, в соответствующие места в стеке при вхождении в функцию. Данный параметр компилятора предназначен только для компиляторов [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] (машинная компиляция и кросс-компиляция).|
|[/ hotpatch](hotpatch-create-hotpatchable-image.md)|Создает образ, допускающий горячее обновление.|
|[/I](i-additional-include-directories.md)|Осуществляет поиск включаемых файлов в каталоге.|
|[/J](j-default-char-type-is-unsigned.md)|Изменяет тип `char` по умолчанию.|
|[/kernel](kernel-create-kernel-mode-binary.md)|Компилятор и компоновщик создадут двоичный файл для выполнения в ядре Windows.|
|[/LD](md-mt-ld-use-run-time-library.md)|Создает библиотеку динамической компоновки.|
|[/ LDd](md-mt-ld-use-run-time-library.md)|Создает отладочную библиотеку динамической компоновки.|
|[/link](link-pass-options-to-linker.md)|Передает указанный параметр в программу LINK.|
|[/LN](ln-create-msil-module.md)|Создает модуль MSIL.|
|[/MD](md-mt-ld-use-run-time-library.md)|Создает многопоточную библиотеку DLL с помощью библиотеки MSVCRT.lib.|
|[/MDd](md-mt-ld-use-run-time-library.md)|Создает отладочную многопоточную библиотеку DLL с помощью библиотеки MSVCRTD.lib.|
|[/MP](mp-build-with-multiple-processes.md)|Компилирует несколько исходных файлов с помощью нескольких процессов.|
|[/MT](md-mt-ld-use-run-time-library.md)|Создает многопоточный исполняемый файл с помощью библиотеки LIBCMT.lib.|
|[/MTd](md-mt-ld-use-run-time-library.md)|Создает отладочный многопоточный исполняемый файл с помощью библиотеки LIBCMTD.lib.|
|[/nologo](nologo-suppress-startup-banner-c-cpp.md)|Подавление отображения приветствия.|
|[/O1](o1-o2-minimize-size-maximize-speed.md)|Уменьшает размер кода.|
|[/O2](o1-o2-minimize-size-maximize-speed.md)|Создает быстрый код.|
|[/Ob](ob-inline-function-expansion.md)|Управляет подстановкой подставляемых функций.|
|[/Od](od-disable-debug.md)|Отключает оптимизацию.|
|[/Og](og-global-optimizations.md)|Не рекомендуется. Использует глобальную оптимизацию.|
|[/Oi](oi-generate-intrinsic-functions.md)|Создает встроенные функции.|
|[/ OpenMP](openmp-enable-openmp-2-0-support.md)|Включает прагма-директиву [#pragma omp](../../preprocessor/omp.md) в исходном коде.|
|[/Os](os-ot-favor-small-code-favor-fast-code.md)|Отдает приоритет уменьшению размера кода.|
|[/Ot](os-ot-favor-small-code-favor-fast-code.md)|Отдает приоритет быстрому коду.|
|[/Ox](ox-full-optimization.md)|Использует максимальную оптимизацию (/Ob2gity /Gs).|
|[/Oy](oy-frame-pointer-omission.md)|Отказ от использования указателя фрейма (только архитектура x86).|
|[/P](p-preprocess-to-a-file.md)|Записывает выходные данные препроцессора в файл.|
|[/ разрешительным-](permissive-standards-conformance.md)|Установить режим совместимости standard.|
|[/Qfast_transcendentals](qfast-transcendentals-force-fast-transcendentals.md)|Создает быстрые трансцендентные функции.|
|[/QIfist](qifist-suppress-ftol.md)|Не рекомендуется. Подавляет использование функции `_ftol` при необходимости преобразования из типа с плавающей запятой в целочисленный тип (только архитектура x86).|
|[/Qimprecise_fwaits](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Удаляет команды `fwait` внутри блоков `try` .|
|[/Qpar (автоматический параллелизатор)](qpar-auto-parallelizer.md)|Включает автоматическую параллелизацию циклов, которые помечены с помощью директивы [#pragma loop()](../../preprocessor/loop.md) .|
|[/Qsafe_fp_loads](qsafe-fp-loads.md)|Использует целочисленные инструкции перемещения значений с плавающей запятой и отключает определенные оптимизации загрузки значений с плавающей запятой.|
|[/Qvec/report (уровень отчетности автоматического векторизатора)](qvec-report-auto-vectorizer-reporting-level.md)|Включает уровни отчетов для автоматической векторизации.|
|[/RTC](rtc-run-time-error-checks.md)|Включает проверку ошибок во время выполнения.|
|[/sdl](sdl-enable-additional-security-checks.md)|Включает дополнительные функции безопасности и предупреждения.|
|[/ showincludes](showincludes-list-include-files.md)|Отображает список включаемых файлов во время компиляции.|
|[/ Source-CharSet](source-charset-set-source-character-set.md)|Кодировка исходного набора.|
|[/std](std-specify-language-standard-version.md)|Селектор совместимости стандартной версии C++.|
|[/Tc](tc-tp-tc-tp-specify-source-file-type.md)|Указывает исходный файл на языке C.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|Указывает, что все исходные файлы, C.|
|[/Tp](tc-tp-tc-tp-specify-source-file-type.md)|Указывает исходный файл на языке C++.|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|Указывает, что все исходные файлы C++.|
|[/U](u-u-undefine-symbols.md)|Удаляет предварительно определенный макрос.|
|[/u](u-u-undefine-symbols.md)|Удаляет все предварительно определенные макросы.|
|[/utf-8](utf-8-set-source-and-executable-character-sets-to-utf-8.md)|Набор источника и выполнение кодировки UTF-8.|
|[/V](v-version-number.md)|Не рекомендуется. Задает строку версии OBJ-файла.|
|[/ Validate-CharSet](validate-charset-validate-for-compatible-characters.md)|Проверка файлов UTF-8 для только совместимые символов.|
|[/vd](vd-disable-construction-displacements.md)|Подавляет или включает скрытые vtordisp-члены класса.|
|[/ vmb](vmb-vmg-representation-method.md)|Использует оптимальное основание для указателей на члены.|
|[/ vmg](vmb-vmg-representation-method.md)|Использует полное обобщение для указателей на члены.|
|[/ VMM](vmm-vms-vmv-general-purpose-representation.md)|Объявляет множественное наследование.|
|[/ vms](vmm-vms-vmv-general-purpose-representation.md)|Объявляет одиночное наследование.|
|[/ vmv](vmm-vms-vmv-general-purpose-representation.md)|Объявляет виртуальное наследование.|
|[/ volatile](volatile-volatile-keyword-interpretation.md)|Выбирает способ интерпретации ключевого слова volatile.|
|[/w](compiler-option-warning-level.md)|Отключает все предупреждения.|
|[/W0, /W1, /W2, /W3, /W4](compiler-option-warning-level.md)|Задает уровень предупреждения для вывода.|
|[/w1, /w2, /w3, /w4](compiler-option-warning-level.md)|Задает уровень для указанного предупреждения.|
|[/Wall](compiler-option-warning-level.md)|Включает все предупреждения, в том числе предупреждения, отключенные по умолчанию.|
|[/wd](compiler-option-warning-level.md)|Отключает указанное предупреждение.|
|[/we](compiler-option-warning-level.md)|Обрабатывает указанное предупреждение как ошибку.|
|[/WL](wl-enable-one-line-diagnostics.md)|Включает однострочные диагностические сообщения об ошибках и предупреждения в ходе компиляции исходного кода C++ из командной строки.|
|[/WO](compiler-option-warning-level.md)|Отображает указанное предупреждение только один раз.|
|[/Wp64](wp64-detect-64-bit-portability-issues.md)|Является устаревшей. Выявляет проблемы 64-битной переносимости.|
|[/Wv](compiler-option-warning-level.md)|Не отображает предупреждения, появившиеся после указанной версии компилятора.|
|[/WX](compiler-option-warning-level.md)|Обрабатывает предупреждения как ошибки.|
|[/X](x-ignore-standard-include-paths.md)|Пропускает стандартный каталог включаемых файлов.|
|[/Y-](y-ignore-precompiled-header-options.md)|Пропускает все прочие параметры компилятора, относящиеся к предварительно скомпилированным заголовкам, в текущем построении.|
|[/Yc](yc-create-precompiled-header-file.md)|Создает файл предкомпилированного заголовка.|
|[/Yd](yd-place-debug-information-in-object-file.md)|Не рекомендуется. Размещает полную отладочную информацию во всех объектных файлах. Используйте [/ZI](z7-zi-zi-debug-information-format.md) вместо него.|
|[/Yl](yl-inject-pch-reference-for-debug-library.md)|Вводит ссылку PCH при создании отладочной библиотеки.|
|[/Yu](yu-use-precompiled-header-file.md)|Использует файл предкомпилированного заголовка при построении.|
|[/Z7](z7-zi-zi-debug-information-format.md)|Приводит к возникновению ошибки совместимости с C 7.0 отладочную информацию.|
|[/ Za](za-ze-disable-language-extensions.md)|Отключает расширения языка.|
|[/Zc](zc-conformance.md)|Задает стандартное поведение при [/Ze](za-ze-disable-language-extensions.md).[ / Za, /Ze (отключить расширения языка)](za-ze-disable-language-extensions.md)|
|[/Ze](za-ze-disable-language-extensions.md)|Не рекомендуется. Включает расширения языка.|
|[/Zf](zf.md)|Ускоряет PDB-ФАЙЛ поколения в параллельных сборок.|
|[/Zg](zg-generate-function-prototypes.md)|Удален в Visual C++ 2015. Создает прототипы функций.|
|[/ZI](z7-zi-zi-debug-information-format.md)|Включает отладочную информацию в базу данных программы, совместимую с функцией "Изменить и продолжить".|
|[/Zi](z7-zi-zi-debug-information-format.md)|Создает полную отладочную информацию.|
|[/Zl](zl-omit-default-library-name.md)|Удаляет имя библиотеки по умолчанию из файла OBJ (только архитектура x86).|
|[/Zm](zm-specify-precompiled-header-memory-allocation-limit.md)|Указывает предел выделения памяти для предкомпилированного заголовка.|
|[/Zp](zp-struct-member-alignment.md)|Упаковывает члены структур.|
|[/Zs](zs-syntax-check-only.md)|Проверяет только синтаксис.|
|[/ZW](zw-windows-runtime-compilation.md)|Создает выходной файл для запуска в среде выполнения Windows.|

## <a name="see-also"></a>См. также
 [Ссылка на построение C/C++](c-cpp-building-reference.md) [параметры компилятора](compiler-options.md) [Настройка параметров компилятора](setting-compiler-options.md)