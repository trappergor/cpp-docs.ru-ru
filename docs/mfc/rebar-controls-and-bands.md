---
title: "Элементы управления и зоны главной панели | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6426a25746858ed5bd7c0d8ef70575e029453bae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="rebar-controls-and-bands"></a>Элементы управления и зоны главной панели
Основная цель управления главной панели — в качестве контейнера для дочерних окон, стандартные элементы управления диалогового окна, меню, панелей инструментов и т. д. Это вложение поддерживается понятие «полосы». Каждой зоны главной панели может содержать любое сочетание полосу захвата, битовая карта, текстовую метку и дочернего окна.  
  
 Класс `CReBarCtrl` содержит многие функции-члены, можно использовать для извлечения и обрабатывать, эти данные для определенной области главной панели:  
  
-   [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) возвращает номер текущего полосами в элементе управления главной панели.  
  
-   [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo) инициализирует **REBARBANDINFO** структуры данными из указанного диапазона. Имеется соответствующий [SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo) функции-члена.  
  
-   [GetRect](../mfc/reference/crebarctrl-class.md#getrect) Возвращает прямоугольник, ограничивающий указанного диапазона.  
  
-   [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount) возвращает число строк аппаратного контроллера управления в элементе управления главной панели.  
  
-   [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex) Извлекает индекс заданного диапазона.  
  
-   [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders) извлекает границы диапазона.  
  
 Дополнение манипуляции предоставляются несколько функций-членов, которые позволяют работать с лентами определенной главной панели.  
  
 [InsertBand](../mfc/reference/crebarctrl-class.md#insertband) и [DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband) добавлять и удалять лентами главной панели. [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband) и [MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband) влияют на текущий размер определенной области главной панели. [MoveBand](../mfc/reference/crebarctrl-class.md#moveband) индекс определенной области главной панели. [ShowBand](../mfc/reference/crebarctrl-class.md#showband) Отображение или скрытие области главной панели от пользователя.  
  
 В следующем примере показано, как добавить панель инструментов (`m_wndToolBar`) в существующий элемент управления главной панели (`m_wndReBar`). Описывается инициализация полосе `rbi` структуры и последующего вызова `InsertBand` функции-члена:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Использование CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

