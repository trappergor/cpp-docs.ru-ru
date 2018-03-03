---
title: "Вкладки свойств и страницы свойств (MFC) | Документы Microsoft"
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
- MFC dialog boxes [MFC], tabs
- property pages [MFC], property sheets
- CPropertyPage class [MFC], property sheets and pages
- CPropertySheet class [MFC], property sheets and pages
- property sheets, propert pages
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 877d83a6833b9505c326bc5312d2f151add07cb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="property-sheets-and-property-pages-mfc"></a>Вкладки свойств и страницы свойств (MFC)
MFC [диалоговое окно](../mfc/dialog-boxes.md) может принимать взглянуть «вкладку диалогового окна», включая вкладки свойств и страницы свойств. Называется «страницы свойств» в MFC, такого рода диалоговом аналогично множество диалоговых окон в Microsoft Word, Excel и Visual C++, видимому содержит стек с вкладками листов, подобно стек папок с файлами с начала до конца или группы windows каскадного. Элементы управления на вкладке передней являются видимыми; только с меткой вкладка отображается на задней панели вкладок. Страницы свойств особенно полезны для управления большим числом свойств или параметров, которые очень аккуратно делятся на несколько групп. Как правило одно окно свойств можно упростить пользовательский интерфейс, заменив нескольких разных диалоговых.  
  
 Начиная с MFC версии 4.0 вкладки свойств и страницы свойств реализуются с помощью стандартных элементов управления, входящие в состав Windows 95 и Windows NT 3.51 и более поздних версий.  
  
 Страницы свойств реализуются с помощью классов [CPropertySheet](../mfc/reference/cpropertysheet-class.md) и [CPropertyPage](../mfc/reference/cpropertypage-class.md) (описано в *Справочник по библиотеке MFC*). `CPropertySheet`Определяет общее диалоговым окном, которое может содержать несколько «страниц» на основе `CPropertyPage`.  
  
 Сведения о создании и работе со страницами свойств см. в разделе [свойств](../mfc/property-sheets-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)   
 [Вкладки свойств и страницы свойств в MFC](../mfc/property-sheets-and-property-pages-in-mfc.md)   
 [Обмен данными](../mfc/exchanging-data.md)   
 [Создание Безмодальной вкладки свойства](../mfc/creating-a-modeless-property-sheet.md)   
 [Обработка кнопки "Применить"](../mfc/handling-the-apply-button.md)

