---
title: Жизненный цикл диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
ms.openlocfilehash: a3772a180e35a57c997446fcf2268d84bec2daa5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291110"
---
# <a name="life-cycle-of-a-dialog-box"></a>Жизненный цикл диалогового окна

В течение жизненного цикла в диалоговом окне пользователь вызывает диалоговое окно, обычно внутри обработчик команды, который создает и инициализирует объект диалогового окна, с которым взаимодействует пользователь с диалоговым окном и диалоговое окно закрывается.

Для модальные диалоговые окна Ваш обработчик собирает все данные, введенные после диалоговое окно будет закрыто пользователем. Поскольку объект диалоговое окно существует после закрытия его диалоговое окно, можно просто использовать переменные-члены класса диалогового окна для извлечения данных.

Для немодальных диалоговых окон может часто извлекать данные из объекта диалогового окна, хотя по-прежнему отображается диалоговое окно. Рано или поздно уничтожении объекта диалогового окна; в этом случае зависит от кода.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Создание и отображение диалоговых окон](../mfc/creating-and-displaying-dialog-boxes.md)

- [Создание модальных диалоговых окон](../mfc/creating-modal-dialog-boxes.md)

- [Создание немодальных диалоговых окон](../mfc/creating-modeless-dialog-boxes.md)

- [Использование шаблона диалогового окна в памяти](../mfc/using-a-dialog-template-in-memory.md)

- [Установка цвета фона диалогового окна](../mfc/setting-the-dialog-boxs-background-color.md)

- [Инициализация диалогового окна](../mfc/initializing-the-dialog-box.md)

- [Обработка сообщений Windows в диалоговом окне.](../mfc/handling-windows-messages-in-your-dialog-box.md)

- [Получение данных из объекта диалогового окна](../mfc/retrieving-data-from-the-dialog-object.md)

- [Закрытие диалогового окна](../mfc/closing-the-dialog-box.md)

- [Уничтожение диалогового окна](../mfc/destroying-the-dialog-box.md)

- [Обмен данными диалоговых окон (DDX) и проверки (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [Диалоговые окна свойств таблицы стилей](../mfc/property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)
