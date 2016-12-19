---
title: "CSplitterWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSplitterWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSplitterWnd class"
  - "dynamic splitter windows"
  - "несколько представлений"
  - "окна разделителей"
  - "static splitter windows"
  - "представления, несколько в одном окне"
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSplitterWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности окна разделитель, окно, которое содержит несколько панелей.  
  
## Синтаксис  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSplitterWnd::CSplitterWnd](../Topic/CSplitterWnd::CSplitterWnd.md)|Вызов метода для создания объекта `CSplitterWnd`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSplitterWnd::ActivateNext](../Topic/CSplitterWnd::ActivateNext.md)|Выполняет следующую команду для области или области.|  
|[CSplitterWnd::CanActivateNext](../Topic/CSplitterWnd::CanActivateNext.md)|Проверяет, если следующая команда области или области обратно в данный момент возможна.|  
|[CSplitterWnd::Create](../Topic/CSplitterWnd::Create.md)|Вызов для создания динамического окно\-разделитель и вложить его к объекту `CSplitterWnd`.|  
|[CSplitterWnd::CreateScrollBarCtrl](../Topic/CSplitterWnd::CreateScrollBarCtrl.md)|Создает общую элемент управления "полоса прокрутки".|  
|[CSplitterWnd::CreateStatic](../Topic/CSplitterWnd::CreateStatic.md)|Вызов, чтобы создать статическое окно\-разделитель и вложить его к объекту `CSplitterWnd`.|  
|[CSplitterWnd::CreateView](../Topic/CSplitterWnd::CreateView.md)|Вызов метода для создания области в поле разделитель.|  
|[CSplitterWnd::DeleteColumn](../Topic/CSplitterWnd::DeleteColumn.md)|Удаляет столбец из окна разделителя.|  
|[CSplitterWnd::DeleteRow](../Topic/CSplitterWnd::DeleteRow.md)|Удаляет строку из окна разделителя.|  
|[CSplitterWnd::DeleteView](../Topic/CSplitterWnd::DeleteView.md)|Удаляет представление из окна разделителя.|  
|[CSplitterWnd::DoKeyboardSplit](../Topic/CSplitterWnd::DoKeyboardSplit.md)|Выполняет команду разбиения клавиатуры, обычно окна "разбиение".|  
|[CSplitterWnd::DoScroll](../Topic/CSplitterWnd::DoScroll.md)|Выполняет прокрутку синхронизировал окон разбиения.|  
|[CSplitterWnd::DoScrollBy](../Topic/CSplitterWnd::DoScrollBy.md)|Прокручивает разбивается окна заданным количеством точек.|  
|[CSplitterWnd::GetActivePane](../Topic/CSplitterWnd::GetActivePane.md)|Задает активную область фокуса или из активного представления во фрейме.|  
|[CSplitterWnd::GetColumnCount](../Topic/CSplitterWnd::GetColumnCount.md)|Возвращает текущее количество столбцов панели.|  
|[CSplitterWnd::GetColumnInfo](../Topic/CSplitterWnd::GetColumnInfo.md)|Возвращает сведения об указанном столбце.|  
|[CSplitterWnd::GetPane](../Topic/CSplitterWnd::GetPane.md)|Возвращает панель, в указанных строке и столбце.|  
|[CSplitterWnd::GetRowCount](../Topic/CSplitterWnd::GetRowCount.md)|Возвращает текущее количество строк панели.|  
|[CSplitterWnd::GetRowInfo](../Topic/CSplitterWnd::GetRowInfo.md)|Возвращает сведения об указанной строке.|  
|[CSplitterWnd::GetScrollStyle](../Topic/CSplitterWnd::GetScrollStyle.md)|Возвращает общий стиль полосы прокрутки.|  
|[CSplitterWnd::IdFromRowCol](../Topic/CSplitterWnd::IdFromRowCol.md)|Возвращает идентификатор дочернего окна области в указанных строке и столбце.|  
|[CSplitterWnd::IsChildPane](../Topic/CSplitterWnd::IsChildPane.md)|Вызов, чтобы определить, является ли окно в данный момент панель дочернего элемента этого окна разделителя.|  
|[CSplitterWnd::IsTracking](../Topic/CSplitterWnd::IsTracking.md)|Определяет панель если разделитель в настоящее время перемещения.|  
|[CSplitterWnd::RecalcLayout](../Topic/CSplitterWnd::RecalcLayout.md)|Вызов для повторного отображения окно\-разделитель после обработки размер строки или столбца.|  
|[CSplitterWnd::SetActivePane](../Topic/CSplitterWnd::SetActivePane.md)|Задает область на активное одним во фрейме.|  
|[CSplitterWnd::SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md)|Вызовите, чтобы задать данные указанного столбца.|  
|[CSplitterWnd::SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md)|Вызовите, чтобы установить указанные данные строк.|  
|[CSplitterWnd::SetScrollStyle](../Topic/CSplitterWnd::SetScrollStyle.md)|Указывает новый стиль для поддержки полосы прокрутки полосы прокрутки окна разделитель общей.|  
|[CSplitterWnd::SplitColumn](../Topic/CSplitterWnd::SplitColumn.md)|Указывает, где фреймовое окно разбивается по вертикали.|  
|[CSplitterWnd::SplitRow](../Topic/CSplitterWnd::SplitRow.md)|Указывает, где фреймовое окно разбивается по горизонтали.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSplitterWnd::OnDraw](../Topic/CSplitterWnd::OnDraw.md)|Вызываемый платформой для рисования окно\-разделитель.|  
|[CSplitterWnd::OnDrawSplitter](../Topic/CSplitterWnd::OnDrawSplitter.md)|Подготавливает образ окна разбиения.|  
|[CSplitterWnd::OnInvertTracker](../Topic/CSplitterWnd::OnInvertTracker.md)|Подготавливает образ окна разбиения, чтобы быть одинаковым размером и фигурой, как фреймовое окно.|  
  
