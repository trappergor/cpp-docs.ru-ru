---
title: "Меню и ресурсы (OLE) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE visual editing servers [MFC]
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- string tables [MFC], visual editing applications
- OLE containers [MFC], menus and resources
- OLE applications [MFC], menus and resources
- OLE server applications [MFC], menus and resources
- toolbars [MFC], OLE document applications
- string editing [MFC], visual editing applications
- server applications [MFC], OLE menus and resources
- applications [OLE], menus and resources
- menus [MFC], OLE document applications
- in-place activation [MFC], OLE menus and resources
- containers [MFC], OLE container applications
- OLE menus and resources [MFC]
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: efe0a5f6dae2cece571eddabc4094ebb87df175b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="menus-and-resources-ole"></a>Меню и ресурсы (OLE)
Эта группа статей Описание использования меню и ресурсы в приложениях MFC OLE документа.  
  
 OLE визуального редактирования накладывает Дополнительные требования на меню и другие ресурсы, предоставляемые приложения документов OLE, так как существует несколько режимов, в которых оба контейнера и может запускаться и использовать приложения сервера (компонент). Например full серверное приложение может работать в любой из этих трех режимов:  
  
-   Независимо от них.  
  
-   На месте для редактирования в контексте элемента контейнера.  
  
-   Открыта для редактирования вне контекста элемента контейнера, часто в отдельном окне.  
  
 Для этого необходимо три отдельных меню макетов, один для каждого возможных режима работы приложения. Таблицы сочетаний клавиш необходимы также для каждого нового режима. Приложения-контейнера может или не поддерживает активацию на месте; в этом случае требуются в новой структуры меню и связанные таблицы сочетаний клавиш.  
  
 Активация на месте требуется контейнер и сервер приложений, которые должны согласовывать пространства панели меню, панели инструментов и состояние. Все ресурсы должны разрабатываться с этим в виду. Статья [меню и ресурсы: слияние меню](../mfc/menus-and-resources-menu-merging.md) рассматриваются в этом разделе подробно.  
  
 Вследствие этих причин приложения документов OLE, созданных с помощью мастера приложений может иметь до четырех отдельных меню и ресурсы таблицы сочетаний клавиш. Они используются по следующим причинам:  
  
|Имя ресурса|Использовать|  
|-------------------|---------|  
|**IDR_MAINFRAME**|Использовать в приложении MDI, если файл не открыт, или в приложении SDI независимо от того, открытые файлы. Это стандартное меню, используемые в приложениях, отличных от OLE.|  
|**IDR_\<проекта > тип**|Используется в приложении MDI, если файлы открыты. Используется, когда приложение выполняется как автономный. Это стандартное меню, используемые в приложениях, отличных от OLE.|  
|**IDR_\<проекта > TYPE_SRVR_IP**|Используется сервером или контейнера, когда открыт объект на месте.|  
|**IDR_\<проекта > TYPE_SRVR_EMB**|Используется серверное приложение, если объект был открыт без активации на месте.|  
  
 Каждый из этих имен ресурсов представляет меню и, как правило, таблицы сочетаний клавиш. Аналогичные схемы можно использовать в приложениях MFC, которые не создаются с помощью мастера приложений.  
  
 Следующие статьи обсудить вопросы, связанные с контейнерами, серверов и слияние необходимыми для реализации встроенной активации меню:  
  
-   [Меню и ресурсы. Добавление контейнеров](../mfc/menus-and-resources-container-additions.md)  
  
-   [Меню и ресурсы. Добавление серверов](../mfc/menus-and-resources-server-additions.md)  
  
-   [Меню и ресурсы. Слияние меню](../mfc/menus-and-resources-menu-merging.md)  
  
## <a name="see-also"></a>См. также  
 [OLE](../mfc/ole-in-mfc.md)

