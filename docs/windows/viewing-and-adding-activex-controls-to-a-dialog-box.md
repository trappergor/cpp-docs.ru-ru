---
title: Просмотр и добавление элементов управления ActiveX в диалоговое окно (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.controls.activex
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], adding ActiveX controls
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bc5360a90690b27f1c52f97cd8b3746ddee5d60a
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318386"
---
# <a name="viewing-and-adding-activex-controls-to-a-dialog-box-c"></a>Просмотр и добавление элементов управления ActiveX в диалоговое окно (C++)

Среда разработки Visual Studio позволяет вставлять элементы ActiveX в диалоговое окно.

### <a name="to-see-the-activex-controls-you-have-available"></a>Просмотр доступных элементов ActiveX

1. Откройте диалоговое окно в редакторе диалоговых окон.

2. Щелкните правой кнопкой мыши в области диалогового окна.

3. В контекстном меню выберите команду **Вставить элемент ActiveX**.

   Появится диалоговое окно [Вставка элемента ActiveX](../windows/insert-activex-control-dialog-box.md) , в котором будут представлены все элементы ActiveX, доступные в системе. В нижней части диалогового окна отображается путь к файлу элемента ActiveX.

### <a name="to-add-an-activex-control-to-a-dialog-box"></a>Добавление элемента ActiveX в диалоговое окно

1. В диалоговом окне [Вставка элемента ActiveX](../windows/insert-activex-control-dialog-box.md)выберите элемент, который необходимо добавить в диалоговое окно, и нажмите кнопку **ОК**.

   Элемент появится в диалоговом окне, после чего его можно будет изменить или создать для него обработчики, как для любого другого элемента управления.

   > [!NOTE]
   > Элементы ActiveX можно добавить в [окно панели элементов](/visualstudio/ide/reference/toolbox).

   > [!CAUTION]
   > Распространение всех элементов ActiveX в системе может быть незаконным. Эти вопросы освещены в лицензионном соглашении к программному обеспечению, которое обеспечивает установку элементов управления. Также можно обратиться к поставщику данного ПО.

   Можно поместить элементы управления в **элементов** окно для упрощения доступа. См. дополнительные сведения о [панели элементов](/visualstudio/ide/reference/toolbox).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)  
[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)  
[Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)