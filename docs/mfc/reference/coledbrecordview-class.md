---
title: "COleDBRecordView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDBRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDBRecordView - класс"
  - "MFC - библиотека, OLE DB"
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# COleDBRecordView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представление отображает записи базы данных в элементах управления.  
  
## Синтаксис  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDBRecordView::COleDBRecordView](../Topic/COleDBRecordView::COleDBRecordView.md)|Создает объект `COleDBRecordView`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDBRecordView::OnGetRowset](../Topic/COleDBRecordView::OnGetRowset.md)|Возвращает стандартное значение `HRESULT`.|  
|[COleDBRecordView::OnMove](../Topic/COleDBRecordView::OnMove.md)|Обновляет текущую запись \(если пакостный\), то в источнике данных, а затем переходит к определенной записи \(далее предыдущий, сначала или последней\).|  
  
## Заметки  
 Представление представление формы напрямую подключенный к объекту `CRowset`.  Представление создано из ресурса шаблона диалоговых окон и отображает поля объекта `CRowset` в элементах управления шаблона диалогового окна.  Объект `COleDBRecordView` использует обмен данными диалоговых окон \(DDX\) и навигационную функциональность, полученный в `CRowset`, для автоматизации перемещения данных между элементами управления формы и полями набора строк.  `COleDBRecordView` также предоставляет реализацию по умолчанию для перемещения сначала следующей, предыдущей или последней записи и интерфейсу для обновления записи в текущий момент в представлении.  
  
 Можно использовать функции DDX с представлением **COleDbRecordView** для получения данных непосредственно из набора записей базы данных и отображения их в элементе управления диалогового окна.  С представлением **COleDbRecordView** следует использовать методы **DDX\_\*** \(например, `DDX_Text`\), а не функции **DDX\_Field\*** \(например, `DDX_FieldText`\).  `DDX_FieldText` не будет работать с **COleDbRecordView** поскольку `DDX_FieldText` принимает дополнительный аргумент типа **CRecordset\*** \(для `CRecordView`\) или **CDaoRecordset\*** \(для `CDaoRecordView`\).  
  
> [!NOTE]
>  При работе с DAO \(DAO\) классифицируете, а не классов шаблона объекта\-получателя OLE DB, используют класс [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).  Дополнительные сведения см. в статье [Общие сведения: программирование базы данных](../../data/data-access-programming-mfc-atl.md).  
  
 `COleDBRecordView` отслеживает положение пользователя в наборе строк, так что представление записей могло обновлять пользовательский интерфейс.  Когда пользователь перемещает к любому конец набора строк, представление записей запрещает объекты пользовательского интерфейса — например пунктов меню или кнопки панели инструментов для перемещения — далее в одном направлении.  
  
 Дополнительные сведения о классах набора строк см. в статье [Использование шаблонов объекта\-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## Требования  
 **Header:**  afxoledb.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)