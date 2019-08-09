---
title: Страницы свойств компилятора MIDL
ms.date: 7/24/2019
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
ms.openlocfilehash: 8174f6382ea2dab4ef2a49f5d30a6e27e8af3f5b
ms.sourcegitcommit: ce3393846c86e7905ff0c86e4cd6610476809585
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2019
ms.locfileid: "68492163"
---
# <a name="midl-property-pages"></a>Страницы свойств MIDL

Страницы свойств MIDL доступны в виде свойства элемента в. IDL-файл в C++ проекте, использующем com. Используйте их для настройки [компилятора MIDL](/windows/win32/midl/using-the-midl-compiler-2). Сведения о программном доступе к параметрам MIDL для проектов C++ см. в описании объекта <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool> См. также [Общий синтаксис командной строки MIDL](/windows/win32/midl/general-midl-command-line-syntax).

## <a name="general-property-page"></a>Страница свойств "Общие"

### <a name="preprocessor-definitions"></a>Определения препроцессора

Задает одно или несколько определений, включая макросы MIDL[](/windows/win32/midl/-d)(/d\[)\].

### <a name="additional-include-directories"></a>Дополнительные каталоги включаемых файлов

Указывает один или несколько каталогов для добавления к пути включения (\]путь[/i](/windows/win32/midl/-i)\[).

### <a name="additional-metadata-directories"></a>Дополнительные каталоги метаданных

Укажите каталог, содержащий файл Windows. Foundation. winmd (\]путь[/metadata_dir](/windows/win32/midl/-metadata-dir) \[).

### <a name="enable-windows-runtime"></a>Включить среда выполнения Windows

Включите семантику среда выполнения Windows, чтобы создать файл метаданных Windows ([/WinRT](/windows/win32/midl/-winrt)).

### <a name="ignore-standard-include-path"></a>Игнорировать стандартный путь включаемых файлов

Пропуск текущих и ВКЛЮЧАЕМых каталогов ([/no_def_idir](/windows/win32/midl/-no-def-idir)).

### <a name="mktyplib-compatible"></a>Совместимый с MkTypLib

Вызывает принудительную совместимость с MkTypLib. exe версии 2,03 ([/mktyplib203](/windows/win32/midl/-mktyplib203)).

### <a name="warning-level"></a>Уровень предупреждений

Устанавливает точность ошибок кода MIDL ([/w](/windows/win32/midl/-w)).

**Элементов**

- **1**
- **1**
- **2**
- **3**
- **4**

### <a name="treat-warnings-as-errors"></a>Обрабатывать предупреждения как ошибки

Позволяет MIDL обрабатывать все предупреждения как ошибки ([/WX](/windows/win32/midl/-wx)).

### <a name="suppress-startup-banner"></a>Отключить загрузочный баннер

Отключает отображение загрузочного баннера и информационного сообщения ([/nologo](/windows/win32/midl/-nologo)).

### <a name="c-compiler-char-type"></a>Тип char компилятора C

Указывает тип символа по умолчанию для компилятора C, который будет использоваться для компиляции созданного кода. ([/char](/windows/win32/midl/-char) подписано | не подписано | ascii7).

**Элементов**

- **Подписано** -подписано
- Без **знака** — без знака
- **ASCII** -ASCII

### <a name="target-environment"></a>Целевая среда

Указывает целевую среду ([/env](/windows/win32/midl/-env) ARM32 | Win32 | ia64 | x64).

**Элементов**

- **Не задано** — Win32
- **Microsoft Windows 32-bit** -Win32
- **Microsoft Windows 64-bit на платформе Itanium** -ia64
- **ARM Microsoft Windows**
- **Microsoft Windows ARM64** — ARM64
- **Microsoft Windows 64-bit на x64** -x64

### <a name="generate-stubless-proxies"></a>Создание прокси без заглушек

Создание полностью интерпретируемых заглушек с расширениями и прокси без заглушек для объектных интерфейсов ([/Oicf](/windows/win32/midl/-Oicf), [/OIF](/windows/win32/midl/-Oif) ).

### <a name="suppress-compiler-warnings"></a>Подавление предупреждений компилятора

Подавлять предупреждающие сообщения компилятора ([/no_warn](/windows/win32/midl/-no_warn)).

### <a name="application-configuration-mode"></a>Режим конфигурации приложения

Разрешить выбранные атрибуты ACF в IDL-файле ([/app_config](/windows/win32/midl/-app_config)).

### <a name="locale-id"></a>КОД локали

Указывает код языка для входных файлов, имен файлов и путей к каталогам ([/LCID](/windows/win32/midl/-lcid) Decimal).

### <a name="multi-processor-compilation"></a>Многопроцессорная компиляция

Одновременное выполнение нескольких экземпляров.

## <a name="output-property-page"></a>Страница свойств «вывод»

### <a name="output-directory"></a>Выходной каталог

Указывает выходной каталог ([/out](/windows/win32/midl/-out) [каталог]).

