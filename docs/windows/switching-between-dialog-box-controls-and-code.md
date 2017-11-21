---
title: "Переключение между элементы управления диалоговых окон и кода | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog editor, accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog editor, switching between controls and code
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 831b8ca3eddec1bfd13d166d98454206bfac1bfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="switching-between-dialog-box-controls-and-code"></a>Переключение между элементами управления диалогового окна и кодом
В приложениях MFC вы можете дважды щелкнуть элементы управления диалоговых окон для перехода к их коду обработчика или быстро создать заглушку функции обработчика.  
  
 Элемент управления, щелкните **события элемента управления** кнопку или **сообщений** кнопку в [окно "Свойства"](/visualstudio/ide/reference/properties-window) Чтобы просмотреть полный список сообщений и событий Windows доступные для выбранного элемента. Выберите из списка, чтобы создать или изменить функции обработчика.  
  
### <a name="to-jump-to-code-from-the-dialog-editor"></a>Чтобы перейти к коду из редактора диалоговых окон  
  
1.  Дважды щелкните элемент управления в диалоговом окне, чтобы перейти к объявлению его последней реализации функции обработки сообщений. (Для классов диалоговых окон, основанных на ATL, вы всегда сразу перейти к определению конструктора.)  
  
### <a name="to-view-events-for-a-control"></a>Чтобы просмотреть события для элемента управления  
  
1.  Элемент управления, щелкните **события элемента управления** кнопку в [окно свойств](/visualstudio/ide/reference/properties-window).  
  
    > [!NOTE]
    >  Щелкнув **события элемента управления** кнопка, если *диалоговое окно* имеет фокус предоставляет список всех элементов управления в диалоговом окне, который можно развернуть, чтобы изменить события для отдельных элементов управления.  
  
     Когда один элемент управления имеет фокус в диалоговом окне, щелкните его правой кнопкой мыши и выбрать можно **добавить обработчик событий** в контекстном меню. Это позволяет задать класс, к которому добавляется обработчик. Дополнительные сведения см. в разделе [Добавление обработчика событий](../ide/adding-an-event-handler-visual-cpp.md).  
  
### <a name="to-view-messages-for-a-dialog-box"></a>Чтобы просмотреть сообщения для диалогового окна  
  
1.  Диалоговое окно, нажмите кнопку **сообщений** кнопку в [окно свойств](/visualstudio/ide/reference/properties-window).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](https://msdn.microsoft.com/library/f45fce5x.aspx) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](https://msdn.microsoft.com/library/xbx3z216.aspx). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактор диалоговых окон](../windows/dialog-editor.md)

