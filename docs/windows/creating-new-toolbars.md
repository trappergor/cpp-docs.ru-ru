---
title: Создание новых панелей инструментов (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.toolbar
helpviewer_keywords:
- toolbars [C++], creating
- Toolbar editor [C++], creating new toolbars
- Insert Resource
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
ms.openlocfilehash: 3c36579560c78ff77a624e4827df9d6a9302ae57
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551311"
---
# <a name="creating-new-toolbars-c"></a>Создание новых панелей инструментов (C++)

### <a name="to-create-a-new-toolbar"></a>Чтобы создать новую панель инструментов

1. В **ресурсов** просмотра, щелкните правой кнопкой мыши RC-файл, а затем выберите **добавить ресурс** в контекстном меню. (При наличии существующую панель инструментов в RC-файл, вы можете просто щелкните правой кнопкой мыши **инструментов** папку и выберите **вставить панель инструментов** в контекстном меню.)

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. В **добавить ресурс** выберите **инструментов** в **тип ресурса** , а затем нажмите кнопку **New**.

   Если знак плюс (**+**) отображается рядом **инструментов** тип ресурса, это означает, что доступны шаблоны. Щелкните знак «плюс», чтобы развернуть список шаблонов, выберите шаблон и нажмите кнопку **New**.

   \- или -

3. [Преобразование существующего растрового изображения на панель инструментов](../windows/converting-bitmaps-to-toolbars.md).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

MFC или ATL

## <a name="see-also"></a>См. также

[Редактор панелей инструментов](../windows/toolbar-editor.md)