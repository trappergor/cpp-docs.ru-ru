---
title: Работа с объектами окон | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4c00649c51e34bbbac7adbf7aa5f3c7d04790ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383371"
---
# <a name="working-with-window-objects"></a>Работа с объектами окон
Работа с вызовов windows для двух видов деятельности:  
  
-   Обработка сообщений Windows  
  
-   Рисование в окне  
  
 Для обработки сообщений Windows в любом окне, включая собственные дочерние окна в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md) для сопоставления сообщения с C++ класс окна. Затем напишите обработчик сообщений функции-члены в классе.  
  
 Большинство рисования в приложении framework происходит в представлении, чьи [OnDraw](../mfc/reference/cview-class.md#ondraw) функция-член вызывается всякий раз, когда необходимо нарисовать содержимого окна. Если окно является дочерним для представления, вы может делегировать некоторые представления Рисование ваше дочернее окно, задав `OnDraw` вызвать одну из функций-членов вашего окна.  
  
 В любом случае необходимо будет контекста устройства для рисования. Можно использовать биржевых перо, кисти и другие графические объекты, содержащиеся в контекст устройства, связанный с вашего окна. Или вы можете изменять эти объекты эффекты рисования, который требуется получить. С текущего контекста устройства, как вам нравится, следует вызвать член функции класса [CDC](../mfc/reference/cdc-class.md) (класс контекста устройства) для рисования линий, фигур и текста; для использования цветов; и для работы с системы координат.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Обработка и сопоставление сообщений](../mfc/message-handling-and-mapping.md)  
  
-   [Рисование в представлении](../mfc/drawing-in-a-view.md)  
  
-   [Контексты устройств](../mfc/device-contexts.md)  
  
-   [Графические объекты](../mfc/graphic-objects.md)  
  
## <a name="see-also"></a>См. также  
 [Объекты окон](../mfc/window-objects.md)

