---
title: Уничтожение объектов окон | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3aacb01d945429bc36543f78e3635c39ef58223d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343380"
---
# <a name="destroying-window-objects"></a>Уничтожение объектов окон
Необходимо соблюдать осторожность с дочерних окон для уничтожения объекта C++ окна при завершении пользователем с окном. Если эти объекты не освобождаются, приложения не будут восстановлены их память. К счастью среда управляет уничтожение окна, а также создания для окна фрейма, представления и диалоговым окнам. При создании дополнительных windows, вы отвечаете за уничтожение их.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Последовательность деструкции окна](../mfc/window-destruction-sequence.md)  
  
-   [Выделение и освобождение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Отсоединение CWnd от HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [Общая последовательность создания окна](../mfc/general-window-creation-sequence.md)  
  
-   [Уничтожение окон фрейма](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>См. также  
 [Объекты окон](../mfc/window-objects.md)

