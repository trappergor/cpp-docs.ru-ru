---
title: Диалоговое окно страниц свойств &lt;Имя_проекта&gt; "Свойства конфигурации", "Инструмент манифеста", "Дополнительно" | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
dev_langs:
- C++
ms.assetid: 3d587366-05ea-4956-a978-313069660735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e44ba6065658c085777ada39f75bd5fa1cdc2fb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382951"
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
[Манифест приложения ClickOnce](/visualstudio/deployment/clickonce-application-manifest)<br>
[Страницы свойств инструмента манифеста](../ide/manifest-tool-property-pages.md)<br>
[Работа со свойствами проектов](../ide/working-with-project-properties.md)