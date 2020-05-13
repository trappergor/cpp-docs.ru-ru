---
title: Страницы свойств средства манифестов
ms.date: 07/24/2019
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.ResourceOutputFileName
- VC.Project.VCManifestTool.GenerateCatalogFiles
- VC.Project.VCManifestTool.ManifestFromManagedAssembly
- VC.Project.VCManifestTool.SuppressDependencyElement
- VC.Project.VCManifestTool.GenerateCategoryTags
- VC.Project.VCManifestTool.EnableDPIAwareness
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.ReplacementsFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- vc.project.AdditionalOptionsPage
ms.assetid: f33499c4-7733-42d9-80e3-8a5018786965
ms.openlocfilehash: e1d0f1ac889cb915216ceb70d48e36efe4ad21bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336298"
---
# <a name="manifest-tool-property-pages"></a>Страницы свойств средства манифестов

Используйте эти страницы, чтобы указать общие варианты [mt.exe](/windows/win32/sbscs/mt-exe). Эти страницы находятся в **project** > **Properties** > **Configuration Properties** > **Manifest Tool.**

## <a name="general-property-page"></a>Страница общего имущества

### <a name="suppress-startup-banner"></a>Отключить загрузочный баннер

   **Да (/nologo)** указывает, что стандартные сведения об авторских правах Майкрософт будут скрыты при запуске инструмента манифеста. Используйте этот параметр, чтобы скрыть нежелательный вывод в файлах журнала, при выполнении mt.exe в рамках процесса сборки или из среды сборки.

### <a name="verbose-output"></a>Результат ы verbose

   **Да (/verbose)** указывает, что при создании манифеста будут отображаться дополнительные сведения о сборке.

### <a name="assembly-identity"></a>Удостоверение сборки

Использует опцию /идентификация для указания строки идентификации, которая включает атрибуты для [ \<сборкиIdentity> элемент.](/visualstudio/deployment/assemblyidentity-element-clickonce-application) Строка идентификации начинается `name` со значения для атрибута и сопровождается парами*значений* *атрибута.* =  Атрибуты в строке удостоверения разделяются запятыми.

Это пример строки идентификации:`Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`

## <a name="input-and-output-property-page"></a>Страница ввода и свойства вывода

### <a name="additional-manifest-files"></a>Дополнительные файлы манифеста

Использует параметр **/manifest**, чтобы указать полные пути к дополнительным файлам манифеста, обрабатываемым или объединяемым инструментом манифеста. Полные пути разделяются точкой с запятой. (-манифест «манифест1» (манифест2)...)

### <a name="input-resource-manifests"></a>Манифесты входных ресурсов

Использует параметр **/inputresource**, чтобы указать полный путь ресурса типа RT_MANIFEST для ввода в инструмент манифеста. После этого пути может стоять заданный идентификатор ресурса. Пример:

`dll_with_manifest.dll;#1`

### <a name="embed-manifest"></a>Внедренный манифест

- Значение **Да** указывает, что система проектов встроит файл манифеста приложения в сборку.

- Значение **Нет** указывает, что система проектов создаст автономный файл манифеста приложения.

### <a name="output-manifest-file"></a>Выходной файл манифеста

Задает имя выходного файла манифеста. Это свойство является необязательным, если инструмент манифеста обрабатывает всего один файл манифеста. (-аут: «файл»; «Идентификатор ресурсов»)

### <a name="manifest-resource-file"></a>Ресурсный файл манифеста

Определяет выходной файл ресурсов для внедрения манифеста в выходные данные проекта.

### <a name="generate-catalog-files"></a>Создавать файлы каталогов

Использует параметр **/makecdfs**, чтобы указать, что инструмент манифеста создаст файлы определений каталогов (CDF-файлы), используемые для создания каталогов. (/макекдфы)

### <a name="generate-manifest-from-managedassembly"></a>Создать манифест из ManagedAssembly

Создает манифест из управляемой сборки. (-управляемыйсборочный имя:\[файл)

### <a name="suppress-dependency-element"></a>Отменить элемент зависимости

Используется с -управляемойсборкой. подавляет генерацию элементов зависимости в окончательном манифесте. (-ноденденденция)

### <a name="generate-category-tags"></a>Создать теги категорий

Используется с -управляемойсборкой. -категория вызывает сгенерированные теги категории. (-категория)

### <a name="dpi-awareness"></a>Осведомленность ДОИ

Указывает, поддерживает ли приложение DPI. По умолчанию этот параметр имеет значение **Да** для проектов MFC и значение **Нет** в противном случае, так как только проекты MFC имеют встроенную поддержку DPI. Вы можете переопределить параметр на значение **Да**, если добавите код для обработки различных параметров DPI. Если включить поддержку DPI при отсутствии таковой, приложение может выглядеть запутанным или мелким.

**Choices**

- **Нет**
- **Высокий DPI осведомлены**
- **За монитор Высокий DPI осведомлены**

## <a name="isolated-com-property-page"></a>Изолированная страница недвижимости COM

Для получения дополнительной информации об изолированных [How to: Build Isolated Applications to Consume COM Components](../how-to-build-isolated-applications-to-consume-com-components.md)COM [см.](/windows/win32/SbsCs/isolated-applications)

### <a name="type-library-file"></a>Файл библиотеки типов

Определяет библиотеку типа для использования для поддержки regfree COM. (-tlb: «файл»)

### <a name="registrar-script-file"></a>Файл скрипта регистратора

Определяет файл скрипта регистратора для использования для поддержки regfree COM. (-ргс: «файл»)

### <a name="component-file-name"></a>Имя файла компонента

Указать имя файла компонента, который построен из .tlb или .rgs указаны. (-dll: (файл)

### <a name="replacements-file"></a>Файл замен

Определяет файл, содержащий значения для сменных строк в файле RGS. (Замены: «файл»)

## <a name="advanced-property-page"></a>Расширенная страница свойств

### <a name="update-file-hashes"></a>Обновлять хэши файлов

Вычисляет хэш файлов, указанных в элементах файла, и обновляет атрибут хэша с помощью этого значения. (хэш-обновление: «путь»)

### <a name="update-file-hashes-search-path"></a>Путь поиска для обновления хэшей файлов

Определяет путь поиска для использования при обновлении хэшов файлов.

### <a name="additional-options"></a>Дополнительные параметры

Дополнительные параметры

## <a name="see-also"></a>См. также раздел

[Ссылка на свойство проекта «СИ»](property-pages-visual-cpp.md)
