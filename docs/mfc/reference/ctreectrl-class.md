---
title: "CTreeCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTreeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl class"
  - "directory lists"
  - "file lists [C++]"
  - "tree view controls"
ms.assetid: 96e20031-6161-4143-8c12-8d1816c66d90
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CTreeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности элемента управления иерархического представления Windows общего.  
  
## Синтаксис  
  
```  
class CTreeCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTreeCtrl::CTreeCtrl](../Topic/CTreeCtrl::CTreeCtrl.md)|Создает объект `CTreeCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTreeCtrl::Create](../Topic/CTreeCtrl::Create.md)|Создает элемент управления иерархического представления и вложение его к объекту `CTreeCtrl`.|  
|[CTreeCtrl::CreateDragImage](../Topic/CTreeCtrl::CreateDragImage.md)|Создается при перетаскивании растровое изображение для указанного элемента представления в виде дерева.|  
|[CTreeCtrl::CreateEx](../Topic/CTreeCtrl::CreateEx.md)|Создает элемент управления дерева с указанными стилей расширенными Windows и вложение его к объекту `CTreeCtrl`.|  
|[CTreeCtrl::DeleteAllItems](../Topic/CTreeCtrl::DeleteAllItems.md)|Удаляет все элементы в элементе управления иерархического представления.|  
|[CTreeCtrl::DeleteItem](../Topic/CTreeCtrl::DeleteItem.md)|Удаляет новый элемент в элементе управления иерархического представления.|  
|[CTreeCtrl::EditLabel](../Topic/CTreeCtrl::EditLabel.md)|Изменяет определенное в\-размещение элемента представления в виде дерева.|  
|[CTreeCtrl::EndEditLabelNow](../Topic/CTreeCtrl::EndEditLabelNow.md)|Отменяет операцию правки на метке элемента представления в виде дерева в текущем элементе управления иерархического представления.|  
|[CTreeCtrl::EnsureVisible](../Topic/CTreeCtrl::EnsureVisible.md)|Гарантирует, что элемент представления в виде дерева видимым в элементе управления иерархического представления.|  
|[CTreeCtrl::Expand](../Topic/CTreeCtrl::Expand.md)|Разверните или сбросы давления, дочерние элементы указанного элемента представления в виде дерева.|  
|[CTreeCtrl::GetBkColor](../Topic/CTreeCtrl::GetBkColor.md)|Извлекает текущий цвет фона элемента управления.|  
|[CTreeCtrl::GetCheck](../Topic/CTreeCtrl::GetCheck.md)|Извлекает состояние проверки элемента управления дерева.|  
|[CTreeCtrl::GetChildItem](../Topic/CTreeCtrl::GetChildItem.md)|Извлекает дочерний элемент указанного элемента представления в виде дерева.|  
|[CTreeCtrl::GetCount](../Topic/CTreeCtrl::GetCount.md)|Получает количество элементов дерева, связанных с элементом управления иерархического представления.|  
|[CTreeCtrl::GetDropHilightItem](../Topic/CTreeCtrl::GetDropHilightItem.md)|Извлекает целевым объектом операции перетаскивания.|  
|[CTreeCtrl::GetEditControl](../Topic/CTreeCtrl::GetEditControl.md)|Извлекает маркер элемента управления "Поле ввода" используется для редактирования указанного элемента представления в виде дерева.|  
|[CTreeCtrl::GetExtendedStyle](../Topic/CTreeCtrl::GetExtendedStyle.md)|Получает расширенные стили, что текущий элемент управления иерархического представления.|  
|[CTreeCtrl::GetFirstVisibleItem](../Topic/CTreeCtrl::GetFirstVisibleItem.md)|Извлекает первый видимый элемент указанного элемента представления в виде дерева.|  
|[CTreeCtrl::GetImageList](../Topic/CTreeCtrl::GetImageList.md)|Извлекает маркер списка образа, связанного с элементом управления иерархического представления.|  
|[CTreeCtrl::GetIndent](../Topic/CTreeCtrl::GetIndent.md)|Получает смещение \(в точках\) элемента представления в виде дерева от родительского элемента.|  
|[CTreeCtrl::GetInsertMarkColor](../Topic/CTreeCtrl::GetInsertMarkColor.md)|Возвращает цвет, используемый для рисования метка вставки для представления в виде дерева.|  
|[CTreeCtrl::GetItem](../Topic/CTreeCtrl::GetItem.md)|Извлекает атрибуты указанного элемента представления в виде дерева.|  
|[CTreeCtrl::GetItemData](../Topic/CTreeCtrl::GetItemData.md)|Возвращает 32 разрядное конкретного приложения значение, связанное с элементом.|  
|[CTreeCtrl::GetItemExpandedImageIndex](../Topic/CTreeCtrl::GetItemExpandedImageIndex.md)|Извлекает индекс образа, который отображается, если указанный элемент текущего элемента управления иерархического представления в развернутом состоянии.|  
|[CTreeCtrl::GetItemHeight](../Topic/CTreeCtrl::GetItemHeight.md)|Извлекает текущая высота элементов представления в виде дерева.|  
|[CTreeCtrl::GetItemImage](../Topic/CTreeCtrl::GetItemImage.md)|Возвращает образы, связанные с элементом.|  
|[CTreeCtrl::GetItemPartRect](../Topic/CTreeCtrl::GetItemPartRect.md)|Возвращает ограничивающий прямоугольник для указанной части заданного элемента в текущем элементе управления иерархического представления.|  
|[CTreeCtrl::GetItemRect](../Topic/CTreeCtrl::GetItemRect.md)|Возвращает ограничивающий прямоугольник для элемента представления в виде дерева.|  
|[CTreeCtrl::GetItemState](../Topic/CTreeCtrl::GetItemState.md)|Возвращает состояние элемента.|  
|[CTreeCtrl::GetItemStateEx](../Topic/CTreeCtrl::GetItemStateEx.md)|Получает расширенное состояние заданного элемента в текущем элементе управления иерархического представления.|  
|[CTreeCtrl::GetItemText](../Topic/CTreeCtrl::GetItemText.md)|Возвращает текст элемента.|  
|[CTreeCtrl::GetLastVisibleItem](../Topic/CTreeCtrl::GetLastVisibleItem.md)|Извлекает последний развернутый элемент в текущем элементе управления иерархического представления.|  
|[CTreeCtrl::GetLineColor](../Topic/CTreeCtrl::GetLineColor.md)|Получает цвет линии для текущего элемента управления иерархического представления.|  
|[CTreeCtrl::GetNextItem](../Topic/CTreeCtrl::GetNextItem.md)|Извлекает следующий элемент представления в виде дерева, который соответствует заданному отношению.|  
|[CTreeCtrl::GetNextSiblingItem](../Topic/CTreeCtrl::GetNextSiblingItem.md)|Возвращает следующий одноуровневый элемент указанного элемента представления в виде дерева.|  
|[CTreeCtrl::GetNextVisibleItem](../Topic/CTreeCtrl::GetNextVisibleItem.md)|Извлекает следующий видимый элемент указанного элемента представления в виде дерева.|  
|[CTreeCtrl::GetParentItem](../Topic/CTreeCtrl::GetParentItem.md)|Возвращает родительский элемент указанного элемента представления в виде дерева.|  
|[CTreeCtrl::GetPrevSiblingItem](../Topic/CTreeCtrl::GetPrevSiblingItem.md)|Извлекает предыдущий одноуровневый элемент для указанного элемента представления в виде дерева.|  
|[CTreeCtrl::GetPrevVisibleItem](../Topic/CTreeCtrl::GetPrevVisibleItem.md)|Извлекает предыдущий видимый элемент указанного элемента представления в виде дерева.|  
|[CTreeCtrl::GetRootItem](../Topic/CTreeCtrl::GetRootItem.md)|Получает корень из указанного элемента представления в виде дерева.|  
|[CTreeCtrl::GetScrollTime](../Topic/CTreeCtrl::GetScrollTime.md)|Получает максимальное время прокрутки элемента управления иерархического представления.|  
|[CTreeCtrl::GetSelectedCount](../Topic/CTreeCtrl::GetSelectedCount.md)|Извлекает число выделенных элементов в текущем элементе управления иерархического представления.|  
|[CTreeCtrl::GetSelectedItem](../Topic/CTreeCtrl::GetSelectedItem.md)|Извлекает выбранный в данный момент элемент представления в виде дерева.|  
|[CTreeCtrl::GetTextColor](../Topic/CTreeCtrl::GetTextColor.md)|Извлекает текущий цвет текста элемента управления.|  
|[CTreeCtrl::GetToolTips](../Topic/CTreeCtrl::GetToolTips.md)|Получает дескриптор для элемента управления tooltip дочернего элемента, используемого элементом управления иерархического представления.|  
|[CTreeCtrl::GetVisibleCount](../Topic/CTreeCtrl::GetVisibleCount.md)|Возвращает количество видимых элементов дерева, связанных с элементом управления иерархического представления.|  
|[CTreeCtrl::HitTest](../Topic/CTreeCtrl::HitTest.md)|Возвращает текущее положение курсора, связанного с объектом `CTreeCtrl`.|  
|[CTreeCtrl::InsertItem](../Topic/CTreeCtrl::InsertItem.md)|Вставляет новый элемент в элементе управления иерархического представления.|  
|[CTreeCtrl::ItemHasChildren](../Topic/CTreeCtrl::ItemHasChildren.md)|Возвращает ненулевое значение, если указанный элемент имеет дочерние элементы.|  
|[CTreeCtrl::MapAccIdToItem](../Topic/CTreeCtrl::MapAccIdToItem.md)|Сопоставляет указанный идентификатор специальных возможностей на дескриптор к элементу представления в виде дерева в текущем элементе управления иерархического представления.|  
|[CTreeCtrl::MapItemToAccID](../Topic/CTreeCtrl::MapItemToAccID.md)|Сопоставляет указанный дескриптор к элементу представления в виде дерева в текущем элементе управления иерархического представления на идентификатор специальных возможностей.|  
|[CTreeCtrl::Select](../Topic/CTreeCtrl::Select.md)|Выберите, прокручивает в представление или перерисовывает указанный элемент представления в виде дерева.|  
|[CTreeCtrl::SelectDropTarget](../Topic/CTreeCtrl::SelectDropTarget.md)|Перерисовывает элемент дерева в качестве целевого объекта операции перетаскивания.|  
|[CTreeCtrl::SelectItem](../Topic/CTreeCtrl::SelectItem.md)|Выбирает указанный элемент представления в виде дерева.|  
|[CTreeCtrl::SelectSetFirstVisible](../Topic/CTreeCtrl::SelectSetFirstVisible.md)|Выбирает указанный элемент представления в виде дерева как первый видимый элемент.|  
|[CTreeCtrl::SetAutoscrollInfo](../Topic/CTreeCtrl::SetAutoscrollInfo.md)|Задает версию autoscroll текущего элемента управления иерархического представления.|  
|[CTreeCtrl::SetBkColor](../Topic/CTreeCtrl::SetBkColor.md)|Устанавливает цвет фона элемента управления.|  
|[CTreeCtrl::SetCheck](../Topic/CTreeCtrl::SetCheck.md)|Задает состояние проверки элемента управления дерева.|  
|[CTreeCtrl::SetExtendedStyle](../Topic/CTreeCtrl::SetExtendedStyle.md)|Задает расширенные стили для текущего элемента управления иерархического представления.|  
|[CTreeCtrl::SetImageList](../Topic/CTreeCtrl::SetImageList.md)|Задает дескриптор списка образа, связанного с элементом управления иерархического представления.|  
|[CTreeCtrl::SetIndent](../Topic/CTreeCtrl::SetIndent.md)|Задает смещение \(в точках\) элемента представления в виде дерева от родительского элемента.|  
|[CTreeCtrl::SetInsertMark](../Topic/CTreeCtrl::SetInsertMark.md)|Размещает метку вставки в элементе управления иерархического представления.|  
|[CTreeCtrl::SetInsertMarkColor](../Topic/CTreeCtrl::SetInsertMarkColor.md)|Устанавливает цвет, используемый для рисования метка вставки для представления в виде дерева.|  
|[CTreeCtrl::SetItem](../Topic/CTreeCtrl::SetItem.md)|Устанавливает атрибуты указанного элемента представления в виде дерева.|  
|[CTreeCtrl::SetItemData](../Topic/CTreeCtrl::SetItemData.md)|Устанавливает 32 разрядное конкретного приложения значение, связанный с элементом.|  
|[CTreeCtrl::SetItemExpandedImageIndex](../Topic/CTreeCtrl::SetItemExpandedImageIndex.md)|Устанавливает индекс образа, который отображается, если указанный элемент текущего элемента управления иерархического представления в развернутом состоянии.|  
|[CTreeCtrl::SetItemHeight](../Topic/CTreeCtrl::SetItemHeight.md)|Задает высоту элементов представления в виде дерева.|  
|[CTreeCtrl::SetItemImage](../Topic/CTreeCtrl::SetItemImage.md)|Связывает образы с элементом.|  
|[CTreeCtrl::SetItemState](../Topic/CTreeCtrl::SetItemState.md)|Устанавливает состояние элемента.|  
|[CTreeCtrl::SetItemStateEx](../Topic/CTreeCtrl::SetItemStateEx.md)|Задает расширенный состояние заданного элемента в текущем элементе управления иерархического представления.|  
|[CTreeCtrl::SetItemText](../Topic/CTreeCtrl::SetItemText.md)|Задает текст элемента.|  
|[CTreeCtrl::SetLineColor](../Topic/CTreeCtrl::SetLineColor.md)|Задает цвет линии для текущего элемента управления иерархического представления.|  
|[CTreeCtrl::SetScrollTime](../Topic/CTreeCtrl::SetScrollTime.md)|Задает максимальное время прокрутки элемента управления иерархического представления.|  
|[CTreeCtrl::SetTextColor](../Topic/CTreeCtrl::SetTextColor.md)|Задает цвет текста элемента управления.|  
|[CTreeCtrl::SetToolTips](../Topic/CTreeCtrl::SetToolTips.md)|Задает элемент управления tooltip дочернего элемента управления иерархического представления.|  
|[CTreeCtrl::ShowInfoTip](../Topic/CTreeCtrl::ShowInfoTip.md)|Отображает подсказку для указанного элемента в текущем элементе управления иерархического представления.|  
|[CTreeCtrl::SortChildren](../Topic/CTreeCtrl::SortChildren.md)|Сортирует потомков заданного родительского элемента.|  
|[CTreeCtrl::SortChildrenCB](../Topic/CTreeCtrl::SortChildrenCB.md)|Сортирует потомков заданного родительского элемента с помощью приложение\- заданную функцию сортировки.|  
  
