---
title: "CPrintInfo Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPrintInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintInfo structure"
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CPrintInfo Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Данные магазинов о задании печати или предварительный просмотр.  
  
## Синтаксис  
  
```  
struct CPrintInfo  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPrintInfo::GetFromPage](../Topic/CPrintInfo::GetFromPage.md)|Получает номер первой страницы, печатанным.|  
|[CPrintInfo::GetMaxPage](../Topic/CPrintInfo::GetMaxPage.md)|Возвращает номер последней страницы документа.|  
|[CPrintInfo::GetMinPage](../Topic/CPrintInfo::GetMinPage.md)|Получает номер первой страницы документа.|  
|[CPrintInfo::GetOffsetPage](../Topic/CPrintInfo::GetOffsetPage.md)|Возвращает число страниц, предшествующих первой страницы элемента DocObject, печатанным в объединенном задании печати DocObject.|  
|[CPrintInfo::GetToPage](../Topic/CPrintInfo::GetToPage.md)|Возвращает номер последней страницы, печатанным.|  
|[CPrintInfo::SetMaxPage](../Topic/CPrintInfo::SetMaxPage.md)|Задает номер последней страницы документа.|  
|[CPrintInfo::SetMinPage](../Topic/CPrintInfo::SetMinPage.md)|Задает номер первой страницы документа.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CPrintInfo::m\_bContinuePrinting](../Topic/CPrintInfo::m_bContinuePrinting.md)|Содержит пометить указывающее, следует ли продолжать границы цикла печати.|  
|[CPrintInfo::m\_bDirect](../Topic/CPrintInfo::m_bDirect.md)|Содержит пометить указывающее, является ли документ печатается напрямую \(без отображения диалогового окна печати\).|  
|[CPrintInfo::m\_bDocObject](../Topic/CPrintInfo::m_bDocObject.md)|Содержит пометить указывающее, печатанным ли документ DocObject.|  
|[CPrintInfo::m\_bPreview](../Topic/CPrintInfo::m_bPreview.md)|Указывает, содержит ли документ просматривается пометить дополнительно.|  
|[CPrintInfo::m\_dwFlags](../Topic/CPrintInfo::m_dwFlags.md)|Указывает операции печати DocObject.|  
|[CPrintInfo::m\_lpUserData](../Topic/CPrintInfo::m_lpUserData.md)|Содержит указатель на пользователь\-, созданной структуре.|  
|[CPrintInfo::m\_nCurPage](../Topic/CPrintInfo::m_nCurPage.md)|Указывает номер выделенного в настоящий момент, печатанной страницы.|  
|[CPrintInfo::m\_nJobNumber](../Topic/CPrintInfo::m_nJobNumber.md)|Указывает номер задания, присвоенный операционной системой для текущего задания печати|  
|[CPrintInfo::m\_nNumPreviewPages](../Topic/CPrintInfo::m_nNumPreviewPages.md)|Указывает число страниц, которые будут отображаться в окне предварительного просмотра. 1 или 2.|  
|[CPrintInfo::m\_nOffsetPage](../Topic/CPrintInfo::m_nOffsetPage.md)|Определяет смещение частности DocObject сначала вызовите в объединенном задании печати DocObject.|  
|[CPrintInfo::m\_pPD](../Topic/CPrintInfo::m_pPD.md)|Содержит указатель на объект `CPrintDialog`, использованный для диалогового окна печати.|  
|[CPrintInfo::m\_rectDraw](../Topic/CPrintInfo::m_rectDraw.md)|Определяет прямоугольник, определяющий текущую годную к использованию область страницы.|  
|[CPrintInfo::m\_strPageDesc](../Topic/CPrintInfo::m_strPageDesc.md)|Содержит строку форматирования для отображения страница\- числа.|  
  
## Заметки  
 `CPrintInfo` структура и не имеет базовый класс.  
  
 Платформа создает объект `CPrintInfo` каждый раз, когда команда печать или предварительный просмотр выбрана и разрушают их, когда команда завершена.  
  
 `CPrintInfo` содержащий сведения о задании печати в целом, например диапазон страниц быть напечатанным, а текущее состояние задания печати, например в настоящее время, печатанным страницы.  Некоторые данные хранятся в связанном объекте [CPrintDialog](../Topic/CPrintDialog%20Class.md); этот объект содержит значения, введенные пользователем в диалоговом окне печать.  
  
 Объект `CPrintInfo` передается между границами и пользовательским классом представления, в процессе печати и используется для обмена информацией между 2.  Например, границы отчет класс представления, страница документа, который будет ввести путем присвоения значения члену `m_nCurPage``CPrintInfo`; класс представления получает значения и выполняет фактическую печать определенной страницы.  
  
 Другим примером является случай, когда неизвестна длина документа до тех пор, пока она не печатается.  В этой ситуации тесты класса представления для конца документа каждый раз при печати страницы.  При достижении конца класс представления устанавливает участника `m_bContinuePrinting``CPrintInfo` к **FALSE**; это предоставляет платформу для остановки цикла печати.  
  
 `CPrintInfo` используется функции\-членами `CView` перечислило в разделе "см. также". Дополнительные сведения об архитектуре печати, предоставленную библиотеки Microsoft Foundation Class см. в разделе [фреймовые окна](../../mfc/frame-windows.md) и [Архитектура документов и представлений](../Topic/Document-View%20Architecture.md) и статей [Печать](../../mfc/printing.md) и [Тип: Многостраничных документов](../../mfc/multipage-documents.md).  
  
## Иерархия наследования  
 `CPrintInfo`  
  
## Требования  
 **Header:**  afxext.h  
  
## См. также  
 [MFC просматривает DIBLOOK](../../top/visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)   
 [CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md)   
 [CView::OnEndPrintPreview](../Topic/CView::OnEndPrintPreview.md)   
 [CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md)   
 [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)   
 [CView::OnPrint](../Topic/CView::OnPrint.md)