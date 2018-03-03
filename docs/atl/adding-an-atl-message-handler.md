---
title: "Добавление обработчика сообщения ATL | Документы Microsoft"
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
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4358dc54589971c559bec48adf77252d4f4cda28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-atl-message-handler"></a>Добавление обработчика сообщения ATL
Добавление обработчика сообщения (член функции, обрабатывающей сообщения Windows) для элемента управления, выберите элемент управления в представлении классов. Затем откройте **свойства** выберите **сообщений** значок и выберите в раскрывающемся списке элемента управления в поле противоположного обязательный сообщений. Это добавит объявление для обработчика сообщений в файл заголовка элемента управления и схему реализации обработчика в CPP-файл элемента управления. Он также добавить схему сообщений и добавьте запись для обработчика.  
  
 Добавление обработчика сообщений в ATL сходно с добавлением обработчика сообщений для класса MFC. В разделе [Добавление обработчика сообщения MFC](../mfc/reference/adding-an-mfc-message-handler.md) для получения дополнительной информации.  
  
 Только для добавления обработчика сообщений ATL применяются следующие условия:  
  
-   Обработчики сообщений выполните то же соглашение об именовании как MFC.  
  
-   В сопоставление основного сообщения добавляются новые записи схемы сообщений. Мастер не распознает альтернативных сопоставлений и цепочки.  
  
## <a name="see-also"></a>См. также  
 [Реализация окна](../atl/implementing-a-window.md)

