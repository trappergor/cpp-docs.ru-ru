---
title: Переключение между элементами управления диалогового окна и код | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog editor, accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog editor, switching between controls and code
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b288e97030cad7e38caf19fb47f7a058c3ead61d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643112"
---
# <a name="switching-between-dialog-box-controls-and-code"></a>Переключение между элементами управления диалогового окна и кодом
В приложениях MFC можно дважды щелкнуть поле элементов управления диалоговых окон для перехода к их код обработчика или быстро создать заглушку функции обработчика.  
  
 С выбранным элементом управления, нажмите кнопку **события элемента управления** кнопку или **сообщений** кнопку [окно "Свойства"](/visualstudio/ide/reference/properties-window) Чтобы просмотреть полный список сообщений Windows и событий доступные для выбранного элемента. Выберите из списка, чтобы создать или изменить функции обработчика.  
  
### <a name="to-jump-to-code-from-the-dialog-editor"></a>Чтобы перейти к коду из редактора диалоговых окон  
  
1.  Дважды щелкните элемент управления в диалоговое окно, чтобы перейти к объявлению для его последней реализации функции обработки сообщений. (Для классы диалоговых окон на основе ATL, вы всегда сразу перейти к определению конструктора.)  
  
### <a name="to-view-events-for-a-control"></a>Чтобы просмотреть события для элемента управления  
  
1.  С выбранным элементом управления, нажмите кнопку **события элемента управления** кнопку [окно "Свойства"](/visualstudio/ide/reference/properties-window).  
  
    > [!NOTE]
    >  Щелкнув **события элемента управления** кнопка, если *диалоговое окно* имеет фокус предоставляет список всех элементов управления в диалоговом окне, который можно развернуть, чтобы изменить события для отдельных элементов управления.  
  
     Когда один элемент управления имеет фокус в диалоговом окне, можно его правой кнопкой мыши и выбрать **добавить обработчик событий** в контекстном меню. Это позволяет указывать класс, к которому добавляется обработчик. Дополнительные сведения см. в разделе [Добавление обработчика событий](../ide/adding-an-event-handler-visual-cpp.md).  
  
### <a name="to-view-messages-for-a-dialog-box"></a>Чтобы просмотреть сообщения для диалогового окна  
  
1.  Диалоговое окно, нажмите кнопку **сообщений** кнопку [окно "Свойства"](/visualstudio/ide/reference/properties-window).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактор диалоговых окон](../windows/dialog-editor.md)