---
title: Просмотр и добавление элементов управления ActiveX в диалоговое окно | Документация Майкрософт
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
- Insert ActiveX Control command
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ad663760efb5f969a7b7cf1b14d187b0382197b7
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643982"
---
# <a name="viewing-and-adding-activex-controls-to-a-dialog-box"></a>Просмотр элементов управления ActiveX и добавление их в диалоговое окно
Среда разработки Visual Studio позволяет вставлять элементы ActiveX в диалоговое окно.  
  
### <a name="to-see-the-activex-controls-you-have-available"></a>Просмотр доступных элементов ActiveX  
  
1.  Откройте диалоговое окно в редакторе диалоговых окон.  
  
2.  Щелкните правой кнопкой мыши в области диалогового окна.  
  
3.  В контекстном меню выберите команду **Вставить элемент ActiveX**.  
  
     Появится диалоговое окно [Вставка элемента ActiveX](../windows/insert-activex-control-dialog-box.md) , в котором будут представлены все элементы ActiveX, доступные в системе. В нижней части диалогового окна отображается путь к файлу элемента ActiveX.  
  
### <a name="to-add-an-activex-control-to-a-dialog-box"></a>Добавление элемента ActiveX в диалоговое окно  
  
1.  В диалоговом окне [Вставка элемента ActiveX](../windows/insert-activex-control-dialog-box.md)выберите элемент, который необходимо добавить в диалоговое окно, и нажмите кнопку **ОК**.  
  
     Элемент появится в диалоговом окне, после чего его можно будет изменить или создать для него обработчики, как для любого другого элемента управления.  
  
    > [!NOTE]
    >  Элементы ActiveX можно добавить в [окно панели элементов](/visualstudio/ide/reference/toolbox). Дополнительные сведения см. в разделе [управление элементами и вкладками на панели элементов](http://msdn.microsoft.com/21285050-cadd-455a-b1f5-a2289a89c4db).  
  
    > [!CAUTION]
    >  Распространение всех элементов ActiveX в системе может быть незаконным. Эти вопросы освещены в лицензионном соглашении к программному обеспечению, которое обеспечивает установку элементов управления. Также можно обратиться к поставщику данного ПО.  
  
     Для упрощения доступа элементы управления можно поместить в окно панели элементов. Дополнительные сведения см. в разделе [диалоговое окно «Настройка области элементов»](http://msdn.microsoft.com/bd07835f-18a8-433e-bccc-7141f65263bb).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)   
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)   
 [Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)