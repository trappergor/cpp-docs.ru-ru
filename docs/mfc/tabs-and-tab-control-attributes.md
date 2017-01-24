---
title: "Вкладки и атрибуты элемента управления &quot;Вкладка&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "атрибуты [C++], справочные разделы"
  - "CTabCtrl - класс, атрибуты элемента управления вкладками"
  - "элементы управления вкладка, атрибуты"
  - "вкладки"
  - "вкладки, атрибуты"
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Вкладки и атрибуты элемента управления &quot;Вкладка&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Имеется значительный элемент управления над внешним видом и расширением функциональности вкладок, составляющие элемента управления "вкладка" \([CTabCtrl](../Topic/CTabCtrl%20Class.md)\).  Каждая вкладка может иметь меток, Значок, состояние элемента, определенное приложением 32 бит значение, связанное с ней.  Для каждой вкладки можно отобразить Значок метку, или оба.  
  
 Кроме того, каждый элемент вкладки, может иметь 3 возможных состояний: pressed, unpressed или выбранный.  Это состояние может быть установлено, заменив существующий элемент вкладки.  Чтобы изменить существующий элемент вкладки, извлечь его с вызовом метода [GetItem](../Topic/CTabCtrl::GetItem.md), изменение структуры `TCITEM` \(а именно элементы данных **dwState** и **dwStateMask** \), а затем возвращает измененную структура `TCITEM` с вызовом метода [SetItem](../Topic/CTabCtrl::SetItem.md).  Если необходимо удалить состояния элемента всех элементов вкладки в объекте `CTabCtrl`, вызывать в [DeselectAll](../Topic/CTabCtrl::DeselectAll.md).  Эта функция сбросит состояние всех элементов вкладки или всех элементов за исключением того, что выбранное одно.  
  
 Следующий код удаляет состояние всех элементов вкладки и затем изменяет состояние третьего элемента:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/CPP/tabs-and-tab-control-attributes_1.cpp)]  
  
 Атрибуты вкладки Дополнительные сведения о см. в разделе [Вкладки и атрибуты вкладки](http://msdn.microsoft.com/library/windows/desktop/bb760550) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Дополнительные сведения о добавление вкладки в элемент управления TAB см. в разделе [Добавление вкладки в элемент управления tab](../mfc/adding-tabs-to-a-tab-control.md) далее в этом разделе.  
  
## См. также  
 [Использование CTabCtrl](../mfc/using-ctabctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)