---
title: Класс COleDBRecordView | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b5494cd21f1385bbd9d89a37725998b521e6452
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373887"
---
# <a name="coledbrecordview-class"></a>COleDBRecordView-класс

Представление, которое отображает записи базы данных в элементах управления.

## <a name="syntax"></a>Синтаксис

```
class COleDBRecordView : public CFormView
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|Создает объект `COleDBRecordView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Возвращает стандартное значение HRESULT.|
|[COleDBRecordView::OnMove](#onmove)|Обновляет текущую запись (если "грязный") в источнике данных и затем переходит к указанной записи (следующего, предыдущего, первого или последнего).|

## <a name="remarks"></a>Примечания

Представление — представление формы, который напрямую подключен к `CRowset` объекта. Представление создается на основе ресурса шаблона диалоговых окон и отображает поля `CRowset` в элементах управления шаблона диалогового окна. `COleDBRecordView` Объект использует обмен данными диалоговых окон (DDX) и навигационные функции встроены в `CRowset`, чтобы автоматизировать движение данных между полями набора строк и элементов управления на форме. `COleDBRecordView` также предоставляет реализацию по умолчанию для перехода к первой, далее, предыдущих или последних записей и интерфейс для обновления записи в данный момент в представлении.

Можно использовать функции DDX с `COleDbRecordView` для получения данных непосредственно из набора записей базы данных и отображения его в элемент управления диалогового окна. Следует использовать `DDX_*` методы (такие как `DDX_Text`), а не `DDX_Field*` функции (такие как `DDX_FieldText`) с `COleDbRecordView`. `DDX_FieldText` не будет работать с `COleDbRecordView` поскольку `DDX_FieldText` принимает дополнительный аргумент типа `CRecordset*` (для `CRecordView`) или `CDaoRecordset*` (для `CDaoRecordView`).

> [!NOTE]
>  Если вы работаете с классами объектов доступа к данным (DAO) вместо классов шаблонов потребителей OLE DB, используйте класс [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) вместо этого. Дополнительные сведения см. в статье [Обзор: программирования баз данных,](../../data/data-access-programming-mfc-atl.md).

`COleDBRecordView` отслеживает этой положение пользователя в наборе строк, представление записей можно обновить пользовательский интерфейс. Когда пользователь перемещает в любой конец набора строк, представление записей отключает объектов пользовательского интерфейса — например пункты меню или кнопки панели инструментов — для перемещения в одном направлении.

Дополнительные сведения о классы набора строк, см. в разделе [с помощью шаблонов потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md) статьи.

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

##  <a name="coledbrecordview"></a>  COleDBRecordView::COleDBRecordView

Создает объект `COleDBRecordView`.

```
COleDBRecordView(LPCTSTR lpszTemplateName);
COleDBRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Параметры

*lpszTemplateName*<br/>
Содержащий заканчивающуюся нулем строку, которая является именем ресурса шаблона диалогового окна.

*nIDTemplate*<br/>
Содержит идентификатор ресурса шаблона диалогового окна.

### <a name="remarks"></a>Примечания

При создании объекта типа производным от `COleDBRecordView`, вызвать один из конструкторов для создания объекта view и определения ресурса диалогового окна, на котором основано представление. Вы можете определить ресурс, либо по имени (pass строку в качестве аргумента в конструктор), либо по его Идентификатору (pass целое число без знака в качестве аргумента).

> [!NOTE]
>  Производный класс *необходимо* предоставить собственный конструктор. В конструкторе, вызвать конструктор `COleDBRecordView::COleDBRecordView`, с именем ресурса или идентификатор в качестве аргумента.

##  <a name="ongetrowset"></a>  COleDBRecordView::OnGetRowset

Возвращает дескриптор для **CRowset <>** объекта, связанного с представлением записи.

```
virtual CRowset<>* OnGetRowset() = 0;

```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Эта функция-член для создания или получения объекта набора строк и возвращает его дескриптор необходимо переопределить. Если вы объявляете класс представления записей с помощью классов, мастер создает переопределение по умолчанию. Реализация по умолчанию в ClassWizard возвращает дескриптор набора строк, хранимых в представлении записей, если он существует. Если нет, он создает объект набора строк типа вы указали с ClassWizard и вызывает его `Open` член функции для открытия таблицы или выполнить запрос и возвращает дескриптор для объекта.

> [!NOTE]
>  До MFC 7.0 `OnGetRowset` возвращается указатель на `CRowset`. Если у вас есть код, который вызывает `OnGetRowset`, вам нужно изменить тип возвращаемого значения для шаблона класса **CRowset <>**.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]

Дополнительные сведения и примеры см. в статье [представления записей: использование представления записей](../../data/using-a-record-view-mfc-data-access.md).

##  <a name="onmove"></a>  COleDBRecordView::OnMove

Переходит на другую запись в наборе строк и отображения его поля в элементах управления записи режиме.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>Параметры

*nIDMoveCommand*<br/>
Одно из следующих значений ID стандартную команду:

- ID_RECORD_FIRST — Переход к первой записи в наборе записей.

- ID_RECORD_LAST — Перейти к последней записи в наборе записей.

- ID_RECORD_NEXT — Переход к следующей записи в наборе записей.

- ID_RECORD_PREV — Перейти к предыдущей записи в наборе записей.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если перемещение прошло успешно; в противном случае — 0, если запрос на перемещение был отклонен.

### <a name="remarks"></a>Примечания

Реализация по умолчанию вызывает соответствующий `Move` функцию-член `CRowset` объекта, связанного с представлением записи.

По умолчанию `OnMove` обновляет текущую запись в источнике данных, если пользователь изменил его в представлении записей.

В мастере приложений создает ресурс меню с пунктами меню первой записи, последнюю запись, следующая запись и предыдущей записи. Если выбран параметр Закрепляемая панель инструментов приложения мастер также создает панель инструментов с кнопками, соответствующий этим командам.

При перемещении за последней записью в наборе записей, представление записей продолжают отображаться последнюю запись. Если переместить назад после первой записи, представление записей продолжают отображаться первой записи.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)



