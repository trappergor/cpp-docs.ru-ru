---
title: Группы с вкладками MDI | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- mdi [MFC], tabbed groups
- tabbed grous [MFC]
ms.assetid: 0a464f36-39b7-4e68-8b67-ec175de28377
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a7cf6420a331d46f2a158c16a30d439f334a46b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350358"
---
# <a name="mdi-tabbed-groups"></a>Группы с вкладками MDI
Компонент несколько групп с вкладками интерфейса (MDI) документа позволяет нескольким приложениям интерфейса (MDI) документа для отображения одного или нескольких окон с вкладками (или групп с вкладками Windows, известные как *группы с вкладками*) в клиентской области MDI. Окна с вкладками можно выравнивать по вертикали или по горизонтали. Если приложение размещено несколько групп с вкладками MDI, групп разделенных разделителями.  
  
## <a name="features"></a>Возможности  
 Ниже перечислены возможности групп с вкладками MDI.  
  
-   Приложение может динамически создать окон с вкладками.  
  
-   Приложение можно выровнять окон с вкладками, горизонтально или вертикально.  
  
-   Группы с вкладками windows разделенных разделителями. Пользователь может изменить размер групп с вкладками с помощью разделителя.  
  
-   Пользователь может перетаскивать отдельные вкладки между группами.  
  
-   Пользователь может перетаскивать отдельные вкладки, чтобы создавать новые группы.  
  
-   Пользователь может переместить вкладки или создавать новые группы с помощью контекстного меню.  
  
-   Приложения можно сохранить и загрузить макет окон с вкладками.  
  
-   Приложение может сохранять и загружать список документов MDI.  
  
-   Приложение может получить доступ к отдельным групп с вкладками и изменять свои параметры.  
  
### <a name="using-mdi-tabbed-groups"></a>Группы с помощью интерфейса MDI с вкладками  
 Ниже приведены задачи, обычно выполняемые с группами с вкладками MDI.  
  
-   Чтобы включить группы с вкладками MDI для фрейма главного окна, вызовите [CMDIFrameWndEx::EnableMDITabbedGroups](../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups). Второй параметр этого метода является экземпляром типа `CMDITabInfo` класса. Можно использовать параметры по умолчанию или измените их, перед вызовом метода `CMDIFrameWndEx::EnableMDITabbedGroups`.  
  
-   Чтобы изменить свойства группы с вкладками MDI во время выполнения, создание или изменение `CMDITabInfo` и вызовите `CMDIFrameWndEx::EnableMDITabbedGroups` еще раз  
  
-   Для получения списка MDI с вкладками windows, вызовите метод `CMDIFrameWndEx::GetMDITabGroups`.  
  
-   Чтобы создать новую группу с вкладками MDI рядом с группе active с вкладками, вызовите `CMDIFrameWndEx::MDITabNewGroup`.  
  
-   Чтобы переместить фокус ввода в окно предыдущего или следующего группы с вкладками, вызовите `CMDIFrameWndEx::MDITabMoveToNextGroup`.  
  
-   Чтобы определить, входит ли окно MDI с вкладками группы вызов `CMDIFrameWndEx::IsMemberOfMDITabGroup`.  
  
-   Чтобы определить, включена ли для окна главного фрейма MDI вкладки или групп с вкладками MDI, вызовите `CMDIFrameWndEx::AreMDITabs`. Чтобы определить, включены ли группы с вкладками MDI, вызовите `CMDIFrameWndEx::IsMDITabbedGroup`.  
  
-   Чтобы отобразить контекстное меню, когда пользователь щелкает вкладку или перетаскивает его в другую группу с вкладками MDI, переопределите `CMDIFrameWndEx::OnShowMDITabContextMenu` в `CMDIFrameWndEx`-производного класса. Если не реализовать этот метод, приложение будет отображаться в контекстном меню.  
  
-   Чтобы сохранить макет групп с вкладками MDI в приложении, вызовите `CMDIFrameWndEx::SaveMDIState`. Для загрузки сохраненного MDI с вкладками группы профиля, вызовите метод `CMDIFrameWndEx::LoadMDIState`. Кроме того, может вызывать эти методы для загрузки и сохранения списка открытых документов в приложении MDI. Дополнительные сведения о сохранении и загрузке состояния MDI см. в разделе [CMDIFrameWndEx::LoadMDIState](../mfc/reference/cmdiframewndex-class.md#loadmdistate).  
  
## <a name="see-also"></a>См. также  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)   
 [Класс CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md)   
 [Класс CMDIChildWndEx](../mfc/reference/cmdichildwndex-class.md)   
 [Класс CMDITabInfo](../mfc/reference/cmditabinfo-class.md)
