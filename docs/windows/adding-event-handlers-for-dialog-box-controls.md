---
title: "Добавление обработчиков событий для элементов управления диалоговых | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Dialog editor, adding event handlers to controls
- controls [C++], event handlers
- dialog box controls, events
- event handlers, for dialog box controls
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: afe50d56d6b96cc4bc0b871f72c27feb0a750e89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="adding-event-handlers-for-dialog-box-controls"></a>Добавление обработчиков событий для элементов управления диалоговых окон
Для проекта диалоговых окон, которые уже связаны с классом можно воспользоваться преимуществами некоторые сочетания клавиш, при создании обработчиков событий. Можно быстро создать обработчик для события уведомления элемента управления по умолчанию или для любого соответствующего сообщения Windows.  
  
#### <a name="to-create-a-handler-for-the-default-control-notification-event"></a>Чтобы создать обработчик для события уведомления элемента управления по умолчанию  
  
1.  Дважды щелкните элемент управления. Откроется редактор текста.  
  
2.  Добавьте код обработчика уведомлений в текстовом редакторе.  
  
#### <a name="to-create-a-handler-for-any-applicable-windows-message"></a>Создание обработчика для любого соответствующего сообщения Windows  
  
1.  Щелкните элемент управления, для которого необходимо обработать событие уведомления.  
  
2.  В [окно свойств](/visualstudio/ide/reference/properties-window), нажмите кнопку **события элемента управления** кнопку, чтобы отобразить список стандартных событий Windows, связанные с элементом управления. Например, стандартная **ОК** кнопку **о** диалоговом окне перечислены следующие события уведомления:  
  
 **BN_CLICKED**  
  
 **BN_DOUBLECLICKED**  
  
 **BN_KILLFOCUS**  
  
 **BN_SETFOCUS**  
  
    > [!NOTE]
    >  Кроме того, диалоговое окно выбора и нажмите кнопку **события элемента управления** кнопку, чтобы отобразить список стандартных событий Windows для всех элементов управления в диалоговом окне.  
  
3.  В **свойства** окно, щелкните столбец справа от события для обработки и выберите имя события предлагаемые уведомления (например, **OnBnClickedOK** дескрипторы **BN_CLICKED** ).  
  
    > [!NOTE]
    >  Кроме того можно предоставить имя обработчика события вашему выбору, чем при выборе имени обработчика событий по умолчанию.  
  
     После выбора события Visual Studio открывает текстовый редактор и отображает код в обработчик событий. Например, следующий код добавляется по умолчанию **OnBnClickedOK**:  
  
 ```  
    void CAboutDlg::OnBnClickedOk(void)  
 { *// TODO: Add your control notification handler code here  
 }  
 ```  
  
 Если вы хотите добавить обработчик событий к классу отличный от того, реализует диалоговое окно, используйте [мастер обработчиков событий](../ide/event-handler-wizard.md). Дополнительные сведения см. в разделе [Добавление обработчика событий](../ide/adding-an-event-handler-visual-cpp.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [События элементов управления по умолчанию](../windows/default-control-events.md)   
 [Определение переменных-членов для элементов управления диалоговых окон](../windows/defining-member-variables-for-dialog-controls.md)   
 [Элементы управления диалоговых окон и типы переменных](../ide/dialog-box-controls-and-variable-types.md)   
 [Добавление класса](../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Обработчик сообщений MFC](../mfc/reference/adding-an-mfc-message-handler.md)

