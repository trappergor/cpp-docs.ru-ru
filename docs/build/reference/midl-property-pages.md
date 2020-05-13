---
title: Страницы свойств компилятора MIDL
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 57498a01-fccc-4a0e-a036-6ff702f83126
f1_keywords:
- VC.Project.VCMidlTool.PreprocessorDefinitions
- VC.Project.VCMidlTool.AdditionalIncludeDirectories
- VC.Project.VCMidlTool.AdditionalMetadataDirectories
- VC.Project.VCMidlTool.IgnoreStandardIncludePath
- VC.Project.VCMidlTool.IgnoreStandardIncludePath
- VC.Project.VCMidlTool.MkTypLibCompatible
- VC.Project.VCMidlTool.WarningLevel
- VC.Project.VCMidlTool.WarnAsError
- VC.Project.VCMidlTool.SuppressStartupBanner
- VC.Project.VCMidlTool.DefaultCharType
- VC.Project.VCMidlTool.TargetEnvironment
- VC.Project.VCMidlTool.GenerateStublessProxies
- VC.Project.VCMidlTool.SuppressCompilerWarnings
- VC.Project.VCMidlTool.ApplicationConfigurationMode
- VC.Project.VCMidlTool.LocaleID
- VC.Project.VCMidlTool.MultiProcMIDL
- VC.Project.VCMidlTool.OutputDirectory
- VC.Project.VCMidlTool.WinmdFileName
- VC.Project.VCMidlTool.HeaderFileName
- VC.Project.VCMidlTool.DLLDataFileName
- VC.Project.VCMidlTool.InterfaceIdentifierFileName
- VC.Project.VCMidlTool.ProxyFileName
- VC.Project.VCMidlTool.GenerateTypeLibrary
- VC.Project.VCMidlTool.TypeLibraryName
- VC.Project.VCMidlTool.GenerateClientFiles
- VC.Project.VCMidlTool.GenerateServerFiles
- VC.Project.VCMidlTool.ClientStubFile
- VC.Project.VCMidlTool.ServerStubFile
- VC.Project.VCMidlTool.TypeLibFormat
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.PreendWithABINamepsace
- VC.Project.VCMidlTool.ValidateParameters
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.MinimumTargetSystem
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: d6833230baca892836c187799df7f0658aa16772
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336244"
---
# <a name="midl-property-pages"></a>Страницы свойств MIDL

Страницы свойств MIDL доступны в качестве свойства элемента на . IDL-файл в проекте СЗЗ, использующем COM. Используйте их для настройки [компилятора MIDL.](/windows/win32/midl/using-the-midl-compiler-2) Сведения о программном доступе к параметрам MIDL для проектов C++ см. в описании объекта <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool> Смотрите также [Генеральный MIDL Командная линия Syntax](/windows/win32/midl/general-midl-command-line-syntax).

## <a name="general-property-page"></a>Страница общего имущества

### <a name="preprocessor-definitions"></a>Определения препроцессора

Определяет один или несколько определяет, в том числе MIDL\]макросы ( /[D](/windows/win32/midl/-d))\[макросы ).

### <a name="additional-include-directories"></a>Дополнительные каталоги включаемых файлов

