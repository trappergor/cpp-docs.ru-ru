---
title: Инструмент манифеста, свойства конфигурации (комментариев документации C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCManifestTool.MergeRulesFile
- VC.Project.VCManifestTool.UseUnicodeResponseFiles
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.UseFAT32Workaround
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
ms.openlocfilehash: 9acdb7f5c934a8cabdd1803074778ac9f01f4960
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271034"
---
# <a name="general-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Диалоговое окно страниц свойств &lt;Имя_проекта&gt; "Свойства конфигурации", "Инструмент манифеста", "Общие"

Используйте это диалоговое окно для указания общих параметров для [Mt.exe](https://msdn.microsoft.com/library/aa375649).

Чтобы открыть это диалоговое окно страницы свойств, откройте страницы свойств для своего проекта или свою страницу свойств. Разверните узел**Инструмент манифеста** в области **Свойства конфигурации**, а затем выберите элемент **Общие**.

## <a name="uielement-list"></a>Список элементов пользовательского интерфейса

- **Отключить загрузочное объявление**

   **Да (/nologo)** указывает, что стандартные сведения об авторских правах Майкрософт будут скрыты при запуске инструмента манифеста. Используйте этот параметр, чтобы скрыть нежелательный вывод в файлах журнала, при выполнении mt.exe в рамках процесса сборки или из среды сборки.

- **Подробный вывод**

   **Да (/verbose)** указывает, что при создании манифеста будут отображаться дополнительные сведения о сборке.

- **Удостоверение сборки**

   Использует параметр /identity для указания строки удостоверения, которая состоит из атрибутов для [элемента \<assemblyIdentity>](/visualstudio/deployment/assemblyidentity-element-clickonce-application). Строка удостоверения начинается со значения для атрибута `name`, за которым следуют пары *атрибут* = *значение*. Атрибуты в строке удостоверения разделяются запятыми.

   Пример строки удостоверения:

   `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`

## <a name="see-also"></a>См. также

[ClickOnce Application Manifest](/visualstudio/deployment/clickonce-application-manifest)<br>
[Страницы свойств инструмента манифеста](manifest-tool-property-pages.md)<br>
[Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md)
