---
title: "CWindow Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CWindow"
  - "ATL::CWindow"
  - "CWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindow class"
ms.assetid: fefa00c8-f053-4bcf-87bc-dc84f5386683
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CWindow Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для работы с окном.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CWindow  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWindow::CWindow](../Topic/CWindow::CWindow.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWindow::ArrangeIconicWindows](../Topic/CWindow::ArrangeIconicWindows.md)|Свернутые упорядочивает все дочерние окна.|  
|[CWindow::Attach](../Topic/CWindow::Attach.md)|Вложение окно к объекту `CWindow`.|  
|[CWindow::BeginPaint](../Topic/CWindow::BeginPaint.md)|Подготавливает окно для рисования.|  
|[CWindow::BringWindowToTop](../Topic/CWindow::BringWindowToTop.md)|Перемещение окно в верхней части заказа Z.|  
|[CWindow::CenterWindow](../Topic/CWindow::CenterWindow.md)|Выравнивает поле с заданным окна.|  
|[CWindow::ChangeClipboardChain](../Topic/CWindow::ChangeClipboardChain.md)|Удаляет окно из цепочки средств просмотра буфера обмена.|  
|[CWindow::CheckDlgButton](../Topic/CWindow::CheckDlgButton.md)|Изменяет состояние проверки указанной кнопки.|  
|[CWindow::CheckRadioButton](../Topic/CWindow::CheckRadioButton.md)|Проверяет заданный переключатель.|  
|[CWindow::ChildWindowFromPoint](../Topic/CWindow::ChildWindowFromPoint.md)|Возвращает дочернее окно, содержащий указанную точку.|  
|[CWindow::ChildWindowFromPointEx](../Topic/CWindow::ChildWindowFromPointEx.md)|Извлекает указанный тип дочернего окна, содержащий указанную точку.|  
|[CWindow::ClientToScreen](../Topic/CWindow::ClientToScreen.md)|Выполняет преобразование клиентских координат для экранировать координаты.|  
|[CWindow::Create](../Topic/CWindow::Create.md)|Создается окно.|  
|[CWindow::CreateCaret](../Topic/CWindow::CreateCaret.md)|Создает новую фигуру для системного курсора.|  
|[CWindow::CreateGrayCaret](../Topic/CWindow::CreateGrayCaret.md)|Создает серый прямоугольник для системного курсора.|  
|[CWindow::CreateSolidCaret](../Topic/CWindow::CreateSolidCaret.md)|Создает сплошной прямоугольник для системного курсора.|  
|[CWindow::DeferWindowPos](../Topic/CWindow::DeferWindowPos.md)|Обновляет заданная структура множественн\-окно\- позиции для указанного окна.|  
|[CWindow::DestroyWindow](../Topic/CWindow::DestroyWindow.md)|Уничтожает окно, связанное с объектом `CWindow`.|  
|[CWindow::Detach](../Topic/CWindow::Detach.md)|Наконец удаляет окно из объекта `CWindow`.|  
|[CWindow::DlgDirList](../Topic/CWindow::DlgDirList.md)|Заполняет список всех файлов с именами соответствующих указанному пути или имени файла.|  
|[CWindow::DlgDirListComboBox](../Topic/CWindow::DlgDirListComboBox.md)|Заполняет поле со списком всех файлов с именами соответствующих указанному пути или имени файла.|  
|[CWindow::DlgDirSelect](../Topic/CWindow::DlgDirSelect.md)|Извлекает текущее выделение из списка.|  
|[CWindow::DlgDirSelectComboBox](../Topic/CWindow::DlgDirSelectComboBox.md)|Извлекает текущее выделение из поля со списком.|  
|[CWindow::DragAcceptFiles](../Topic/CWindow::DragAcceptFiles.md)|Регистрирует, принимает ли окно перетащенные файлы.|  
|[CWindow::DrawMenuBar](../Topic/CWindow::DrawMenuBar.md)|Перерисовывает строка меню окно.|  
|[CWindow::EnableScrollBar](../Topic/CWindow::EnableScrollBar.md)|Включение или отключение стрелки полосы прокрутки.|  
|[CWindow::EnableWindow](../Topic/CWindow::EnableWindow.md)|Позволяет включить или отключить вход.|  
|[CWindow::EndPaint](../Topic/CWindow::EndPaint.md)|Помечает конец рисования.|  
|[CWindow::FlashWindow](../Topic/CWindow::FlashWindow.md)|Проблескивает окно раз.|  
|[CWindow::GetClientRect](../Topic/CWindow::GetClientRect.md)|Получает координаты клиентской области.|  
|[CWindow::GetDC](../Topic/CWindow::GetDC.md)|Получает контекст устройства для клиентской области.|  
|[CWindow::GetDCEx](../Topic/CWindow::GetDCEx.md)|Получает контекст устройства для клиентской области и параметры отсечения.|  
|[CWindow::GetDescendantWindow](../Topic/CWindow::GetDescendantWindow.md)|Извлекает заданное окно потомков.|  
|[CWindow::GetDlgControl](../Topic/CWindow::GetDlgControl.md)|Извлекает интерфейс на элементе управления.|  
|[CWindow::GetDlgCtrlID](../Topic/CWindow::GetDlgCtrlID.md)|Извлекает идентификатор окна \(для дочерних окон\).|  
|[CWindow::GetDlgHost](../Topic/CWindow::GetDlgHost.md)|Извлекает указатель на интерфейс размещения элемента управления в контейнере библиотеки ATL.|  
|[CWindow::GetDlgItem](../Topic/CWindow::GetDlgItem.md)|Извлекает указанное дочернее окно.|  
|[CWindow::GetDlgItemInt](../Topic/CWindow::GetDlgItemInt.md)|Смещает текст элемента управления в целое число.|  
|[CWindow::GetDlgItemText](../Topic/CWindow::GetDlgItemText.md)|Извлекает текст элемента управления.|  
|[CWindow::GetExStyle](../Topic/CWindow::GetExStyle.md)|Получает расширенные стили окна.|  
|[CWindow::GetFont](../Topic/CWindow::GetFont.md)|Получает шрифт окна текущий.|  
|[CWindow::GetHotKey](../Topic/CWindow::GetHotKey.md)|Определяет горячую клавиши, связанную с окном.|  
|[CWindow::GetIcon](../Topic/CWindow::GetIcon.md)|Извлекает большой или маленький значок окна.|  
|[CWindow::GetLastActivePopup](../Topic/CWindow::GetLastActivePopup.md)|Возвращает последнее активное всплывающее окно.|  
|[CWindow::GetMenu](../Topic/CWindow::GetMenu.md)|Извлекает меню окно.|  
|[CWindow::GetNextDlgGroupItem](../Topic/CWindow::GetNextDlgGroupItem.md)|Извлекает предыдущий либо следующий элемент управления в пределах группы в составе элементы управления.|  
|[CWindow::GetNextDlgTabItem](../Topic/CWindow::GetNextDlgTabItem.md)|Извлекает предыдущий либо следующий элемент управления, имеющих стиль **WS\_TABSTOP**.|  
|[CWindow::GetParent](../Topic/CWindow::GetParent.md)|Извлекает немедленное родительское окно.|  
|[CWindow::GetScrollInfo](../Topic/CWindow::GetScrollInfo.md)|Получает параметры для полосы прокрутки.|  
|[CWindow::GetScrollPos](../Topic/CWindow::GetScrollPos.md)|Получает положение ползунка полосы прокрутки.|  
|[CWindow::GetScrollRange](../Topic/CWindow::GetScrollRange.md)|Извлекает в диапазоне для полосы прокрутки.|  
|[CWindow::GetStyle](../Topic/CWindow::GetStyle.md)|Получает стили окна.|  
|[CWindow::GetSystemMenu](../Topic/CWindow::GetSystemMenu.md)|Создает копию меню системы для изменения.|  
|[CWindow::GetTopLevelParent](../Topic/CWindow::GetTopLevelParent.md)|Извлекает окно верхнего уровня родительского объекта или владелец.|  
|[CWindow::GetTopLevelWindow](../Topic/CWindow::GetTopLevelWindow.md)|Извлекает окно верхнего уровня владелец.|  
|[CWindow::GetTopWindow](../Topic/CWindow::GetTopWindow.md)|Возвращает дочернее окно верхнего уровня.|  
|[CWindow::GetUpdateRect](../Topic/CWindow::GetUpdateRect.md)|Возвращает координаты прямоугольника, который полностью наименьшего ограничивающий область обновления.|  
|[CWindow::GetUpdateRgn](../Topic/CWindow::GetUpdateRgn.md)|Извлекает область обновления и копирует их в заданной области.|  
|[CWindow::GetWindow](../Topic/CWindow::GetWindow.md)|Извлекает заданное окно.|  
|[CWindow::GetWindowContextHelpId](../Topic/CWindow::GetWindowContextHelpId.md)|Извлекает идентификатор контекста справки окна.|  
|[CWindow::GetWindowDC](../Topic/CWindow::GetWindowDC.md)|Получает контекст устройства для всего окна.|  
|[CWindow::GetWindowLong](../Topic/CWindow::GetWindowLong.md)|Извлекает 32 разрядное значение с заданным смещением в дополнительную память окна.|  
|[CWindow::GetWindowLongPtr](../Topic/CWindow::GetWindowLongPtr.md)|Извлекает сведения о конкретном окне, включая значение с заданным смещением в дополнительную память окна.|  
|[CWindow::GetWindowPlacement](../Topic/CWindow::GetWindowPlacement.md)|Извлекает состояние и положения показать.|  
|[CWindow::GetWindowProcessID](../Topic/CWindow::GetWindowProcessID.md)|Извлекает идентификатор процесса, который создал окно.|  
|[CWindow::GetWindowRect](../Topic/CWindow::GetWindowRect.md)|Получает размеры окна ограничивающего.|  
|[CWindow::GetWindowRgn](../Topic/CWindow::GetWindowRgn.md)|Возвращает копию области окна.|  
|[CWindow::GetWindowText](../Topic/CWindow::GetWindowText.md)|Извлекает текст окна.|  
|[CWindow::GetWindowTextLength](../Topic/CWindow::GetWindowTextLength.md)|Извлекает длина текста окна.|  
|[CWindow::GetWindowThreadID](../Topic/CWindow::GetWindowThreadID.md)|Извлекает идентификатор потока, который создал указанное окно.|  
|[CWindow::GetWindowWord](../Topic/CWindow::GetWindowWord.md)|Извлекает 16 разрядное значение с заданным смещением в дополнительную память окна.|  
|[CWindow::GotoDlgCtrl](../Topic/CWindow::GotoDlgCtrl.md)|Устанавливает фокус клавиатуры на элемент управления в диалоговом окне.|  
|[CWindow::HideCaret](../Topic/CWindow::HideCaret.md)|Скрывает системный курсор.|  
|[CWindow::HiliteMenuItem](../Topic/CWindow::HiliteMenuItem.md)|Главное или удалить подсветку пункта меню верхнего уровня.|  
|[CWindow::Invalidate](../Topic/CWindow::Invalidate.md)|Делает недействительной всю клиентскую область.|  
|[CWindow::InvalidateRect](../Topic/CWindow::InvalidateRect.md)|Делает недействительной клиентскую область в пределах заданного прямоугольника.|  
|[CWindow::InvalidateRgn](../Topic/CWindow::InvalidateRgn.md)|Делает недействительной клиентскую область внутри заданной области.|  
|[CWindow::IsChild](../Topic/CWindow::IsChild.md)|Определяет, является ли указанное дочернее окно, окно.|  
|[CWindow::IsDialogMessage](../Topic/CWindow::IsDialogMessage.md)|Указывает, предназначено ли сообщение для указанного диалогового окна.|  
|[CWindow::IsDlgButtonChecked](../Topic/CWindow::IsDlgButtonChecked.md)|Указывает состояние проверки кнопки.|  
|[CWindow::IsIconic](../Topic/CWindow::IsIconic.md)|Определяет свернуто ли окно.|  
|[CWindow::IsParentDialog](../Topic/CWindow::IsParentDialog.md)|Определяет, если родительское окно элемента управления диалоговое окно.|  
|[CWindow::IsWindow](../Topic/CWindow::IsWindow.md)|Определяет, указывает ли заданный дескриптор окна существующее окно.|  
|[CWindow::IsWindowEnabled](../Topic/CWindow::IsWindowEnabled.md)|Определяет, включено ли поле для ввода.|  
|[CWindow::IsWindowUnicode](../Topic/CWindow::IsWindowUnicode.md)|Определяет, является ли указанное окно собственное окно в юникоде.|  
|[CWindow::IsWindowVisible](../Topic/CWindow::IsWindowVisible.md)|Указывает состояние видимости окна.|  
|[CWindow::IsZoomed](../Topic/CWindow::IsZoomed.md)|Определяет развернуто ли окно.|  
|[CWindow::KillTimer](../Topic/CWindow::KillTimer.md)|Удаляет событие таймера.|  
|[CWindow::LockWindowUpdate](../Topic/CWindow::LockWindowUpdate.md)|Запрещает или включает документ в окне.|  
|[CWindow::MapWindowPoints](../Topic/CWindow::MapWindowPoints.md)|Преобразует набор точек из окна координированной место в пространстве координат другого окна.|  
|[CWindow::MessageBox](../Topic/CWindow::MessageBox.md)|Отображает окно сообщения.|  
|[CWindow::ModifyStyle](../Topic/CWindow::ModifyStyle.md)|Изменение стилей окна.|  
|[CWindow::ModifyStyleEx](../Topic/CWindow::ModifyStyleEx.md)|Изменить расширенные стили окна.|  
|[CWindow::MoveWindow](../Topic/CWindow::MoveWindow.md)|Изменяет размер и положение окна.|  
|[CWindow::NextDlgCtrl](../Topic/CWindow::NextDlgCtrl.md)|Устанавливает фокус ввода к следующему элементу управления в диалоговом окне.|  
|[CWindow::OpenClipboard](../Topic/CWindow::OpenClipboard.md)|Открывает буфер обмена.|  
|[CWindow::PostMessage](../Topic/CWindow::PostMessage.md)|Задает сообщение в очереди сообщений, связанной с потоком, который создал окно.  Return, не дожидаясь поток для обработки сообщения.|  
|[CWindow::PrevDlgCtrl](../Topic/CWindow::PrevDlgCtrl.md)|Устанавливает фокус ввода к предыдущему элементу управления в диалоговом окне.|  
|[CWindow::Print](../Topic/CWindow::Print.md)|Запросы, которые были нарисована окно в указанном контексте устройства.|  
|[CWindow::PrintClient](../Topic/CWindow::PrintClient.md)|Запросы, которые были нарисована клиентская область окна в указанном контексте устройства.|  
|[CWindow::RedrawWindow](../Topic/CWindow::RedrawWindow.md)|Обновляет указанный прямоугольник или область в клиентской области.|  
|[CWindow::ReleaseDC](../Topic/CWindow::ReleaseDC.md)|Освобождает контекст устройства.|  
|[CWindow::ResizeClient](../Topic/CWindow::ResizeClient.md)|Изменяет размер окна.|  
|[CWindow::ScreenToClient](../Topic/CWindow::ScreenToClient.md)|Экранные координаты новообращенных к клиентским координатам.|  
|[CWindow::ScrollWindow](../Topic/CWindow::ScrollWindow.md)|Прокручивает конкретной клиентской области.|  
|[CWindow::ScrollWindowEx](../Topic/CWindow::ScrollWindowEx.md)|Прокручивает указанная в клиентскую область с дополнительными функциями.|  
|[CWindow::SendDlgItemMessage](../Topic/CWindow::SendDlgItemMessage.md)|Отправляет сообщение в элемент управления.|  
|[CWindow::SendMessage](../Topic/CWindow::SendMessage.md)|Отправляет сообщение в окне и не возвращает до тех пор, пока процедура окна не будет обработки сообщения.|  
|[CWindow::SendMessageToDescendants](../Topic/CWindow::SendMessageToDescendants.md)|Отправляет сообщение с указанным окна потомков.|  
|[CWindow::SendNotifyMessage](../Topic/CWindow::SendNotifyMessage.md)|Отправляет сообщение в окно.  Если окно было создано вызывающим потоком, то `SendNotifyMessage` не возвращает до тех пор, пока процедура окна не будет обработки сообщения.  В противном случае возвращается немедленно.|  
|[CWindow::SetActiveWindow](../Topic/CWindow::SetActiveWindow.md)|Активировать окно.|  
|[CWindow::SetCapture](../Topic/CWindow::SetCapture.md)|Отправляет все последующие ввода мыши в окне.|  
|[CWindow::SetClipboardViewer](../Topic/CWindow::SetClipboardViewer.md)|Добавляет поле в цепочке средства просмотра буфера обмена.|  
|[CWindow::SetDlgCtrlID](../Topic/CWindow::SetDlgCtrlID.md)|Изменяет идентификатор окна.|  
|[CWindow::SetDlgItemInt](../Topic/CWindow::SetDlgItemInt.md)|Изменяет текст элемента управления в строковое представление значения целого числа.|  
|[CWindow::SetDlgItemText](../Topic/CWindow::SetDlgItemText.md)|Изменяет текст элемента управления.|  
|[CWindow::SetFocus](../Topic/CWindow::SetFocus.md)|Устанавливает фокус на окно.|  
|[CWindow::SetFont](../Topic/CWindow::SetFont.md)|Изменяет шрифт окна текущий.|  
|[CWindow::SetHotKey](../Topic/CWindow::SetHotKey.md)|Связывает горячая клавиша с окном.|  
|[CWindow::SetIcon](../Topic/CWindow::SetIcon.md)|Изменяет значок окна большой или маленький.|  
|[CWindow::SetMenu](../Topic/CWindow::SetMenu.md)|Изменяет текущее меню окно.|  
|[CWindow::SetParent](../Topic/CWindow::SetParent.md)|Изменяет родительское окно.|  
|[CWindow::SetRedraw](../Topic/CWindow::SetRedraw.md)|Задает или снимите клиринги пометить перерисовывает себя.|  
|[CWindow::SetScrollInfo](../Topic/CWindow::SetScrollInfo.md)|Устанавливает параметры для полосы прокрутки.|  
|[CWindow::SetScrollPos](../Topic/CWindow::SetScrollPos.md)|Изменяет положение ползунка полосы прокрутки.|  
|[CWindow::SetScrollRange](../Topic/CWindow::SetScrollRange.md)|Изменяется в диапазоне для полосы прокрутки.|  
|[CWindow::SetTimer](../Topic/CWindow::SetTimer.md)|Создает событие таймера.|  
|[CWindow::SetWindowContextHelpId](../Topic/CWindow::SetWindowContextHelpId.md)|Задает идентификатор контекста справки окна.|  
|[CWindow::SetWindowLong](../Topic/CWindow::SetWindowLong.md)|Устанавливает 32 на указанное смещение в разрядное значение дополнительную память окна.|  
|[CWindow::SetWindowLongPtr](../Topic/CWindow::SetWindowLongPtr.md)|Изменяется атрибут указанного окна, а также устанавливает значение дополнительного на указанное смещение в памяти окна.|  
|[CWindow::SetWindowPlacement](../Topic/CWindow::SetWindowPlacement.md)|Устанавливает состояние и положения показать.|  
|[CWindow::SetWindowPos](../Topic/CWindow::SetWindowPos.md)|Устанавливает размер, положения и порядок Z.|  
|[CWindow::SetWindowRgn](../Topic/CWindow::SetWindowRgn.md)|Задает область окна.|  
|[CWindow::SetWindowText](../Topic/CWindow::SetWindowText.md)|Изменяет текст окна.|  
|[CWindow::SetWindowWord](../Topic/CWindow::SetWindowWord.md)|Устанавливает 16 на указанное смещение в разрядное значение дополнительную память окна.|  
|[CWindow::ShowCaret](../Topic/CWindow::ShowCaret.md)|Обозначает системный курсор.|  
|[CWindow::ShowOwnedPopups](../Topic/CWindow::ShowOwnedPopups.md)|Скрывать или отображать всплывающие окна, принадлежащие окном.|  
|[CWindow::ShowScrollBar](../Topic/CWindow::ShowScrollBar.md)|Показать или скрывает полоса прокрутки.|  
|[CWindow::ShowWindow](../Topic/CWindow::ShowWindow.md)|Показать задает состояние окна.|  
|[CWindow::ShowWindowAsync](../Topic/CWindow::ShowWindowAsync.md)|Задает состояние окна показать созданного другим потоком.|  
|[CWindow::UpdateWindow](../Topic/CWindow::UpdateWindow.md)|Обновляет клиентскую область.|  
|[CWindow::ValidateRect](../Topic/CWindow::ValidateRect.md)|Проверяет клиентскую область в пределах заданного прямоугольника.|  
|[CWindow::ValidateRgn](../Topic/CWindow::ValidateRgn.md)|Проверяет клиентскую область внутри заданной области.|  
|[CWindow::WinHelp](../Topic/CWindow::WinHelp.md)|Запуск справки Windows.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWindow::operator HWND](../Topic/CWindow::operator%20HWND.md)|Преобразует объект `CWindow` к `HWND`.|  
|[CWindow::operator \=](../Topic/CWindow::operator%20=.md)|Присвоит `HWND` к объекту `CWindow`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CWindow::m\_hWnd](../Topic/CWindow::m_hWnd.md)|Дескриптор окна, связанный с объектом `CWindow`.|  
|[CWindow::rcDefault](../Topic/CWindow::rcDefault.md)|Содержит размеры окна по умолчанию.|  
  
