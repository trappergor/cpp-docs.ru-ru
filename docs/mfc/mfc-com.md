---
title: "MFC COM | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MFC COM (MFC)
dev_langs:
- C++
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd9035c7b80b36e8124c827c0b3d1b76c59deb52
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="mfc-com"></a>MFC COM
Подмножество MFC предназначен для поддержки модели COM, хотя большинство из Active Template Library (ATL) предназначен для программирования в модели COM. Подразделы в этом разделе описывается поддержка MFC для модели COM.  
  
 Технологии Active (такие как ActiveX элементов управления, вложение активного документа, OLE и т. д) используйте модель объектов компонентов (COM), чтобы включить программным компонентам взаимодействовать друг с другом в сетевой среде, независимо от языка, с которым они были создать. Активные технологий можно использовать для создания приложений, выполняющихся на рабочем столе или в Интернете. Дополнительные сведения см. [Знакомство с COM](../atl/introduction-to-com.md) или [модель COM](http://msdn.microsoft.com/library/windows/desktop/ms694363).  
  
 Активные включает следующие технологии клиентских и серверных технологий, включая следующие:  
  
-   [Вложение активного документа](../mfc/active-document-containment.md), поддерживаемые в MFC версии 4.2 и более поздних версий, позволяет пользователям просматривать [активные документы](../mfc/active-documents.md) (например, Microsoft Excel или Word) и активировать весь интерфейс собственного документа приложение всю клиентскую область [контейнер активного документа](../mfc/active-document-containers.md) как Microsoft Office Binder или Microsoft Internet Explorer. Контейнеры выступают в качестве клиентов, пока предоставленные документы [серверы активных документов](../mfc/active-document-servers.md). Дополнительные сведения об использовании активные документы в веб-приложений см. в разделе: [активные документы в Интернете](../mfc/active-documents-on-the-internet.md).  
  
-   Элементы управления ActiveX являются интерактивных объектов, которые могут использоваться в контейнерах, таких как веб-сайта. Дополнительные сведения для элементов управления ActiveX см. в разделе:  
  
    -   [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)  
  
    -   [Элементы управления ActiveX в Интернете](../mfc/activex-controls-on-the-internet.md)  
  
    -   [Overview: Internet](../mfc/mfc-internet-programming-basics.md)  
  
    -   [Обновление существующего элемента управления ActiveX для использования в Интернете](../mfc/upgrading-an-existing-activex-control.md)  
  
    -   [Отладка элемента управления ActiveX](/visualstudio/debugger/how-to-debug-an-activex-control)  
  
-   Активные сценарии управляет поведением интеграции один или несколько элементов управления ActiveX из браузера или сервера. Дополнительные сведения об активных сценариев см. в разделе [Технология Active в Интернете](../mfc/active-technology-on-the-internet.md).  
  
-   [Автоматизация](../mfc/automation.md) (прежнее название — OLE-автоматизация) делает возможным для одного приложения для работы с объектами, реализованными в другом приложении, или для «предоставления» объекты, поэтому ими можно управлять.  
  
     Автоматизированный объект может быть локальным или удаленным (находиться на другом компьютере, доступном по сети). Автоматизация доступна для OLE- и COM-объектов.  
  
-   Здесь также приведены сведения о том, как создавать компоненты COM, с помощью MFC, например, в [точки подключения](../mfc/connection-points.md).  
  
 Обсуждение по-прежнему называемое OLE и что теперь называется active-технология, см. в разделах на [OLE](../mfc/ole-in-mfc.md).  
  
 Кроме того, в статье базы знаний Q248019: Практическое руководство: предотвратить сервер занят диалогового окна поле из отображаются во время продолжительной COM операции.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Вложение активного документа](../mfc/active-document-containment.md)  
  
 [Автоматизация](../mfc/automation.md)  
  
 [Точки подключения](../mfc/connection-points.md)  
  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../mfc/mfc-concepts.md)

