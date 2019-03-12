---
title: Диалоговое окно страниц свойств &lt;Имя_проекта&gt; "Свойства конфигурации", "Инструмент манифеста", "Дополнительно"
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
ms.assetid: 3d587366-05ea-4956-a978-313069660735
ms.openlocfilehash: 183b4613362acde9f48c98ee00a76b1fb8a2c4d3
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742275"
---
# <a name="advanced-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Диалоговое окно страниц свойств &lt;Имя_проекта&gt; "Свойства конфигурации", "Инструмент манифеста", "Дополнительно"

Используйте это диалоговое окно для указания дополнительных параметров для [Mt.exe](https://msdn.microsoft.com/library/aa375649).

Чтобы открыть это диалоговое окно страницы свойств, откройте страницы свойств для своего проекта или свою страницу свойств. Разверните узел**Инструмент манифеста** в области **Свойства конфигурации**, а затем выберите элемент **Дополнительно**.

## <a name="uielement-list"></a>Список элементов пользовательского интерфейса

- **Обновлять хэши файлов**

   Использует параметр /hashupdate, чтобы указать, что инструмент манифеста вычислит хэш файлов, указанных в элементах `<file>`, а затем обновить атрибуты хэша с использованием вычисленного значения.

- **Путь поиска для обновления хэшей файлов**

   Указывает путь поиска для файлов, на которые есть ссылки в элементах `<file>`. Этот параметр также использует параметр /hashupdate.

## <a name="see-also"></a>См. также

[Элемент \<file>](/visualstudio/deployment/file-element-clickonce-application)<br>
[ClickOnce Application Manifest](/visualstudio/deployment/clickonce-application-manifest)<br>
[Страницы свойств инструмента манифеста](../ide/manifest-tool-property-pages.md)<br>
[Работа со свойствами проектов](../ide/working-with-project-properties.md)
