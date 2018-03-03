---
title: "Как: Добавление элементов управления ленты и обработчики событий | Документы Microsoft"
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
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f5d5015fdf5fd2a97b6b8a9b9ee9cf5ccc755ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>Практическое руководство. Добавление элементов управления и обработчиков событий ленты
Элементы управления ленты — элементы, такие как кнопки и поля со списком, добавляемые панелей. Панели — областями панель ленты, в которых отображаются группы связанных элементов управления.  
  
 В этом разделе будет открыть конструктор лент, добавьте кнопку и свяжите событие, которое отображает «Hello World».  
  
### <a name="to-open-the-ribbon-designer"></a>Чтобы открыть конструктор лент  
  
1.  В Visual Studio на **представление** меню, нажмите кнопку **представление ресурсов**.  
  
2.  В **представление ресурсов**, дважды щелкните ресурс ленты, чтобы отобразить ее в рабочей области конструирования.  
  
### <a name="to-add-a-button-and-an-event-handler"></a>Чтобы добавить кнопку и обработчик событий  
  
1.  Из **инструментов**, нажмите кнопку **кнопку** и перетащите его на панель в рабочей области конструирования.  
  
2.  Правой кнопкой мыши и выберите **добавить обработчик событий**.  
  
3.  В **мастер обработчиков событий**Подтвердите параметры по умолчанию и нажмите кнопку **добавлять и редактировать**. Дополнительные сведения см. в разделе [мастер обработчиков событий](../ide/event-handler-wizard.md).  
  
4.  В редакторе кода добавьте следующий код в функцию обработчика:  
  
 ```  
    MessageBox((LPCTSTR)L"Hello World");

 ```  
  
## <a name="see-also"></a>См. также  
 [Пример RibbonGadgets: Ленты мини-приложения приложения](../visual-cpp-samples.md)   
 [Конструктор ленты (MFC)](../mfc/ribbon-designer-mfc.md)

