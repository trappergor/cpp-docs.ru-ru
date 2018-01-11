---
title: "Уничтожение окон фрейма | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PostNcDestroy
dev_langs: C++
helpviewer_keywords:
- Default method [MFC]
- DestroyWindow method [MFC]
- frame windows [MFC], destroying
- OnNcDestroy method, and frame windows
- document frame windows [MFC], destroying
- destroying frame windows
- MFC, frame windows
- windows [MFC], destroying
- OnClose method [MFC]
- PostNcDestroy method [MFC]
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1cbd96f5044626c7c3c07e8fca115c2b1dca8cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-frame-windows"></a>Уничтожение окон фрейма
Платформа MFC управляет уничтожение окна, а также создание этих окон, связанных с framework документов и представлений. При создании дополнительных windows, вы отвечаете за уничтожение их.  
  
 В платформе, когда пользователь закрывает окно фрейма окна по умолчанию [OnClose](../mfc/reference/cwnd-class.md#onclose) вызовов обработчика [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Последний функцию-член вызывается при уничтожении окна Windows [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), который не Очистка некоторых вызывает [по умолчанию](../mfc/reference/cwnd-class.md#default) член для выполнения очистки Windows и наконец вызывает виртуальная функция-член [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). [CFrameWnd](../mfc/reference/cframewnd-class.md) реализация `PostNcDestroy` удаляет объект window C++. Никогда не следует использовать C++ **удалить** оператора в окне фрейма. Взамен рекомендуется использовать `DestroyWindow`.  
  
 Приложение закрывается при закрытии главного окна. Если изменяются несохраненные документы, платформа отображает окно сообщения для запроса, если следует сохранить документы и гарантирует, что соответствующие документы сохраняются при необходимости.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>См. также  
 [Использование окон фрейма](../mfc/using-frame-windows.md)

