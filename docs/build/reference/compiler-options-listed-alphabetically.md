---
title: "Параметры компилятора в алфавитном порядке | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: compiler options, C++
ms.assetid: 98375dad-c9c6-4796-aaa6-fd573269d4ae
caps.latest.revision: "66"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee6062b04c1f406fe3286f6035eba1cda65ef1fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-options-listed-alphabetically"></a>Параметры компилятора в алфавитном порядке
Ниже приведен полный список параметров компилятора в алфавитном порядке. Список параметров по категориям см. в разделе [Параметры компилятора по категориям](../../build/reference/compiler-options-listed-by-category.md).  
  
|Параметр|Цель|  
|------------|-------------|  
|[@](../../build/reference/at-specify-a-compiler-response-file.md)|Указывает файл ответа.|  
|[/?](../../build/reference/help-compiler-command-line-help.md)|Отображает список параметров компилятора.|  
|[/AI](../../build/reference/ai-specify-metadata-directories.md)|Указывает каталог поиска для разрешения ссылок на файлы, указанные в директиве [#using](../../preprocessor/hash-using-directive-cpp.md) .|  
|[/analyze](../../build/reference/analyze-code-analysis.md)|Включение анализа кода.|  
|[/arch](../../build/reference/arch-minimum-cpu-architecture.md)|Задает архитектуру для создания кода.|  
|[/ await](await-enable-coroutine-support.md)|Включите расширения сопрограммы (возобновляемые функции).|  
|[/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)|Увеличивает число адресуемых секций в OBJ-файле.|  
|[/C](../../build/reference/c-preserve-comments-during-preprocessing.md)|Сохраняет комментарии на этапе предварительной обработки.|  
|[/c](../../build/reference/c-compile-without-linking.md)|Задает компиляцию без компоновки.|  
|[/cgthreads](../../build/reference/cgthreads-code-generation-threads.md)|Задает число потоков cl.exe, используемых для оптимизации и создания кода.|  
|[/clr](../../build/reference/clr-common-language-runtime-compilation.md)|Создает выходной файл, предназначенный для выполнения в среде CLR.|  
|[/constexpr](constexpr-control-constexpr-evaluation.md)|Вычисление constexpr элемента управления во время компиляции.|  
|[/D](../../build/reference/d-preprocessor-definitions.md)|Определяет константы и макросы.|  
|[/Diagnostics](diagnostics-compiler-diagnostic-options.md)|Определяет формат диагностических сообщений.|  
|[/doc](../../build/reference/doc-process-documentation-comments-c-cpp.md)|Сведение документирующих комментариев в XML-файл.|  
|[/E](../../build/reference/e-preprocess-to-stdout.md)|Копирует выходные данные препроцессора в стандартный вывод.|  
|[/EH](../../build/reference/eh-exception-handling-model.md)|Задает модель обработки исключений.|  
|[/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)|Копирует выходные данные препроцессора в стандартный вывод.|  
|[/errorReport](../../build/reference/errorreport-report-internal-compiler-errors.md)|Разрешает передавать данные о внутренних ошибках компилятора (ICE) непосредственно в группу Visual C++.|  
|[/ Execution-CharSet](execution-charset-set-execution-character-set.md)|Набор символов исполнения набора.|  
|[/F](../../build/reference/f-set-stack-size.md)|Задает размер стека.|  
|[/favor](../../build/reference/favor-optimize-for-architecture-specifics.md)|Формирует код, оптимизированный для конкретной архитектуры [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] или для специфики микроархитектур в архитектурах AMD64 и EM64T.|  
|[/FA](../../build/reference/fa-fa-listing-file.md)|Создает файл листинга.|  
|[/Fa](../../build/reference/fa-fa-listing-file.md)|Задает имя файла листинга.|  
|[/FC](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)|Вывод полного пути файлов исходного кода, переданных программе cl.exe, в диагностическом тексте.|  
|[/Fd](../../build/reference/fd-program-database-file-name.md)|Переименовывает файл базы данных программы.|  
|[/Fe](../../build/reference/fe-name-exe-file.md)|Переименовывает исполняемый файл.|  
|[/FI](../../build/reference/fi-name-forced-include-file.md)|Выполняет предварительную обработку указанного включаемого файла.|  
|[/Fi](../../build/reference/fi-preprocess-output-file-name.md)|Задает предобработанное имя выходного файла.|  
|[/Fm](../../build/reference/fm-name-mapfile.md)|Создает файл сопоставления.|  
|[/Fo](../../build/reference/fo-object-file-name.md)|Создает объектный файл.|  
|[/fp](../../build/reference/fp-specify-floating-point-behavior.md)|Задает поведение чисел с плавающей запятой.|  
|[/Fp](../../build/reference/fp-name-dot-pch-file.md)|Задает имя файла предкомпилированного заголовка.|  
|[/FR](../../build/reference/fr-fr-create-dot-sbr-file.md)<br /><br /> [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)|Создает файлы браузера. **/Fr** не рекомендуется к использованию.|  
|[/FS](../../build/reference/fs-force-synchronous-pdb-writes.md)|Обеспечивает принудительную сериализацию записей в файл базы данных программы (PDB) с помощью MSPDBSRV.EXE.|  
|[/FU](../../build/reference/fu-name-forced-hash-using-file.md)|Принудительное использование имени файла, как если бы оно было указано в директиве [#using](../../preprocessor/hash-using-directive-cpp.md) .|  
|[/Fx](../../build/reference/fx-merge-injected-code.md)|Включает введенный код в исходный файл.|  
|[/GA](../../build/reference/ga-optimize-for-windows-application.md)|Выполняет оптимизацию кода для приложений Windows.|  
|[/Gd](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__cdecl` (только архитектура x86).|  
|[/Ge](../../build/reference/ge-enable-stack-probes.md)|Не рекомендуется. Включает стековые зонды.|  
|[/GF](../../build/reference/gf-eliminate-duplicate-strings.md)|Включает объединение строк.|  
|[/GH](../../build/reference/gh-enable-pexit-hook-function.md)|Вызывает функцию-обработчик `_pexit`.|  
|[/Gh](../../build/reference/gh-enable-penter-hook-function.md)|Вызывает функцию-обработчик `_penter`.|  
|[/GL](../../build/reference/gl-whole-program-optimization.md)|Включает оптимизацию всей программы.|  
|[/Gm](../../build/reference/gm-enable-minimal-rebuild.md)|Включает минимальное перепостроение.|  
|[/GR](../../build/reference/gr-enable-run-time-type-information.md)|Включает информацию о типах во время выполнения (RTTI).|  
|[/Gr](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__fastcall` (только архитектура x86).|  
|[/GS](../../build/reference/gs-buffer-security-check.md)|Буферизует проверку безопасности.|  
|[/Gs](../../build/reference/gs-control-stack-checking-calls.md)|Управляет стековыми зондами.|  
|[/GT](../../build/reference/gt-support-fiber-safe-thread-local-storage.md)|Поддерживает безопасность относительно волокон для данных, размещаемых с помощью статической локальной памяти потока.|  
|[/guard:cf](../../build/reference/guard-enable-control-flow-guard.md)|Добавление проверок безопасности для защиты потока управления.|  
|[/Gv](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__vectorcall` . (только x86 и x64)|  
|[/Gw](../../build/reference/gw-optimize-global-data.md)|Включает глобальную оптимизацию данных всей программы.|  
|[/GX](../../build/reference/gx-enable-exception-handling.md)|Не рекомендуется. Включает синхронную обработку исключений. Используйте вместо этого параметр [/EH](../../build/reference/eh-exception-handling-model.md) .|  
|[/Gy](../../build/reference/gy-enable-function-level-linking.md)|Включает компоновку на уровне функций.|  
|[/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)|Не рекомендуется. Аналогично [/RTC1](../../build/reference/rtc-run-time-error-checks.md).|  
|[/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__stdcall` (только архитектура x86).|  
|[/H](../../build/reference/h-restrict-length-of-external-names.md)|Не рекомендуется. Ограничивает длину внешних (открытых) имен.|  
|[/HELP](../../build/reference/help-compiler-command-line-help.md)|Отображает список параметров компилятора.|  
|[/homeparams](../../build/reference/homeparams-copy-register-parameters-to-stack.md)|Принудительная запись параметров, переданных в регистрах, в соответствующие места в стеке при вхождении в функцию. Данный параметр компилятора предназначен только для компиляторов [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] (машинная компиляция и кросс-компиляция).|  
|[/hotpatch](../../build/reference/hotpatch-create-hotpatchable-image.md)|Создает образ, допускающий горячее обновление.|  
|[/I](../../build/reference/i-additional-include-directories.md)|Осуществляет поиск включаемых файлов в каталоге.|  
|[/J](../../build/reference/j-default-char-type-is-unsigned.md)|Изменяет тип `char` по умолчанию.|  
|[/kernel](../../build/reference/kernel-create-kernel-mode-binary.md)|Компилятор и компоновщик создадут двоичный файл для выполнения в ядре Windows.|  
|[/LD](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает библиотеку динамической компоновки.|  
|[/LDd](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает отладочную библиотеку динамической компоновки.|  
|[/link](../../build/reference/link-pass-options-to-linker.md)|Передает указанный параметр в программу LINK.|  
|[/LN](../../build/reference/ln-create-msil-module.md)|Создает модуль MSIL.|  
|[/MD](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает многопоточную библиотеку DLL с помощью библиотеки MSVCRT.lib.|  
|[/MDd](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает отладочную многопоточную библиотеку DLL с помощью библиотеки MSVCRTD.lib.|  
|[/MP](../../build/reference/mp-build-with-multiple-processes.md)|Компилирует несколько исходных файлов с помощью нескольких процессов.|  
|[/MT](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает многопоточный исполняемый файл с помощью библиотеки LIBCMT.lib.|  
|[/MTd](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает отладочный многопоточный исполняемый файл с помощью библиотеки LIBCMTD.lib.|  
|[/nologo](../../build/reference/nologo-suppress-startup-banner-c-cpp.md)|Подавление отображения приветствия.|  
|[/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|Уменьшает размер кода.|  
|[/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|Создает быстрый код.|  
|[/Ob](../../build/reference/ob-inline-function-expansion.md)|Управляет подстановкой подставляемых функций.|  
|[/Od](../../build/reference/od-disable-debug.md)|Отключает оптимизацию.|  
|[/Og](../../build/reference/og-global-optimizations.md)|Не рекомендуется. Использует глобальную оптимизацию.|  
|[/Oi](../../build/reference/oi-generate-intrinsic-functions.md)|Создает встроенные функции.|  
|[/openmp](../../build/reference/openmp-enable-openmp-2-0-support.md)|Включает прагма-директиву [#pragma omp](../../preprocessor/omp.md) в исходном коде.|  
|[/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|Отдает приоритет уменьшению размера кода.|  
|[/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|Отдает приоритет быстрому коду.|  
|[/Ox](../../build/reference/ox-full-optimization.md)|Использует максимальную оптимизацию (/Ob2gity /Gs).|  
|[/Oy](../../build/reference/oy-frame-pointer-omission.md)|Отказ от использования указателя фрейма (только архитектура x86).|  
|[/P](../../build/reference/p-preprocess-to-a-file.md)|Записывает выходные данные препроцессора в файл.|  
|[/ разрешительным-](permissive-standards-conformance.md)|Установить режим совместимости standard.|  
|[/Qfast_transcendentals](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md)|Создает быстрые трансцендентные функции.|  
|[/QIfist](../../build/reference/qifist-suppress-ftol.md)|Не рекомендуется. Подавляет использование функции `_ftol` при необходимости преобразования из типа с плавающей запятой в целочисленный тип (только архитектура x86).|  
|[/Qimprecise_fwaits](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Удаляет команды `fwait` внутри блоков `try` .|  
|[/ Qpar (автоматический Параллелизатор)](../../build/reference/qpar-auto-parallelizer.md)|Включает автоматическую параллелизацию циклов, которые помечены с помощью директивы [#pragma loop()](../../preprocessor/loop.md) .|  
|[/Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md)|Использует целочисленные инструкции перемещения значений с плавающей запятой и отключает определенные оптимизации загрузки значений с плавающей запятой.|  
|[/ Qvec-report (уровень отчетности автоматического Векторизатора)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md)|Включает уровни отчетов для автоматической векторизации.|  
|[/RTC](../../build/reference/rtc-run-time-error-checks.md)|Включает проверку ошибок во время выполнения.|  
|[/sdl](../../build/reference/sdl-enable-additional-security-checks.md)|Включает дополнительные функции безопасности и предупреждения.|  
|[/showIncludes](../../build/reference/showincludes-list-include-files.md)|Отображает список включаемых файлов во время компиляции.|  
|[/ Source-CharSet](source-charset-set-source-character-set.md)|Кодировка исходного набора.|  
|[/std](std-specify-language-standard-version.md)|Селектор совместимости стандартной версии C++.|  
|[/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Указывает исходный файл на языке C.|  
|[/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Указывает, что все исходные файлы, C.|  
|[/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Указывает исходный файл на языке C++.|  
|[/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Указывает, что все исходные файлы C++.|  
|[/U](../../build/reference/u-u-undefine-symbols.md)|Удаляет предварительно определенный макрос.|  
|[/u](../../build/reference/u-u-undefine-symbols.md)|Удаляет все предварительно определенные макросы.|  
|[/ UTF-8](utf-8-set-source-and-executable-character-sets-to-utf-8.md)|Набор источника и выполнение кодировки UTF-8.|  
|[/V](../../build/reference/v-version-number.md)|Не рекомендуется. Задает строку версии OBJ-файла.|  
|[/ Validate-CharSet](validate-charset-validate-for-compatible-characters.md)|Проверка файлов UTF-8 для только совместимые символов.|  
|[/vd](../../build/reference/vd-disable-construction-displacements.md)|Подавляет или включает скрытые vtordisp-члены класса.|  
|[/vmb](../../build/reference/vmb-vmg-representation-method.md)|Использует оптимальное основание для указателей на члены.|  
|[/vmg](../../build/reference/vmb-vmg-representation-method.md)|Использует полное обобщение для указателей на члены.|  
|[/vmm](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Объявляет множественное наследование.|  
|[/vms](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Объявляет одиночное наследование.|  
|[/vmv](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Объявляет виртуальное наследование.|  
|[/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md)|Выбирает способ интерпретации ключевого слова volatile.|  
|[/w](../../build/reference/compiler-option-warning-level.md)|Отключает все предупреждения.|  
|[/W0, /W1, /W2, /W3, /W4](../../build/reference/compiler-option-warning-level.md)|Задает уровень предупреждения для вывода.|  
|[/w1, /w2, /w3, /w4](../../build/reference/compiler-option-warning-level.md)|Задает уровень для указанного предупреждения.|  
|[/Wall](../../build/reference/compiler-option-warning-level.md)|Включает все предупреждения, в том числе предупреждения, отключенные по умолчанию.|  
|[/wd](../../build/reference/compiler-option-warning-level.md)|Отключает указанное предупреждение.|  
|[/we](../../build/reference/compiler-option-warning-level.md)|Обрабатывает указанное предупреждение как ошибку.|  
|[/WL](../../build/reference/wl-enable-one-line-diagnostics.md)|Включает однострочные диагностические сообщения об ошибках и предупреждения в ходе компиляции исходного кода C++ из командной строки.|  
|[/wo](../../build/reference/compiler-option-warning-level.md)|Отображает указанное предупреждение только один раз.|  
|[/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md)|Является устаревшей. Выявляет проблемы 64-битной переносимости.|  
|[/Wv](../../build/reference/compiler-option-warning-level.md)|Не отображает предупреждения, появившиеся после указанной версии компилятора.|  
|[/WX](../../build/reference/compiler-option-warning-level.md)|Обрабатывает предупреждения как ошибки.|  
|[/X](../../build/reference/x-ignore-standard-include-paths.md)|Пропускает стандартный каталог включаемых файлов.|  
|[/Y-](../../build/reference/y-ignore-precompiled-header-options.md)|Пропускает все прочие параметры компилятора, относящиеся к предварительно скомпилированным заголовкам, в текущем построении.|  
|[/Yc](../../build/reference/yc-create-precompiled-header-file.md)|Создает файл предкомпилированного заголовка.|  
|[/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|Не рекомендуется. Размещает полную отладочную информацию во всех объектных файлах. Используйте вместо этого параметр [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) .|  
|[/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)|Вводит ссылку PCH при создании отладочной библиотеки.|  
|[/Yu](../../build/reference/yu-use-precompiled-header-file.md)|Использует файл предкомпилированного заголовка при построении.|  
|[/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)|Приводит к возникновению ошибки совместимости с C 7.0 отладочную информацию.|  
|[/Za](../../build/reference/za-ze-disable-language-extensions.md)|Отключает расширения языка.|  
|[/Zc](../../build/reference/zc-conformance.md)|Задает стандартное поведение при [/Ze](../../build/reference/za-ze-disable-language-extensions.md).[ / Za, /Ze (отключить расширения языка)](../../build/reference/za-ze-disable-language-extensions.md)|  
|[/Ze](../../build/reference/za-ze-disable-language-extensions.md)|Не рекомендуется. Включает расширения языка.|  
|[/Zg](../../build/reference/zg-generate-function-prototypes.md)|Удален в Visual C++ 2015. Создает прототипы функций.|  
|[/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)|Включает отладочную информацию в базу данных программы, совместимую с функцией "Изменить и продолжить".|  
|[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)|Создает полную отладочную информацию.|  
|[/Zl](../../build/reference/zl-omit-default-library-name.md)|Удаляет имя библиотеки по умолчанию из файла OBJ (только архитектура x86).|  
|[/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)|Указывает предел выделения памяти для предкомпилированного заголовка.|  
|[/Zp](../../build/reference/zp-struct-member-alignment.md)|Упаковывает члены структур.|  
|[/Zs](../../build/reference/zs-syntax-check-only.md)|Проверяет только синтаксис.|  
|[/ZW](../../build/reference/zw-windows-runtime-compilation.md)|Создает выходной файл для запуска в среде выполнения Windows.|  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о построении C/C++](../../build/reference/c-cpp-building-reference.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)