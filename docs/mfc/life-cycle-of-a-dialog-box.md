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
ms.openlocfilehash: d365be21ef19a6779df649e9368fdc0cda4851df
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621446"
---
# <a name="working-with-dialog-boxes-in-mfc"></a>Работа с диалоговыми окнами в MFC

В течение жизненного цикла диалогового окна пользователь вызывает диалоговое окно, как правило, внутри обработчика команд, который создает и инициализирует диалоговый объект, пользователь взаимодействует с диалоговым окном, а затем закрывает диалоговое окно.

Для модальных диалоговых окон обработчик собирает любые данные, которые пользователь указал после закрытия диалогового окна. Так как объект диалогового окна существует после закрытия диалогового окна, можно просто использовать переменные члена класса диалогового окна для извлечения данных.

Для немодальных диалоговых окон часто можно извлекать данные из диалогового объекта, когда диалоговое окно остается видимым. В какой-то момент объект диалогового окна уничтожается; когда это происходит, зависит от вашего кода.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Создание и отображение диалоговых окон](creating-and-displaying-dialog-boxes.md)

- [Создание модальных диалоговых окон](creating-modal-dialog-boxes.md)

- [Создание немодальных диалоговых окон](creating-modeless-dialog-boxes.md)

- [Использование шаблона диалогового окна в памяти](using-a-dialog-template-in-memory.md)

- [Задание цвета фона диалогового окна](setting-the-dialog-boxs-background-color.md)

- [Инициализация диалогового окна](initializing-the-dialog-box.md)

- [Обработка сообщений Windows в диалоговом окне](handling-windows-messages-in-your-dialog-box.md)

- [Извлечение данных из объекта диалогового окна](retrieving-data-from-the-dialog-object.md)

- [Закрытие диалогового окна](closing-the-dialog-box.md)

- [Уничтожение диалогового окна](destroying-the-dialog-box.md)

- [Обмен данными диалоговых окон (DDX) и проверка (DDV)](dialog-data-exchange-and-validation.md)

- [Диалоговые окна страницы свойств](property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>См. также раздел

[Диалоговые окна](dialog-boxes.md)
