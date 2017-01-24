---
title: "CComboBoxEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComboBoxEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComboBoxEx class"
  - "поля со списком [C++], CComboBoxEx class"
  - "common controls [C++], extended combo boxes"
  - "extended combo boxes, CComboBoxEx class"
  - "Internet Explorer 4.0 common controls"
  - "Windows common controls [C++], extended combo boxes"
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
caps.latest.revision: 26
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComboBoxEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Расширяет элемент управления поля со списком, предоставляя поддержку для списков образа.  
  
## Синтаксис  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComboBoxEx::CComboBoxEx](../Topic/CComboBoxEx::CComboBoxEx.md)|Создает объект `CComboBoxEx`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComboBoxEx::Create](../Topic/CComboBoxEx::Create.md)|Создает поля со списком и вложение его к объекту `CComboBoxEx`.|  
|[CComboBoxEx::CreateEx](../Topic/CComboBoxEx::CreateEx.md)|Создает поле со списком с указанными стилей расширенными Windows и вложение его к объекту **ComboBoxEx**.|  
|[CComboBoxEx::DeleteItem](../Topic/CComboBoxEx::DeleteItem.md)|Удаляет элемент из элемента управления **ComboBoxEx**.|  
|[CComboBoxEx::GetComboBoxCtrl](../Topic/CComboBoxEx::GetComboBoxCtrl.md)|Извлекает указатель в элемент управления поля со списком дочерних элементов.|  
|[CComboBoxEx::GetEditCtrl](../Topic/CComboBoxEx::GetEditCtrl.md)|Получает дескриптор для части элемента управления "Поле ввода" управления **ComboBoxEx**.|  
|[CComboBoxEx::GetExtendedStyle](../Topic/CComboBoxEx::GetExtendedStyle.md)|Получает расширенные стили, используемые для управления **ComboBoxEx**.|  
|[CComboBoxEx::GetImageList](../Topic/CComboBoxEx::GetImageList.md)|Извлекает указатель на список образа присвоенному к элементу управления **ComboBoxEx**.|  
|[CComboBoxEx::GetItem](../Topic/CComboBoxEx::GetItem.md)|Получает данные элемента для данного элемента **ComboBoxEx**.|  
|[CComboBoxEx::HasEditChanged](../Topic/CComboBoxEx::HasEditChanged.md)|Указывает, что пользователь изменил содержимое элемента управления "Поле ввода" **ComboBoxEx** путем ввода.|  
|[CComboBoxEx::InsertItem](../Topic/CComboBoxEx::InsertItem.md)|Вставляет новый элемент в элемент управления **ComboBoxEx**.|  
|[CComboBoxEx::SetExtendedStyle](../Topic/CComboBoxEx::SetExtendedStyle.md)|Расширенные стили наборами в элементе управления **ComboBoxEx**.|  
|[CComboBoxEx::SetImageList](../Topic/CComboBoxEx::SetImageList.md)|Задает список завершения образа для управления **ComboBoxEx**.|  
|[CComboBoxEx::SetItem](../Topic/CComboBoxEx::SetItem.md)|Задает атрибуты для элемента в элементе управления **ComboBoxEx**.|  
|[CComboBoxEx::SetWindowTheme](../Topic/CComboBoxEx::SetWindowTheme.md)|Задает визуальный стиль расширенного элемента управления " поле со списком.|  
  
## Заметки  
 С помощью `CComboBoxEx` для создания элементов управления " поле со списком, которые больше не требуется реализовать собственный код документа образа.  Вместо этого используйте `CComboBoxEx` для доступа к образы из списка образа.  
  
## Поддержка списка образа  
 В стандартном поле со списком, владелец поля со списком отвечает за создание образа, можно создать поле со списком как элемент управления рисования владельцем.  При использовании `CComboBoxEx`, не нужно задать стили **CBS\_OWNERDRAWFIXED** и **CBS\_HASSTRINGS** документа, поскольку они подразумеваются.  В противном случае необходимо написать код для выполнения операции рисования.  Элемент управления поддерживает до 3 `CComboBoxEx` образа в элемент. одно для выбранного состояния, по одному на невыбранном состояния и один для образа перекрытия.  
  
## Стили  
 `CComboBoxEx` поддерживает стили **CBS\_SIMPLE**, **CBS\_DROPDOWN**, **CBS\_DROPDOWNLIST** и **WS\_CHILD**.  Все остальные стили, передаваемые при создании окна игнорируются элементом управления.  После открытия окна создано можно указать другие стили поля со списком, вызвав функцию\-член [SetExtendedStyle](../Topic/CComboBoxEx::SetExtendedStyle.md)`CComboBoxEx`.  С помощью этих стилей можно:  
  
-   Установка поиск строки в списке, который должен быть учитывается регистр.  
  
-   Создайте элемент управления поля со списком, в котором используется косая черта \(\/\), обратная косая черта \("\\"\) и точкой \(.\) в качестве разделителей слов.  Это позволяет пользователям гиперссылке из слова к слову, используя СТРЕЛКИ сочетание клавиш CTRL\+.  
  
-   Задайте элемент управления поля со списком или отображения, либо отображало образа.  Если изображение не отображается, то поле со списком может удалить отступ текста, адаптирующий образа.  
  
-   Создайте частая элемент управления поля со списком, включая определение размера его поэтому он отсекает более широкое поле со списком, которые он содержит.  
  
 Эти флаги стиля описаны далее в [Использование CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## Атрибуты элемента срока и обратного вызова элемента  
 Данные элемента в качестве индексов для элементов и изображений, значения отступов и текстовые строки, хранятся в Win32 структуры [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Структура также содержит члены, которые соответствуют флагам обратного вызова.  
  
 Подробное обсуждение, концепции см. в разделе [Использование CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## Требования  
 **Header:**  afxcmn.h  
  
## См. также  
 [Образец MFCIE MFC](../../top/visual-cpp-samples.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)