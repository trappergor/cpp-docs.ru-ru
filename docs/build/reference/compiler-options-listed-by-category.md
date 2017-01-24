---
title: "Параметры компилятора, упорядоченные по категориям | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
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
ms.assetid: c4750dcf-dba0-4229-99b6-45cdecc11729
caps.latest.revision: 64
caps.handback.revision: 64
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Параметры компилятора, упорядоченные по категориям
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эта статья содержит сортированный по категориям список параметров компилятора. Сортированный в алфавитном порядке список см. в разделе [Параметры компилятора в алфавитном порядке](../../build/reference/compiler-options-listed-alphabetically.md).  
  
### Оптимизация  
  
|Параметр|Назначение|  
|--------------|----------------|  
|[\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|Уменьшает размер кода.|  
|[\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|Создает быстрый код.|  
|[\/Ob](../../build/reference/ob-inline-function-expansion.md)|Управляет подстановкой подставляемых функций.|  
|[\/Od](../../build/reference/od-disable-debug.md)|Отключает оптимизацию.|  
|[\/Og](../../build/reference/og-global-optimizations.md)|Не рекомендуется. Использует глобальную оптимизацию.|  
|[\/Oi](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md)|Создает встроенные функции.|  
|[\/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|Отдает приоритет уменьшению размера кода.|  
|[\/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|Отдает приоритет быстрому коду.|  
|[\/Ox](../../build/reference/ox-full-optimization.md)|Использует максимальную оптимизацию \(\/Ob2gity \/Gs\).|  
|[\/Oy](../../build/reference/oy-frame-pointer-omission.md)|Пропускает указатель на фрейм. \(только x86\)|  
|[\/favor](../../build/reference/favor-optimize-for-architecture-specifics.md)|Создает код, который оптимизирован для конкретной архитектуры или диапазона архитектур.|  
  
### Создание кода  
  
|Параметр|Назначение|  
|--------------|----------------|  
|[\/arch](../../build/reference/arch-x86.md)|Использование инструкций SSE или SSE2 при создании кода. \(только x86\)|  
|[\/clr](../../build/reference/clr-common-language-runtime-compilation.md)|Создает выходной файл, предназначенный для выполнения в среде CLR.|  
|[\/EH](../../build/reference/eh-exception-handling-model.md)|Задает модель обработки исключений.|  
|[\/fp](../../build/reference/fp-specify-floating-point-behavior.md)|Указывает поведение чисел с плавающей запятой.|  
|[\/GA](../../build/reference/ga-optimize-for-windows-application.md)|Выполняет оптимизацию для приложений Windows.|  
|[\/Gd](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__cdecl`. \(только x86\)|  
|[\/Ge](../Topic/-Ge%20\(Enable%20Stack%20Probes\).md)|Не рекомендуется. Включает стековые зонды.|  
|[\/GF](../Topic/-GF%20\(Eliminate%20Duplicate%20Strings\).md)|Включает объединение строк.|  
|[\/Gh](../../build/reference/gh-enable-penter-hook-function.md)|Вызывает функцию\-обработчик `_penter`.|  
|[\/GH](../../build/reference/gh-enable-pexit-hook-function.md)|Вызывает функцию\-обработчик `_pexit`.|  
|[\/GL](../../build/reference/gl-whole-program-optimization.md)|Включает оптимизацию всей программы.|  
|[\/Gm](../../build/reference/gm-enable-minimal-rebuild.md)|Включает минимальное перепостроение.|  
|[\/GR](../Topic/-GR%20\(Enable%20Run-Time%20Type%20Information\).md)|Включает информацию о типах во время выполнения \(RTTI\).|  
|[\/Gr](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__fastcall`. \(только x86\)|  
|[\/GS](../Topic/-GS%20\(Buffer%20Security%20Check\).md)|Проверяет безопасность буфера.|  
|[\/Gs](../../build/reference/gs-control-stack-checking-calls.md)|Управляет стековыми зондами.|  
|[\/GT](../../build/reference/gt-support-fiber-safe-thread-local-storage.md)|Поддерживает безопасность волокон для данных, размещаемых с помощью статической локальной памяти потока.|  
|[\/guard:cf](../../build/reference/guard-enable-control-flow-guard.md)|Добавление проверок безопасности для защиты потока управления.|  
|[\/Gv](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__vectorcall`. \(только x86 и x64\)|  
|[\/Gw](../../build/reference/gw-optimize-global-data.md)|Включает глобальную оптимизацию данных всей программы.|  
|[\/GX](../Topic/-GX%20\(Enable%20Exception%20Handling\).md)|Не рекомендуется. Включает синхронную обработку исключений. Используйте вместо этого параметр [\/EH](../../build/reference/eh-exception-handling-model.md).|  
|[\/Gy](../../build/reference/gy-enable-function-level-linking.md)|Включает компоновку на уровне функций.|  
|[\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)|Не рекомендуется. Включает быстрые проверки. \(Аналогично [\/RTC1](../../build/reference/rtc-run-time-error-checks.md)\)|  
|[\/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__stdcall`. \(только x86\)|  
|[\/homeparams](../../build/reference/homeparams-copy-register-parameters-to-stack.md)|Принудительная запись параметров, переданных в регистрах, в соответствующие места в стеке при вхождении в функцию. Данный параметр компилятора предназначен только для компиляторов [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] \(машинная компиляция и кросс\-компиляция\).|  
|[\/hotpatch](../../build/reference/hotpatch-create-hotpatchable-image.md)|Создает образ, допускающий горячее обновление.|  
|[\/Qfast\_transcendentals](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md)|Создает быстрые трансцендентные функции.|  
|[QIfist](../../build/reference/qifist-suppress-ftol.md)|Не рекомендуется. Подавляет вызов вспомогательной функции `_ftol` при необходимости преобразования из типа с плавающей запятой в целочисленный тип. \(только x86\)|  
|[\/Qimprecise\_fwaits](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Удаляет команды `fwait` внутри блоков `try`.|  
|[\/Qpar](../Topic/-Qpar%20\(Auto-Parallelizer\).md)|Включает автоматическую параллелизацию циклов.|  
|[\/Qpar\-report](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)|Включает уровни отчетов для автоматической параллелизации.|  
|[\/Qsafe\_fp\_loads](../../build/reference/qsafe-fp-loads.md)|Использует целочисленные инструкции перемещения значений с плавающей запятой и отключает определенные оптимизации загрузки значений с плавающей запятой.|  
|[\/Qvec\-report \(уровень отчетности автоматического векторизатора\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md)|Включает уровни отчетов для автоматической векторизации.|  
|[\/RTC](../../build/reference/rtc-run-time-error-checks.md)|Включает проверку ошибок во время выполнения.|  
|[\/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md)|Выбирает способ интерпретации ключевого слова volatile.|  
  
### Выходные файлы  
  
|Параметр|Назначение|  
|--------------|----------------|  
|[\/doc](../../build/reference/doc-process-documentation-comments-c-cpp.md)|Обрабатывает комментарии к документации в XML\-файл.|  
|[\/FA](../../build/reference/fa-fa-listing-file.md)|Настраивает файл списка сборки.|  
|[\/Fa](../../build/reference/fa-fa-listing-file.md)|Создает файл списка сборки.|  
|[\/Fd](../../build/reference/fd-program-database-file-name.md)|Переименовывает файл базы данных программы.|  
|[\/Fe](../../build/reference/fe-name-exe-file.md)|Переименовывает исполняемый файл.|  
|[\/Fi](../../build/reference/fi-preprocess-output-file-name.md)|Задает предобработанное имя выходного файла.|  
|[\/Fm](../Topic/-Fm%20\(Name%20Mapfile\).md)|Создает файл сопоставления.|  
|[\/Fo](../../build/reference/fo-object-file-name.md)|Создает объектный файл.|  
|[\/Fp](../Topic/-Fp%20\(Name%20.Pch%20File\).md)|Задает имя файла предкомпилированного заголовка.|  
|[\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)|Создает файлы браузера.|  
  
### Препроцессор  
  
|Параметр|Назначение|  
|--------------|----------------|  
|[\/AI](../../build/reference/ai-specify-metadata-directories.md)|Указывает каталог поиска для разрешения ссылок на файлы, указанные в директиве[\#using](../../preprocessor/hash-using-directive-cpp.md).|  
|[\/C](../../build/reference/c-preserve-comments-during-preprocessing.md)|Сохраняет комментарии на этапе предварительной обработки.|  
|[\/D](../../build/reference/d-preprocessor-definitions.md)|Определяет константы и макросы.|  
|[\/E](../../build/reference/e-preprocess-to-stdout.md)|Копирует выходные данные препроцессора в стандартный вывод.|  
|[\/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)|Копирует выходные данные препроцессора в стандартный вывод.|  
|[\/FI](../Topic/-FI%20\(Name%20Forced%20Include%20File\).md)|Выполняет предварительную обработку указанного включаемого файла.|  
|[\/FU](../../build/reference/fu-name-forced-hash-using-file.md)|Обеспечивает принудительное использование имени файла, как если бы оно было указано в директиве [\#using](../../preprocessor/hash-using-directive-cpp.md).|  
|[\/Fx](../../build/reference/fx-merge-injected-code.md)|Выполняет слияние введенного кода с исходным файлом.|  
|[\/I](../../build/reference/i-additional-include-directories.md)|Осуществляет поиск включаемых файлов в каталоге.|  
|[\/P](../../build/reference/p-preprocess-to-a-file.md)|Записывает выходные данные препроцессора в файл.|  
|[\/U](../Topic/-U,%20-u%20\(Undefine%20Symbols\).md)|Удаляет предварительно определенный макрос.|  
|[\/u](../Topic/-U,%20-u%20\(Undefine%20Symbols\).md)|Удаляет все предварительно определенные макросы.|  
|[\/X](../../build/reference/x-ignore-standard-include-paths.md)|Пропускает стандартный каталог включаемых файлов.|  
  
### Язык  
  
|Параметр|Назначение|  
|--------------|----------------|  
|[\/openmp](../../build/reference/openmp-enable-openmp-2-0-support.md)|Включает прагма\-директиву [\#pragma omp](../../preprocessor/omp.md) в исходном коде.|  
|[\/vd](../../build/reference/vd-disable-construction-displacements.md)|Подавляет или включает скрытые члены класса `vtordisp`.|  
|[\/vmb](../../build/reference/vmb-vmg-representation-method.md)|Использует оптимальное основание для указателей на члены.|  
|[\/vmg](../../build/reference/vmb-vmg-representation-method.md)|Использует полное обобщение для указателей на члены.|  
|[\/vmm](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Объявляет множественное наследование.|  
|[\/vms](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Объявляет одиночное наследование.|  
|[\/vmv](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Объявляет виртуальное наследование.|  
|[\/Z7](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)|Создает отладочную информацию, совместимую с C 7.0.|  
|[\/Za](../../build/reference/za-ze-disable-language-extensions.md)|Отключает расширения языка.|  
|[\/Zc](../../build/reference/zc-conformance.md)|Задает стандартное поведение при использовании параметра [\/Ze](../../build/reference/za-ze-disable-language-extensions.md).|  
|[\/Ze](../../build/reference/za-ze-disable-language-extensions.md)|Не рекомендуется. Включает расширения языка.|  
|[\/ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)|Включает отладочную информацию в базу данных программы, совместимую с функцией "Изменить и продолжить". \(только x86\)|  
|[\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)|Создает полную отладочную информацию.|  
|[\/Zl](../../build/reference/zl-omit-default-library-name.md)|Удаляет имя библиотеки по умолчанию из OBJ\-файла.|  
|[\/Zp](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md) *n*|Упаковывает члены структур.|  
|[\/Zs](../../build/reference/zs-syntax-check-only.md)|Проверяет только синтаксис.|  
|[\/ZW](../../build/reference/zw-windows-runtime-compilation.md)|Создает выходной файл для выполнения в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].|  
  
### Компоновка  
  
|Параметр|Назначение|  
|--------------|----------------|  
|[\/F](../../build/reference/f-set-stack-size.md)|Задает размер стека.|  
|[\/LD](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает библиотеку динамической компоновки.|  
|[\/LDd](../../build/reference/md-mt-ld-use-run-time-library.md)|Создает отладочную библиотеку динамической компоновки.|  
|[\/link](../Topic/-link%20\(Pass%20Options%20to%20Linker\).md)|Передает указанный параметр в программу LINK.|  
|[\/LN](../../build/reference/ln-create-msil-module.md)|Создает модуль MSIL.|  
|[\/MD](../../build/reference/md-mt-ld-use-run-time-library.md)|Компилирует для создания многопотоковой библиотеки DLL с помощью библиотеки MSVCRT.lib.|  
|[\/MDd](../../build/reference/md-mt-ld-use-run-time-library.md)|Компилирует для создания отладочной многопотоковой библиотеки DLL с помощью библиотеки MSVCRTD.lib.|  
|[\/MT](../../build/reference/md-mt-ld-use-run-time-library.md)|Компилирует для создания многопотокового исполняемого файла с помощью библиотеки LIBCMT.lib.|  
|[\/MTd](../../build/reference/md-mt-ld-use-run-time-library.md)|Компилирует для создания отладочного многопотокового исполняемого файла с помощью библиотеки LIBCMTD.lib.|  
  
### Предкомпилированный заголовок  
  
|Параметр|Назначение|  
|--------------|----------------|  
|[\/Y\-](../Topic/-Y-%20\(Ignore%20Precompiled%20Header%20Options\).md)|Пропускает все прочие параметры компилятора, относящиеся к предварительно скомпилированным заголовкам, в текущем построении.|  
|[\/Yc](../../build/reference/yc-create-precompiled-header-file.md)|Создает файл предкомпилированного заголовка.|  
|[\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|Размещает полную отладочную информацию во всех объектных файлах.|  
|[\/Yu](../../build/reference/yu-use-precompiled-header-file.md)|Использует файл предкомпилированного заголовка при построении.|  
  
### Прочее  
  
|Параметр|Назначение|  
|--------------|----------------|  
|[\/?](../../build/reference/help-compiler-command-line-help.md)|Отображает список параметров компилятора.|  
|[@](../../build/reference/at-specify-a-compiler-response-file.md)|Указывает файл ответа.|  
|[\/analyze](../../build/reference/analyze-code-analysis.md)|Включает анализ кода|  
|[\/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)|Увеличивает число адресуемых секций в OBJ\-файле.|  
|[\/c](../../build/reference/c-compile-without-linking.md)|Задает компиляцию без компоновки.|  
|[\/cgthreads](../../build/reference/cgthreads-code-generation-threads.md)|Задает число потоков cl.exe, используемых для оптимизации и создания кода.|  
|[\/errorReport](../Topic/-errorReport%20\(Report%20Internal%20Compiler%20Errors\).md)|Разрешает передавать данные о внутренних ошибках компилятора \(ICE\) непосредственно в группу Visual C\+\+.|  
|[\/FC](../Topic/-FC%20\(Full%20Path%20of%20Source%20Code%20File%20in%20Diagnostics\).md)|Отображает полный путь файлов исходного кода, переданных программе cl.exe, в диагностическом тексте.|  
|[\/FS](../../build/reference/fs-force-synchronous-pdb-writes.md)|Обеспечивает принудительную сериализацию записей в файл базы данных программы \(PDB\) с помощью MSPDBSRV.EXE.|  
|[\/H](../../build/reference/h-restrict-length-of-external-names.md)|Не рекомендуется. Ограничивает длину внешних \(открытых\) имен.|  
|[\/HELP](../../build/reference/help-compiler-command-line-help.md)|Отображает список параметров компилятора.|  
|[\/J](../../build/reference/j-default-char-type-is-unsigned.md)|Изменяет тип `char` по умолчанию.|  
|[\/kernel](../../build/reference/kernel-create-kernel-mode-binary.md)|Компилятор и компоновщик создадут двоичный файл для выполнения в ядре Windows.|  
|[\/MP](../../build/reference/mp-build-with-multiple-processes.md)|Параллельное построение нескольких исходных файлов.|  
|[\/nologo](../../build/reference/nologo-suppress-startup-banner-c-cpp.md)|Подавление отображения приветствия.|  
|[\/sdl](../../build/reference/sdl-enable-additional-security-checks.md)|Включает дополнительные функции безопасности и предупреждения.|  
|[\/showIncludes](../Topic/-showIncludes%20\(List%20Include%20Files\).md)|Отображает список всех включаемых файлов во время компиляции.|  
|[\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) [\/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Указывает исходный файл на языке C.|  
|[\/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) [\/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Указывает исходный файл на языке C\+\+.|  
|[\/V](../../build/reference/v-version-number.md)|Не рекомендуется. Задает строку версии.|  
|[\/w](../../build/reference/compiler-option-warning-level.md)|Отключает все предупреждения.|  
|[\/W0, \/W1, \/W2, \/W3, \/W4](../../build/reference/compiler-option-warning-level.md)|Задает уровень выходного предупреждения.|  
|[\/w1, \/w2, \/w3, \/w4](../../build/reference/compiler-option-warning-level.md)|Задает уровень для указанного предупреждения.|  
|[\/Wall](../../build/reference/compiler-option-warning-level.md)|Включает все предупреждения, в том числе предупреждения, отключенные по умолчанию.|  
|[\/wd](../../build/reference/compiler-option-warning-level.md)|Отключает указанное предупреждение.|  
|[\/we](../../build/reference/compiler-option-warning-level.md)|Обрабатывает указанное предупреждение как ошибку.|  
|[\/WL](../../build/reference/wl-enable-one-line-diagnostics.md)|Включает однострочные диагностические сообщения об ошибках и предупреждения в ходе компиляции исходного кода C\+\+ из командной строки.|  
|[\/wo](../../build/reference/compiler-option-warning-level.md)|Отображает указанное предупреждение только один раз.|  
|[\/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md)|Является устаревшей. Выявляет проблемы 64\-битной переносимости.|  
|[\/Wv](../../build/reference/compiler-option-warning-level.md)|Отключает предупреждения, появившиеся в более поздних версиях компилятора.|  
|[\/WX](../../build/reference/compiler-option-warning-level.md)|Обрабатывает предупреждения как ошибки.|  
|[\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|Не рекомендуется. Размещает полную отладочную информацию во всех объектных файлах. Используйте вместо этого параметр [\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md).|  
|[\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)|Вставляет ссылку PCH при создании отладочной библиотеки.|  
|[\/Zm](../Topic/-Zm%20\(Specify%20Precompiled%20Header%20Memory%20Allocation%20Limit\).md)|Указывает предел выделения памяти для предкомпилированного заголовка.|  
  
### Нерекомендуемые и удаленные параметры компилятора  
  
|Параметр|Назначение|  
|--------------|----------------|  
|[\/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md)|Не рекомендуется. Взамен рекомендуется использовать [\/LN \(создание модуля MSIL\)](../../build/reference/ln-create-msil-module.md).|  
|[\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)|Не рекомендуется. Создает файл информации об исходном коде без локальных переменных.|  
|[\/Ge](../Topic/-Ge%20\(Enable%20Stack%20Probes\).md)|Не рекомендуется. Включает стековые зонды. По умолчанию включен.|  
|[\/GX](../Topic/-GX%20\(Enable%20Exception%20Handling\).md)|Не рекомендуется. Включает синхронную обработку исключений. Используйте вместо этого параметр [\/EH](../../build/reference/eh-exception-handling-model.md).|  
|[\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)|Не рекомендуется. Включает быстрые проверки. Используйте вместо этого параметр [\/RTC1](../../build/reference/rtc-run-time-error-checks.md).|  
|[\/H](../../build/reference/h-restrict-length-of-external-names.md)|Не рекомендуется. Ограничивает длину внешних \(открытых\) имен.|  
|[\/Og](../../build/reference/og-global-optimizations.md)|Не рекомендуется. Использует глобальную оптимизацию.|  
|[QIfist](../../build/reference/qifist-suppress-ftol.md)|Не рекомендуется. Используется один раз для указания способа преобразования типа с плавающей запятой в целочисленный тип.|  
|[\/V](../../build/reference/v-version-number.md)|Не рекомендуется. Задает строку версии OBJ\-файла.|  
|[\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|Не рекомендуется. Размещает полную отладочную информацию во всех объектных файлах. Используйте вместо этого параметр [\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md).|  
|[\/Zc:forScope\-](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)|Не рекомендуется. Отключает согласование видимости переменных, объявленных в заголовке оператора for.|  
|[\/Ze](../../build/reference/za-ze-disable-language-extensions.md)|Не рекомендуется. Включает расширения языка.|  
|[\/Zg](../../build/reference/zg-generate-function-prototypes.md)|Удален в Visual C\+\+ 2015. Создает прототипы функций.|  
  
## См. также  
 [Образец построения C\/C\+\+](../Topic/C-C++%20Building%20Reference.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)