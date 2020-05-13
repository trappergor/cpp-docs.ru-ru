---
title: Функции обмена данными в диалоговых окнах для CRecordView и CDaoRecordView
ms.date: 09/17/2019
f1_keywords:
- AFXDAO/DDX_FieldCBIndex
- AFXDAO/DDX_FieldCBString
- AFXDAO/DDX_FieldCBStringExact
- AFXDAO/DDX_FieldCheck
- AFXDAO/DDX_FieldLBIndex
- AFXDAO/DDX_FieldLBString
- AFXDAO/DDX_FieldLBStringExact
- AFXDAO/DDX_FieldRadio
- AFXDAO/DDX_FieldScroll
- AFXDAO/DDX_FieldText
helpviewer_keywords:
- DDX_Field functions [MFC]
- ODBC [MFC], dialog data exchange (DDX) support
- DDX (dialog data exchange) [MFC], database support
- DDX (dialog data exchange) [MFC], functions
- databases [MFC], dialog data exchange (DDX) support
- DAO [MFC], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
ms.openlocfilehash: 3128b1ba459cb017d1cdb2321bc55d865aa4f8b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365777"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>Функции обмена данными в диалоговых окнах для CRecordView и CDaoRecordView

В этой теме перечислены функции DDX_Field, используемые для обмена данными между [CRecordset](../../mfc/reference/crecordset-class.md) и [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) и [cDaoRecordView](../../mfc/reference/cdaorecordview-class.md) форме. DAO используется с базами данных Access и поддерживается в Office 2013. DAO 3.6 является окончательной версией, и он считается устаревшим.

> [!NOTE]
> DDX_Field функции похожи на функции DDX в том, что они обмениваются данными с элементами управления в форме. Но в отличие от DDX, они обмениваются данными с полями связанного с типом объекта записи представления, а не с полями самого представления записи. Для получения дополнительной `CRecordView` информации, см. `CDaoRecordView`

### <a name="ddx_field-functions"></a>функции DDX_Field