## Заметки  
 `CWindow` предоставляет основные функциональные возможности для управления окно библиотеки ATL.  Многие методы `CWindow` просто создают программу\-оболочку одно из функций API Win32.  Например, сравните заполнители для `CWindow::ShowWindow` и `ShowWindow`:  
  
|Метод CWindow|Функция Win32|  
|-------------------|-------------------|  
|**BOOL ShowWindow\( int**  `nCmdShow` **\);**|**BOOL ShowWindow\( HWND**  `hWnd` **, int**  `nCmdShow` **\);**|  
  
 `CWindow::ShowWindow` вызывает функцию Win32 `ShowWindow` путем передачи `CWindow::m_hWnd` как первый параметр.  Каждый метод `CWindow`, непосредственно программу\-оболочку создает функцию Win32 передает элемента `m_hWnd`; поэтому многие из документации `CWindow` ссылался на [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Не каждая функция related окно\- Win32 создает программу\-оболочкуа `CWindow` и использованими не программы\-оболочками каждого метода `CWindow` функция Win32.  
  
 `CWindow::m_hWnd` хранит `HWND`, который определяет окно.  `HWND` присоединяется к конкретному объекту, когда:  
  
-   Укажите `HWND` в конструкторе `CWindow`.  
  
-   Вызов метода `CWindow::Attach`.  
  
-   Используйте **operator \=**`CWindow`.  
  
-   Создайте или подкласс окно с помощью одного из следующих классов, унаследованным от `CWindow`:  
  
     [CWindowImpl](../Topic/CWindowImpl%20Class.md) позволяет создать новое окно или подкласс существующее окно.  
  
     [CContainedWindow](../Topic/CContainedWindowT%20Class.md) реализует окно, содержащихся в другой объект.  Можно создать новое окно или подкласс существующее окно.  
  
     [CDialogImpl](../Topic/CDialogImpl%20Class.md) позволяет создать или режимного безрежимное диалоговое окно.  
  
 Дополнительные сведения об окнах см. в разделе [Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) и последующие в подразделах [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Дополнительные сведения об использовании окон в библиотеке ATL см. в статье [Классы окна библиотеки ATL](../Topic/ATL%20Window%20Classes.md).  
  
## Требования  
 **Header:**  atlwin.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)