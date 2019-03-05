---
title: Пример Отображение диалогового окна через команду меню
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
ms.openlocfilehash: 8c60469747c24b4c295348a14cb569c4118c76d9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260482"
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>Пример Отображение диалогового окна через команду меню

Этот раздел содержит процедуры для:

- Отображение модального диалогового окна через команду меню.

- Отобразить немодального диалогового окна через команду меню.

Оба примера процедуры для приложений MFC и будет работать в приложении, созданного с использованием [мастер приложений MFC](../mfc/reference/mfc-application-wizard.md).

В процедурах используются следующие имена и значения:

|Элемент|Имя или значение|
|----------|-------------------|
|Приложение|DisplayDialog|
|Команды меню|Тестирование команды в меню "Вид"; ИД команды = ID_VIEW_TEST|
|Диалоговое окно|Диалоговое окно Test; Класс = CTestDialog; Файл заголовка = TestDialog.h; Переменная = testdlg ptestdlg|
|Обработчик команд|OnViewTest|

### <a name="to-display-a-modal-dialog-box"></a>Для отображения модального диалогового окна

1. Создание команды меню; см. в разделе [Создание меню и пунктов меню](../windows/creating-a-menu.md).

1. Создание диалогового окна; см. в разделе [запуск редактора диалоговых окон](../windows/creating-a-new-dialog-box.md).

1. Добавьте класс диалогового окна. См. в разделе [Добавление класса](../ide/adding-a-class-visual-cpp.md) Дополнительные сведения.

1. В **представление классов**, выберите класс документа (CDisplayDialogDoc). В окне **Свойства** нажмите кнопку **События** . Дважды щелкните идентификатор команды меню (ID_VIEW_TEST) в левой части **свойства** и выберите **команда**. В области справа щелкните стрелку вниз и выберите  **\<Добавить > OnViewTest**.

   Если вы добавили команду меню мэйнфрейма MDI-приложения, выберите класс приложения (CDisplayDialogApp).

1. Добавьте следующие включать инструкцию CDisplayDialogDoc.cpp (или CDisplayDialogApp.cpp) после существующего включают инструкции:

   [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]

1. Добавьте следующий код, чтобы `OnViewTest` для выполнения функции:

   [!code-cpp[NVC_MFCControlLadenDialog#43](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_2.cpp)]

### <a name="to-display-a-modeless-dialog-box"></a>Для отображения немодального диалогового окна

1. Выполните первые четыре шага для отображения модальное диалоговое окно, за исключением того, выберите класс представления (CDisplayDialogView) на шаге 4.

1. Измените DisplayDialogView.h:

   - Объявите предшествующей первого класса объявлению класса диалогового окна:

         [!code-cpp[NVC_MFCControlLadenDialog#44](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_3.h)]

   - Объявите указатель на окно после открытого раздела «Attributes»:

         [!code-cpp[NVC_MFCControlLadenDialog#45](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_4.h)]

1. Измените DisplayDialogView.cpp:

   - Добавьте следующие инструкции после существующего включают инструкции:

         [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]

   - Добавьте следующий код в конструктор:

         [!code-cpp[NVC_MFCControlLadenDialog#46](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_5.cpp)]

   - Добавьте следующий код деструктора:

         [!code-cpp[NVC_MFCControlLadenDialog#47](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_6.cpp)]

   - Добавьте следующий код, чтобы `OnViewTest` для выполнения функции:

         [!code-cpp[NVC_MFCControlLadenDialog#48](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_7.cpp)]

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Модальные и немодальные диалоговые окна](../mfc/modal-and-modeless-dialog-boxes.md)
