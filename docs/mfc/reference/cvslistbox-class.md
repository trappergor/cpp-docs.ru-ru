---
title: "CVSListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CVSListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CVSListBox class"
  - "CVSListBox::PreTranslateMessage method"
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CVSListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CVSListBox` поддерживает редактируемые элемент управления "Список".  
  
## Синтаксис  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CVSListBox::CVSListBox](../Topic/CVSListBox::CVSListBox.md)|Создает объект `CVSListBox`.|  
|`CVSListBox::~CVSListBox`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CVSListBox::AddItem](../Topic/CVSListBox::AddItem.md)|Добавляет строку к элементу управления "Список".  \(Переопределяет `CVSListBoxBase::AddItem`\).|  
|[CVSListBox::EditItem](../Topic/CVSListBox::EditItem.md)|Начинает операцию правки для текста элемента управления "Список".  \(Переопределяет `CVSListBoxBase::EditItem`\).|  
|[CVSListBox::GetCount](../Topic/CVSListBox::GetCount.md)|Извлекает число строк в редактируемой элементе управления "Список".  \(Переопределяет `CVSListBoxBase::GetCount`\).|  
|[CVSListBox::GetItemData](../Topic/CVSListBox::GetItemData.md)|Извлекает определенное для приложений 32 разрядное значение, сопоставлено с редактируемые элементом для элемента управления "Список".  \(Переопределяет `CVSListBoxBase::GetItemData`\).|  
|[CVSListBox::GetItemText](../Topic/CVSListBox::GetItemText.md)|Извлекает текст редактируемого элемента управления "Список".  \(Переопределяет `CVSListBoxBase::GetItemText`\).|  
|[CVSListBox::GetSelItem](../Topic/CVSListBox::GetSelItem.md)|Извлекает нулевой\- основан индекс выбранного элемента в редактируемой элементе управления "Список".  \(Переопределяет `CVSListBoxBase::GetSelItem`\).|  
|`CVSListBox::PreTranslateMessage`|Преобразует сообщения окна до их посланы к функциям [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows.  Дополнительные сведения и синтаксиса методов см. в разделе [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(Переопределяет `CVSListBoxBase::PreTranslateMessage`\).|  
|[CVSListBox::RemoveItem](../Topic/CVSListBox::RemoveItem.md)|Удаляет элемент из редактируемых элемента управления "Список".  \(Переопределяет `CVSListBoxBase::RemoveItem`\).|  
|[CVSListBox::SelectItem](../Topic/CVSListBox::SelectItem.md)|Выберите изменяемую строку элемента управления "Список".  \(Переопределяет `CVSListBoxBase::SelectItem`\).|  
|[CVSListBox::SetItemData](../Topic/CVSListBox::SetItemData.md)|Связывает конкретного приложения 32 разрядное значение с редактируемые элементом для элемента управления "Список".  \(Переопределяет `CVSListBoxBase::SetItemData`\).|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CVSListBox::GetListHwnd](../Topic/CVSListBox::GetListHwnd.md)|Возвращает маркер на внедренный в элемент управления "список".|  
  
## Заметки  
 Класс `CVSListBox` предоставляет набор кнопок правки, которые позволяют пользователю для создания, изменения, удаления или изменения порядка элементов в элементе управления "Список".  
  
 Следующее изображение редактируемого элемента управления "Список".  Вторая запись списка, которая называется "Item2", выделена для редактирования.  
  
 ![Элемент управления CVSListBox](../../mfc/reference/media/cvslistbox.png "cvslistbox")  
  
 При использовании редактора ресурсов для добавления редактируемый элемент управления "Список", обратите внимание, что панель **Панель элементов** редактор не предоставляет предопределенный редактируемый элемент управления "Список".  Вместо этого добавьте статический элемент управления как элемент управления **Область группы**.  Инфраструктура использует статический элемент управления в качестве заполнителя для определения размера и положения редактируемого элемента управления "Список".  
  
 Для использования редактируемого элемента управления "Список" в шаблоне диалогового окна, объявите переменную `CVSListBox` в классе диалогового окна.  Для поддержки обмена данными между переменной и элементом управления, укажите запись макроса `DDX_Control` в методе `DoDataExchange` диалогового окна.  По умолчанию изменяемый элемент управления "Список" создано без кнопок правки.  Используйте унаследованный метод [CVSListBoxBase::SetStandardButtons](http://msdn.microsoft.com/ru-ru/129e530f-97e9-42eb-b128-371c2a5686ba) для включения кнопки правки.  
  
 Дополнительные сведения см. в разделе sample `New Controls` каталог образцов Page3.cpp, файлы и Page3.h.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CStatic](../Topic/CStatic%20Class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## Требования  
 **заголовок:** afxvslistbox.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)