## Заметки  
 Панель обычно относящийся к приложению объект, производный от [CView](../Topic/CView%20Class.md), но может быть любым объектом [CWnd](../Topic/CWnd%20Class.md), имеющий соответствующее идентификатор дочернего окна  
  
 Объект `CSplitterWnd` обычно встраивание в родительском объекте [CFrameWnd](../../mfc/reference/cframewnd-class.md) или [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md).  Создайте объект `CSplitterWnd` с помощью следующих шагов:  
  
1.  Внедрение переменную\-член `CSplitterWnd` в родительском фрейме.  
  
2.  Переопределить функцию\-член [CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md) родительского фрейма.  
  
3.  Из переопределенного `OnCreateClient`, вызовите функцию\-член [Создание](../Topic/CSplitterWnd::Create.md) или [CreateStatic](../Topic/CSplitterWnd::CreateStatic.md)`CSplitterWnd`.  
  
 Вызовите функцию\-член **Создать** для создания динамического окно\-разделитель.  Динамическое окно\-разделитель, как правило, используется для создания и прокрутка несколько отдельных панелей или представления одного и того же документа.  Платформа автоматически создают начальная область для разделения; затем платформа создает, размеров и dispose дополнительных панелей по мере того, как пользователь работает с управления окнами разделителя.  
  
 При вызове **Создать** определяется минимальное значение высоты строк и ширину столбцов, определяющее, когда области слишком малы полностью отобразить.  После вызова **Создать**, можно обработать эти минимумы путем вызова функции\-члены [SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) и [SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md).  
  
 Также используйте функции\-члены `SetColumnInfo` и `SetRowInfo` для задания "в идеале" ширину столбца и "идеальный" высоту строки.  Когда границы отображаются окно\-разделитель, сначала они указывают родительский кадр, затем окно\-разделитель.  Границы затем помещаются за пределами области в столбцы и строки согласно их в идеале измерениям, работающий с верхн\- левой стороны к низк\- правому углу клиентской области окна разделителя.  
  
 Все области в окне динамической разделителя должны быть одного и того же класса.  Знакомые приложения, поддерживающие динамические окна разделитель включают Microsoft Word и Microsoft Excel.  
  
 Использование функции\-члена `CreateStatic` чтобы создать статическое окно\-разделитель.  Пользователь может изменить только размер панели в статическом поле разделитель, а не их числа или заказ.  
  
 Необходимо специально создание панелей все статические разделитель при создании статического разделителя.  Убедитесь, чтобы создать все области, прежде чем функцию\-член `OnCreateClient` родительского фрейма возвращает или границы не отобразит окно правильно.  
  
 Функция\-член `CreateStatic` автоматически инициализирует статический разделитель с минимальным высотой и шириной столбцов 0 строк.  После вызова **Создать**, настройте эти минимумы путем вызова функции\-члены [SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) и [SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md).  Также используйте `SetColumnInfo` и `SetRowInfo` после вызова `CreateStatic` для отображения нужных в идеале измерения панели.  
  
 Отдельные панели статического разделитель часто принадлежащих другим классам.  Примеры статических полях разделитель см. в разделе редактор графики и файловый менеджер Windows.  
  
 Окно\-разделитель поддерживает специальные полосы прокрутки \(отдельно от полос прокрутки, области могут содержать\).  Эти полосы прокрутки дочерние элементы объекта `CSplitterWnd` и совместно использованы с областями.  
  
 Вы создаете эти специальные полосы прокрутки при создании окно\-разделитель.  Например, `CSplitterWnd`, имеет одну строку, 2 столбцов и стиль **WS\_VSCROLL** будет отображать вертикальную полосу прокрутки, которая совместно использована 2 областями.  Когда пользователь перемещается полоса прокрутки, сообщения `WM_VSCROLL` отправлены к обеим панели.  Если панель задают положение полосы прокрутки, общая полоса прокрутки установлена.  
  
 Дополнительные сведения о windows разделитель см. в разделах:  
  
-   [Техническая примечание 29](../../mfc/tn029-splitter-windows.md)  
  
-   Q262024 статья базы знаний Майкрософт: Практическое руководство: используйте CPropertySheet как дочерний элемент CSplitterWnd  
  
 Дополнительные сведения о создании динамических окна разделитель см. в разделах:  
  
-   Пример [Scribble](../../top/visual-cpp-samples.md) MFC  
  
-   Пример [VIEWEX](../../top/visual-cpp-samples.md) MFC.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CSplitterWnd`  
  
## Требования  
 **Header:**  afxext.h  
  
## См. также  
 [В образце VIEWEX MFC](../../top/visual-cpp-samples.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView Class](../Topic/CView%20Class.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)