---
title: "CReBarCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CReBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBarCtrl class"
  - "rebar controls, control bar"
  - "rebar controls, CReBarCtrl class"
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CReBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует функциональные возможности элемента управления " Главная панель, который контейнер для дочернего окна.  
  
## Синтаксис  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CReBarCtrl::CReBarCtrl](../Topic/CReBarCtrl::CReBarCtrl.md)|Создает объект `CReBarCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CReBarCtrl::BeginDrag](../Topic/CReBarCtrl::BeginDrag.md)|Задает элемент управления "Главная панель" в режим перетаскивания.|  
|[CReBarCtrl::Create](../Topic/CReBarCtrl::Create.md)|Создает элемент управления "Главная панель" и вложение его к объекту `CReBarCtrl`.|  
|[CReBarCtrl::CreateEx](../Topic/CReBarCtrl::CreateEx.md)|Создает элемент управления "Главная панель" с заданными стилей расширенными Windows и вложение его к объекту `CReBarCtrl`.|  
|[CReBarCtrl::DeleteBand](../Topic/CReBarCtrl::DeleteBand.md)|Удаляет диапазон из элемента управления " Главная панель.|  
|[CReBarCtrl::DragMove](../Topic/CReBarCtrl::DragMove.md)|Обновляет позиция перетаскивания в элементе управления "Главная панель" после вызова метода `BeginDrag`.|  
|[CReBarCtrl::EndDrag](../Topic/CReBarCtrl::EndDrag.md)|Завершает операции перетаскивания элемента управления " Главная панель.|  
|[CReBarCtrl::GetBandBorders](../Topic/CReBarCtrl::GetBandBorders.md)|Извлекает границы диапазона.|  
|[CReBarCtrl::GetBandCount](../Topic/CReBarCtrl::GetBandCount.md)|Получает количество полос в данный момент в элементе управления " Главная панель.|  
|[CReBarCtrl::GetBandInfo](../Topic/CReBarCtrl::GetBandInfo.md)|Извлекает сведения о конкретной полосе в элементе управления " Главная панель.|  
|[CReBarCtrl::GetBandMargins](../Topic/CReBarCtrl::GetBandMargins.md)|Извлекает поля полосы.|  
|[CReBarCtrl::GetBarHeight](../Topic/CReBarCtrl::GetBarHeight.md)|Получает высоту элемента управления " Главная панель.|  
|[CReBarCtrl::GetBarInfo](../Topic/CReBarCtrl::GetBarInfo.md)|Получить данные об элементе управления "Главная панель" и используется список образа.|  
|[CReBarCtrl::GetBkColor](../Topic/CReBarCtrl::GetBkColor.md)|Возвращает цвет фона элемента управления "Главная панель" по умолчанию.|  
|[CReBarCtrl::GetColorScheme](../Topic/CReBarCtrl::GetColorScheme.md)|Извлекает структуру [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502), связанная с элементом управления " Главная панель.|  
|[CReBarCtrl::GetDropTarget](../Topic/CReBarCtrl::GetDropTarget.md)|Получает указатель интерфейса `IDropTarget` элемента управления " Главная панель.|  
|[CReBarCtrl::GetExtendedStyle](../Topic/CReBarCtrl::GetExtendedStyle.md)|Получает расширенный стиль текущего элемента управления " Главная панель.|  
|[CReBarCtrl::GetImageList](../Topic/CReBarCtrl::GetImageList.md)|Извлекает список образа, связанный с элементом управления " Главная панель.|  
|[CReBarCtrl::GetPalette](../Topic/CReBarCtrl::GetPalette.md)|Извлекает элемента управления "Главная панель" текущая палитра.|  
|[CReBarCtrl::GetRect](../Topic/CReBarCtrl::GetRect.md)|Возвращает ограничивающий прямоугольник для данной полосы в элементе управления " Главная панель.|  
|[CReBarCtrl::GetRowCount](../Topic/CReBarCtrl::GetRowCount.md)|Извлекает число строк полосы в элементе управления " Главная панель.|  
|[CReBarCtrl::GetRowHeight](../Topic/CReBarCtrl::GetRowHeight.md)|Получает высоту указанной строки в элементе управления " Главная панель.|  
|[CReBarCtrl::GetTextColor](../Topic/CReBarCtrl::GetTextColor.md)|Возвращает цвет текста элемента управления "Главная панель" по умолчанию.|  
|[CReBarCtrl::GetToolTips](../Topic/CReBarCtrl::GetToolTips.md)|Получает дескриптор к любому элементу управления всплывающей подсказки, связанный с элементом управления " Главная панель.|  
|[CReBarCtrl::HitTest](../Topic/CReBarCtrl::HitTest.md)|Определяет, какая часть зоны главной панели на данном этапе на экране, если полоса главной панели существует в этой точке.|  
|[CReBarCtrl::IDToIndex](../Topic/CReBarCtrl::IDToIndex.md)|Преобразует идентификатор зоны \(id\) для индексации полосы в элементе управления " Главная панель.|  
|[CReBarCtrl::InsertBand](../Topic/CReBarCtrl::InsertBand.md)|Вставляет новую полосой в элемент управления " Главная панель.|  
|[CReBarCtrl::MaximizeBand](../Topic/CReBarCtrl::MaximizeBand.md)|Изменяет размер полосы в элементе управления "Главная панель" с его самой большой размер.|  
|[CReBarCtrl::MinimizeBand](../Topic/CReBarCtrl::MinimizeBand.md)|Изменяет размер полосы в элементе управления "Главная панель" с его наименьшему размеру.|  
|[CReBarCtrl::MoveBand](../Topic/CReBarCtrl::MoveBand.md)|Перемещает диапазон из одного индекса в другой.|  
|[CReBarCtrl::PushChevron](../Topic/CReBarCtrl::PushChevron.md)|Программным образом публикует шеврон.|  
|[CReBarCtrl::RestoreBand](../Topic/CReBarCtrl::RestoreBand.md)|Изменяет размер полосы в элементе управления "Главная панель" с его идеальным размера.|  
|[CReBarCtrl::SetBandInfo](../Topic/CReBarCtrl::SetBandInfo.md)|Задает характеристики существующей полосы в элементе управления " Главная панель.|  
|[CReBarCtrl::SetBandWidth](../Topic/CReBarCtrl::SetBandWidth.md)|Задает ширину указанной состыкованной полосы в текущем элементе управления " Главная панель.|  
|[CReBarCtrl::SetBarInfo](../Topic/CReBarCtrl::SetBarInfo.md)|Задает характеристики элемента управления " Главная панель.|  
|[CReBarCtrl::SetBkColor](../Topic/CReBarCtrl::SetBkColor.md)|Устанавливает цвет фона элемента управления "Главная панель" по умолчанию.|  
|[CReBarCtrl::SetColorScheme](../Topic/CReBarCtrl::SetColorScheme.md)|Задает цветовую схему для кнопок в элементе управления " Главная панель.|  
|[CReBarCtrl::SetExtendedStyle](../Topic/CReBarCtrl::SetExtendedStyle.md)|Задает расширенные стили для текущего элемента управления " Главная панель.|  
|[CReBarCtrl::SetImageList](../Topic/CReBarCtrl::SetImageList.md)|Задает список образа элемента управления " Главная панель.|  
|[CReBarCtrl::SetOwner](../Topic/CReBarCtrl::SetOwner.md)|Назначает окно владельцем элемента управления " Главная панель.|  
|[CReBarCtrl::SetPalette](../Topic/CReBarCtrl::SetPalette.md)|Задает палитру элемента управления "Главная панель" текущую.|  
|[CReBarCtrl::SetTextColor](../Topic/CReBarCtrl::SetTextColor.md)|Задает цвет текста элемента управления "Главная панель" по умолчанию.|  
|[CReBarCtrl::SetToolTips](../Topic/CReBarCtrl::SetToolTips.md)|Связывает элемент управления всплывающей подсказки с элементом управления " Главная панель.|  
|[CReBarCtrl::SetWindowTheme](../Topic/CReBarCtrl::SetWindowTheme.md)|Задает визуальный стиль элемента управления " Главная панель.|  
|[CReBarCtrl::ShowBand](../Topic/CReBarCtrl::ShowBand.md)|Показать или скрывает заданный диапазон в элементе управления " Главная панель.|  
|[CReBarCtrl::SizeToRect](../Topic/CReBarCtrl::SizeToRect.md)|По размеру элемент управления "Главная панель" с заданным прямоугольником.|  
  
