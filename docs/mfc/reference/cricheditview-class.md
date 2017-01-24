---
title: "CRichEditView Class | Microsoft Docs"
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
  - "CRichEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditView class"
  - "document/view architecture, элементы управления Rich Edit"
  - "OLE containers, rich edit"
  - "элементы управления Rich Edit, OLE container"
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
caps.latest.revision: 25
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRichEditView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

С [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) и [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) предоставляет функциональные возможности управления расширенного редактирования в контексте архитектуры представления документов MFC.  
  
## Синтаксис  
  
```  
  
class CRichEditView : public CCtrlView  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRichEditView::CRichEditView](../Topic/CRichEditView::CRichEditView.md)|Создает объект `CRichEditView`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRichEditView::AdjustDialogPosition](../Topic/CRichEditView::AdjustDialogPosition.md)|Перемещает диалоговое окно, чтобы оно не затемнит текущее выделение.|  
|[CRichEditView::CanPaste](../Topic/CRichEditView::CanPaste.md)|Указывает, содержит ли буфер обмена данные, которые можно вставлять в представление расширенного редактирования.|  
|[CRichEditView::DoPaste](../Topic/CRichEditView::DoPaste.md)|Вставляет элемент OLE в это представление расширенного редактирования.|  
|[CRichEditView::FindText](../Topic/CRichEditView::FindText.md)|Находит заданный текст, вызывающее курсор ожидания.|  
|[CRichEditView::FindTextSimple](../Topic/CRichEditView::FindTextSimple.md)|Находит заданный текст.|  
|[CRichEditView::GetCharFormatSelection](../Topic/CRichEditView::GetCharFormatSelection.md)|Извлекает атрибуты форматирования символов для текущего выделения.|  
|[CRichEditView::GetDocument](../Topic/CRichEditView::GetDocument.md)|Извлекает указатель к связанному [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|  
|[CRichEditView::GetInPlaceActiveItem](../Topic/CRichEditView::GetInPlaceActiveItem.md)|Извлекает элемент OLE, который в настоящий момент активны в\- размещения в представлении расширенного редактирования.|  
|[CRichEditView::GetMargins](../Topic/CRichEditView::GetMargins.md)|Извлекает поля для данного представления расширенного редактирования.|  
|[CRichEditView::GetPageRect](../Topic/CRichEditView::GetPageRect.md)|Получает прямоугольник страницы для данного представления расширенного редактирования.|  
|[CRichEditView::GetPaperSize](../Topic/CRichEditView::GetPaperSize.md)|Получает размер бумаги для данного представления расширенного редактирования.|  
|[CRichEditView::GetParaFormatSelection](../Topic/CRichEditView::GetParaFormatSelection.md)|Извлекает атрибуты формата абзаца для текущего выделения.|  
|[CRichEditView::GetPrintRect](../Topic/CRichEditView::GetPrintRect.md)|Получает прямоугольник печати для данного представления расширенного редактирования.|  
|[CRichEditView::GetPrintWidth](../Topic/CRichEditView::GetPrintWidth.md)|Получает ширину печати для данного представления расширенного редактирования.|  
|[CRichEditView::GetRichEditCtrl](../Topic/CRichEditView::GetRichEditCtrl.md)|Извлекает элемент управления расширенного редактирования.|  
|[CRichEditView::GetSelectedItem](../Topic/CRichEditView::GetSelectedItem.md)|Извлекает выбранный элемент из представления расширенного редактирования.|  
|[CRichEditView::GetTextLength](../Topic/CRichEditView::GetTextLength.md)|Получает длину текста в представлении расширенного редактирования.|  
|[CRichEditView::GetTextLengthEx](../Topic/CRichEditView::GetTextLengthEx.md)|Извлекает число символов или байтов в представлении расширенного редактирования.  Разрезанная список пометить для метода указании длины.|  
|[CRichEditView::InsertFileAsObject](../Topic/CRichEditView::InsertFileAsObject.md)|Вставляет файл как элемент OLE.|  
|[CRichEditView::InsertItem](../Topic/CRichEditView::InsertItem.md)|Вставляет новый элемент как элемент OLE.|  
|[CRichEditView::IsRichEditFormat](../Topic/CRichEditView::IsRichEditFormat.md)|Указывает, содержит ли буфер обмена данные в расширенном редактировании или текстовом формате.|  
|[CRichEditView::OnCharEffect](../Topic/CRichEditView::OnCharEffect.md)|Переключает форматирования символов для текущего выделения.|  
|[CRichEditView::OnParaAlign](../Topic/CRichEditView::OnParaAlign.md)|Изменяется выравнивание абзацев.|  
|[CRichEditView::OnUpdateCharEffect](../Topic/CRichEditView::OnUpdateCharEffect.md)|Обновляет пользовательский интерфейс команды для функций\-членов открытого символа.|  
|[CRichEditView::OnUpdateParaAlign](../Topic/CRichEditView::OnUpdateParaAlign.md)|Обновляет пользовательский интерфейс команды для функций\-членов открытого абзаца.|  
|[CRichEditView::PrintInsideRect](../Topic/CRichEditView::PrintInsideRect.md)|Форматирует указываемый текст в заданном прямоугольнике.|  
|[CRichEditView::PrintPage](../Topic/CRichEditView::PrintPage.md)|Форматирует указанный текст в заданной страницы.|  
|[CRichEditView::SetCharFormat](../Topic/CRichEditView::SetCharFormat.md)|Устанавливает атрибуты форматирования символов для текущего выделения.|  
|[CRichEditView::SetMargins](../Topic/CRichEditView::SetMargins.md)|Устанавливает поля для данного представления расширенного редактирования.|  
|[CRichEditView::SetPaperSize](../Topic/CRichEditView::SetPaperSize.md)|Задает размер бумаги для данного представления расширенного редактирования.|  
|[CRichEditView::SetParaFormat](../Topic/CRichEditView::SetParaFormat.md)|Устанавливает атрибуты формата абзаца для текущего выделения.|  
|[CRichEditView::TextNotFound](../Topic/CRichEditView::TextNotFound.md)|Сбросить внутреннее состояние поиска элемента управления.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRichEditView::GetClipboardData](../Topic/CRichEditView::GetClipboardData.md)|Извлекает объект буфера обмена для диапазона в этом представлении расширенного редактирования.|  
|[CRichEditView::GetContextMenu](../Topic/CRichEditView::GetContextMenu.md)|Возвращает контекстное меню для использования на правой кнопки мыши.|  
|[CRichEditView::IsSelected](../Topic/CRichEditView::IsSelected.md)|Указывает если выбрать данный элемент OLE.|  
|[CRichEditView::OnFindNext](../Topic/CRichEditView::OnFindNext.md)|Находит следующее вхождение подстроки.|  
|[CRichEditView::OnInitialUpdate](../Topic/CRichEditView::OnInitialUpdate.md)|Обновляет представление при первом вложена к документу.|  
|[CRichEditView::OnPasteNativeObject](../Topic/CRichEditView::OnPasteNativeObject.md)|Извлекает собственные данные из OLE элемента.|  
|[CRichEditView::OnPrinterChanged](../Topic/CRichEditView::OnPrinterChanged.md)|Задает характеристики печати в заданное устройство.|  
|[CRichEditView::OnReplaceAll](../Topic/CRichEditView::OnReplaceAll.md)|Заменяет все вхождения заданной строки на новую строку.|  
|[CRichEditView::OnReplaceSel](../Topic/CRichEditView::OnReplaceSel.md)|Заменяет текущее выделение.|  
|[CRichEditView::OnTextNotFound](../Topic/CRichEditView::OnTextNotFound.md)|Обрабатывает уведомление пользователей, текст не находило запрошенного.|  
|[CRichEditView::QueryAcceptData](../Topic/CRichEditView::QueryAcceptData.md)|Запросы, которые нужно узнать о данных в `IDataObject`.|  
|[CRichEditView::WrapChanged](../Topic/CRichEditView::WrapChanged.md)|Обрабатывает устройство вывода целевого объекта для данного представления расширенного редактирования, основанное на значении `m_nWordWrap`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CRichEditView::m\_nBulletIndent](../Topic/CRichEditView::m_nBulletIndent.md)|Указывает число отступа для списков маркера.|  
|[CRichEditView::m\_nWordWrap](../Topic/CRichEditView::m_nWordWrap.md)|Указывает ограничения по миграции по словам.|  
  
## Заметки  
 Элемент управления" окно "расширенного редактирования, в котором пользователь может вводить и редактирования текста.  Текст можно присвоить символ и форматирование абзаца, и может включать внедренные объект OLE.  Управления расширенного редактирования предоставляют программный интерфейс для форматирования текста.  Однако приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для операций форматирования, доступным для пользователя.  
  
 `CRichEditView` поддерживает характерные текст и форматирование текста.  Клиента OLE `CRichEditDoc` ведет список элементов, которые в представлении.  `CRichEditCntrItem` предоставляет доступ к элементу OLE контейнер\- на стороне клиента.  
  
 Это общее \(элемент управления Windows и, следовательно, [CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md) и связанные классы\) доступны только для программ, выполняемых в рамках версии 3.51 в Windows 95 и Windows NT \/98 и более поздних версий.  
  
 Пример использования представления расширенного редактирования в приложении MFC см. в разделе пример приложения [WORDPAD](../../top/visual-cpp-samples.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## Требования  
 **Header:**  afxrich.h  
  
## См. также  
 [MFC просматривает WORDPAD](../../top/visual-cpp-samples.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc Class](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditCntrItem Class](../../mfc/reference/cricheditcntritem-class.md)