## Заметки  
 "Элемент управления иерархического представления" окно, в котором отображается иерархический список элементов, например заголовка в документе, записях в индексе или файлами и каталогами на диске.  Каждый элемент состоит из меток и bitmapped необязательным образа, а каждый элемент может иметь список подэлементов, связанных с ним.  Если щелкнуть элемент, пользователь мог развернуть и свернуть, связанный список подэлементов.  
  
 Этот элемент управления \(и, следовательно, класс `CTreeCtrl` \) доступны только для программ, выполняемых в рамках Windows версии 4 и Windows NT 98 и более поздних версий.  
  
 Дополнительные сведения об использовании `CTreeCtrl` см. в разделах:  
  
-   [Элементы управления](../../mfc/controls-mfc.md)  
  
-   [Использование CTreeCtrl](../Topic/Using%20CTreeCtrl.md)  
  
-   [ссылка элемента управления иерархического представления](http://msdn.microsoft.com/library/windows/desktop/bb759988) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
-   Q222905 статья базы знаний Майкрософт: Практическое руководство: Отображает контекстное меню для CTreeCtrl  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CTreeCtrl`  
  
## Требования  
 **Header:**  afxcmn.h  
  
## См. также  
 [MFC просматривает CMNCTRL1](../../top/visual-cpp-samples.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CImageList Class](../Topic/CImageList%20Class.md)