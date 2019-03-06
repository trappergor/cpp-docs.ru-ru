---
title: Параметры компоновщика
ms.date: 08/20/2018
f1_keywords:
- link
helpviewer_keywords:
- linker [C++]
- linker [C++], options listed
- libraries [C++], linking to COFF
- LINK tool [C++], linker options
ms.assetid: c1d51b8a-bd23-416d-81e4-900e02b2c129
ms.openlocfilehash: 63cfa784242af1f737c116629a29be5ad77af31d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415205"
---
# <a name="linker-options"></a>Параметры компоновщика

LINK.exe связывает объектные файлы в формате COFF и библиотеки для создания исполняемого файла (EXE) или библиотеки динамической компоновки (DLL).

В таблице ниже перечислены параметры для программы LINK.exe. Подробнее о LINK см. в следующих разделах.

- [Управляемые компилятором параметры LINK](../../build/reference/compiler-controlled-link-options.md)

- [Входные LINK-файлы](../../build/reference/link-input-files.md)

- [Выходные данные LINK](../../build/reference/link-output.md)

- [Зарезервированные слова](../../build/reference/reserved-words.md)

В командной строке параметры компоновщика указываются без учета регистра; Например / base и/Base идентичны. Дополнительные сведения о том, как указать каждый параметр в командной строке или в Visual Studio, см. в документации для этого параметра.

Директиву pragma [comment](../../preprocessor/comment-c-cpp.md) можно использовать для задания некоторых параметров компоновщика.

