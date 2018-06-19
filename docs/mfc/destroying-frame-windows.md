---
title: Уничтожение окон фрейма | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- PostNcDestroy
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81182c0e5633e19126d3036b5793de7658ad3d2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343480"
---
# <a name="destroying-frame-windows"></a>Уничтожение окон фрейма
Платформа MFC управляет уничтожение окна, а также создание этих окон, связанных с framework документов и представлений. При создании дополнительных windows, вы отвечаете за уничтожение их.  
  
 В платформе, когда пользователь закрывает окно фрейма окна по умолчанию [OnClose](../mfc/reference/cwnd-class.md#onclose) вызовов обработчика [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Последний функцию-член вызывается при уничтожении окна Windows [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), который не Очистка некоторых вызывает [по умолчанию](../mfc/reference/cwnd-class.md#default) член для выполнения очистки Windows и наконец вызывает виртуальная функция-член [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). [CFrameWnd](../mfc/reference/cframewnd-class.md) реализация `PostNcDestroy` удаляет объект window C++. Никогда не следует использовать C++ **удалить** оператора в окне фрейма. Взамен рекомендуется использовать `DestroyWindow`.  
  
 Приложение закрывается при закрытии главного окна. Если изменяются несохраненные документы, платформа отображает окно сообщения для запроса, если следует сохранить документы и гарантирует, что соответствующие документы сохраняются при необходимости.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>См. также  
 [Использование окон фрейма](../mfc/using-frame-windows.md)

