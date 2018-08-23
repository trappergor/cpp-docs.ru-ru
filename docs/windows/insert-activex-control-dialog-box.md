---
title: Вставить элемент управления ActiveX диалоговое окно | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.insertActiveXControls
dev_langs:
- C++
helpviewer_keywords:
- Insert ActiveX Control dialog box
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: 06638ea3-0726-40da-a989-9b89292d0e3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6e9f14b696ff67b52c365617682c0cc4c43432cd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602820"
---
# <a name="insert-activex-control-dialog-box"></a>Диалоговое окно "Вставка элемента управления ActiveX"

Это диалоговое окно позволяет [вставлять элементы управления ActiveX в диалоговое окно](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md) при использовании [редактор диалоговых окон](../windows/dialog-editor.md).

### <a name="activex-control"></a>Элемент управления ActiveX

Отображает список элементов управления Active X. Вставка элемента управления в этом диалоговом окне не создает класс-оболочку. Если вам требуется класс-оболочку, используйте [представление классов](http://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925) ее создать (Дополнительные сведения см. в разделе [Добавление класса](../ide/adding-a-class-visual-cpp.md)). Если элемент управления Active X в этом диалоговом окне не отображается, попробуйте установить элемент управления в соответствии с инструкциями производителя.

### <a name="path"></a>Путь

Открывает файл, в котором находится элемент управления ActiveX.

Можно поместить элементы управления в **элементов** окно для упрощения доступа. Дополнительные сведения см. в разделе [диалоговое окно «Настройка области элементов»](http://msdn.microsoft.com/bd07835f-18a8-433e-bccc-7141f65263bb).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Панель элементов, вкладка "Редактор диалоговых окон"](../windows/dialog-editor-tab-toolbox.md)  
[Файлы ресурсов](../windows/resource-files-visual-studio.md)  
[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)