Укажите один или несколько каталогов, чтобы добавить\]в путь включения ([/I](/windows/win32/midl/-i)\[путь ).

### <a name="additional-metadata-directories"></a>Дополнительные каталоги метаданных

Укажите каталог, содержащий файл Windows.Foundation.WinMD\]([/metadata_dir](/windows/win32/midl/-metadata-dir) \[путь).

### <a name="enable-windows-runtime"></a>Включить время выполнения Windows

Включить семантику Windows Runtime для создания файла метаданных Windows ([/winrt](/windows/win32/midl/-winrt)).

### <a name="ignore-standard-include-path"></a>Игнорировать Стандартный Включить Путь

Игнорировать текущие и INCLUDE каталоги ([/ no_def_idir](/windows/win32/midl/-no-def-idir)).

### <a name="mktyplib-compatible"></a>MkTypLib Совместима

Силовая совместимость с mktyplib.exe версией 2.03 ([/mktyplib203](/windows/win32/midl/-mktyplib203)).

### <a name="warning-level"></a>Уровень предупреждений

Выбирает строгость ошибок кода MIDL ([/W](/windows/win32/midl/-w)).

**Choices**

- **1**
- **1**
- **2**
- **3**
- **4**

### <a name="treat-warnings-as-errors"></a>Обрабатывать предупреждения как ошибки

Позволяет MIDL рассматривать все предупреждения как ошибки ([/WX).](/windows/win32/midl/-wx)

### <a name="suppress-startup-banner"></a>Отключить загрузочный баннер

Подавите отображение баннера запуска и информационного сообщения ([/nologo](/windows/win32/midl/-nologo)).

### <a name="c-compiler-char-type"></a>C Компилятор Чар Тип

Определяет тип символа по умолчанию компилятора C, который будет использоваться для компиляции генерируемого кода. ([/char](/windows/win32/midl/-char) подписано неподписанным ascii7).

**Choices**

- **Подписано** - Подписано
- **Не подписано** - Неподписано
- **Асци** - Асци

### <a name="target-environment"></a>Целевое окружение

Определяет, в какой среде нацеливаться ([/env](/windows/win32/midl/-env) arm32'win32-ia64'x64).

**Choices**

- **Не набор** - Win32
- **Microsoft Windows 32-битный** - Win32
- **Microsoft Windows 64-битный на Itanium** - IA64
- **Microsoft Windows ARM** - ARM
- **Microsoft Windows ARM64** - ARM64
- **Microsoft Windows 64-битный на x64** - X64

### <a name="generate-stubless-proxies"></a>Создание безукоризненные прокси

Создание полностью интерпретируемых заглушки с расширениями и безоглухих прокси для интерфейсов объектов ([/Oicf](/windows/win32/midl/-oi), [/Oif](/windows/win32/midl/-oi) ).

### <a name="suppress-compiler-warnings"></a>Подавление предупреждений компилятора

Подавите предупреждающие сообщения компилятора[(/no_warn).](/windows/win32/midl/-no-warn)

### <a name="application-configuration-mode"></a>Режим конфигурации приложений

Разрешить выбранные атрибуты ACF в файле IDL ([/app_config).](/windows/win32/midl/-app-config)

### <a name="locale-id"></a>Код языка

Осваивай LCID для вхотворных файлов, имен файлов и путей каталога[(/lcid](/windows/win32/midl/-lcid) DECIMAL).

### <a name="multi-processor-compilation"></a>Многопроцессорная компиляция

Выполнить несколько экземпляров одновременно.

## <a name="output-property-page"></a>Страница свойств вывода

### <a name="output-directory"></a>Выходной каталог

Определяет каталог вывода ([/из](/windows/win32/midl/-out) «каталога»).

### <a name="metadata-file"></a>Файл метаданных

Угоняет название сгенерированного файла метаданных ([/winmd](/windows/win32/midl/-winmd) filename).

### <a name="header-file"></a>Файл заголовка

Угоняется название генерируемого файла заголовка ([/h](/windows/win32/midl/-h) имя файла).

### <a name="dlldata-file"></a>Файл DllData

Упогоняет название файла DLLDATA ([/dlldata](/windows/win32/midl/-dlldata) filename).

### <a name="iid-file"></a>Файл IID

Угоняет название файла идентификатора интерфейса[(/iid](/windows/win32/midl/-iid) filename).

### <a name="proxy-file"></a>Прокси-файл

Угоняет название файла прокси[(/прокси-файла).](/windows/win32/midl/-proxy)

### <a name="generate-type-library"></a>Создание библиотеки типа

Укажите не создавать библиотеку типов (no).

### <a name="type-library"></a>Тип библиотеки

Угоняет имя файла библиотеки типа[(/tlb](/windows/win32/midl/-tlb) filename).

### <a name="generate-client-stub-files"></a>Создание файлов клиентских ступов

Генерировать файл клиента заглушки только ([/клиент](/windows/win32/midl/-client) »stub »нет»).

**Choices**

- **Заглушка** - Заглушка
- **Нет** - Нет

### <a name="generate-server-stub-files"></a>Создание файлов сервера Stub

Генерировать только файл сервера заглушки[(/сервер](/windows/win32/midl/-server) «stub»none).

**Choices**

- **Заглушка** - Заглушка
- **Нет** - Нет

### <a name="client-stub-file"></a>КлиентСкий файл Stub

Укажите файл клиентской заглушки[(/cstub](/windows/win32/midl/-cstub) (файл).

### <a name="server-stub-file"></a>Сервер Stub файл

Укажите файл заглушки сервера[(/sstub](/windows/win32/midl/-sstub) (файл).

### <a name="type-library-format"></a>Формат библиотеки типа

Обрабражем формат файла библиотеки типа (з/старый/newtlb)...

**Choices**

- **NewFormat** - Новый формат
- **СтарыйФормат** - Старый Формат

## <a name="advanced-property-page"></a>Расширенная страница свойств

### <a name="c-preprocess-options"></a>Параметры preprocess C

Определяет коммутаторы для передачи препроцессору c-компилятора[(/cpp_opt](/windows/win32/midl/-cpp-opt) переключатели).

### <a name="undefine-preprocessor-definitions"></a>Отменить определения препроцессора

Определяет один или несколько неопределенных, в том числе midL макросов ([/ U](/windows/win32/midl/-U) (макрос).

### <a name="enable-error-checking"></a>Проверка ошибок включить

Выберите опцию проверки ошибок («ошибка всех» (no).

**Choices**

- **EnableCustom** - Все
- **Все** - Все
- **Нет** - Нет

### <a name="check-allocations"></a>Проверка распределения

Проверьте наличие ошибок памяти ([/распределение ошибок).](/windows/win32/midl/-error)

### <a name="check-bounds"></a>Проверка границ

Проверьте размер против спецификации длины передачи ([/ошибка](/windows/win32/midl/-error) bounds_check).

### <a name="check-enum-range"></a>Проверить диапазон Enum

Проверьте значения enum, чтобы быть в допустимом диапазоне ([/ошибка](/windows/win32/midl/-error) enum).

### <a name="check-reference-pointers"></a>Проверить ориентиры

Проверьте указатели реф, чтобы быть не-недействительными ([/ошибка](/windows/win32/midl/-error) рефери).

### <a name="check-stub-data"></a>Проверка данных Stub

Эмит дополнительной проверки для сервера стороне заглушки данных достоверности ([/ ошибка](/windows/win32/midl/-error) stub_data).

### <a name="prepend-with-abi-namespace"></a>Подготовительс с пространством имен 'ABI'

Подготовьте пространство имен 'ABI' для всех типов.  ([/ns_prefix](/windows/win32/midl/-ns-prefix)).

### <a name="validate-parameters"></a>Параметры проверки

Создание дополнительной информации для проверки параметров ( | [/robust/no_robust).](/windows/win32/midl/-no-robust)[/robust](/windows/win32/midl/-robust)

### <a name="struct-member-alignment"></a>Выравнивание участников Struct

Определяет уровень упаковки структур в целевой системе (/ЗПН).

**Choices**

- **Не набор** - не установить
- **1 Байт** - P1
- **2 Байт** - P2
- **4 Байт** - P4
- **8 Байт** - P8

### <a name="redirect-output"></a>Перенаправить выход

Перенаправляет выход с экрана на файл[(/o](/windows/win32/midl/-o) файл).

### <a name="minimum-target-system"></a>Минимальная целевая система

Установите минимальную целевую систему ([/target](/windows/win32/midl/-target) STRING).