### <a name="metadata-file"></a>Файл метаданных

Задает имя создаваемого файла метаданных ([/WinMD](/windows/win32/midl/-winmd) filename).

### <a name="header-file"></a>Заголовочный файл

Задает имя создаваемого файла заголовка ([/h](/windows/win32/midl/-h) filename).

### <a name="dlldata-file"></a>Файл DllData

Указывает имя файла DLLDATA ([/dlldata](/windows/win32/midl/-dlldata) filename).

### <a name="iid-file"></a>Файл IID

Задает имя для файла идентификатора интерфейса ([/IID](/windows/win32/midl/-iid) filename).

### <a name="proxy-file"></a>Файл прокси-сервера

Указывает имя прокси-файла ([/proxy](/windows/win32/midl/-proxy) filename).

### <a name="generate-type-library"></a>Создать библиотеку типов

Укажите не создавать библиотеку типов ([/notlb] для No).

### <a name="type-library"></a>Библиотека типов

Задает имя файла библиотеки типов ([/tlb](/windows/win32/midl/-tlb) filename).

### <a name="generate-client-stub-files"></a>Создание файлов заглушки клиента

Создать только файл заглушки клиента ([/Client](/windows/win32/midl/-client) [заглушка | нет]).

**Элементов**

- Заглушка заглушки
- **None** — нет.

### <a name="generate-server-stub-files"></a>Создание файлов заглушки сервера

Создать только файл заглушки сервера ([/Server](/windows/win32/midl/-server) [заглушка | нет]).

**Элементов**

- Заглушка заглушки
- **None** — нет.

### <a name="client-stub-file"></a>Клиентский файл заглушки

Укажите файл заглушки клиента ([/cstub](/windows/win32/midl/-cstub) [файл]).

### <a name="server-stub-file"></a>Файл заглушки сервера

Укажите файл заглушки сервера ([/sstub](/windows/win32/midl/-sstub) [файл]).

### <a name="type-library-format"></a>Формат библиотеки типов

Указывает формат файла библиотеки типов ([/oldtlb |/newtlb]).

**Элементов**

- **Невформат** — новый формат
- **Олдформат** — старый формат

## <a name="advanced-property-page"></a>Страница свойств «Дополнительно»

### <a name="c-preprocess-options"></a>Параметры предварительной обработки C

Указывает параметры для передачи препроцессору компилятора C (параметры[/cpp_opt](/windows/win32/midl/-cpp_opt) ).

### <a name="undefine-preprocessor-definitions"></a>Отменить определения препроцессора

Задает одно или несколько неопределений, включая MIDL-макросы ([/u](/windows/win32/midl/-U) [Macros]).

### <a name="enable-error-checking"></a>Включить проверку ошибок

Выберите параметр проверки ошибок ([/Error все | нет]).

**Элементов**

- **Енаблекустом** — все
- **Все** -все
- **None** — нет.

### <a name="check-allocations"></a>Проверка выделений

Проверьте наличие ошибок нехватки памяти ([/Error](/windows/win32/midl/-error) выделение).

### <a name="check-bounds"></a>Проверить границы

Проверьте определение размера и длины передачи ([/Error](/windows/win32/midl/-error) bounds_check).

### <a name="check-enum-range"></a>Проверить диапазон перечисления

Проверьте значения перечисления, которые должны находиться в допустимом диапазоне (перечисление[/Error](/windows/win32/midl/-error) ).

### <a name="check-reference-pointers"></a>Проверить указатели ссылок

Проверьте ссылочные указатели на значения, отличные от NULL ([/Error](/windows/win32/midl/-error) ref).

### <a name="check-stub-data"></a>Проверка данных заглушки

Выдавать дополнительную проверку на допустимость данных заглушки на стороне сервера ([/Error](/windows/win32/midl/-error) stub_data).

### <a name="prepend-with-abi-namespace"></a>Начало с пространством имен "ABI"

Добавьте в начало пространства имен ABI все типы.  ([/ns_prefix](/windows/win32/midl/-ns_prefix)).

### <a name="validate-parameters"></a>Проверка параметров

Создайте дополнительные сведения для проверки параметров ([/robust](/windows/win32/midl/-robust) | [/robust](/windows/win32/midl/-no_robust)).

### <a name="struct-member-alignment"></a>Выравнивание членов структуры

Задает уровень упаковки для структур в целевой системе ([/ZpN](/windows/win32/midl/-zpn)).

**Элементов**

- **Не задано** — не задано
- **1 байт** — Zp1
- **2 байта** — Zp2
- **4 байта** — Zp4
- **8 байт** — Zp8

### <a name="redirect-output"></a>Перенаправление вывода

Перенаправляет выходные данные с экрана в файл ([/o](/windows/win32/midl/-o) -файл).

### <a name="minimum-target-system"></a>Минимальная целевая система

Задайте минимальную целевую систему (строку[/Target](/windows/win32/midl/-target) ).