|Параметр|Цель|
|------------|-------------|
|[@](../../build/reference/at-specify-a-linker-response-file.md)|Указывает файл ответа.|
|[/ALIGN](../../build/reference/align-section-alignment.md)|Задает выравнивание каждой секции.|
|[/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md)|Указывает на то, что библиотека DLL не может быть привязана.|
|[/ALLOWISOLATION](../../build/reference/allowisolation-manifest-lookup.md)|Задает поведение нахождения файлов манифеста.|
|[/APPCONTAINER](../../build/reference/appcontainer-windows-store-app.md)|Определяет, должно ли приложение выполняться в среде процесса контейнера приложений.|
|[/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)|Добавляет атрибут <xref:System.Diagnostics.DebuggableAttribute> в управляемый образ.|
|[/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)|Создает ссылку на управляемый ресурс.|
|[/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)|Указывает на то, что в сборку должен быть импортирован модуль MSIL.|
|[/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)|Внедряет файл управляемых ресурсов в сборку.|
|[/BASE](../../build/reference/base-base-address.md)|Задает базовый адрес для программы.|
|[/CGTHREADS](../../build/reference/cgthreads-compiler-threads.md)|Задает число потоков cl.exe, используемых для оптимизации и создания кода, если задано создание кода во время компоновки.|
|[/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md)|Задает тип (IJW, pure или safe) CLR-образа.|
|[/CLRSUPPORTLASTERROR](../../build/reference/clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)|Сохраняет последний код ошибки функций, вызываемых с помощью механизма P/Invoke.|
|[/CLRTHREADATTRIBUTE](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md)|Указывает атрибут потока для применения к точке входа CLR-программы.|
|[/CLRUNMANAGEDCODECHECK](../../build/reference/clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md)|Указывает, должен ли компоновщик применять атрибут SuppressUnmanagedCodeSecurity к создаваемым компоновщиком заглушкам PInvoke, осуществляющим вызовы из управляемого кода в библиотеки DLL неуправляемого кода.|
|[/DEBUG](../../build/reference/debug-generate-debug-info.md)|Создает отладочную информацию.|
|[/DEBUGTYPE](../../build/reference/debugtype-debug-info-options.md)|Указывает, какие данные необходимо включить в отладочную информацию.|
|[/DEF](../../build/reference/def-specify-module-definition-file.md)|Передает компоновщику файл определения модуля (DEF).|
|[/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md)|Проводит поиск по указанной библиотеке при разрешении внешних ссылок.|
|[/DELAY](../../build/reference/delay-delay-load-import-settings.md)|Управляет отложенной загрузкой библиотек DLL.|
|[/DELAYLOAD](../../build/reference/delayload-delay-load-import.md)|Включает отложенную загрузку указанной библиотеки DLL.|
|[/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)|Частично подписывает сборку.|
|[/ DEPENDENTLOADFLAG](dependentloadflag.md)|Задает флаги по умолчанию для зависимой загрузки DLL.|
|[/DLL](../../build/reference/dll-build-a-dll.md)|Выполняет сборку библиотеки DLL.|
|[/DRIVER](../../build/reference/driver-windows-nt-kernel-mode-driver.md)|Создает драйвер режима ядра.|
|[/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md)|Указывает, следует ли создавать исполняемый образ, базовый адрес которого может быть случайным образом изменен во время загрузки с помощью технологии ASLR.|
|[/ENTRY](../../build/reference/entry-entry-point-symbol.md)|Задает начальный адрес.|
|[/errorReport](../../build/reference/errorreport-report-internal-linker-errors.md)|Передает сведения о внутренних ошибках компоновщика в Майкрософт.|
|[/EXPORT](../../build/reference/export-exports-a-function.md)|Экспортирует функцию.|
|[/ FILEALIGN](../../build/reference/filealign.md)|Выравнивание разделов в выходном файле на кратные с указанным значением.|
|[/FIXED](../../build/reference/fixed-fixed-base-address.md)|Создает программу, которая может загружаться только по предпочтительному базовому адресу.|
|[/FORCE](../../build/reference/force-force-file-output.md)|Принудительное завершение компоновки даже в случае наличия неразрешенных или многократно определенных символов.|
|[/FUNCTIONPADMIN](../../build/reference/functionpadmin-create-hotpatchable-image.md)|Создает образ, для которого можно выполнять горячее обновление.|
|[/GENPROFILE, /FASTGENPROFILE](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)|Оба эти параметра задают создание PGD-файла компоновщиком для поддержки профильной оптимизации (PGO). /GENPROFILE и /FASTGENPROFILE используют разные параметры по умолчанию.|
|[/GUARD](../../build/reference/guard-enable-guard-checks.md)|Включает защиту потока управления.|
|[/HEAP](../../build/reference/heap-set-heap-size.md)|Задает размер кучи в байтах.|
|[/HIGHENTROPYVA](../../build/reference/highentropyva-support-64-bit-aslr.md)|Определяет поддержку 64-разрядной функции Address Space Layout Randomization (ASLR) с высоким уровнем энтропии.|
|[/IDLOUT](../../build/reference/idlout-name-midl-output-files.md)|Указывает имя файла IDL и имена других выходных файлов MIDL.|
|[/IGNORE](../../build/reference/ignore-ignore-specific-warnings.md)|Отменяет вывод указанных предупреждений компоновщика.|
|[/IGNOREIDL](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)|Предотвращает преобразование сведений атрибутов в файл IDL.|
|[/IMPLIB](../../build/reference/implib-name-import-library.md)|Переопределяет имя библиотеки импорта по умолчанию.|
|[/INCLUDE](../../build/reference/include-force-symbol-references.md)|Принудительное использование ссылок на символы.|
|[/INCREMENTAL](../../build/reference/incremental-link-incrementally.md)|Управляет инкрементной компоновкой.|
|[/INTEGRITYCHECK](../../build/reference/integritycheck-require-signature-check.md)|Указывает на то, что модуль требует проверки подписи во время загрузки.|
|[/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)|Задает контейнер ключей для подписи сборки.|
|[/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)|Задает ключ или пару ключей для подписи сборки.|
|[/LARGEADDRESSAWARE](../../build/reference/largeaddressaware-handle-large-addresses.md)|Указывает компилятору на то, что приложение поддерживает адреса, превышающие два гигабайта.|
|[/LIBPATH](../../build/reference/libpath-additional-libpath.md)|Указывает путь для поиска перед путем среды библиотеки.|
|[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)|Задает создание кода во время компоновки.|
|[/MACHINE](../../build/reference/machine-specify-target-platform.md)|Указывает целевую платформу.|
|[/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)|Создает параллельный файл манифеста и при необходимости включает его в двоичный файл.|
|[/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md)|Указывает \<dependentAssembly > раздела в файле манифеста.|
|[/MANIFESTFILE](../../build/reference/manifestfile-name-manifest-file.md)|Изменяет имя файла манифеста по умолчанию.|
|[/MANIFESTINPUT](../../build/reference/manifestinput-specify-manifest-input.md)|Задает входной файл манифеста для обработки и внедрения компоновщиком в двоичный файл. Этот параметр можно использовать несколько раз, чтобы указать несколько входных файлов манифеста.|
|[/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)|Указывает, следует ли внедрять в манифест программы сведения о контроле учетных записей.|
|[/MAP](../../build/reference/map-generate-mapfile.md)|Создает файл сопоставления.|
|[/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)|Включает указанные сведения в файл сопоставления.|
|[/MERGE](../../build/reference/merge-combine-sections.md)|Объединяет разделы.|
|[/MIDL](../../build/reference/midl-specify-midl-command-line-options.md)|Задает параметры командной строки MIDL.|
|[/ NATVIS](../../build/reference/natvis-add-natvis-to-pdb.md)|Добавляет визуализаторы отладчика из файла Natvis в PDB-ФАЙЛ.|
|[/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)|Подавляет создание сборки .NET Framework.|
|[/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)|Пропускает все (или только указанные) библиотеки по умолчанию при разрешении внешних ссылок.|
|[/NOENTRY](../../build/reference/noentry-no-entry-point.md)|Создает библиотеку DLL, содержащую только ресурсы.|
|[/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)|Отключает загрузочный баннер.|
|[/NXCOMPAT](../../build/reference/nxcompat-compatible-with-data-execution-prevention.md)|Помечает исполняемый файл как файл, проверенный на совместимость с компонентом предотвращения выполнения данных Windows.|
|[/OPT](../../build/reference/opt-optimizations.md)|Управляет оптимизацией LINK.|
|[/ORDER](../../build/reference/order-put-functions-in-order.md)|Помещает секции COMDAT в образ в предопределенном порядке.|
|[/OUT](../../build/reference/out-output-file-name.md)|Задает имя выходного файла.|
|[/PDB](../../build/reference/pdb-use-program-database.md)|Создает файл базы данных программы (PDB).|
|[/PDBALTPATH](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)|Использует альтернативное местоположение для сохранения файла PDB.|
|[/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)|Создает файл базы данных программы (PDB), не содержащий закрытых символов.|
|[/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)|Задает файл PGD для профильных оптимизаций.|
|[/POGOSAFEMODE](../../build/reference/pogosafemode-linker-option.md)|**Устаревшие** создает сборку инструментирования профильной Оптимизации поточно ориентированными.|
|[/PROFILE](../../build/reference/profile-performance-tools-profiler.md)|Создает выходной файл, который может быть использован для профилировщика производительности инструментов.|
|[/RELEASE](../../build/reference/release-set-the-checksum.md)|Задает контрольную сумму в заголовке файла EXE.|
|[/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)|Указывает на то, что образ будет содержать таблицу безопасных обработчиков исключений.|
|[/SECTION](../../build/reference/section-specify-section-attributes.md)|Переопределяет атрибуты секции.|
|[/ SOURCELINK](../../build/reference/sourcelink.md)|Указывает файл SourceLink для добавления в PDB.|
|[/STACK](../../build/reference/stack-stack-allocations.md)|Задает размер стека (в байтах).|
|[/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)|Присоединяет программу-заглушку MS-DOS к программе Win32.|
|[/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)|Указывает операционной системе, как запускать файл EXE.|
|[/SWAPRUN](../../build/reference/swaprun-load-linker-output-to-swap-file.md)|Указывает операционной системе на необходимость копирования выходного файла компоновщика в файл подкачки перед его запуском.|
|[/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md)|Указывает идентификатор ресурса библиотеки типов, создаваемой компоновщиком.|
|[/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)|Указывает имя файла TLB и имена других выходных файлов MIDL.|
|[/TSAWARE](../../build/reference/tsaware-create-terminal-server-aware-application.md)|Создает приложение, специально рассчитанное на запуск под управлением сервера терминалов.|
|[/USEPROFILE](../../build/reference/useprofile.md)|Использует профильной оптимизации обучающих данных для создания оптимизированного образа.|
|[/VERBOSE](../../build/reference/verbose-print-progress-messages.md)|Печатает сообщения хода выполнения компоновщика.|
|[/VERSION](../../build/reference/version-version-information.md)|Присваивает номер версии.|
|[/ WHOLEARCHIVE](../../build/reference/wholearchive-include-all-library-object-files.md)|Включает в себя каждого файла объект из указанного статических библиотек.|
|[/WINMD](../../build/reference/winmd-generate-windows-metadata.md)|Включает создание файлов метаданных среды выполнения Windows.|
|[/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md)|Задает имя файла для выходного файла метаданных среды выполнения Windows (winmd), создаваемого параметром компоновщика [/WINMD](../../build/reference/winmd-generate-windows-metadata.md) .|
|[/WINMDKEYFILE](../../build/reference/winmdkeyfile-specify-winmd-key-file.md)|Задает ключ или пару ключей для подписи файла метаданных среды выполнения Windows.|
|[/WINMDKEYCONTAINER](../../build/reference/winmdkeycontainer-specify-key-container.md)|Указывает контейнер ключей для подписания файла метаданных Windows.|
|[/WINMDDELAYSIGN](../../build/reference/winmddelaysign-partially-sign-a-winmd.md)|Частично подписывает файл метаданных среды выполнения Windows (.winmd), установив открытый ключ в файле winmd.|
|[/WX](../../build/reference/wx-treat-linker-warnings-as-errors.md)|Обрабатывает предупреждения компоновщика как ошибки.|

Дополнительные сведения см. в разделе [Compiler-Controlled LINK Options](../../build/reference/compiler-controlled-link-options.md).

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](../../build/reference/c-cpp-building-reference.md)<br/>
[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)
