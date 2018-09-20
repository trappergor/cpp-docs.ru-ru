---
title: Функции обмена данными диалоговых окнах для CRecordView и CDaoRecordView | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- DDX_Field functions [MFC]
- ODBC [MFC], dialog data exchange (DDX) support
- DDX (dialog data exchange) [MFC], database support
- DDX (dialog data exchange) [MFC], functions
- databases [MFC], dialog data exchange (DDX) support
- DAO [MFC], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 295e19d875585e0ea166dfce552866b8c1fc81b7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392274"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>Функции обмена данными в диалоговых окнах для CRecordView и CDaoRecordView

В этом разделе перечислены ddx_field-функции, используемые для обмена данными между [CRecordset](../../mfc/reference/crecordset-class.md) и [CRecordView](../../mfc/reference/crecordview-class.md) формы или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) и [ CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) формы.

> [!NOTE]
>  Ddx_field-функции похожи на функции DDX тем, что они обмениваются данными с элементами управления в форме. Но в отличие от DDX, обмена данными с полями из этого представления ассоциированным объектом набора записей, а не с полями самого представления записи. Дополнительные сведения см. в разделе классы `CRecordView` и `CDaoRecordView`.

### <a name="ddxfield-functions"></a>Ddx_field-функции

|||
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Передает целочисленные данные между элементом набора записей поля данных и индекс текущего выделенного фрагмента в поле со списком в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|
|[DDX_FieldCBString](#ddx_fieldcbstring)|Передача `CString` поле данных между элементом набора записей поля данных и поле ввода в поле со списком `CRecordView` или `CDaoRecordView`. При перемещении данных из набора записей в элементе управления, эта функция выбирает элемент в поле со списком, который начинается с символов в указанной строке.|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Передача `CString` поле данных между элементом набора записей поля данных и поле ввода в поле со списком `CRecordView` или `CDaoRecordView`. При перемещении данных из набора записей в элементе управления, эта функция выбирает элемент в поле со списком, точно соответствующую указанной строке.|
|[DDX_FieldCheck](#ddx_fieldcheck)|Передает логический тип данных между элементом набора записей поля данных и типа "флажок" в `CRecordView` или `CDaoRecordView`.|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Передает целочисленные данные между элементом набора записей поля данных и индекс текущего выделенного фрагмента в поле со списком в `CRecordView` или `CDaoRecordView`.|
|[DDX_FieldLBString](#ddx_fieldlbstring)|Управляет передачей [CString](../../atl-mfc-shared/reference/cstringt-class.md) данных между элементами данных полей набора записей и управления списка. При перемещении данных из набора записей в элементе управления, эта функция выбирает элемент в списке, которая начинается с символов в указанной строке.|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Управляет передачей `CString` данных между элементами данных полей набора записей и управления списка. При перемещении данных из набора записей в элементе управления, эта функция выбирает первый элемент, точно соответствующую указанной строке.|
|[DDX_FieldRadio](#ddx_fieldradio)|Передает целочисленные данные между элементом набора записей поля данных и группу переключателей в `CRecordView` или `CDaoRecordView`.|
|[DDX_FieldScroll](#ddx_fieldscroll)|Задает или получает позицию прокрутки полосы прокрутки в `CRecordView` или `CDaoRecordView`. Вызов из вашей [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) функции.|
|[DDX_FieldSlider](#ddx_fieldslider)|Синхронизирует позицию бегунка элемента управления "ползунок" в представлении записей и `int` элемента данных поля в наборе записей. |
|[DDX_FieldText](#ddx_fieldtext)|Перегруженные версии доступны для передачи `int`, **UINT**, **long**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float** , **двойные**, **короткие**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), и [COleCurrency](../../mfc/reference/colecurrency-class.md) данных между элементом поля данных набора записей и изменения в поле `CRecordView` или `CDaoRecordView`.|

##  <a name="ddx_fieldcbindex"></a>  DDX_FieldCBIndex

`DDX_FieldCBIndex` Функция синхронизирует индекс выбранного элемента в элементе управления поля списка элемента управления полем со списком в представлении записей и `int` элемента данных поля в наборе записей, связанный с представлением записи.

```
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

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.

*Индекс*<br/>
Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.

*pRecordset*<br/>
Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, с которым обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей в элементе управления, эта функция задает выделение в элементе управления, основываясь на значении, заданном в *индекс*. При перемещении из набора записей в элемент управления Если набор записей поле имеет значение Null, MFC задает значение индекса 0. При перемещении из элемента управления в набор записей Если элемент управления является пустым, или если элемент не выбран, поля записей имеет значение 0.

Используйте первой версии, если вы работаете с классы на основе ODBC. Во второй версии следует используйте при работе с классами основе DAO.

Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Пример

См. в разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Пример будет выглядеть для `DDX_FieldCBIndex`.

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

##  <a name="ddx_fieldcbstring"></a>  DDX_FieldCBString

`DDX_FieldCBString` Функция управляет передачей [CString](../../atl-mfc-shared/reference/cstringt-class.md) данных между поле ввода элемента управления полем со списком в представлении записей и `CString` элемента данных поля в наборе записей, связанный с представлением записи.

```
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

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.

*значение*<br/>
Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.

*pRecordset*<br/>
Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, с которым обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей в элементе управления, эта функция задает текущее выделение в поле со списком в первую строку, которая начинается с символов в строку, указанную в *значение*. При перемещении из набора записей с элементом управления, набор записей является ли поле значение Null, любой выбор будет удален из поля со списком, и поле ввода поля со списком имеет значение пустое. При перемещении из элемента управления в набор записей, если элемент управления является пустым, набор записей поля задается значение Null Если поле допускает.

Используйте первой версии, если вы работаете с классы на основе ODBC. Во второй версии следует используйте при работе с классами основе DAO.

Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Пример

См. в разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. В пример включен вызов `DDX_FieldCBString`.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="ddx_fieldcbstringexact"></a>  DDX_FieldCBStringExact

`DDX_FieldCBStringExact` Функция управляет передачей [CString](../../atl-mfc-shared/reference/cstringt-class.md) данных между поле ввода элемента управления полем со списком в представлении записей и `CString` элемента данных поля в наборе записей, связанный с представлением записи.

```
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

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.

*значение*<br/>
Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.

*pRecordset*<br/>
Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, с которым обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей в элементе управления, эта функция задает текущее выделение в поле со списком в первую строку, которая точно совпадает с строкой, указанной в *значение*. При перемещении из набора записей с элементом управления, набор записей является ли поле значение NULL, любой выбор будет удален из поля со списком, и поле ввода поля со списком имеет значение пустое. При перемещении из элемента управления в набор записей Если элемент управления является пустым, поля записей задается значение NULL.

Используйте первой версии, если вы работаете с классы на основе ODBC. Во второй версии следует используйте при работе с классами основе DAO.

Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Пример

См. в разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldCBStringExact` будет выглядеть.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

##  <a name="ddx_fieldcheck"></a>  DDX_FieldCheck

`DDX_FieldCheck` Функция управляет передачей **int** данных между управления "флажок" в диалоговом окне, представлении формы или объекте представления элемента управления и **int** элемент данных диалоговое окно, представлении формы или элемента управления Объект представления.

```
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

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор ресурса элемента управления "флажок", связанного со свойством элемента управления.

*значение*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, обмен данными с помощью которого осуществляется.

*pRecordset*<br/>
Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, с которым обмен данными.

### <a name="remarks"></a>Примечания

При `DDX_FieldCheck` вызове *значение* присваивается текущее состояние элемента управления "флажок", или состояние элемента управления имеет значение *значение*, в зависимости от направления передачи.

Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

##  <a name="ddx_fieldlbindex"></a>  DDX_FieldLBIndex

`DDX_FieldLBIndex` Функция синхронизирует индекс выбранного элемента в элементе управления списке в представлении записей и **int** элемента данных поля в наборе записей, связанный с представлением записи.

```
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

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.

*Индекс*<br/>
Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.

*pRecordset*<br/>
Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, с которым обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей в элементе управления, эта функция задает выделение в элементе управления, основываясь на значении, заданном в *индекс*. При перемещении из набора записей в элемент управления Если набор записей поле имеет значение Null, MFC задает значение индекса 0. При перемещении из элемента управления в набор записей Если элемент управления является пустым, поля записей равен 0.

Используйте первой версии, если вы работаете с классы на основе ODBC. Во второй версии следует используйте при работе с классами основе DAO.

Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Пример

См. в разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

##  <a name="ddx_fieldlbstring"></a>  DDX_FieldLBString

`DDX_FieldLBString` Копирует текущее выделение из списка в представлении записей для [CString](../../atl-mfc-shared/reference/cstringt-class.md) элемента данных поля в наборе записей, связанный с представлением записи.

```
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

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.

*значение*<br/>
Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.

*pRecordset*<br/>
Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, с которым обмен данными.

### <a name="remarks"></a>Примечания

В обратном направлении, эта функция задает текущее выделение в поле со списком в первую строку, который начинается с символов в строку, указанную с *значение*. При перемещении из набора записей в элемент управления набор записей является ли поле значение Null, любого выделения удаляется из списка. При перемещении из элемента управления в набор записей Если элемент управления является пустым, поля записей задается значение Null.

Используйте первой версии, если вы работаете с классы на основе ODBC. Во второй версии следует используйте при работе с классами основе DAO.

Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Пример

См. в разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldLBString` будет выглядеть.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

##  <a name="ddx_fieldlbstringexact"></a>  DDX_FieldLBStringExact

`DDX_FieldLBStringExact` Функция копирует текущее выделение из списка в представлении записей для [CString](../../atl-mfc-shared/reference/cstringt-class.md) элемента данных поля в наборе записей, связанный с представлением записи.

```
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

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.

*значение*<br/>
Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.

*pRecordset*<br/>
Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, с которым обмен данными.

### <a name="remarks"></a>Примечания

В обратном направлении, эта функция задает текущее выделение в поле со списком в первую строку, которая точно совпадает с строкой, указанной в *значение*. При перемещении из набора записей в элемент управления набор записей является ли поле значение Null, любого выделения удаляется из списка. При перемещении из элемента управления в набор записей Если элемент управления является пустым, поля записей задается значение Null.

Используйте первой версии, если вы работаете с классы на основе ODBC. Во второй версии следует используйте при работе с классами основе DAO.

Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Пример

См. в разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldLBStringExact` будет выглядеть.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

##  <a name="ddx_fieldradio"></a>  DDX_FieldRadio

`DDX_FieldRadio` Функция связывает отсчитываемый от нуля **int** переменную-член набора записей представления записей с помощью выбранного переключателя в группе переключателей в представлении записей.

```
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

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор первого в группе (с помощью стиля WS_GROUP) смежные переключателей в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.

*значение*<br/>
Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.

*pRecordset*<br/>
Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, с которым обмен данными.

### <a name="remarks"></a>Примечания

При передаче из поля набора записей в представлении, эта функция включает *n-й* "переключатель" (от нуля), а также отключает другие кнопки. В обратном направлении эта функция задает для поля набора записей порядковый номер переключателя, является в данный момент (флажок установлен). При перемещении из набора записей в элемент управления Если набор записей поле имеет значение Null, кнопка "Нет" будет выбрана. При перемещении из элемента управления в набор записей Если элемент управления не выбран, поля записей будет присвоено значение Null Если поле допускает.

Используйте первой версии, если вы работаете с классы на основе ODBC. Во второй версии следует используйте при работе с классами основе DAO.

Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Пример

См. в разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldRadio` будет выглядеть.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

##  <a name="ddx_fieldscroll"></a>  DDX_FieldScroll

`DDX_FieldScroll` Функция синхронизирует позицию прокрутки полосы прокрутки в представлении записей и **int** элемента данных поля в наборе записей, связанного с представлением записи (или любой целочисленной переменной, выберите его, чтобы сопоставить) .

```
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

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор первого в группе (с помощью стиля WS_GROUP) смежные переключателей в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.

*значение*<br/>
Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.

*pRecordset*<br/>
Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, с которым обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей в элементе управления, эта функция задает позицию прокрутки полосы прокрутки к значению, указанному в *значение*. При перемещении из набора записей в элемент управления Если набор записей поле имеет значение Null, полосы прокрутки равен 0. При перемещении из элемента управления в набор записей Если элемент управления является пустым, значение поля набора записей равен 0.

Используйте первой версии, если вы работаете с классы на основе ODBC. Во второй версии следует используйте при работе с классами основе DAO.

Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Пример

См. в разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldScroll` будет выглядеть.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

  ## <a name="nameddxfieldslidera--ddxfieldslider"></a>Имя = «ddx_fieldslider» ></a> DDX_FieldSlider
`DDX_FieldSlider` Функция синхронизирует позицию бегунка элемента управления "ползунок" в представлении записей и **int** элемента данных поля в наборе записей, связанного с представлением записи (или любой целочисленной переменной, выберите его, чтобы сопоставить).

### <a name="syntax"></a>Синтаксис

  ```
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

*pDX*<br/>
Указатель на [CDataExchange](cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор ресурса элемента управления "ползунок".

*значение*<br/>
Ссылка на значение для обмена. Этот параметр содержит или будет использоваться для установки текущую позицию бегунка элемента управления "ползунок".

*pRecordset*<br/>
Указатель на соответствующий `CRecordset` или `CDaoRecordset` объекта, с которым обмен данными.

### <a name="remarks"></a>Примечания

При перемещении данных из набора записей "ползунок", эта функция задает положение ползунка к значению, указанному в *значение*. При перемещении из набора записей в элемент управления Если набор записей поле имеет значение Null, положение элемента управления "ползунок" имеет значение 0. При перемещении из элемента управления в набор записей Если элемент управления является пустым, значение поля набора записей равен 0.

`DDX_FieldSlider` не обмениваться данными диапазона с элементами управления "ползунок", можно настроить диапазон, а не просто позиция.

Первое переопределение функции следует используйте, если вы работаете с классы на основе ODBC. Используйте второе переопределение с помощью классов на основе DAO.

Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об DDX для `CRecordView` и `CDaoRecordView` поля, см. в разделе [представления записей](../../data/record-views-mfc-data-access.md). Сведения об элементах управления "ползунок", см. в разделе [использование CSliderCtrl](../using-csliderctrl.md).

### <a name="example"></a>Пример

См. в разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldSlider` будет выглядеть.

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

### <a name="see-also"></a>См. также

[Макросы и глобальные объекты](mfc-macros-and-globals.md)

##  <a name="ddx_fieldtext"></a>  DDX_FieldText

`DDX_FieldText` Функция управляет передачей **int**, **короткие**, **long**, параметр DWORD под [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **двойные**, **BOOL**, или **БАЙТОВ** данных между элементом управления поля ввода и элементами данных полей набора записей.

```
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

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*nIDC*<br/>
Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.

*значение*<br/>
Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта. Тип данных значения зависит от того, какие из перегруженных версий `DDX_FieldText` использовании.

*pRecordset*<br/>
Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, с которым обмен данными. Этот указатель позволяет `DDX_FieldText` для обнаружения и установки значений Null.

### <a name="remarks"></a>Примечания

Для [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объектов, `DDX_FieldText` также управляет передачи [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), и [COleCurrency](../../mfc/reference/colecurrency-class.md) значения. Поле ввода пустым указывает значение Null. При перемещении из набора записей в элемент управления, если набор записей поле имеет значение Null, устанавливается поле ввода пустым. При перемещении из элемента управления в набор записей Если элемент управления является пустым, поля записей задается значение Null.

Использовать версии с [CRecordset](../../mfc/reference/crecordset-class.md) параметров при работе с классами основе ODBC. Использовать версии с [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) параметров при работе с классами основе DAO.

Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об DDX для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Пример

Следующие `DoDataExchange` работать для [CRecordView](../../mfc/reference/crecordview-class.md) содержит `DDX_FieldText` функция вызывает для трех типов данных: `IDC_COURSELIST` является списком; другие два элемента управления, поля ввода. Для программирования DAO *m_pSet* параметр является указателем на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]


### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
