---
title: "COleDBRecordView-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
dev_langs: C++
helpviewer_keywords:
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd827d729af5186d6872536cdaa3d8863d1f8d10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="coledbrecordview-class"></a>COleDBRecordView-класс
Представление, которое отображает записи базы данных в элементах управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|Создает объект `COleDBRecordView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Возвращает стандартный `HRESULT` значение.|  
|[COleDBRecordView::OnMove](#onmove)|Обновляет текущую запись (если «грязных») в источнике данных, а затем перемещает к определенной записи (следующего, предыдущего, первого или последнего).|  
  
## <a name="remarks"></a>Примечания  
 Представление — это представление формы, непосредственно подключенные к `CRowset` объекта. Представление создается на основе ресурс шаблона диалоговых окон и отображает поля `CRowset` в элементах управления шаблона диалогового окна. `COleDBRecordView` Объект использует обмен данными диалоговых окон (DDX) и навигационные функции встроены в `CRowset`, для автоматизации перемещения данных между полями набора строк и элементов управления в форме. `COleDBRecordView`также предоставляет реализацию по умолчанию для перемещения к первому следующего, предыдущего или последней записи и интерфейс для обновления записи в настоящее время для представления.  
  
 Можно использовать функции DDX с **COleDbRecordView** для получения данных непосредственно из набора записей базы данных и его отображения в элементе управления диалогового окна. Следует использовать **DDX_\***  методы (такие как `DDX_Text`), а не **DDX_Field\***  функции (такие как `DDX_FieldText`) с **COleDbRecordView** . `DDX_FieldText`не будет работать с **COleDbRecordView** из-за `DDX_FieldText` принимает дополнительный аргумент типа **CRecordset\***  (для `CRecordView`) или **CDaoRecordset \***  (для `CDaoRecordView`).  
  
> [!NOTE]
>  Если вы работаете с классами объектов доступа к данным (DAO), а не классов шаблонов потребителей OLE DB, используйте класс [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) вместо него. Дополнительные сведения см. в статье [Обзор: программирования баз данных](../../data/data-access-programming-mfc-atl.md).  
  
 `COleDBRecordView`сохраняет сведения о положение пользователя в наборе строк, чтобы представление записей можно обновить пользовательский интерфейс. При перемещении либо конца набора строк, представление записей отключает объекты пользовательского интерфейса — например, пункты меню или кнопки панели инструментов — для перемещения дальнейших в одном направлении.  
  
 Дополнительные сведения о классах строк см. в разделе [с помощью шаблонов потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md) статьи.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxoledb.h  
  
##  <a name="coledbrecordview"></a>COleDBRecordView::COleDBRecordView  
 Создает объект `COleDBRecordView`.  
  
```  
COleDBRecordView(LPCTSTR lpszTemplateName);  
COleDBRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszTemplateName`  
 Содержит строку, завершающуюся значением null, являющееся именем ресурса шаблона диалогового окна.  
  
 `nIDTemplate`  
 Содержит идентификатор ресурса шаблона диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 При создании объекта типа производным от `COleDBRecordView`, вызвать один из конструкторов для создания объекта view и определения ресурса диалогового окна, лежащие в основе представления. Можно указать ресурс по имени (передавать строку в качестве аргумента конструктору) или по его Идентификатору (pass целое число без знака в качестве аргумента).  
  
> [!NOTE]
>  Производный класс *должен* предоставить свой собственный конструктор. В конструкторе, вызвать конструктор `COleDBRecordView::COleDBRecordView`, с именем ресурса или идентификатор в качестве аргумента.  
  
##  <a name="ongetrowset"></a>COleDBRecordView::OnGetRowset  
 Возвращает дескриптор для **CRowset <>** объект, связанный с представлением записи.  
  
```  
virtual CRowset<>* OnGetRowset() = 0;  
 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Необходимо переопределить эту функцию-член для создания или получения объекта набора строк и возвращает его дескриптор. Если объявить класс представления записей с помощью классов, мастер создает переопределение по умолчанию. Реализация по умолчанию мастер классов возвращает дескриптор набора строк, хранится в представлении записей, если он существует. Если нет, он создает объект набора строк типа, указанный с ClassWizard и вызывает его **откройте** член для открытия таблицы или выполнить запрос и возвращает дескриптор для объекта.  
  
> [!NOTE]
>  До MFC 7.0 `OnGetRowset` возвращается указатель `CRowset`. Если у вас есть код, который вызывает `OnGetRowset`, необходимо изменить тип возвращаемого значения для шаблона класса **CRowset <>**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]  
  
 Дополнительные сведения и примеры см. в статье [представления записей: использование представления записей](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>COleDBRecordView::OnMove  
 Переходит к другой записи в наборе строк и отображения его поля в элементах управления записи режиме.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDMoveCommand`  
 Одно из следующих значений ID стандартную команду:  
  
- `ID_RECORD_FIRST`— Перемещение к первой записи в наборе записей.  
  
- `ID_RECORD_LAST`— Переход к последней записи в наборе записей.  
  
- `ID_RECORD_NEXT`— Перемещение к следующей записи в наборе записей.  
  
- `ID_RECORD_PREV`— Переход к предыдущей записи в наборе записей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если перемещение прошло успешно; в противном случае значение 0, если запрос на перемещение запрещен.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает соответствующий **переместить** функцию-член `CRowset` объект, связанный с представлением записи.  
  
 По умолчанию `OnMove` обновляет текущую запись в источнике данных, если пользователь был изменен в режиме записи.  
  
 В мастере приложений создает ресурс меню с пунктами меню первой записи, последнюю запись, следующая запись и предыдущей записи. Если выбран параметр Закрепляемая панель инструментов приложения мастер также создает панель инструментов с кнопками, соответствующий эти команды.  
  
 При перемещении за последней записью в наборе записей, представление записей продолжают отображаться последнюю запись. Если переместить назад после первой записи, представление записей продолжают отображаться первой записи.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



