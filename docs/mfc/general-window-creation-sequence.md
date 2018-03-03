---
title: "Общая последовательность создания окна | Документы Microsoft"
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
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59bed4387a6b8e6edeb504e29d221e76a0b39d18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="general-window-creation-sequence"></a>Общая последовательность создания окна
При создании окна собственный, такие как дочерний элемент окна, платформа использует гораздо того же процесса, описанного в [создание документов и представлений](../mfc/document-view-creation.md).  
  
 Классы окон, предоставляемых MFC используют [двухэтапного создания](../mfc/one-stage-and-two-stage-construction-of-objects.md). То есть во время вызова функций C++ **новый** оператор, конструктор выделяет и инициализирует объект C++, но не создает соответствующее окно Windows. После этого выполняется путем вызова [создать](../mfc/reference/cwnd-class.md#create) функции-члена объекта window.  
  
 **Создать** функции-члена делает окно Windows и сохраняет его `HWND` в объекте C++ открытый элемент данных [m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd). **Создание** дает полную гибкость параметры создания. Перед вызовом метода **создать**, может потребоваться зарегистрировать класс окна в глобальной функции [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) Чтобы задать значок и класс стили рамки.  
  
 Окна фрейма, можно использовать [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) вместо функции-члена **создать**. `LoadFrame`делает окно Windows, с помощью меньшее число параметров. Многие значения по умолчанию он получает от ресурсов, включая заголовок, значок, таблицу сочетаний клавиш и меню опорного кадра.  
  
> [!NOTE]
>  Ваш значок, таблицу сочетаний клавиш и ресурсов меню должны иметь общий идентификатор ресурса, например **IDR_MAINFRAME**, для них должна быть загружена по LoadFrame.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Объекты окон](../mfc/window-objects.md)  
  
-   [Регистрация классов «окон»](../mfc/registering-window-classes.md)  
  
-   [Уничтожение объектов окон](../mfc/destroying-window-objects.md)  
  
-   [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>См. также  
 [Создание окон](../mfc/creating-windows.md)

