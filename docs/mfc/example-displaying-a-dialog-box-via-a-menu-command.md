---
title: "Пример. Отображение диалогового окна через команду меню | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "диалоговые окна, MFC - библиотека"
  - "примеры [MFC], диалоговые окна"
  - "пункты меню, примеры"
  - "диалоговые окна MFC, отображение"
  - "диалоговые окна MFC, примеры"
  - "модальные диалоговые окна, отображение"
  - "безрежимные диалоговые окна, отображение"
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Пример. Отображение диалогового окна через команду меню
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот раздел содержит процедуры:  
  
-   Отображает модальное диалоговое окно с помощью команды меню.  
  
-   Отображение безрежимное диалоговое окно с помощью команды меню.  
  
 Обе процедуры примера для приложений MFC и будут работать в приложении создается с помощью [Мастер приложений MFC](../Topic/MFC%20Application%20Wizard.md).  
  
 Процедуры используют следующие имена и значения:  
  
|Элемент|Имя или значение|  
|-------------|----------------------|  
|Приложение|DisplayDialog|  
|Команда меню|Команда теста в меню; Идентификатор команды \= ID\_VIEW\_TEST|  
|Диалоговое окно|Диалоговое окно теста; Класс \= CTestDialog; Файл заголовка \= TestDialog.h; Testdlg, ptestdlg \= переменная|  
|Обработчик команды|OnViewTest|  
  
### Отображать модальное диалоговое окно  
  
1.  Создание команды меню; в разделе [Создание меню или пункты меню](../windows/creating-a-menu.md).  
  
2.  Создать диалоговое окно; в разделе [Запуск редактора диалоговых окон](../mfc/creating-a-new-dialog-box.md).  
  
3.  Добавьте класс для диалогового окна.  Дополнительные сведения см. в разделе [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md).  
  
4.  В **Представление классов** выберите класс документа \(CDisplayDialogDoc\).  В поле **Свойства**, нажмите кнопку **События** .  Дважды щелкните идентификатор команды меню \(ID\_VIEW\_TEST\) в левой области окна **Свойства** и выделите **Команда**.  В области справа щелкните стрелку вниз и выберите **\<Add\> OnViewTest**.  
  
     При добавлении команды меню в мейнфрейму приложения MDI, выделите класс приложения \(CDisplayDialogApp\) вместо него.  
  
5.  Добавьте следующее включите формулировку в CDisplayDialogDoc.cpp \(или CDisplayDialogApp.cpp\) после существовать включите формулировки:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
6.  Добавьте следующий код в `OnViewTest` для реализации функциональности.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#43](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_2.cpp)]  
  
### Отображение безрежимное диалоговое окно  
  
1.  Выполните первые 4 шага для отображения модального диалогового окна, за исключением select класс представления \(CDisplayDialogView\) в шаге 4.  
  
2.  Правка DisplayDialogView.h:  
  
    -   Объявите класс диалогового окна перед объявлением первого класса:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#44](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_3.h)]  
  
    -   Объявите указатель в диалоговое окно после раздела открытого атрибутов:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#45](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_4.h)]  
  
3.  Правка DisplayDialogView.cpp:  
  
    -   Добавьте следующее включите формулировку существовать после включения формулировки:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
    -   Добавьте следующий код в конструктор.  
  
         [!code-cpp[NVC_MFCControlLadenDialog#46](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_5.cpp)]  
  
    -   Добавьте следующий код в деструктора:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#47](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_6.cpp)]  
  
    -   Добавьте следующий код в `OnViewTest` для реализации функциональности.  
  
         [!code-cpp[NVC_MFCControlLadenDialog#48](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_7.cpp)]  
  
 Также см. в следующей статье базы знаний:  
  
-   Q251059: HOWTO: Введите имя класса диалогового окна для окна MFC  
  
## См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Модальные и немодальные диалоговые окна](../mfc/modal-and-modeless-dialog-boxes.md)