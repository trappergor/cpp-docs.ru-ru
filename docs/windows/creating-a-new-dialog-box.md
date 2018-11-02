---
title: Создание нового диалогового окна (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog
helpviewer_keywords:
- dialog boxes [C++], creating
- Dialog Editor [C++], creating dialog boxes
ms.assetid: 303de801-c4f8-42e1-b622-353f6423f688
ms.openlocfilehash: ed1bb21029b2a61eb51b54386ed51ef08b90e149
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605349"
---
# <a name="creating-a-new-dialog-box-c"></a>Создание нового диалогового окна (C++)

### <a name="to-create-a-new-dialog-box"></a>Чтобы создать новое диалоговое окно

1. В [представление ресурсов](../windows/resource-view-window.md), щелкните правой кнопкой мыши RC-файл, а затем выберите **добавить ресурс** в контекстном меню.

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. В **добавить ресурс** выберите **диалоговое окно** в **тип ресурса** , а затем нажмите кнопку **New**.

   Если знак плюс (**+**) отображается рядом **диалоговое окно** тип ресурса, это означает, что шаблонов диалогового доступны. Щелкните знак «плюс», чтобы развернуть список шаблонов, выберите шаблон и нажмите кнопку **New**.

   Откроется новое диалоговое окно в **диалоговое окно** редактора.

   Вы также можете [открыть существующие диалоговые окна в редакторе диалоговое окно для редактирования](../windows/viewing-and-editing-resources-in-a-resource-editor.md).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Практическое руководство. Создание ресурса](../windows/how-to-create-a-resource.md)<br/>
[Файлы ресурсов](../windows/resource-files-visual-studio.md)<br/>
[Редактор диалоговых окон](../windows/dialog-editor.md)