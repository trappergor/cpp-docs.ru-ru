---
title: Буфер обмена | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2ad21bcbff31335f6ec79a4527ef7d99e07e547
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="clipboard"></a>буфер обмена
Этот сборник статей способы реализации поддержки в буфер обмена Windows в приложениях MFC. В буфер обмена Windows используется двумя способами:  
  
-   Реализация стандартных команд в меню, например, Вырезать, копировать и вставить.  
  
-   Реализация универсального данных передачи с помощью перетаскивания и drop (OLE).  
  
 Буфер обмена является стандартным Windows, переноса данных между источником и назначением. Также можно использовать в операциях OLE. С появлением OLE имеется два механизма буфера обмена в Windows. Стандартный API-Интерфейс буфер обмена Windows по-прежнему доступен, но она была дополнена механизм передачи данных OLE. Передача универсального данных OLE (UDT) поддерживает операции вырезания, копирования и с помощью буфера обмена и перетащите.  
  
 Буфер обмена — это системная служба, совместно использоваться всего сеанса Windows, поэтому он не имеет дескриптор или свой собственный класс. Управление буфера обмена посредством функции-члены класса [CWnd](../mfc/reference/cwnd-class.md).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Использование механизма буфера обмена](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)  
  
-   [С помощью традиционных API буфера обмена Windows](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [Использование механизма буфера обмена OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
-   [Копирование и вставка данных](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Добавление других форматов](../mfc/clipboard-adding-other-formats.md)  
  
-   [В буфер обмена Windows](https://msdn.microsoft.com/library/ms648709)  
  
-   [Реализация перетаскивание (OLE)](../mfc/drag-and-drop-ole.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)
