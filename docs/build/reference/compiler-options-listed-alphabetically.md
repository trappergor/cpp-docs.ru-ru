---
title: "Параметры компилятора в алфавитном порядке | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "параметры компилятора, C++"
ms.assetid: 98375dad-c9c6-4796-aaa6-fd573269d4ae
caps.latest.revision: 66
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 66
---
# Параметры компилятора в алфавитном порядке
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ниже приведен полный список параметров компилятора в алфавитном порядке. Список параметров по категориям см. в разделе [Параметры компилятора по категориям](../../build/reference/compiler-options-listed-by-category.md).  
  
|Параметр|Цель|  
|--------------|----------|  
|[@](../../build/reference/at-specify-a-compiler-response-file.md)|Указывает файл ответа.|  
|[\/?](../../build/reference/help-compiler-command-line-help.md)|Отображает список параметров компилятора.|  
|[\/AI](../../build/reference/ai-specify-metadata-directories.md)|Указывает каталог поиска для разрешения ссылок на файлы, указанные в директиве[\#using](../../preprocessor/hash-using-directive-cpp.md).|  
|[\/analyze](../../build/reference/analyze-code-analysis.md)|Включение анализа кода.|  
|[\/arch](../../build/reference/arch-minimum-cpu-architecture.md)|Задает архитектуру для создания кода.|  
|[\/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)|Увеличивает число адресуемых секций в OBJ\-файле.|  
|[\/C](../../build/reference/c-preserve-comments-during-preprocessing.md)|Сохраняет комментарии на этапе предварительной обработки.|  
|[\/c](../../build/reference/c-compile-without-linking.md)|Задает компиляцию без компоновки.|  
|[\/cgthreads](../../build/reference/cgthreads-code-generation-threads.md)|Задает число потоков cl.exe, используемых для оптимизации и создания кода.|  
|[\/clr](../../build/reference/clr-common-language-runtime-compilation.md)|Создает выходной файл, предназначенный для выполнения в среде CLR.|  
|[\/D](../../build/reference/d-preprocessor-definitions.md)|Определяет константы и макросы.|  
|[\/doc](../../build/reference/doc-process-documentation-comments-c-cpp.md)|Сведение документирующих комментариев в XML\-файл.|  
|[\/E](../../build/reference/e-preprocess-to-stdout.md)|Копирует выходные данные препроцессора в стандартный вывод.|  
|[\/EH](../../build/reference/eh-exception-handling-model.md)|Задает модель обработки исключений.|  
|[\/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)|Копирует выходные данные препроцессора в стандартный вывод.|  
|[\/errorReport](../Topic/-errorReport%20\(Report%20Internal%20Compiler%20Errors\).md)|Разрешает передавать данные о внутренних ошибках компилятора \(ICE\) непосредственно в группу Visual C\+\+.|  
|[\/F](../../build/reference/f-set-stack-size.md)|Задает размер стека.|  
|[\/favor](../../build/reference/favor-optimize-for-architecture-specifics.md)|Формирует код, оптимизированный для конкретной архитектуры [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] или для специфики микроархитектур в архитектурах AMD64 и EM64T.|  
|[\/FA](../../build/reference/fa-fa-listing-file.md)|Создает файл листинга.|  
|[\/Fa](../../build/reference/fa-fa-listing-file.md)|Задает имя файла листинга.|  
|[\/FC](../Topic/-FC%20\(Full%20Path%20of%20Source%20Code%20File%20in%20Diagnostics\).md)|Вывод полного пути файлов исходного кода, переданных программе cl.exe, в диагностическом тексте.|  
|[\/Fd](../../build/reference/fd-program-database-file-name.md)|Переименовывает файл базы данных программы.|  
|[\/Fe](../../build/reference/fe-name-exe-file.md)|Переименовывает исполняемый файл.|  
|[\/FI](../Topic/-FI%20\(Name%20Forced%20Include%20File\).md)|Выполняет предварительную обработку указанного включаемого файла.|  
|[\/Fi](../../build/reference/fi-preprocess-output-file-name.md)|Задает предобработанное имя выходного файла.|  
|[\/Fm](../Topic/-Fm%20\(Name%20Mapfile\).md)|Создает файл сопоставления.|  
|[\/Fo](../../build/reference/fo-object-file-name.md)|Создает объектный файл.|  
|[\/fp](../../build/reference/fp-specify-floating-point-behavior.md)|Задает поведение чисел с плавающей запятой.|  
|[\/Fp](../Topic/-Fp%20\(Name%20.Pch%20File\).md)|Задает имя файла предкомпилированного заголовка.|  
|[\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md)<br /><br /> [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)|Создает файлы браузера.**\/Fr** не рекомендуется к использованию.|  
|[\/FS](../../build/reference/fs-force-synchronous-pdb-writes.md)|Обеспечивает принудительную сериализацию записей в файл базы данных программы \(PDB\) с помощью MSPDBSRV.EXE.|  
|[\/FU](../../build/reference/fu-name-forced-hash-using-file.md)|Принудительное использование имени файла, как если бы оно было указано в директиве [\#using](../../preprocessor/hash-using-directive-cpp.md).|  
|[\/Fx](../../build/reference/fx-merge-injected-code.md)|Включает введенный код в исходный файл.|  
|[\/GA](../../build/reference/ga-optimize-for-windows-application.md)|Выполняет оптимизацию кода для приложений Windows.|  
|[\/Gd](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__cdecl` \(только архитектура x86\).|  
|[\/Ge](../Topic/-Ge%20\(Enable%20Stack%20Probes\).md)|Не рекомендуется. Включает стековые зонды.|  
|[\/GF](../Topic/-GF%20\(Eliminate%20Duplicate%20Strings\).md)|Включает объединение строк.|  
|[\/GH](../../build/reference/gh-enable-pexit-hook-function.md)|Вызывает функцию\-обработчик `_pexit`.|  
|[\/Gh](../../build/reference/gh-enable-penter-hook-function.md)|Вызывает функцию\-обработчик `_penter`.|  
|[\/GL](../../build/reference/gl-whole-program-optimization.md)|Включает оптимизацию всей программы.|  
|[\/Gm](../../build/reference/gm-enable-minimal-rebuild.md)|Включает минимальное перепостроение.|  
|[\/GR](../Topic/-GR%20\(Enable%20Run-Time%20Type%20Information\).md)|Включает информацию о типах во время выполнения \(RTTI\).|  
|[\/Gr](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__fastcall` \(только архитектура x86\).|  
|[\/GS](../Topic/-GS%20\(Buffer%20Security%20Check\).md)|Буферизует проверку безопасности.|  
|[\/Gs](../../build/reference/gs-control-stack-checking-calls.md)|Управляет стековыми зондами.|  
|[\/GT](../../build/reference/gt-support-fiber-safe-thread-local-storage.md)|Поддерживает безопасность относительно волокон для данных, размещаемых с помощью статической локальной памяти потока.|  
|[\/guard:cf](../../build/reference/guard-enable-control-flow-guard.md)|Добавление проверок безопасности для защиты потока управления.|  
|[\/Gv](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__vectorcall`. \(только x86 и x64\)|  
|[\/Gw](../../build/reference/gw-optimize-global-data.md)|Включает глобальную оптимизацию данных всей программы.|  
|[\/GX](../Topic/-GX%20\(Enable%20Exception%20Handling\).md)|Не рекомендуется. Включает синхронную обработку исключений. Используйте вместо этого параметр [\/EH](../../build/reference/eh-exception-handling-model.md).|  
|[\/Gy](../../build/reference/gy-enable-function-level-linking.md)|Включает компоновку на уровне функций.|  
|[\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)|Не рекомендуется. Аналогично [\/RTC1](../../build/reference/rtc-run-time-error-checks.md).|  
|[\/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__stdcall` \(только архитектура x86\).|  
|[\/H](../../build/reference/h-restrict-length-of-external-names.md)|Не рекомендуется. Ограничивает длину внешних \(открытых\) имен.|  
|[\/HELP](../../build/reference/help-compiler-command-line-help.md)|Отображает список параметров компилятора.|  
|[\/homeparams](../../build/reference/homeparams-copy-register-parameters-to-stack.md)|Принудительная запись параметров, переданных в регистрах, в соответствующие места в стеке при вхождении в функцию. Данный параметр компилятора предназначен только для компиляторов [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] \(машинная компиляция и кросс\-компиляция\).|  
|[\/hotpatch](../../build/reference/hotpatch-create-hotpatchable-image.md)|Создает образ, допускающий горячее обновление.|  
|[\/I](../../build/reference/i-additional-include-directories.md)|Осуществляет поиск включаемых файлов в каталоге.|  
|[\/J](../../build/reference/j-default-char-type-is-unsigned.md)|Изменяет тип `char` по умолчанию.|  
|[\/kernel](../../build/reference/kernel-create-kernel-mode-binary.md)|Компилятор и компоновщик создадут двоичный файл для выполнения в ядре Windows.|  
|[\/LD](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает библиотеку динамической компоновки.|  
|[\/LDd](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает отладочную библиотеку динамической компоновки.|  
|[\/link](../Topic/-link%20\(Pass%20Options%20to%20Linker\).md)|Передает указанный параметр в программу LINK.|  
|[\/LN](../../build/reference/ln-create-msil-module.md)|Создает модуль MSIL.|  
|[\/MD](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает многопоточную библиотеку DLL с помощью библиотеки MSVCRT.lib.|  
|[\/MDd](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает отладочную многопоточную библиотеку DLL с помощью библиотеки MSVCRTD.lib.|  
|[\/MP](../../build/reference/mp-build-with-multiple-processes.md)|Компилирует несколько исходных файлов с помощью нескольких процессов.|  
|[\/MT](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает многопоточный исполняемый файл с помощью библиотеки LIBCMT.lib.|  
|[\/MTd](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает отладочный многопоточный исполняемый файл с помощью библиотеки LIBCMTD.lib.|  
|[\/nologo](../../build/reference/nologo-suppress-startup-banner-c-cpp.md)|Подавление отображения приветствия.|  
|[\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|Уменьшает размер кода.|  
|[\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|Создает быстрый код.|  
|[\/Ob](../../build/reference/ob-inline-function-expansion.md)|Управляет подстановкой подставляемых функций.|  
|[\/Od](../../build/reference/od-disable-debug.md)|Отключает оптимизацию.|  
|[\/Og](../../build/reference/og-global-optimizations.md)|Не рекомендуется. Использует глобальную оптимизацию.|  
|[\/Oi](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md)|Создает встроенные функции.|  
|[\/openmp](../../build/reference/openmp-enable-openmp-2-0-support.md)|Включает прагма\-директиву [\#pragma omp](../../preprocessor/omp.md) в исходном коде.|  
|[\/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|Отдает приоритет уменьшению размера кода.|  
|[\/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|Отдает приоритет быстрому коду.|  
|[\/Ox](../../build/reference/ox-full-optimization.md)|Использует максимальную оптимизацию \(\/Ob2gity \/Gs\).|  
|[\/Oy](../../build/reference/oy-frame-pointer-omission.md)|Отказ от использования указателя фрейма \(только архитектура x86\).|  
|[\/P](../../build/reference/p-preprocess-to-a-file.md)|Записывает выходные данные препроцессора в файл.|  
|[\/Qfast\_transcendentals](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md)|Создает быстрые трансцендентные функции.|  
|[\/QIfist](../../build/reference/qifist-suppress-ftol.md)|Не рекомендуется. Подавляет использование функции `_ftol` при необходимости преобразования из типа с плавающей запятой в целочисленный тип \(только архитектура x86\).|  
|[\/Qimprecise\_fwaits](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Удаляет команды `fwait` внутри блоков `try`.|  
|[\/Qpar \(автоматический параллелизатор\)](../Topic/-Qpar%20\(Auto-Parallelizer\).md)|Включает автоматическую параллелизацию циклов, которые помечены с помощью директивы [\#pragma loop\(\)](../../preprocessor/loop.md).|  
|[\/Qsafe\_fp\_loads](../../build/reference/qsafe-fp-loads.md)|Использует целочисленные инструкции перемещения значений с плавающей запятой и отключает определенные оптимизации загрузки значений с плавающей запятой.|  
|[\/Qvec\-report \(уровень отчетности автоматического векторизатора\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md)|Включает уровни отчетов для автоматической векторизации.|  
|[\/RTC](../../build/reference/rtc-run-time-error-checks.md)|Включает проверку ошибок во время выполнения.|  
|[\/sdl](../../build/reference/sdl-enable-additional-security-checks.md)|Включает дополнительные функции безопасности и предупреждения.|  
|[\/showIncludes](../Topic/-showIncludes%20\(List%20Include%20Files\).md)|Отображает список включаемых файлов во время компиляции.|  
|[\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)<br /><br /> [\/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Указывает исходный файл на языке C.|  
|[\/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)<br /><br /> [\/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Указывает исходный файл на языке C\+\+.|  
|[\/U](../Topic/-U,%20-u%20\(Undefine%20Symbols\).md)|Удаляет предварительно определенный макрос.|  
|[\/u](../Topic/-U,%20-u%20\(Undefine%20Symbols\).md)|Удаляет все предварительно определенные макросы.|  
|[\/V](../../build/reference/v-version-number.md)|Не рекомендуется. Задает строку версии OBJ\-файла.|  
|[\/vd](../../build/reference/vd-disable-construction-displacements.md)|Подавляет или включает скрытые vtordisp\-члены класса.|  
|[\/vmb](../../build/reference/vmb-vmg-representation-method.md)|Использует оптимальное основание для указателей на члены.|  
|[\/vmg](../../build/reference/vmb-vmg-representation-method.md)|Использует полное обобщение для указателей на члены.|  
|[\/vmm](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Объявляет множественное наследование.|  
|[\/vms](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Объявляет одиночное наследование.|  
|[\/vmv](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Объявляет виртуальное наследование.|  
|[\/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md)|Выбирает способ интерпретации ключевого слова volatile.|  
|[\/w](../../build/reference/compiler-option-warning-level.md)|Отключает все предупреждения.|  
|[\/W0, \/W1, \/W2, \/W3, \/W4](../../build/reference/compiler-option-warning-level.md)|Задает уровень предупреждения для вывода.|  
|[\/w1, \/w2, \/w3, \/w4](../../build/reference/compiler-option-warning-level.md)|Задает уровень для указанного предупреждения.|  
|[\/Wall](../../build/reference/compiler-option-warning-level.md)|Включает все предупреждения, в том числе предупреждения, отключенные по умолчанию.|  
|[\/wd](../../build/reference/compiler-option-warning-level.md)|Отключает указанное предупреждение.|  
|[\/we](../../build/reference/compiler-option-warning-level.md)|Обрабатывает указанное предупреждение как ошибку.|  
|[\/WL](../../build/reference/wl-enable-one-line-diagnostics.md)|Включает однострочные диагностические сообщения об ошибках и предупреждения в ходе компиляции исходного кода C\+\+ из командной строки.|  
|[\/wo](../../build/reference/compiler-option-warning-level.md)|Отображает указанное предупреждение только один раз.|  
|[\/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md)|Является устаревшей. Выявляет проблемы 64\-битной переносимости.|  
|[\/Wv](../../build/reference/compiler-option-warning-level.md)|Не отображает предупреждения, появившиеся после указанной версии компилятора.|  
|[\/WX](../../build/reference/compiler-option-warning-level.md)|Обрабатывает предупреждения как ошибки.|  
|[\/X](../../build/reference/x-ignore-standard-include-paths.md)|Пропускает стандартный каталог включаемых файлов.|  
|[\/Y\-](../Topic/-Y-%20\(Ignore%20Precompiled%20Header%20Options\).md)|Пропускает все прочие параметры компилятора, относящиеся к предварительно скомпилированным заголовкам, в текущем построении.|  
|[\/Yc](../../build/reference/yc-create-precompiled-header-file.md)|Создает файл предкомпилированного заголовка.|  
|[\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|Не рекомендуется. Размещает полную отладочную информацию во всех объектных файлах. Используйте вместо этого параметр [\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md).|  
|[\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)|Вводит ссылку PCH при создании отладочной библиотеки.|  
|[\/Yu](../../build/reference/yu-use-precompiled-header-file.md)|Использует файл предкомпилированного заголовка при построении.|  
|[\/Z7](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)|Создает отладочную информацию, совместимую с C 7.0.|  
|[\/Za](../../build/reference/za-ze-disable-language-extensions.md)|Отключает расширения языка.|  
|[\/Zc](../../build/reference/zc-conformance.md)|Задает стандартное поведение при использовании параметра [\/Ze](../../build/reference/za-ze-disable-language-extensions.md).[\/Za, \/Ze \(отключить расширения языка\)](../../build/reference/za-ze-disable-language-extensions.md)|  
|[\/Ze](../../build/reference/za-ze-disable-language-extensions.md)|Не рекомендуется. Включает расширения языка.|  
|[\/Zg](../../build/reference/zg-generate-function-prototypes.md)|Удален в Visual C\+\+ 2015. Создает прототипы функций.|  
|[\/ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)|Включает отладочную информацию в базу данных программы, совместимую с функцией "Изменить и продолжить".|  
|[\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)|Создает полную отладочную информацию.|  
|[\/Zl](../../build/reference/zl-omit-default-library-name.md)|Удаляет имя библиотеки по умолчанию из файла OBJ \(только архитектура x86\).|  
|[\/Zm](../Topic/-Zm%20\(Specify%20Precompiled%20Header%20Memory%20Allocation%20Limit\).md)|Указывает предел выделения памяти для предкомпилированного заголовка.|  
|[\/Zp](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md)|Упаковывает члены структур.|  
|[\/Zs](../../build/reference/zs-syntax-check-only.md)|Проверяет только синтаксис.|  
|[\/ZW](../../build/reference/zw-windows-runtime-compilation.md)|Создает выходной файл для выполнения в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].|  
  
## См. также  
 [Образец построения C\/C\+\+](../Topic/C-C++%20Building%20Reference.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)