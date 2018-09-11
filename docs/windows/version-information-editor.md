---
title: Редактор сведений о версии (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version.F1
dev_langs:
- C++
helpviewer_keywords:
- Version Information editor [C++], about Version Information editor
- editors, Version Information
- resource editors [C++], Version Information editor
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1d8a4eb57996bcc2afd9ddc92a9eecf354f88116
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313707"
---
# <a name="version-information-editor-c"></a>Редактор сведений о версии (C++)

Сведения о версии включают идентификационные данные о компании и продукте, номер версии продукта и уведомление об авторских правах и товарных знаках. С помощью **сведения о версии** редакторе, создавать и поддерживать эти данные, которые хранятся в ресурсе сведений о версии. Ресурс сведений о версии не является обязательным для приложения, но он удобен для сбора сведений, позволяющих идентифицировать приложение. Сведения о версии также используются API-интерфейсами настройки.

Ресурс сведений о версии содержит верхний блок и один или несколько нижних блоков: один блок фиксированных сведений вверху и один или несколько блоков сведений о версии внизу (для других языков или кодировок). Верхний блок содержит как редактируемые числовые поля, так и раскрывающиеся списки с вариантами для выбора. Нижние блоки содержат только редактируемые текстовые поля.

> [!NOTE]
> Стандарт Windows разрешает наличие только одного ресурса сведений о версии, который называется VS_VERSION_INFO.

**Сведения о версии** редактор позволяет:

- [изменять строку в ресурсе сведений о версии;](../windows/editing-a-string-in-a-version-information-resource.md)

- [добавлять сведения о версии для другого языка (новый блок сведений о версии);](../windows/adding-version-information-for-another-language.md)

- [удалять блок сведений о версии;](../windows/deleting-a-version-information-block.md)

- [получать доступ к сведениям о версии из создаваемой программы.](../windows/accessing-version-information-from-within-your-program.md)

   > [!NOTE]
   > При использовании **сведения о версии** редактора во многих случаях, щелкнуть правой кнопкой мыши для отображения контекстное меню связанных с ресурсом команд. Например, при нажатии кнопки мыши на заголовке блока, контекстное меню показано **новый блок сведений о версии** и **удалить блок сведений о версии** команды.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редакторы ресурсов](../windows/resource-editors.md)  
[Меню и другие ресурсы](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)