---
title: "Пример: Отображение диалогового окна через команду меню | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e2715e1b64c1565d122f6eec012a8a33c2525ac9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>Пример. Отображение диалогового окна через команду меню
В этом разделе содержатся процедуры для:  
  
-   Отображение модального диалогового окна через команду меню.  
  
-   Отображение немодального диалогового окна через команду меню.  
  
 Обе процедуры образца предназначены для приложений MFC и будет работать в приложении, создать с [мастер приложений MFC](../mfc/reference/mfc-application-wizard.md).  
  
 В процедурах используется следующие имена и значения:  
  
|Элемент|Имя или значение|  
|----------|-------------------|  
|Приложение|DisplayDialog|  
|Команда меню|Тестирование команды в меню «Вид»; ИД команды = ID_VIEW_TEST|  
|Диалоговое окно|Диалоговое окно теста; Класс = CTestDialog; Файл заголовка = TestDialog.h; Переменная = testdlg ptestdlg|  
|Обработчик команд|OnViewTest|  
  
### <a name="to-display-a-modal-dialog-box"></a>Для отображения модального диалогового окна  
  
1.  Создать команду меню; в разделе [Создание меню или пункты меню](../windows/creating-a-menu.md).  
  
2.  Создать диалоговое окно. в разделе [запуск редактора диалоговых окон](../windows/creating-a-new-dialog-box.md).  
  
3.  Добавление класса для диалогового окна. В разделе [Добавление класса](../ide/adding-a-class-visual-cpp.md) для получения дополнительной информации.  
  
4.  В **представление классов**, выберите класс документа (CDisplayDialogDoc). В окне **Свойства** нажмите кнопку **События** . Идентификатор команды меню (ID_VIEW_TEST) в левой области дважды щелкните **свойства** и выберите **команда**. В области справа щелкните стрелку вниз и выберите  **\<Добавить > OnViewTest**.  
  
     Если вы добавили команду меню мэйнфрейма MDI-приложения, выберите класс приложения (CDisplayDialogApp).  
  
5.  Добавьте следующие включаемых инструкции CDisplayDialogDoc.cpp (или CDisplayDialogApp.cpp) после существующего включают в себя инструкции:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
6.  Добавьте следующий код в `OnViewTest` для выполнения функции:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#43](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_2.cpp)]  
  
### <a name="to-display-a-modeless-dialog-box"></a>Чтобы отобразить немодального диалогового окна  
  
1.  Первые четыре действий для отображения модальным диалоговым окном, за исключением того, выберите класс представления (CDisplayDialogView) на шаге 4.  
  
2.  Изменение DisplayDialogView.h:  
  
    -   Объявите класс диалогового окна поле, предшествующие объявлению первого класса:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#44](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_3.h)]  
  
    -   Объявите указатель на окно после раздел общих атрибутов:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#45](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_4.h)]  
  
3.  Изменение DisplayDialogView.cpp:  
  
    -   Добавьте следующий оператор #include после существующего включают в себя инструкции:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
    -   Добавьте следующий код в конструктор:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#46](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_5.cpp)]  
  
    -   Деструктор добавьте следующий код:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#47](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_6.cpp)]  
  
    -   Добавьте следующий код в `OnViewTest` для выполнения функции:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#48](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_7.cpp)]  
  
 Кроме того см. в следующей статье базы знаний:  
  
-   Q251059: Практическое руководство: введите собственное имя класса окна для диалоговом окне MFC  
  
## <a name="see-also"></a>См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Модальные и немодальные диалоговые окна](../mfc/modal-and-modeless-dialog-boxes.md)

