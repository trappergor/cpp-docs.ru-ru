---
title: "COleDBRecordView-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- MFC, OLE DB
- COleDBRecordView class
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 89b5cb175900d11854dcad03440a1ef0bfb8cff9
ms.lasthandoff: 02/24/2017

---
# <a name="coledbrecordview-class"></a>COleDBRecordView-класс
Представление, которое отображает записи базы данных в элементах управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|Создает объект `COleDBRecordView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Возвращает стандартный `HRESULT` значение.|  
|[COleDBRecordView::OnMove](#onmove)|Обновляет текущую запись (если это «грязный») в источнике данных и затем переходит к указанной записи (следующего, предыдущего, первого или последнего).|  
  
## <a name="remarks"></a>Примечания  
 Это представление является представление формы, непосредственно подключенные к `CRowset` объекта. Представление создается на основе ресурс шаблона диалоговых окон и отображает поля `CRowset` в элементах управления шаблона диалогового окна. `COleDBRecordView` Объект использует обмен данными диалоговых окон (DDX) и навигационные функции встроены в `CRowset`, для автоматизации перемещения данных между элементами управления формы и полями набора строк. `COleDBRecordView`также предоставляет реализацию по умолчанию для перехода к первой, следующего, предыдущего или последней записи и интерфейс для обновления записи в данный момент в представлении.  
  
 Можно использовать функции DDX с **COleDbRecordView** для получения данных непосредственно из набора записей базы данных и его отображения в элементе управления диалогового окна. Следует использовать **DDX_\* ** методов (таких как `DDX_Text`), а не **DDX_Field\* ** функции (такие как `DDX_FieldText`) с **COleDbRecordView**. `DDX_FieldText`не будет работать с **COleDbRecordView** из-за `DDX_FieldText` берет дополнительный аргумент типа **CRecordset\* ** (для `CRecordView`) или **CDaoRecordset\* ** (для `CDaoRecordView`).  
  
> [!NOTE]
>  Если вы работаете с классами объектов доступа к данным (DAO), а не классы шаблонов потребителей OLE DB, используйте класс [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) вместо. Дополнительные сведения см. в статье [Обзор: программирования баз данных](../../data/data-access-programming-mfc-atl.md).  
  
 `COleDBRecordView`сохраняет сведения о положение пользователя в наборе строк, чтобы представление записей можно обновить пользовательский интерфейс. При перемещении либо конца набора строк, представление записей отключает пользователя интерфейса объектов â €» такие, как элементы меню или панель инструментов кнопки â €» для перемещения в одном направлении.  
  
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
 Содержит нулем строку, имя ресурса шаблона диалогового окна.  
  
 `nIDTemplate`  
 Содержит идентификатор ресурса шаблона диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 При создании объекта типа производным от `COleDBRecordView`, вызовите один из конструкторов для создания объекта представления и определения ресурса диалогового окна, лежащие в основе представления. Ресурс можно определить по имени (передавать строку в качестве аргумента конструктору) или по его Идентификатору (pass целое число без знака в качестве аргумента).  
  
> [!NOTE]
>  Производный класс *необходимо* предоставить свой собственный конструктор. В конструкторе, вызвав конструктор, `COleDBRecordView::COleDBRecordView`, имя ресурса или идентификатор в качестве аргумента.  
  
##  <a name="ongetrowset"></a>COleDBRecordView::OnGetRowset  
 Возвращает дескриптор для **CRowset<> </> ** объект, связанный с представлением записи.  
  
```  
virtual CRowset<>* OnGetRowset(Â) = 0;  
 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член для создания или получения объекта набора строк и возвращает дескриптор его необходимо переопределить. Если объявляется класс представления записей с помощью классов, мастер создает переопределение по умолчанию. Реализация по умолчанию для классов возвращает дескриптор набора строк, хранится в представлении записей, если таковой существует. Если нет, он создает объект набора строк типа, указанный с ClassWizard и вызывает его **откройте** член для открытия таблицы или выполнить запрос и затем возвращает дескриптор для объекта.  
  
> [!NOTE]
>  Предшествующему MFC 7.0 `OnGetRowset` возвращается указатель `CRowset`. Если у вас есть код, который вызывает `OnGetRowset`, необходимо изменить тип возвращаемого значения для шаблона класса **CRowset<>**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDatabase&#38;](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]  
  
 Дополнительные сведения и примеры см. в статье [представления записей: использование представления записей](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>COleDBRecordView::OnMove  
 Переход к другой записи в набор строк и отображения его поля в элементах управления записи просмотра.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDMoveCommand`  
 Одно из следующих значений ИД стандартных команд:  
  
- `ID_RECORD_FIRST`Â Â Â перемещение к первой записи в наборе записей.  
  
- `ID_RECORD_LAST`Â Â Â перейти к последней записи в наборе записей.  
  
- `ID_RECORD_NEXT`Â Â Â перемещения к следующей записи в наборе записей.  
  
- `ID_RECORD_PREV`Â Â Â переместить предыдущие записи в наборе записей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если перемещение прошло успешно; в противном случае — 0, если запрос на перемещение был отклонен.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает соответствующий **перемещение** функцию-член `CRowset` объект, связанный с представлением записи.  
  
 По умолчанию `OnMove` обновление текущей записи в источнике данных, если пользователь изменил ее в представлении записей.  
  
 Мастер приложения создает ресурс меню с первой записи, последней записи, следующей записи и предыдущей записи пунктов меню. Если выбран параметр Закрепляемая панель инструментов приложения мастер также создает панель инструментов с кнопками, соответствующие этим командам.  
  
 При перемещении за последней записью в наборе записей, представление записей продолжают отображаться последней записи. При перемещении назад после первой записи в представлении записей продолжают отображаться первой записи.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




