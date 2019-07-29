---
title: Страницы свойств средства манифестов
ms.date: 7/24/2019
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
ms.openlocfilehash: adc821370201eeb83b6c6b4b875e5e62b0fa523f
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606442"
---
# <a name="manifest-tool-property-pages"></a>Страницы свойств средства манифестов

Используйте эти страницы, чтобы указать общие параметры для [MT. exe](https://msdn.microsoft.com/library/aa375649). Эти страницы находятся в разделе**Свойства** >  **проекта** > **Свойства** > конфигурации**манифеста**.

## <a name="general-property-page"></a>Страница свойств "Общие"

### <a name="suppress-startup-banner"></a>Отключить загрузочный баннер

   **Да (/nologo)** указывает, что стандартные сведения об авторских правах Майкрософт будут скрыты при запуске инструмента манифеста. Используйте этот параметр, чтобы скрыть нежелательный вывод в файлах журнала, при выполнении mt.exe в рамках процесса сборки или из среды сборки.

### <a name="verbose-output"></a>Подробный вывод

   **Да (/verbose)** указывает, что при создании манифеста будут отображаться дополнительные сведения о сборке.

### <a name="assembly-identity"></a>Удостоверение сборки * *

Использует параметр /identity для указания строки удостоверения, которая состоит из атрибутов для [элемента \<assemblyIdentity>](/visualstudio/deployment/assemblyidentity-element-clickonce-application). Строка удостоверения начинается со значения для атрибута `name`, за которым следуют пары *атрибут* = *значение*. Атрибуты в строке удостоверения разделяются запятыми.

Вот пример строки идентификатора:`Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`

## <a name="input-and-output-property-page"></a>Страница свойств «входные и выходные данные»     

###  <a name="additional-manifest-files"></a>Дополнительные файлы манифеста

Использует параметр **/manifest**, чтобы указать полные пути к дополнительным файлам манифеста, обрабатываемым или объединяемым инструментом манифеста. Полные пути разделяются точкой с запятой. (-manifest [manifest1] [manifest2]...)

###  <a name="input-resource-manifests"></a>Манифесты входных ресурсов

Использует параметр **/inputresource**, чтобы указать полный путь ресурса типа RT_MANIFEST для ввода в инструмент манифеста. После этого пути может стоять заданный идентификатор ресурса. Например:

`dll_with_manifest.dll;#1`

###  <a name="embed-manifest"></a>Внедрить манифест

- Значение **Да** указывает, что система проектов встроит файл манифеста приложения в сборку.

- Значение **Нет** указывает, что система проектов создаст автономный файл манифеста приложения.

###  <a name="output-manifest-file"></a>Выходной файл манифеста

Задает имя выходного файла манифеста. Это свойство является необязательным, если инструмент манифеста обрабатывает всего один файл манифеста. (-out: [файл]; # [идентификатор ресурса])

###  <a name="manifest-resource-file"></a>Файл ресурсов манифеста

Определяет выходной файл ресурсов для внедрения манифеста в выходные данные проекта.

###  <a name="generate-catalog-files"></a>Создание файлов каталога

Использует параметр **/makecdfs**, чтобы указать, что инструмент манифеста создаст файлы определений каталогов (CDF-файлы), используемые для создания каталогов. /makecdfs

###  <a name="generate-manifest-from-managedassembly"></a>Создать манифест из ManagedAssembly

Создает манифест из управляемой сборки. (-манажедассемблинаме: [файл])

###  <a name="suppress-dependency-element"></a>Подавлять элемент зависимости

Используется с параметром-managedassembly. подавляет создание элементов зависимостей в окончательном манифесте. (-независимый)

###  <a name="generate-category-tags"></a>Создать теги категорий

Используется с параметром-managedassembly. -Category приводит к формированию тегов категорий. (-Category)

###  <a name="dpi-awareness"></a>Поддержка DPI

Указывает, поддерживает ли приложение DPI. По умолчанию этот параметр имеет значение **Да** для проектов MFC и значение **Нет** в противном случае, так как только проекты MFC имеют встроенную поддержку DPI. Вы можете переопределить параметр на значение **Да**, если добавите код для обработки различных параметров DPI. Если включить поддержку DPI при отсутствии таковой, приложение может выглядеть запутанным или мелким.

**Элементов**

- **None**
- **С поддержкой высокого DPI**
- **С поддержкой высокого DPI на монитор**

## <a name="isolated-com-property-page"></a>Изолированная страница свойств COM

Дополнительные сведения об изолированном com см. в разделе [изолированные приложения](/windows/desktop/SbsCs/isolated-applications) и [инструкции. Создание изолированных приложений для использования COM](../how-to-build-isolated-applications-to-consume-com-components.md)-компонентов.

###  <a name="type-library-file"></a>Файл библиотеки типов

Указывает библиотеку типов, используемую для поддержки манифеста RegFree COM. (-TLB: [файл])

###  <a name="registrar-script-file"></a>Файл скрипта регистратора

Указывает файл скрипта регистратора, используемый для поддержки манифеста RegFree COM. (-RGS: [файл])

###  <a name="component-file-name"></a>Имя файла компонента

Указывает имя файла компонента, созданного из указанного TLB-файла или RGS. (-DLL: [файл])

###  <a name="replacements-file"></a>Файл замены

Указывает файл, содержащий значения для заменяемых строк в RGS файле. (замены: [файл])

## <a name="advanced-property-page"></a>Страница свойств «Дополнительно»

###  <a name="update-file-hashes"></a>Обновить хэши файлов

Выполняет вычисление хэша файлов, указанных в элементах File, и обновляет атрибут Hash с помощью этого значения. (хашупдате: [путь])

###  <a name="update-file-hashes-search-path"></a>Путь поиска хэшей файлов обновления

Указывает путь поиска, используемый при обновлении хэшей файлов.

###  <a name="additional-options"></a>Дополнительные параметры

Дополнительные параметры


## <a name="see-also"></a>См. также

[C++Справочник по страницам свойств проекта](property-pages-visual-cpp.md)
