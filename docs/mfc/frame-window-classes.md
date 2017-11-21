---
title: "Классы окна фрейма | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame window classes [MFC], about frame window classes
- frame window classes [MFC]
- windows [MFC], MDI
- document frame windows [MFC], classes
- single document interface (SDI), frame windows
- window classes [MFC], frame
- MFC, frame windows
- MDI [MFC], frame windows
- classes [MFC], window
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 60f3938042cd42c7b02c12eb4e6316a00783c280
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="frame-window-classes"></a>Классы окна фрейма
Каждое приложение имеет один «фрейма главного окна», окно на рабочем столе, который обычно имеет имя приложения в его заголовок. Каждый документ обычно имеет одно «окном фрейма документа». Окно фрейма документа содержит хотя бы одно представление, позволяющее представить данные документа.  
  
## <a name="frame-windows-in-sdi-and-mdi-applications"></a>Окна фрейма в SDI и MDI-приложения  
 Для приложения SDI имеется одно окно фрейма, производный от класса [CFrameWnd](../mfc/reference/cframewnd-class.md). Это окно будет фрейма главного окна и окна фрейма документа. Для приложения MDI фрейма главного окна является производным от класса [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), и окна фрейма документа, которые являются дочерними окнами MDI, являются производными от класса [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).  
  
## <a name="use-the-frame-window-class-or-derive-from-it"></a>Используйте класс фреймового окна или производный от него  
 Эти классы обеспечивают большую часть окна фрейма функциональные возможности, необходимые для ваших приложений. В обычных условиях по умолчанию поведение и внешний вид, им будет при необходимости. Если требуются дополнительные функциональные возможности, наследуют от этих классов.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Классы окна фрейма, созданные с помощью мастера приложений](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)  
  
-   [Изменение стилей окна, созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## <a name="see-also"></a>См. также  
 [Окна фрейма](../mfc/frame-windows.md)

