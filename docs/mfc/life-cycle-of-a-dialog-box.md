---
title: Жизненный цикл диалогового окна | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: faf204f05c03e742e0f491fb3991b56d3405ebc4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346185"
---
# <a name="life-cycle-of-a-dialog-box"></a>Жизненный цикл диалогового окна
На протяжении жизненного цикла диалогового окна пользователь вызывает диалоговое окно, обычно внутри обработчик команды, который создает и инициализирует объект диалогового окна, взаимодействие пользователя с диалоговым окном и диалоговое окно закрывается.  
  
 Для модальные диалоговые окна Ваш обработчик собирает все данные пользователя, введенные после закрытия этого диалогового. Поскольку объекта диалогового окна существует после закрытия его диалоговое окно, можно просто использовать переменные-члены класса диалогового окна для извлечения данных.  
  
 Для безрежимные диалоговые окна может часто извлекать данные из объекта диалогового окна, хотя по-прежнему отображается диалоговое окно. На некотором этапе уничтожении объекта диалогового окна; в этом случае зависит от кода.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Создание и отображение диалоговых окон](../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [Создание модальных диалоговых окон](../mfc/creating-modal-dialog-boxes.md)  
  
-   [Создание немодальных диалоговых окон](../mfc/creating-modeless-dialog-boxes.md)  
  
-   [Использование шаблона диалогового окна в памяти](../mfc/using-a-dialog-template-in-memory.md)  
  
-   [Установка цвета фона диалоговое окно «»](../mfc/setting-the-dialog-boxs-background-color.md)  
  
-   [Инициализация диалогового окна](../mfc/initializing-the-dialog-box.md)  
  
-   [Обработка сообщений Windows для диалогового окна](../mfc/handling-windows-messages-in-your-dialog-box.md)  
  
-   [Получение данных из объекта диалогового окна](../mfc/retrieving-data-from-the-dialog-object.md)  
  
-   [Закрытие диалогового окна](../mfc/closing-the-dialog-box.md)  
  
-   [Уничтожение диалогового окна](../mfc/destroying-the-dialog-box.md)  
  
-   [Обмен данными (диалоговых окон DDX) и проверки (DDV)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Диалоговые окна свойств таблицы](../mfc/property-sheets-and-property-pages-mfc.md)  
  
## <a name="see-also"></a>См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)

