---
title: Вставить элемент управления ActiveX диалоговое окно (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.insertActiveXControls
helpviewer_keywords:
- Insert ActiveX Control dialog box [C++]
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: 06638ea3-0726-40da-a989-9b89292d0e3d
ms.openlocfilehash: 495245141b62850067196c81bfe4c6f984dcfa88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592755"
---
# <a name="insert-activex-control-dialog-box-c"></a>Вставить элемент управления ActiveX диалоговое окно (C++)

Это диалоговое окно позволяет [вставлять элементы управления ActiveX в диалоговое окно](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md) при использовании [редактор диалоговых окон](../windows/dialog-editor.md).

### <a name="activex-control"></a>Элемент управления ActiveX

Отображает список элементов управления Active X. Вставка элемента управления в этом диалоговом окне не создает класс-оболочку. Если вам требуется класс-оболочку, используйте [представление классов](/visualstudio/ide/viewing-the-structure-of-code) ее создать (Дополнительные сведения см. в разделе [Добавление класса](../ide/adding-a-class-visual-cpp.md)). Если элемент управления Active X в этом диалоговом окне не отображается, попробуйте установить элемент управления в соответствии с инструкциями производителя.

### <a name="path"></a>Путь

Открывает файл, в котором находится элемент управления ActiveX.

Можно поместить элементы управления в **элементов** окно для упрощения доступа. См. дополнительные сведения о [панели элементов](/visualstudio/ide/reference/).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Панель элементов, вкладка "Редактор диалоговых окон"](../windows/dialog-editor-tab-toolbox.md)<br/>
[Файлы ресурсов](../windows/resource-files-visual-studio.md)<br/>
[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)