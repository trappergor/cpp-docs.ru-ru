---
title: "Серверы: Реализация сервера | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 148a3da3c904f5c314c75fb71deede3c92163cc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="servers-implementing-a-server"></a>Серверы. Реализация сервера
В этой статье объясняется, мастер приложений MFC создает для серверного приложения визуального редактирования. Если вы не используете мастер приложений, в этой статье перечислены области, где необходимо написать код для реализации серверного приложения.  
  
 При использовании мастера приложений для создания нового приложения сервера он предоставляет значительный объем кода для конкретного сервера. При добавлении визуального редактирования функциональные возможности сервера к существующему приложению необходимо повторяющийся код, который предоставлен в мастере приложений будет перед добавлением остальные необходимые серверного кода.  
  
 Код сервера, мастер приложений предоставляет подразделяется на несколько категорий.  
  
-   Определение ресурсов сервера:  
  
    -   Меню ресурса, используемого при сервер редактируется встроенного элемента в отдельном окне.  
  
    -   Меню и панели инструментов ресурсы, используемые, когда сервер находится в активной на месте.  
  
     Дополнительные сведения об этих ресурсов см. в разделе [меню и ресурсы: Добавление серверов](../mfc/menus-and-resources-server-additions.md).  
  
-   Определение класса элемента производным от `COleServerItem`. Дополнительные сведения для элементов сервера в разделе [серверов: элементы сервера](../mfc/servers-server-items.md).  
  
-   Изменение базового класса для класса документа `COleServerDoc`. Дополнительные сведения см. в разделе [серверы: реализация документов сервера](../mfc/servers-implementing-server-documents.md).  
  
-   Определение класса окна фрейма производным от `COleIPFrameWnd`. Дополнительные сведения см. в разделе [серверы: реализация окон фрейма на месте](../mfc/servers-implementing-in-place-frame-windows.md).  
  
-   Создание записи для серверного приложения в базе данных регистрации Windows и регистрации нового экземпляра сервера в системе OLE. Сведения по этой теме см. в разделе [регистрации](../mfc/registration.md).  
  
-   Инициализация и запуск приложения сервера. Сведения по этой теме см. в разделе [регистрации](../mfc/registration.md).  
  
 Дополнительные сведения см. в разделе [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerDoc](../mfc/reference/coleserverdoc-class.md), и [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) в *Справочник по библиотеке классов*.  
  
## <a name="see-also"></a>См. также  
 [Серверы](../mfc/servers.md)   
 [Контейнеры](../mfc/containers.md)   
 [Меню и ресурсы (OLE)](../mfc/menus-and-resources-ole.md)   
 [Регистрация](../mfc/registration.md)

