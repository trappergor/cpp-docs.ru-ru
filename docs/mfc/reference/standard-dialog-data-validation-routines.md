---
title: Стандартные программы проверки данных диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
ms.openlocfilehash: 77b08945c99b9e9e2652a40e5710d8c4e89846b7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269682"
---
# <a name="standard-dialog-data-validation-routines"></a>Стандартные программы проверки данных диалоговых окон

В этом разделе перечислены процедуры проверки (DDV) данных стандартное диалоговое окно, используемые для общих элементов управления диалогового окна MFC.

> [!NOTE]
>  Стандартные данные exchange диалоговых окон, определяются в afxdd_.h файл заголовка. Тем не менее приложения должны иметь afxwin.h.

### <a name="ddv-functions"></a>Функции DDV

|||
|-|-|
|[DDV_MaxChars](#ddv_maxchars)|Проверяет, что количество символов в заданном элементе управления значение не превышает заданного максимального.|
|[DDV_MinMaxByte](#ddv_minmaxbyte)|Проверяет, не будет превышать это значение заданного элемента управления данного **БАЙТОВ** диапазона.|
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|Проверяет, что значение заданного элемента управления не превышает заданный диапазон времени.|
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|Проверяет, не будет превышать это значение заданного элемента управления данного **двойные** диапазона.|
|[DDV_MinMaxDWord](#ddv_minmaxdword)|Проверяет, не будет превышать это значение заданного элемента управления данного **DWORD** диапазона.|
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|Проверяет, не будет превышать это значение заданного элемента управления данного **float** диапазона.|
|[DDV_MinMaxInt](#ddv_minmaxint)|Проверяет, не будет превышать это значение заданного элемента управления данного **int** диапазона.|
|[DDV_MinMaxLong](#ddv_minmaxlong)|Проверяет, не будет превышать это значение заданного элемента управления данного **long** диапазона.|
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|Проверяет, не будет превышать это значение заданного элемента управления данного **longlong приведенным к ПУСТОМУ** диапазона.|
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|Проверяет, что значение заданного элемента управления не превышает указанного диапазона дат.|
|[DDV_MinMaxShort](#ddv_minmaxshort)|Проверяет, не будет превышать это значение заданного элемента управления данного **короткие** диапазона.|
|[DDV_MinMaxSlider](#ddv_minmaxslider)|Проверяет, что значение элемента управления данного ползунка попадает в заданном диапазоне.|
|[DDV_MinMaxUInt](#ddv_minmaxuint)|Проверяет, не будет превышать это значение заданного элемента управления данного **UINT** диапазона.|
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|Проверяет, что заданного элемента управления значение находится между двумя указанными значениями.|
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|Проверяет, не будет превышать это значение заданного элемента управления данного **ULONGLONG** диапазона.|

##  <a name="ddv_maxchars"></a>  DDV_MaxChars

Вызовите `DDV_MaxChars` чтобы убедиться, что количество символов в элементе управления связана с *значение* не превышает *nChars*.

```
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,
    CString const& value,
    int nChars);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*nChars*<br/>
Максимальное допустимое число символов.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxbyte"></a>  DDV_MinMaxByte

Вызовите `DDV_MinMaxByte` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

```
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,
    BYTE value,
    BYTE minVal,
    BYTE maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*minVal*<br/>
Минимальное значение (типа BYTE) разрешено.

*maxVal*<br/>
Максимальное значение (типа BYTE) разрешено.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxdatetime"></a>  DDV_MinMaxDateTime

Вызовите `DDV_MinMaxDateTime` чтобы убедиться, что значение даты и времени в средстве выбора даты и времени элемента управления ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) связан *refValue* попадает *refMinRange*и *refMaxRange*.

```
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление. Удалить этот объект не нужно.

*refValue*<br/>
Ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) или [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, связанный с переменную-член диалоговое окно, представлении формы или объекте представления элемента управления. Этот объект содержит данные для проверки.

*refMinRange*<br/>
Минимальное допустимое значение даты и времени.

*refMaxRange*<br/>
Допустимое значение максимальной даты и времени.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxdouble"></a>  DDV_MinMaxDouble

Вызовите `DDV_MinMaxDouble` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

```
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,
    double const& value,
    double minVal,
    double maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*minVal*<br/>
Минимальное значение (типа **двойные**) разрешено.

*maxVal*<br/>
Максимальное значение (типа **двойные**) разрешено.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxdword"></a>  DDV_MinMaxDWord

Вызовите `DDV_MinMaxDWord` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

```
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,
    DWORD const& value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*minVal*<br/>
Минимальное значение (типа DWORD) разрешено.

*maxVal*<br/>
Максимальное значение (типа DWORD) разрешено.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxfloat"></a>  DDV_MinMaxFloat

Вызовите `DDV_MinMaxFloat` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

```
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,
    float value,
    float minVal,
    float maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*minVal*<br/>
Минимальное значение (типа **float**) разрешено.

*maxVal*<br/>
Максимальное значение (типа **float**) разрешено.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxint"></a>  DDV_MinMaxInt

Вызовите `DDV_MinMaxInt` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

```
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,
    int value,
    int minVal,
    int maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*minVal*<br/>
Минимальное значение (типа **int**) разрешено.

*maxVal*<br/>
Максимальное значение (типа **int**) разрешено.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxlong"></a>  DDV_MinMaxLong

Вызовите `DDV_MinMaxLong` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

```
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,
    long value,
    long minVal,
    long maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*minVal*<br/>
Минимальное значение (типа **long**) разрешено.

*maxVal*<br/>
Максимальное значение (типа **long**) разрешено.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxlonglong"></a>  DDV_MinMaxLongLong

Вызовите `DDV_MinMaxLongLong` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

```
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,
    LONGLONG value,
    LONGLONG minVal,
    LONGLONG maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*minVal*<br/>
Минимальное значение (типа longlong приведенным к ПУСТОМУ) разрешено.

*maxVal*<br/>
Максимальное значение (типа longlong приведенным к ПУСТОМУ) разрешено.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxmonth"></a>  DDV_MinMaxMonth

Вызовите `DDV_MinMaxMonth` чтобы убедиться, что значение даты и времени в месячном календаре элемента управления ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) связан *refValue* попадает *refMinRange* и *refMaxRange*.

```
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*refValue*<br/>
Ссылку на объект типа `CTime` или `COleDateTime` связаны с переменную-член диалогового окна, представление формы или объекта представления элемента управления. Этот объект содержит данные для проверки. Передает MFC, это ссылаться при `DDV_MinMaxMonth` вызывается.

*refMinRange*<br/>
Минимальное допустимое значение даты и времени.

*refMaxRange*<br/>
Допустимое значение максимальной даты и времени.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxshort"></a>  DDV_MinMaxShort

Вызовите `DDV_MinMaxShort` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

```
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,
    short value,
    short minVal,
    short maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*minVal*<br/>
Минимальное значение (типа **короткие**) разрешено.

*maxVal*<br/>
Максимальное значение (типа **короткие**) разрешено.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxslider"></a>  DDV_MinMaxSlider

Вызовите `DDV_MinMaxSlider` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

```
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,
    DWORD value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на значение для проверки. Этот параметр содержит или задает текущее положение бегунка элемента управления "ползунок".

*minVal*<br/>
Минимально допустимое значение.

*maxVal*<br/>
Максимально допустимое значение.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Сведения об элементах управления "ползунок", см. в разделе [использование CSliderCtrl](../../mfc/using-csliderctrl.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxuint"></a>  DDV_MinMaxUInt

Вызовите `DDV_MinMaxUInt` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

```
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,
    UINT value,
    UINT minVal,
    UINT maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*minVal*<br/>
Минимальное значение (типа целое число без знака) разрешено.

*maxVal*<br/>
Максимальное значение (типа целое число без знака) разрешено.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

##  <a name="ddv_minmaxulonglong"></a>  DDV_MinMaxULongLong

Вызовите `DDV_MinMaxULongLong` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

```
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,
    ULONGLONG value,
    ULONGLONG  minVal ,
    ULONGLONG  maxVal);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*minVal*<br/>
Минимальное значение (типа ULONGLONG) разрешено.

*maxVal*<br/>
Максимальное значение (типа ULONGLONG) разрешено.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddvminmaxunsigned"></a>DDV_MinMaxUnsigned

Вызовите `DDV_MinMaxUnsigned` чтобы убедиться, что значение в элементе управления, связанное с *значение* попадает *minVal* и *maxVal*.

### <a name="syntax"></a>Синтаксис

```
   void AFXAPI DDV_MinMaxUnsigned(
       CDataExchange* pDX,
       unsigned value,
       unsigned minVal,
       unsigned maxVal );
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на объект `CDataExchange` . Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную-член диалоговое окно, представлении формы или объекте представления элемента управления, с которой данные проверяются.

*minVal*<br/>
Минимальное значение (типа **без знака** ) разрешено.

*maxVal*<br/>
Максимальное значение (типа **без знака** ) разрешено.

### <a name="remarks"></a>Примечания

Дополнительные сведения о DDV к элементам Управления, см. в разделе [обмен данными диалоговых окон и проверка](../dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxdd_.h

## <a name="see-also"></a>См. также

[Стандартные программы обмена данными диалоговых окон](standard-dialog-data-exchange-routines.md)<br/>
[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[DDX_Slider](standard-dialog-data-exchange-routines.md#ddx_slider)<br/>
[DDX_FieldSlider](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md#ddx_fieldslider)