## Заметки  
 Приложение, в котором находится элемент управления "Главная панель" присвоить дочернее окно содержит элементом управления "Главная панель" на полосе главной панели.  Дочернее окно обычно другой общий элемент управления.  
  
 Элементы управления "Главная панель" содержат один или несколько полосы.  Каждый диапазон может содержать сочетание панель отслеживания, растровое изображение, текстовая подпись и дочернее окно.  Полоса может содержать только одно из каждого из этих элементов.  
  
 Элемент управления "Главная панель" может означать дочернее окно с указанным растровым изображением фона.  Все " элемента управления " Главная панель можно изменить размер, за исключением тех, в которых используется стиль **RBBS\_FIXEDSIZE**.  По мере перемещаете или измените размер полосы элемента управления " Главная панель элемент управления "Главная панель" управляет размер и положение дочерних окон, присвоенный этой полосе.  Размер или изменить порядок полос в пределах элемента управления, щелкните и перетащите панель отслеживания полосы.  
  
 На следующем рисунке показан элемент управления "Главная панель" с 3 ":  
  
-   Полоса 0 содержит плоский, прозрачный элемент управления " Панель инструментов.  
  
-   Полоса 1 содержит прозрачные стандартные кнопки и прозрачные раскрывающиеся.  
  
-   Полоса содержит поле со списком 2 и 4 стандартных кнопки.  
  
     ![Пример меню "Главная панель"](../../mfc/reference/media/vc4scc1.png "vc4SCC1")  
  
## Элемент управления " Главная панель  
 Поддержка элементов управления "Главная панель":  
  
-   Списки образа.  
  
-   Обработка сообщений.  
  
-   Пользовательская функциональность рисования.  
  
-   Различные стили элемента управления в дополнение к стандартным стилей окна.  Список этих стилей см. в разделе [Стили элемента управления " Главная панель](http://msdn.microsoft.com/library/windows/desktop/bb774377) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения см. в разделе [Использование CReBarCtrl](../Topic/Using%20CReBarCtrl.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CReBarCtrl`  
  
## Требования  
 **Header:**  afxcmn.h  
  
## См. также  
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)