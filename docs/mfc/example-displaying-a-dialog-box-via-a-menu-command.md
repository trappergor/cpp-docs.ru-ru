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
ms.openlocfilehash: 1e730125e47609f0bf87814b32962336cb752b04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173311"
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

   ```cpp
   #include "TestDialog.h"
   ```

1. Добавьте следующий код, чтобы `OnViewTest` для выполнения функции:

   ```cpp
   CTestDialog testdlg;
   testdlg.DoModal();  
   ```

### <a name="to-display-a-modeless-dialog-box"></a>Для отображения немодального диалогового окна

1. Выполните первые четыре шага для отображения модальное диалоговое окно, за исключением того, выберите класс представления (CDisplayDialogView) на шаге 4.

1. Измените DisplayDialogView.h:

   - Объявите предшествующей первого класса объявлению класса диалогового окна:

   ```cpp
   class CTestDialog;
   ```

   - Объявите указатель на окно после открытого раздела «Attributes»:

   ```cpp
   CTestDialog* m_pTestDlg;
   ```

1. Измените DisplayDialogView.cpp:

   - Добавьте следующие инструкции после существующего включают инструкции:

   ```cpp
   #include "TestDialog.h"
   ```

   - Добавьте следующий код в конструктор:

   ```cpp
   m_pTestDlg = NULL;
   ```

   - Добавьте следующий код деструктора:

   ```cpp
   delete m_pTestDlg;
   ```

   - Добавьте следующий код, чтобы `OnViewTest` для выполнения функции:

   ```cpp
   if (NULL == m_pTestDlg)
   {
      m_pTestDlg = new CTestDialog(this);
      m_pTestDlg->Create(CTestDialog::IDD, this);
   }
   m_pTestDlg->ShowWindow(SW_SHOW); 
   ```

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Модальные и немодальные диалоговые окна](../mfc/modal-and-modeless-dialog-boxes.md)
