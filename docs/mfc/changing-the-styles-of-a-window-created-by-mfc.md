---
title: "Изменение стилей окна, созданного MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- window styles [MFC]
- WS_OVERLAPPEDWINDOW macro [MFC]
- single document interface (SDI), changing window attributes
- MDI [MFC], window styles
- windows [MFC], MFC
- child windows [MFC], styles
- MFC, windows
- CFrameWnd class [MFC], window styles
- CREATESTRUCT macro [MFC]
- CMDIChildWnd class [MFC], changing window styles
- multidocument interface style
- PreCreateWindow method [MFC], window styles
- single document interface (SDI), style
- default window style
- defaults [MFC], window style
- PreCreateWindow method [MFC], changing window styles
- CMainFrame class [MFC]
- styles [MFC], windows
ms.assetid: 77fa4f03-96b4-4687-9ade-41e46f7e4b0a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7745054066a928c414360a215605cf343971ddf4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>Изменение стилей окна, созданного MFC
В свою версию `WinMain` функции MFC регистрирует несколько классов стандартного окна. Поскольку MFC обычно не редактировать `WinMain`, что функция предоставляет возможности изменять стили окна MFC по умолчанию. В этой статье объясняется, как изменить стили такой класс предварительно зарегистрированный окна в существующем приложении.  
  
##  <a name="_core_changing_styles_in_a_new_mfc_application"></a>Изменение стиля в новое приложение MFC  
 Если вы используете Visual C++ 2.0 или более поздней версии, вы можете изменить стили окна по умолчанию в мастере приложений, при создании приложения. На странице функции пользовательского интерфейса в мастере приложений можно изменить стили для окна главного и дочерних MDI-окон. Для каждого типа окна, можно указать его толщину рамки (толстого или тонкого) и любые из следующих действий:  
  
-   Имеет ли окно свернуть или развернуть элементы управления.  
  
-   Ли окно отображается изначально свернутого развернуто, и ни одного.  
  
 Для фрейма главного окна можно также указать, имеет ли окно системного меню. Для дочерних MDI-окон можно указать, поддерживает ли окно области разделителей.  
  
##  <a name="_core_changing_styles_in_an_existing_application"></a>Изменение стиля в существующее приложение  
 При изменении окна атрибутов в существующем приложении, следуйте инструкциям в оставшейся части этой статьи.  
  
 Чтобы изменить атрибуты окна по умолчанию, используемый приложением framework, созданных с помощью мастера приложений, переопределить окна [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) виртуальная функция-член. `PreCreateWindow`позволяет приложению получить доступ к обычно управляется внутренне процесса создания [CDocTemplate](../mfc/reference/cdoctemplate-class.md) класса. Платформа вызывает `PreCreateWindow` только до создания окна. Изменив [CREATESTRUCT](../mfc/reference/createstruct-structure.md) структуры передается `PreCreateWindow`, приложение может изменить атрибуты, используемые для создания окна. Например чтобы убедиться, что окно не использует заголовок, используйте следующие побитовой операции:  
  
 [!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]  
  
 [CTRLBARS](../visual-cpp-samples.md) образце приложения показано изменение атрибутов окна такой метод. В зависимости от того, изменения в приложении `PreCreateWindow`, может оказаться необходимым для вызова реализации базового класса функции.  
  
 Следующее обсуждение охватывает SDI так и [случае MDI](#_core_the_mdi_case).  
  
##  <a name="_core_the_sdi_case"></a>В случае SDI  
 В приложении однооконный интерфейс (SDI) стиль окна по умолчанию в framework представляет собой сочетание **WS_OVERLAPPEDWINDOW** и **FWS_ADDTOTITLE** стили. **FWS_ADDTOTITLE** стиль зависящие от MFC, который указывает, что добавляемая платформа название документа для заголовка окна. Изменение атрибутов окна в приложении SDI, переопределите `PreCreateWindow` функции в класс производным от `CFrameWnd` (который имена мастера приложений `CMainFrame`). Пример:  
  
 [!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]  
  
 Этот код создает главное окно без кнопки свертывания и развертывания и изменяемые границы. Изначально окно центрируется на экране.  
  
##  <a name="_core_the_mdi_case"></a>В случае MDI  
 Чтобы изменить стиль окна дочернего окна в приложении несколько интерфейса (MDI) документа требуется немного больше работы. По умолчанию приложения MDI-приложения, созданного с помощью мастера приложений использует значение по умолчанию [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) класса, определенного в MFC. Чтобы изменить стиль окна дочернего окна MDI, должен наследовать новый класс из `CMDIChildWnd` и замените все ссылки на `CMDIChildWnd` проекта со ссылкой на новый класс. Скорее всего, только ссылка на `CMDIChildWnd` в приложение находится в вашем приложении `InitInstance` функции-члена.  
  
 Стиль окна по умолчанию, используемые в приложениях MDI представляет собой сочетание **WS_CHILD**, **WS_OVERLAPPEDWINDOW**, и **FWS_ADDTOTITLE** стили. Чтобы изменить атрибуты окна дочерних окон MDI-приложения, необходимо переопределить [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) функции в класс производным от `CMDIChildWnd`. Пример:  
  
 [!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]  
  
 Этот код создает дочерней MDI-формы windows без кнопки развертывания.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Стили Windows](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
-   [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)  
  
-   [Стили окна](http://msdn.microsoft.com/library/windows/desktop/ms632600)  
  
## <a name="see-also"></a>См. также  
 [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)

