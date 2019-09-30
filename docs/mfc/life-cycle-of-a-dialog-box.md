---
title: Работа с диалоговыми окнами в MFC
ms.date: 09/27/2019
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
ms.openlocfilehash: ad15250cf9a8dd663072cf9423263260bbb40a0e
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685734"
---
# <a name="working-with-dialog-boxes-in-mfc"></a>Работа с диалоговыми окнами в MFC

В течение жизненного цикла диалогового окна пользователь вызывает диалоговое окно, как правило, внутри обработчика команд, который создает и инициализирует диалоговый объект, пользователь взаимодействует с диалоговым окном, а затем закрывает диалоговое окно.

Для модальных диалоговых окон обработчик собирает любые данные, которые пользователь указал после закрытия диалогового окна. Так как объект диалогового окна существует после закрытия диалогового окна, можно просто использовать переменные члена класса диалогового окна для извлечения данных.

Для немодальных диалоговых окон часто можно извлекать данные из диалогового объекта, когда диалоговое окно остается видимым. В какой-то момент объект диалогового окна уничтожается; когда это происходит, зависит от вашего кода.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Создание и отображение диалоговых окон](../mfc/creating-and-displaying-dialog-boxes.md)

- [Создание модальных диалоговых окон](../mfc/creating-modal-dialog-boxes.md)

- [Создание немодальных диалоговых окон](../mfc/creating-modeless-dialog-boxes.md)

- [Использование шаблона диалогового окна в памяти](../mfc/using-a-dialog-template-in-memory.md)

- [Задание цвета фона диалогового окна](../mfc/setting-the-dialog-boxs-background-color.md)

- [Инициализация диалогового окна](../mfc/initializing-the-dialog-box.md)

- [Обработка сообщений Windows в диалоговом окне](../mfc/handling-windows-messages-in-your-dialog-box.md)

- [Извлечение данных из объекта диалогового окна](../mfc/retrieving-data-from-the-dialog-object.md)

- [Закрытие диалогового окна](../mfc/closing-the-dialog-box.md)

- [Уничтожение диалогового окна](../mfc/destroying-the-dialog-box.md)

- [Обмен данными диалоговых окон (DDX) и проверка (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [Диалоговые окна страницы свойств](../mfc/property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)
