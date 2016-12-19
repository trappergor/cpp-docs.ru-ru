---
title: "CMenu Class | Microsoft Docs"
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
  - "CMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMenu class"
  - "HMENU"
  - "меню, базовый класс"
  - "меню, класс"
  - "меню, создание"
  - "меню, управление"
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMenu Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсуляция Windows `HMENU`.  
  
## Синтаксис  
  
```  
class CMenu : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMenu::CMenu](../Topic/CMenu::CMenu.md)|Создает объект `CMenu`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)|Добавляет новый элемент в конец этого меню.|  
|[CMenu::Attach](../Topic/CMenu::Attach.md)|Вложение дескриптор меню Windows на объект `CMenu`.|  
|[CMenu::CheckMenuItem](../Topic/CMenu::CheckMenuItem.md)|Устанавливает флажок возле или снимает флажок с пункта меню во всплывающем меню.|  
|[CMenu::CheckMenuRadioItem](../Topic/CMenu::CheckMenuRadioItem.md)|Задает переключатель рядом с пунктом меню и удаляет переключатель от всех остальных пунктов меню в группе.|  
|[CMenu::CreateMenu](../Topic/CMenu::CreateMenu.md)|Создает пустое меню и вложение его к объекту `CMenu`.|  
|[CMenu::CreatePopupMenu](../Topic/CMenu::CreatePopupMenu.md)|Создает пустую всплывающее меню и вложение его к объекту `CMenu`.|  
|[CMenu::DeleteMenu](../Topic/CMenu::DeleteMenu.md)|Удаляет указанный элемент из меню.  Если у контекстного меню пункт меню, меню, уничтожает дескриптор всплывающему меню и освобождает память, используемую ней.|  
|[CMenu::DeleteTempMap](../Topic/CMenu::DeleteTempMap.md)|Удаляет все временные объекты, созданные `CMenu` функцией\-членом `FromHandle`.|  
|[CMenu::DestroyMenu](../Topic/CMenu::DestroyMenu.md)|Уничтожает вложенном меню к объекту `CMenu` и освобождает любой память, которую меню заняло.|  
|[CMenu::Detach](../Topic/CMenu::Detach.md)|Наконец удаляет дескриптор меню Windows из объекта `CMenu` и возвращает маркер.|  
|[CMenu::DrawItem](../Topic/CMenu::DrawItem.md)|Вызываемый платформой, когда визуальных аспектов определяемого пользователем меню изменяется.|  
|[CMenu::EnableMenuItem](../Topic/CMenu::EnableMenuItem.md)|Включает, отключить или снизит серые цвета яркость \(\) пункта меню.|  
|[CMenu::FromHandle](../Topic/CMenu::FromHandle.md)|Возвращает указатель на объект `CMenu` заданный дескриптор меню Windows.|  
|[CMenu::GetDefaultItem](../Topic/CMenu::GetDefaultItem.md)|Указывает значение по умолчанию пункт меню в заданном меню.|  
|[CMenu::GetMenuContextHelpId](../Topic/CMenu::GetMenuContextHelpId.md)|Извлекает идентификатор контекста справки, связанный с меню.|  
|[CMenu::GetMenuInfo](../Topic/CMenu::GetMenuInfo.md)|Извлекает сведения о конкретном меню.|  
|[CMenu::GetMenuItemCount](../Topic/CMenu::GetMenuItemCount.md)|Указывает число элементов во всплывающем меню верхнего уровня.|  
|[CMenu::GetMenuItemID](../Topic/CMenu::GetMenuItemID.md)|Получает идентификатор пункта меню для пункта меню, находящегося на указанной позиции.|  
|[CMenu::GetMenuItemInfo](../Topic/CMenu::GetMenuItemInfo.md)|Извлекает сведения о пункте меню.|  
|[CMenu::GetMenuState](../Topic/CMenu::GetMenuState.md)|Возвращает состояние заданного пункта меню или число элементов в всплывающем меню.|  
|[CMenu::GetMenuString](../Topic/CMenu::GetMenuString.md)|Извлекает маркер указанного пункта меню.|  
|[CMenu::GetSafeHmenu](../Topic/CMenu::GetSafeHmenu.md)|Возвращает `m_hMenu` создает программу\-оболочку этим объектом `CMenu`.|  
|[CMenu::GetSubMenu](../Topic/CMenu::GetSubMenu.md)|Извлекает указатель на всплывающему меню.|  
|[CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)|Вставляет новый пункт меню в заданную позицию, перемещения и другие элементы вниз с меню.|  
|[CMenu::InsertMenuItem](../Topic/CMenu::InsertMenuItem.md)|Вставляет новый пункт меню в заданную позицию в меню.|  
|[CMenu::LoadMenu](../Topic/CMenu::LoadMenu.md)|Загружает ресурс меню из исполняемого файла и вложение его к объекту `CMenu`.|  
|[CMenu::LoadMenuIndirect](../Topic/CMenu::LoadMenuIndirect.md)|Загружает меню из шаблона меню в памяти и вложение его к объекту `CMenu`.|  
|[CMenu::MeasureItem](../Topic/CMenu::MeasureItem.md)|Вызываемый платформой для определения измерения меню, когда меню создано определенное пользователем.|  
|[CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)|Изменяет существующий пункт меню в заданном месте.|  
|[CMenu::RemoveMenu](../Topic/CMenu::RemoveMenu.md)|Удаляет пункт меню меню со связанным всплывающим из указанного меню.|  
|[CMenu::SetDefaultItem](../Topic/CMenu::SetDefaultItem.md)|По умолчанию задается пункт меню для конкретного меню.|  
|[CMenu::SetMenuContextHelpId](../Topic/CMenu::SetMenuContextHelpId.md)|Задает идентификатор контекста справки, связываемое с меню.|  
|[CMenu::SetMenuInfo](../Topic/CMenu::SetMenuInfo.md)|Задает сведения о конкретном меню.|  
|[CMenu::SetMenuItemBitmaps](../Topic/CMenu::SetMenuItemBitmaps.md)|Связывает указанные растровые изображения галочки к пункту меню.|  
|[CMenu::SetMenuItemInfo](../Topic/CMenu::SetMenuItemInfo.md)|Изменяет сведения о пункте меню.|  
|[CMenu::TrackPopupMenu](../Topic/CMenu::TrackPopupMenu.md)|Отображает контекстное меню в заданном месте с меню и отслеживает выделение элементов во всплывающем меню.|  
|[CMenu::TrackPopupMenuEx](../Topic/CMenu::TrackPopupMenuEx.md)|Отображает контекстное меню в заданном месте с меню и отслеживает выделение элементов во всплывающем меню.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMenu::operator HMENU](../Topic/CMenu::operator%20HMENU.md)|Получает дескриптор объекта меню.|  
|[CMenu::operator \!\=](../Topic/CMenu::operator%20!=.md)|Определяет, 2 объекта меню не равны.|  
|[CMenu::operator \=\=](../Topic/CMenu::operator%20==.md)|Определяет, равны 2 объекта меню.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMenu::m\_hMenu](../Topic/CMenu::m_hMenu.md)|Определяет дескриптор меню Windows вложенный в объект `CMenu`.|  
  
## Заметки  
 Он предоставляет функции\-члены для создания отслеживания, обновления и разрушать меню.  
  
 Создайте объект `CMenu` в кадре стека как местное, а затем вызвать функции\-члены `CMenu` для управления меню создать.  Затем вызовите [CWnd::SetMenu](../Topic/CWnd::SetMenu.md) для задания меню окна, следует немедленно при вызове функции\-члену [Наконец удалить](../Topic/CMenu::Detach.md) объекта `CMenu`.  Функция\-член `CWnd::SetMenu` устанавливает меню окна в новое меню, приводит к тому, что окно быть повторно перетаскиваются, чтобы отразить изменение меню, а также передает владение меню окна.  Вызов **Отсоединить** наконец удаляет `HMENU` из объекта `CMenu`, поэтому при локальная переменная `CMenu` пройдет из области, деструктор объекта `CMenu` не будет пытаться удалить меню он больше не имеет.  Само меню автоматически удалено при уничтожении окна.  
  
 Можно использовать функции\-члена [LoadMenuIndirect](../Topic/CMenu::LoadMenuIndirect.md) для создания меню из шаблона в памяти, но меню, созданное из ресурса вызовом [LoadMenu](../Topic/CMenu::LoadMenu.md) более легко поддерживаемого, а сам меню ресурс может быть создания и изменения редактора меню.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CMenu`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [В образце CTRLTEST MFC](../../top/visual-cpp-samples.md)   
 [Образец DYNAMENU MFC](../../top/visual-cpp-samples.md)   
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CObject Class](../Topic/CObject%20Class.md)