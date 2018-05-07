---
title: Общая последовательность создания окна | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75a9c6ecf6516adceda845dadd4f0313ae605f0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="general-window-creation-sequence"></a>Общая последовательность создания окна
При создании окна собственный, такие как дочерний элемент окна, платформа использует гораздо того же процесса, описанного в [создание документов и представлений](../mfc/document-view-creation.md).  
  
 Классы окон, предоставляемых MFC используют [двухэтапного создания](../mfc/one-stage-and-two-stage-construction-of-objects.md). То есть во время вызова функций C++ **новый** оператор, конструктор выделяет и инициализирует объект C++, но не создает соответствующее окно Windows. После этого выполняется путем вызова [создать](../mfc/reference/cwnd-class.md#create) функции-члена объекта window.  
  
 **Создать** функции-члена делает окно Windows и сохраняет его `HWND` в объекте C++ открытый элемент данных [m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd). **Создание** дает полную гибкость параметры создания. Перед вызовом метода **создать**, может потребоваться зарегистрировать класс окна в глобальной функции [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) Чтобы задать значок и класс стили рамки.  
  
 Окна фрейма, можно использовать [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) вместо функции-члена **создать**. `LoadFrame` делает окно Windows, с помощью меньшее число параметров. Многие значения по умолчанию он получает от ресурсов, включая заголовок, значок, таблицу сочетаний клавиш и меню опорного кадра.  
  
> [!NOTE]
>  Ваш значок, таблицу сочетаний клавиш и ресурсов меню должны иметь общий идентификатор ресурса, например **IDR_MAINFRAME**, для них должна быть загружена по LoadFrame.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Объекты окон](../mfc/window-objects.md)  
  
-   [Регистрация классов «окон»](../mfc/registering-window-classes.md)  
  
-   [Уничтожение объектов окон](../mfc/destroying-window-objects.md)  
  
-   [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>См. также  
 [Создание окон](../mfc/creating-windows.md)

