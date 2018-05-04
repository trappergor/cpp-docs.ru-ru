---
title: Добавление обработчика сообщения ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e79598b79ccbad13ad98c7fc1284808fe1b05cfc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="adding-an-atl-message-handler"></a>Добавление обработчика сообщения ATL
Добавление обработчика сообщения (член функции, обрабатывающей сообщения Windows) для элемента управления, выберите элемент управления в представлении классов. Затем откройте **свойства** выберите **сообщений** значок и выберите в раскрывающемся списке элемента управления в поле противоположного обязательный сообщений. Это добавит объявление для обработчика сообщений в файл заголовка элемента управления и схему реализации обработчика в CPP-файл элемента управления. Он также добавить схему сообщений и добавьте запись для обработчика.  
  
 Добавление обработчика сообщений в ATL сходно с добавлением обработчика сообщений для класса MFC. В разделе [Добавление обработчика сообщения MFC](../mfc/reference/adding-an-mfc-message-handler.md) для получения дополнительной информации.  
  
 Только для добавления обработчика сообщений ATL применяются следующие условия:  
  
-   Обработчики сообщений выполните то же соглашение об именовании как MFC.  
  
-   В сопоставление основного сообщения добавляются новые записи схемы сообщений. Мастер не распознает альтернативных сопоставлений и цепочки.  
  
## <a name="see-also"></a>См. также  
 [Реализация окна](../atl/implementing-a-window.md)