|||
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Передача неосподданных данных между участником данных полевых данных и индексом текущего выбора в комбо-поле в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|
|[DDX_FieldCBString](#ddx_fieldcbstring)|Передача `CString` данных между членом данных полевого набора и управлением комбо-коробкой в `CRecordView` или `CDaoRecordView`. При перемещении данных из набора записей в управление эта функция выбирает элемент в комбо-поле, который начинается с символов в указанной строке.|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Передача `CString` данных между членом данных полевого набора и управлением комбо-коробкой в `CRecordView` или `CDaoRecordView`. При перемещении данных из набора записей в управление эта функция выбирает элемент в комбо-коробке, который точно соответствует указанной строке.|
|[DDX_FieldCheck](#ddx_fieldcheck)|Передача данных Boolean между участником данных полевого `CDaoRecordView`набора и флажками в или `CRecordView` .|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Передача неослоеданных данных между участником данных поля записи `CRecordView` `CDaoRecordView`и индексом текущего выбора в поле списка в или .|
|[DDX_FieldLBString](#ddx_fieldlbstring)|Управляет передачей данных [CString](../../atl-mfc-shared/reference/cstringt-class.md) между управлением список ящиков и полевыми данными, входящие в набор записей. При перемещении данных из набора записей в элемент управления эта функция выбирает элемент в поле списка, который начинается с символов в указанной строке.|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Управляет передачей `CString` данных между управлением список ящиков и полевыми данными, входящие в состав регистрации. При перемещении данных из набора записей в элемент управления эта функция выбирает первый элемент, который точно соответствует указанной строке.|
|[DDX_FieldRadio](#ddx_fieldradio)|Передача несколько данных между участником данных полевых данных `CRecordView` `CDaoRecordView`и группой радиокнопок в или .|
|[DDX_FieldScroll](#ddx_fieldscroll)|Устанавливает или получает положение прокрутки `CRecordView` управления `CDaoRecordView`баром прокрутки в или . Звоните из функции [DoFieldExchange.](../../mfc/reference/cdaorecordset-class.md#dofieldexchange)|
|[DDX_FieldSlider](#ddx_fieldslider)|Синхронизирует положение большого пальца управления ползунок в `int` представлении записи и элемента данных поля в наборе записей. |
|[DDX_FieldText](#ddx_fieldtext)|Перегруженные версии доступны для `int`передачи, **UINT**, **длинные** `DWORD`, , [CString](../../atl-mfc-shared/reference/cstringt-class.md), **плавать**, **двойной**, **короткий**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), и [COleCurrency](../../mfc/reference/colecurrency-class.md) данные между записью поля данных члена и редактировать окно в `CRecordView` или `CDaoRecordView`.|

## <a name="ddx_fieldcbindex"></a><a name="ddx_fieldcbindex"></a>DDX_FieldCBIndex

Функция `DDX_FieldCBIndex` синхронизирует индекс выбранного элемента в управлении полем списка управления комбо-боксом `int` в представлении записи и члена данных поля, связанного с представлением записи.

```cpp
void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView.](../../mfc/reference/cdaorecordview-class.md)

*Индекс*<br/>
Ссылка на члена данных `CRecordset` поля `CDaoRecordset` в связанном или объекте.

*pRecordset*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) с которым обмениваются данными.

### <a name="remarks"></a>Remarks

При перемещении данных из уровня записи в элемент управления эта функция устанавливает выделение в элементе управления на основе значения, указанного в *индексе.* При переходе из рекорда в контроль, если поле записи Null, MFC устанавливает значение индекса до 0. При передаче от элемента к рекорду, если элемент пустой или если элемент не выбран, поле записи устанавливается до 0.

Используйте первую версию, если вы работаете с классами на основе ODBC. Используйте вторую версию, если вы работаете с классами dAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Для примеров и дополнительной информации о DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [Record Views](../../data/record-views-mfc-data-access.md) [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см.

### <a name="example"></a>Пример

На [примере DDX_FieldText](#ddx_fieldtext) можно ознакомиться с общим примером DDX_Field. Пример будет похож `DDX_FieldCBIndex`на .

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="ddx_fieldcbstring"></a><a name="ddx_fieldcbstring"></a>DDX_FieldCBString

Функция `DDX_FieldCBString` управляет передачей данных [CString](../../atl-mfc-shared/reference/cstringt-class.md) между управлением элементаком управления комбо-коробкой в представлении записи и полевым элементом `CString` данных набора записей, связанных с представлением записи.

```cpp
void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView.](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
Ссылка на члена данных `CRecordset` поля `CDaoRecordset` в связанном или объекте.

*pRecordset*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) с которым обмениваются данными.

### <a name="remarks"></a>Remarks

При перемещении данных из набора записей в управление эта функция устанавливает текущий выбор в комбо-поле в первый ряд, который начинается с символов строки, указанной в *значении.* При передаче из рекорда в управление, если поле записи null, любой выбор удаляется из комбо-коробки и управление мольпового элемента устанавливается на пустоту. При передаче из управления в рекорд, если элемент элемент апогея пуст, поле записей устанавливается в Null, если поле позволяет.

Используйте первую версию, если вы работаете с классами на основе ODBC. Используйте вторую версию, если вы работаете с классами dAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Для примеров и дополнительной информации о DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [Record Views](../../data/record-views-mfc-data-access.md) [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см.

### <a name="example"></a>Пример

На [примере DDX_FieldText](#ddx_fieldtext) можно ознакомиться с общим примером DDX_Field. Пример включает вызов `DDX_FieldCBString`в .

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="ddx_fieldcbstringexact"></a><a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact

Функция `DDX_FieldCBStringExact` управляет передачей данных [CString](../../atl-mfc-shared/reference/cstringt-class.md) между управлением элементаком управления комбо-коробкой в представлении записи и полевым элементом `CString` данных набора записей, связанных с представлением записи.

```cpp
void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView.](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
Ссылка на члена данных `CRecordset` поля `CDaoRecordset` в связанном или объекте.

*pRecordset*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) с которым обмениваются данными.

### <a name="remarks"></a>Remarks

При перемещении данных из набора записей в управление эта функция устанавливает текущий выбор в комбо-поле к первому ряду, которое точно соответствует строке, указанной в *значении.* При передаче из рекорда в управление, если поле рекорда null, любой выбор удаляется из комбо-коробки и коробка для отсылки комбо-бокса становится пустой. При передаче из элемента управления в запись, если элемент элемент пустой, поле записей устанавливается в NULL.

Используйте первую версию, если вы работаете с классами на основе ODBC. Используйте вторую версию, если вы работаете с классами dAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Для примеров и дополнительной информации о DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [Record Views](../../data/record-views-mfc-data-access.md) [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см.

### <a name="example"></a>Пример

На [примере DDX_FieldText](#ddx_fieldtext) можно ознакомиться с общим примером DDX_Field. Призывы `DDX_FieldCBStringExact` к были бы похожи.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="ddx_fieldcheck"></a><a name="ddx_fieldcheck"></a>DDX_FieldCheck

Функция `DDX_FieldCheck` управляет передачей данных **Int** между управлением флажками в диалоговом поле, объектом представления формы или элементом управления и членом **int** data в диалоговом поле, представлением формы или объектом управления.

```cpp
void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор ресурса управления флажком, связанный с свойством управления.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или объекта управления, с которым обмениваются данными.

*pRecordset*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) с которым обмениваются данными.

### <a name="remarks"></a>Remarks

При `DDX_FieldCheck` вызове *значение* устанавливается в текущее состояние управления флажком или значение состояния элемента управления *в*зависимости от направления передачи.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="ddx_fieldlbindex"></a><a name="ddx_fieldlbindex"></a>DDX_FieldLBIndex

Функция `DDX_FieldLBIndex` синхронизирует индекс выбранного элемента в элементе управления полем списка в представлении записи и членом данных **int** field, связанного с представлением записи.

```cpp
void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView.](../../mfc/reference/cdaorecordview-class.md)

*Индекс*<br/>
Ссылка на члена данных `CRecordset` поля `CDaoRecordset` в связанном или объекте.

*pRecordset*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) с которым обмениваются данными.

### <a name="remarks"></a>Remarks

При перемещении данных из уровня записи в элемент управления эта функция устанавливает выделение в элементе управления на основе значения, указанного в *индексе.* При переходе из рекорда в контроль, если поле записи Null, MFC устанавливает значение индекса до 0. При передаче из элемента управления в запись, если элемент пусто, поле записи устанавливается до 0.

Используйте первую версию, если вы работаете с классами на основе ODBC. Используйте вторую версию, если вы работаете с классами dAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Для примеров и дополнительной информации о DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [Record Views](../../data/record-views-mfc-data-access.md) [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см.

### <a name="example"></a>Пример

На [примере DDX_FieldText](#ddx_fieldtext) можно ознакомиться с общим примером DDX_Field.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="ddx_fieldlbstring"></a><a name="ddx_fieldlbstring"></a>DDX_FieldLBString

Копирует `DDX_FieldLBString` текущее выделение элемента управления "список" в представлении записей в элемент данных поля [CString](../../atl-mfc-shared/reference/cstringt-class.md) в наборе записей, связанном с представлением записей.

```cpp
void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView.](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
Ссылка на члена данных `CRecordset` поля `CDaoRecordset` в связанном или объекте.

*pRecordset*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) с которым обмениваются данными.

### <a name="remarks"></a>Remarks

В обратном направлении эта функция устанавливает текущий выбор в поле списка к первому ряду, который начинается с символов в строке, указанной *значением.* При передаче из рекорда в управление, если поле записи null, любой выбор удаляется из окна списка. При передаче из элемента управления в запись, если элемент элемент пустой, поле записей устанавливается на Null.

Используйте первую версию, если вы работаете с классами на основе ODBC. Используйте вторую версию, если вы работаете с классами dAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Для примеров и дополнительной информации о DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [Record Views](../../data/record-views-mfc-data-access.md) [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см.

### <a name="example"></a>Пример

На [примере DDX_FieldText](#ddx_fieldtext) можно ознакомиться с общим примером DDX_Field. Призывы `DDX_FieldLBString` к были бы похожи.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="ddx_fieldlbstringexact"></a><a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact

Функция `DDX_FieldLBStringExact` копирует текущее выделение элемента управления "список" в представлении записей в элемент данных поля [CString](../../atl-mfc-shared/reference/cstringt-class.md) в наборе записей, связанном с представлением записей.

```cpp
void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView.](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
Ссылка на члена данных `CRecordset` поля `CDaoRecordset` в связанном или объекте.

*pRecordset*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) с которым обмениваются данными.

### <a name="remarks"></a>Remarks

В обратном направлении эта функция устанавливает текущий выбор в поле списка к первому ряду, которое точно соответствует строке, указанной в *значении.* При передаче из рекорда в управление, если поле записи null, любой выбор удаляется из окна списка. При передаче из элемента управления в запись, если элемент элемент пустой, поле записей устанавливается на Null.

Используйте первую версию, если вы работаете с классами на основе ODBC. Используйте вторую версию, если вы работаете с классами dAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Для примеров и дополнительной информации о DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [Record Views](../../data/record-views-mfc-data-access.md) [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см.

### <a name="example"></a>Пример

На [примере DDX_FieldText](#ddx_fieldtext) можно ознакомиться с общим примером DDX_Field. Призывы `DDX_FieldLBStringExact` к были бы похожи.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="ddx_fieldradio"></a><a name="ddx_fieldradio"></a>DDX_FieldRadio

Функция `DDX_FieldRadio` связывает переменную нулевого **члена** с записью представления записи с выбранной в настоящее время радиокнопкой в группе радиокнопок в представлении записи.

```cpp
void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор первого в группе (со стилем WS_GROUP) смежных элементов управления кнопкой радио в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView.](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
Ссылка на члена данных `CRecordset` поля `CDaoRecordset` в связанном или объекте.

*pRecordset*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) с которым обмениваются данными.

### <a name="remarks"></a>Remarks

При переносе из поля записи в вид эта функция включает кнопку *nth* radio (нулевая) и выключает другие кнопки. В обратном направлении эта функция устанавливает поле рекорда на обычное число радиокнопки, которая в настоящее время находится на (проверено). При переходе из рекорда в управление, если поле записи Null, кнопка не выбирается. При переходе из управления в рекорд, если элемент управления не выбран, поле записей устанавливается в Null, если поле позволяет это.

Используйте первую версию, если вы работаете с классами на основе ODBC. Используйте вторую версию, если вы работаете с классами dAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Для примеров и дополнительной информации о DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [Record Views](../../data/record-views-mfc-data-access.md) [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см.

### <a name="example"></a>Пример

На [примере DDX_FieldText](#ddx_fieldtext) можно ознакомиться с общим примером DDX_Field. Призывы `DDX_FieldRadio` к были бы похожи.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="ddx_fieldscroll"></a><a name="ddx_fieldscroll"></a>DDX_FieldScroll

`DDX_FieldScroll` Функция синхронизирует положение прокрутки управления баром прокрутки в представлении записи и член данных **int** field, связанный с представлением записи (или с любой равной переменной, которую вы решите сопоставить с ней).

```cpp
void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор первого в группе (со стилем WS_GROUP) смежных элементов управления кнопкой радио в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView.](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
Ссылка на члена данных `CRecordset` поля `CDaoRecordset` в связанном или объекте.

*pRecordset*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) с которым обмениваются данными.

### <a name="remarks"></a>Remarks

При перемещении данных из уровня записи в элемент управления эта функция устанавливает положение прокрутки элемента управления прокруткой панели к значению, указанному в *значении.* При передаче из рекорда в управление, если поле записи Null, управление панелью прокрутки устанавливается до 0. При передаче из элемента управления в запись, если элемент элемент пуст, значение поля записи составляет 0.

Используйте первую версию, если вы работаете с классами на основе ODBC. Используйте вторую версию, если вы работаете с классами dAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Для примеров и дополнительной информации о DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [Record Views](../../data/record-views-mfc-data-access.md) [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см.

### <a name="example"></a>Пример

На [примере DDX_FieldText](#ddx_fieldtext) можно ознакомиться с общим примером DDX_Field. Призывы `DDX_FieldScroll` к были бы похожи.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="ddx_fieldslider"></a><a name="ddx_fieldslider"></a>DDX_FieldSlider

`DDX_FieldSlider` Функция синхронизирует положение большого пальца управления ползунок в представлении записи и член данных **int** field of the recordset, связанный с представлением записи (или с любой равномерной переменной, которую вы решите сопоставить с ней).

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DDX_FieldSlider(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset );

void AFXAPI DDX_FieldSlider(
   CDataExchange* pDX,
   int nIDC,
   int& value,
   CDaoRecordset* pRecordset );
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор ресурса управления ползунок.

*value*<br/>
Ссылка на значение, подаваемый на обмен. Этот параметр удерживает или будет использоваться для установки текущего положения большого пальца слайдера.

*pRecordset*<br/>
Указатель на `CRecordset` связанный `CDaoRecordset` или объект, с которым обмениваются данными.

### <a name="remarks"></a>Remarks

При перемещении данных из набора данных в слайдер эта функция устанавливает положение слайдера к значению, указанному в *значении.* При передаче из рекорда в управление, если поле записи Null, положение управления ползунок устанавливается до 0. При передаче от элемента управления к рекорду, если элемент пусто, значение поля рекорда составляет 0.

`DDX_FieldSlider`не обмениваются информацией о диапазоне с элементами управления ползунок, способными устанавливать диапазон, а не просто положение.

Используйте первый переопределение функции, если вы работаете с классами на основе ODBC. Используйте второй переопределение с классами на основе DAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../dialog-data-exchange-and-validation.md). Для примеров и дополнительной информации о DDX для `CRecordView` и `CDaoRecordView` полях, см. [Record Views](../../data/record-views-mfc-data-access.md) Для получения информации о элементах управления слайдер, [см.](../using-csliderctrl.md)

### <a name="example"></a>Пример

На [примере DDX_FieldText](#ddx_fieldtext) можно ознакомиться с общим примером DDX_Field. Призывы `DDX_FieldSlider` к были бы похожи.

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="ddx_fieldtext"></a><a name="ddx_fieldtext"></a>DDX_FieldText

Функция `DDX_FieldText` управляет передачей данных типа **int**, **short**, **long**, DWORD, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **double**, **BOOL**, или **BYTE** между элементом управления "поле ввода" и элементами данных поля элемента записей.

```cpp
void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    UINT& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    long& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    float& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    double& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    short& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BOOL& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    long& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    float& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    double& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    COleCurrency& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в объекте [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView.](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
Ссылка на члена данных `CRecordset` поля `CDaoRecordset` в связанном или объекте. Тип значения данных зависит от того, какую из перегруженных версий `DDX_FieldText` вы используете.

*pRecordset*<br/>
Указатель на объект [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) с которым обмениваются данными. Этот указатель `DDX_FieldText` позволяет обнаруживать и устанавливать значения Null.

### <a name="remarks"></a>Remarks

Для объектов [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)`DDX_FieldText` также управляет передачей значений [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)и [COleCurrency](../../mfc/reference/colecurrency-class.md). Элемент пустого элемента управления окном для отсечения указывает значение Null. При передаче из рекордного уровня в управление, если поле записи null, коробка отсечения устанавливается на пустоту. При передаче из элемента управления в запись, если элемент элемент пустой, поле записей устанавливается на Null.

Используйте версии с параметрами [CRecordset,](../../mfc/reference/crecordset-class.md) если вы работаете с классами на основе ODBC. Используйте версии с параметрами [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) если вы работаете с классами dAO.

Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Для примеров и дополнительной информации о DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [Record Views](../../data/record-views-mfc-data-access.md) [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см.

### <a name="example"></a>Пример

Следующая `DoDataExchange` функция для [CRecordView](../../mfc/reference/crecordview-class.md) содержит `DDX_FieldText` функции `IDC_COURSELIST` вызовов для трех типов данных: это комбо-бокс; два других элемента управления являются коробками для отсеиваний. Для программирования DAO, *m_pSet* параметр является указателем на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)
