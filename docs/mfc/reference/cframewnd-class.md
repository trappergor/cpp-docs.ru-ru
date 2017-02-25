---
title: "CFrameWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFrameWnd class"
  - "frame window classes, базовый класс"
  - "frame windows, создание"
  - "однооконный интерфейс (SDI), frame windows"
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональность фреймового окна интерфейса одинарного документа Windows \(SDI\) или перекрывающихся контекстного меню, вместе с элементами управления в окне.  
  
## Синтаксис  
  
```  
class CFrameWnd : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFrameWnd::CFrameWnd](../Topic/CFrameWnd::CFrameWnd.md)|Создает объект `CFrameWnd`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFrameWnd::ActivateFrame](../Topic/CFrameWnd::ActivateFrame.md)|Создает кадр является видимым и доступными пользователям.|  
|[CFrameWnd::BeginModalState](../Topic/CFrameWnd::BeginModalState.md)|Устанавливает фреймовое окно режимному.|  
|[CFrameWnd::Create](../Topic/CFrameWnd::Create.md)|Вызовите для создания и инициализации фреймовое окно Windows, связанное с объектом `CFrameWnd`.|  
|[CFrameWnd::CreateView](../Topic/CFrameWnd::CreateView.md)|Создает представление внутри кадр, который не является производным от `CView`.|  
|[CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md)|Закрепит панель элементов управления.|  
|[CFrameWnd::EnableDocking](../Topic/CFrameWnd::EnableDocking.md)|Разрешает панель элементов управления, который необходимо закрепить.|  
|[CFrameWnd::EndModalState](../Topic/CFrameWnd::EndModalState.md)|Завершает фреймового окна модальное состояние.  Включает все окна монитор заблокированных `BeginModalState`.|  
|[CFrameWnd::FloatControlBar](../Topic/CFrameWnd::FloatControlBar.md)|Располагается панель элементов управления.|  
|[CFrameWnd::GetActiveDocument](../Topic/CFrameWnd::GetActiveDocument.md)|Возвращает активный объект **CDocument**.|  
|[CFrameWnd::GetActiveFrame](../Topic/CFrameWnd::GetActiveFrame.md)|Возвращает активный объект `CFrameWnd`.|  
|[CFrameWnd::GetActiveView](../Topic/CFrameWnd::GetActiveView.md)|Возвращает активный объект `CView`.|  
|[CFrameWnd::GetControlBar](../Topic/CFrameWnd::GetControlBar.md)|Извлекает панель элементов управления.|  
|[CFrameWnd::GetDockState](../Topic/CFrameWnd::GetDockState.md)|Извлекает состояние закрепления фреймового окна.|  
|[CFrameWnd::GetMenuBarState](../Topic/CFrameWnd::GetMenuBarState.md)|Извлекает состояние отображения меню в приложении MFC набору.|  
|[CFrameWnd::GetMenuBarVisibility](../Topic/CFrameWnd::GetMenuBarVisibility.md)|Указывает, является ли функциональности по умолчанию меню в приложении MFC текущего или скрыта или видимой.|  
|[CFrameWnd::GetMessageBar](../Topic/CFrameWnd::GetMessageBar.md)|Возвращает указатель на строку состояния, принадлежащие фреймовому окно.|  
|[CFrameWnd::GetMessageString](../Topic/CFrameWnd::GetMessageString.md)|Получает сообщение, соответствующее идентификатору команды|  
|[CFrameWnd::GetTitle](../Topic/CFrameWnd::GetTitle.md)|Возвращает имя связанной области элементов управления.|  
|[CFrameWnd::InitialUpdateFrame](../Topic/CFrameWnd::InitialUpdateFrame.md)|Вызывает функцию\-член `OnInitialUpdate`, принадлежащие всем представлениям фреймовом окне, которую необходимо вызвать.|  
|[CFrameWnd::InModalState](../Topic/CFrameWnd::InModalState.md)|Возвращает значение, показывающее, является ли фреймовое окно в модальном состоянии.|  
|[CFrameWnd::IsTracking](../Topic/CFrameWnd::IsTracking.md)|Определяет панель если разделитель в настоящее время перемещения.|  
|[CFrameWnd::LoadAccelTable](../Topic/CFrameWnd::LoadAccelTable.md)|Вызов для загрузки таблицы сочетаний клавиш.|  
|[CFrameWnd::LoadBarState](../Topic/CFrameWnd::LoadBarState.md)|Вызов, чтобы извлечь параметры панели элементов управления.|  
|[CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md)|Вызов для динамического создания фреймовое окно из сведений о ресурсах.|  
|[CFrameWnd::NegotiateBorderSpace](../Topic/CFrameWnd::NegotiateBorderSpace.md)|Обсуждается место границы в фреймовом окне.|  
|[CFrameWnd::OnBarCheck](../Topic/CFrameWnd::OnBarCheck.md)|Вызываемого при выполнении действия на панели управления.|  
|[CFrameWnd::OnContextHelp](../Topic/CFrameWnd::OnContextHelp.md)|Справка маркеров SHIFT\+F1 для элементов в\-размещения.|  
|[CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md)|Устанавливает фреймовое главное окно приложения и из режима предварительного просмотра.|  
|[CFrameWnd::OnUpdateControlBarMenu](../Topic/CFrameWnd::OnUpdateControlBarMenu.md)|Вызываемый платформой, если связанное меню обновлено.|  
|[CFrameWnd::RecalcLayout](../Topic/CFrameWnd::RecalcLayout.md)|Изменяет положение панели элементов управления объекта `CFrameWnd`.|  
|[CFrameWnd::SaveBarState](../Topic/CFrameWnd::SaveBarState.md)|Вызов, чтобы сохранить параметры панели элементов управления.|  
|[CFrameWnd::SetActivePreviewView](../Topic/CFrameWnd::SetActivePreviewView.md)|Обозначает указанное представление, чтобы быть активными представлением, богатого предварительного просмотра.|  
|[CFrameWnd::SetActiveView](../Topic/CFrameWnd::SetActiveView.md)|Задает активный объект `CView`.|  
|[CFrameWnd::SetDockState](../Topic/CFrameWnd::SetDockState.md)|Вызов для закрепления фреймовое окно в главном окне.|  
|[CFrameWnd::SetMenuBarState](../Topic/CFrameWnd::SetMenuBarState.md)|Устанавливает состояние отображения меню, которое открывается в приложении MFC для скрытого или текущий.|  
|[CFrameWnd::SetMenuBarVisibility](../Topic/CFrameWnd::SetMenuBarVisibility.md)|Задает расширение функциональности по умолчанию меню в приложении MFC текущего быть или скрывать или видимым.|  
|[CFrameWnd::SetMessageText](../Topic/CFrameWnd::SetMessageText.md)|Устанавливает текст стандартной строки состояния.|  
|[CFrameWnd::SetProgressBarPosition](../Topic/CFrameWnd::SetProgressBarPosition.md)|Задает текущее положение индикатора выполнения для отображаемого на панели задач Windows 7.|  
|[CFrameWnd::SetProgressBarRange](../Topic/CFrameWnd::SetProgressBarRange.md)|Наборы \- для индикатора выполнения Windows 7, отображаемого на панели задач.|  
|[CFrameWnd::SetProgressBarState](../Topic/CFrameWnd::SetProgressBarState.md)|Задает тип и состояние индикатора хода выполнения на кнопке панели задач отображается.|  
|[CFrameWnd::SetTaskbarOverlayIcon](../Topic/CFrameWnd::SetTaskbarOverlayIcon.md)|Перегружен.  Применяет наложение на кнопке панели задач для отображения состояния приложения или уведомление пользователю.|  
|[CFrameWnd::SetTitle](../Topic/CFrameWnd::SetTitle.md)|Задает имя связанной области элементов управления.|  
|[CFrameWnd::ShowControlBar](../Topic/CFrameWnd::ShowControlBar.md)|Вызов для вывода области элементов управления.|  
|[CFrameWnd::ShowOwnedWindows](../Topic/CFrameWnd::ShowOwnedWindows.md)|Отображает все окна, которые являются потомками объекта `CFrameWnd`.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md)|Создает окно клиента для кадра.|  
|[CFrameWnd::OnHideMenuBar](../Topic/CFrameWnd::OnHideMenuBar.md)|Перед меню в приложении MFC с текущим скрывает.|  
|[CFrameWnd::OnShowMenuBar](../Topic/CFrameWnd::OnShowMenuBar.md)|Меню в приложении MFC, вызываемый до текущего.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CFrameWnd::m\_bAutoMenuEnable](../Topic/CFrameWnd::m_bAutoMenuEnable.md)|Элементы управления автоматически включают функции и запрещен для пунктов меню.|  
|[CFrameWnd::rectDefault](../Topic/CFrameWnd::rectDefault.md)|Передайте это статическое `CRect` как параметр создать объект `CFrameWnd` для разрешения Windows для выбора размер и положение окна начальный.|  
  
## Заметки  
 Чтобы создать полезный фреймовое окно приложения, наследуйте класс от `CFrameWnd`.  Добавьте элемент переменные к производному классу для хранения данных, относящийся к приложению.  Реализуйте функции\-члены обработчика сообщений и сопоставление сообщения в производном классе позволяет определить, что происходит, когда сообщения направляются в окно.  
  
 3 Способа построения фреймовое окно:  
  
-   Непосредственно постройте его с помощью [Создание](../Topic/CFrameWnd::Create.md).  
  
-   Непосредственно постройте его с помощью [LoadFrame](../Topic/CFrameWnd::LoadFrame.md).  
  
-   Косвенно выполните его построение с помощью шаблона документа.  
  
 Прежде чем вызывать метод или **Создать** или `LoadFrame` необходимо построить объекте фреймового окна в куче с помощью оператора C\+\+ **новый**.  Перед вызовом **Создать** можно также зарегистрировать класс окна с функцией [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) глобальный, чтобы задать стили значка и класса для кадра.  
  
 Использование функции\-члена **Создать** чтобы передать параметры создания кадра, как непосредственные аргументы.  
  
 `LoadFrame` требуется меньшее число аргументов, чем **Создать**, а вместо этого извлекает большинство значений по умолчанию из ресурсов, включая заголовок кадра, значок таблицы сочетаний клавиш и меню.  `LoadFrame` быть доступны все эти ресурсы должны иметь один и тот же идентификатор ресурсов \(например, **IDR\_MAINFRAME**\).  
  
 Если объект `CFrameWnd` содержащий представления и документов, они созданы неявно платформой, а не напрямую по программиста.  Объект `CDocTemplate` оркеструет создание фрейма, создание представлений и представлений, содержащий соединение в соответствующий документу.  Параметры конструктора `CDocTemplate` определяют `CRuntimeClass` 3 классов, которые участвуют \(документ, кадр и представление\).  Объект `CRuntimeClass` используется платформой для динамического создания новых определенный пользователем кадров \(например, с помощью команды файла новой или нескольких команд окне интерфейса MDI новую\).  
  
 Класс фреймового окна, производный от `CFrameWnd` должен быть объявлен с `DECLARE_DYNCREATE`, вышеуказанный механизм `RUNTIME_CLASS` работал правильно.  
  
 `CFrameWnd` содержит реализации по умолчанию выполнять следующие функции главного окна в типичном приложении Windows:  
  
-   Отслеживает представления фреймовое окно `CFrameWnd` а в настоящий момент активно, которое не зависит от активного окна Windows или текущего фокуса ввода.  Если кадр, которая активное представление уведомлено путем вызова `CView::OnActivateView`.  
  
-   Сообщения команды и многие часто сообщений кадр\- уведомления, включая те обрабатываемые `OnSetFocus`, `OnHScroll` и функции `OnVScroll``CWnd`, делегированы фреймовым окном `CFrameWnd` для текущего активного представления.  
  
-   Активное в данный момент представление \(или активное в данный момент фреймовое окно дочернего элемента интерфейса MDI в случае с кадра MDI\) может определить заголовок фреймового окна.  Эта функция может быть отключена, чтобы отключить стиль **FWS\_ADDTOTITLE** сдержанная фреймового окна.  
  
-   Фреймовое окно `CFrameWnd` управляет расположение панелей элементов управления, представлений и других дочерних окон в клиентской области фреймового окна.  Фреймовое окно также выполняет обновление времени простоя панели кнопок панели инструментов и других элементов управления.  Фреймовое окно `CFrameWnd` также имеет реализации по умолчанию команд для переключения на и с панели инструментов и строки состояния.  
  
-   Фреймовое окно `CFrameWnd` управляет главном меню.  Если контекстное меню меню отображается, фреймовое окно использует механизм **UPDATE\_COMMAND\_UI**, чтобы определить, какие элементы меню должны быть включены, отключены или проверены.  Когда пользователь выбирает пункт меню, фреймовое окно обновляет строку состояния со строкой сообщения для данной команды.  
  
-   Фреймовое окно `CFrameWnd` содержит дополнительную таблицу сочетаний клавиш, которая автоматически преобразует сочетания клавиш клавиатуры.  
  
-   Фреймовое окно `CFrameWnd` имеет необязательный идентификатор справки задается с `LoadFrame`, используемое для контекстной справки.  Фреймовое окно главный модуль взаимодействия semimodal как режимы состояний контекстной справки \(SHIFT\+F1\) и предварительного просмотра.  
  
-   Фреймовое окно `CFrameWnd` перетащенный открытии файла из файлового менеджеров и удаленный в фреймовом окне.  Если расширение файла зарегистрирован и сопоставлено с приложением, фреймовое окно отвечает на динамический обмена данными \(запрос открытого DDE\), происходит, когда пользователь открывает файл данных в файловом менеджере или при называется функция **ShellExecute** Windows.  
  
-   Если фреймовое окно главное окно приложения \(то есть `CWinThread::m_pMainWnd`\), когда пользователь закрывает приложение, фреймовое окно предлагает пользователю сохранить все измененные документов \(для `OnClose` и `OnQueryEndSession`\).  
  
-   Если фреймовое окно главное окно приложения, фреймовое окно контекст для выполнения WinHelp.  Закрытие фреймовое окно отключает WINHELP.EXE если оно было начать справки для данного приложения.  
  
 Не используйте оператор C\+\+ **удалить** для уничтожения фреймовое окно.  Взамен рекомендуется использовать `CWnd::DestroyWindow`.  Реализация `CFrameWnd``PostNcDestroy` удаляет объект C\+\+, если окно будет удалено.  Когда пользователь закрывает фреймовое окно, по умолчанию будут вызывать `DestroyWindow` обработчика `OnClose`.  
  
 Дополнительные сведения о `CFrameWnd` см. в разделе [фреймовые окна](../../mfc/frame-windows.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CFrameWnd`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [CMDIFrameWnd Class](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)   
 [CView Class](../Topic/CView%20Class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CRuntimeClass Structure](../Topic/CRuntimeClass%20Structure.md)