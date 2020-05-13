---
title: Стандартные программы проверки данных диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
ms.openlocfilehash: 83e3e215ec8d66321bbac5a4a308b04ef69dc68c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372902"
---
# <a name="standard-dialog-data-validation-routines"></a>Стандартные программы проверки данных диалоговых окон

В этой теме перечислены стандартные процедуры проверки данных диалогов (DDV), используемые для общего управления диалогом MFC.

> [!NOTE]
> Стандартные процедуры обмена данными диалогов определяются в файле заголовка afxdd_.h. Тем не менее, приложения должны включать afxwin.h.

### <a name="ddv-functions"></a>Функции DDV

|||
|-|-|
|[DDV_MaxChars](#ddv_maxchars)|Проверяет количество символов в заданном контрольном значении не превышает заданного максимума.|
|[DDV_MinMaxByte](#ddv_minmaxbyte)|Проверяет заданное значение управления не превышает заданного диапазона **BYTE.**|
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|Проверяет заданное значение управления не превышает заданного диапазона времени.|
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|Проверяется заданное значение управления, не превышающее заданного **двойного** диапазона.|
|[DDV_MinMaxDWord](#ddv_minmaxdword)|Проверяет заданное значение управления не превышает заданного диапазона **DWORD.**|
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|Проверяет заданное значение управления не превышает заданного диапазона **поплавка.**|
|[DDV_MinMaxInt](#ddv_minmaxint)|Проверяет заданное значение управления не превышает заданного диапазона **int.**|
|[DDV_MinMaxLong](#ddv_minmaxlong)|Проверяет заданное значение управления не превышает заданного **дальнего** радиуса действия.|
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|Проверяет заданное значение управления не превышает заданного диапазона **LONGLONG.**|
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|Проверяется заданное значение управления, не превышающее заданного диапазона дат.|
|[DDV_MinMaxShort](#ddv_minmaxshort)|Проверяет заданное значение управления не превышает заданного **короткого** диапазона.|
|[DDV_MinMaxSlider](#ddv_minmaxslider)|Проверяет заданное значение управления ползунок в пределах заданного диапазона.|
|[DDV_MinMaxUInt](#ddv_minmaxuint)|Проверяет сяданное контрольное значение не превышает заданного диапазона **UINT.**|
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|Проверяя, что определенное значение управления падает между двумя указанными значениями.|
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|Проверяется заданное значение управления, не превышающее заданного диапазона **ULONGLONG.**|

## <a name="ddv_maxchars"></a><a name="ddv_maxchars"></a>DDV_MaxChars

Звоните, `DDV_MaxChars` чтобы убедиться, что количество символов в элементе управления, связанном с *значением,* не превышает *nChars.*

```cpp
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,
    CString const& value,
    int nChars);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*nChars*<br/>
Разрешено максимальное количество разрешенных символов.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxbyte"></a><a name="ddv_minmaxbyte"></a>DDV_MinMaxByte

Позвоните, `DDV_MinMaxByte` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

```cpp
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,
    BYTE value,
    BYTE minVal,
    BYTE maxVal);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*minVal*<br/>
Минимальное значение (типа BYTE) разрешено.

*maxVal*<br/>
Разрешено максимальное значение (типа BYTE).

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxdatetime"></a><a name="ddv_minmaxdatetime"></a>DDV_MinMaxDateTime

Звоните, `DDV_MinMaxDateTime` чтобы убедиться, что значение времени/даты в контроле сборщика даты и времени [(CDateTimeCtrl),](../../mfc/reference/cdatetimectrl-class.md)связанное с *refValue,* падает между *refMinRange* и *refMaxRange.*

```cpp
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

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление. Вам не нужно удалять этот объект.

*refValue*<br/>
Ссылка на объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) или [COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) связанный с переменной элемента диалогового окна, представления формы или объекта управления. Этот объект содержит данные, которые должны быть проверены.

*refMinRange*<br/>
Разрешено минимальное значение даты/времени.

*refMaxRange*<br/>
Разрешено максимальное значение даты/времени.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxdouble"></a><a name="ddv_minmaxdouble"></a>DDV_MinMaxDouble

Позвоните, `DDV_MinMaxDouble` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

```cpp
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,
    double const& value,
    double minVal,
    double maxVal);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*minVal*<br/>
Минимальное значение (типа **двойной**) разрешено.

*maxVal*<br/>
Максимальное значение (типа **двойной**) допускается.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxdword"></a><a name="ddv_minmaxdword"></a>DDV_MinMaxDWord

Позвоните, `DDV_MinMaxDWord` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

```cpp
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,
    DWORD const& value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*minVal*<br/>
Минимальное значение (типа DWORD) разрешено.

*maxVal*<br/>
Разрешено максимальное значение (типа DWORD).

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxfloat"></a><a name="ddv_minmaxfloat"></a>DDV_MinMaxFloat

Позвоните, `DDV_MinMaxFloat` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

```cpp
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,
    float value,
    float minVal,
    float maxVal);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*minVal*<br/>
Минимальное значение (типа **поплавка**) разрешено.

*maxVal*<br/>
Максимальное значение (типа **поплавка**) разрешено.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxint"></a><a name="ddv_minmaxint"></a>DDV_MinMaxInt

Позвоните, `DDV_MinMaxInt` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

```cpp
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,
    int value,
    int minVal,
    int maxVal);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*minVal*<br/>
Минимальное значение (типа **int)** разрешено.

*maxVal*<br/>
Максимальное значение (типа **int)** разрешено.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxlong"></a><a name="ddv_minmaxlong"></a>DDV_MinMaxLong

Позвоните, `DDV_MinMaxLong` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

```cpp
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,
    long value,
    long minVal,
    long maxVal);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*minVal*<br/>
Минимальное значение (типа **длиннее)** разрешено.

*maxVal*<br/>
Максимальное значение (типа **длиной)** разрешено.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxlonglong"></a><a name="ddv_minmaxlonglong"></a>DDV_MinMaxLongLong

Позвоните, `DDV_MinMaxLongLong` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

```cpp
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,
    LONGLONG value,
    LONGLONG minVal,
    LONGLONG maxVal);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*minVal*<br/>
Минимальное значение (типа LONGLONG) разрешено.

*maxVal*<br/>
Разрешено максимальное значение (типа LONGLONG).

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxmonth"></a><a name="ddv_minmaxmonth"></a>DDV_MinMaxMonth

Звоните, `DDV_MinMaxMonth` чтобы убедиться, что значение времени/даты в месячном календарном контроле [(CMonthCalCtrl),](../../mfc/reference/cmonthcalctrl-class.md)связанное с *refValue,* падает между *refMinRange* и *refMaxRange.*

```cpp
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

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*refValue*<br/>
Ссылка на объект `CTime` типа `COleDateTime` или связанная с переменной элемента диалогового окна, представления формы или объекта представления управления. Этот объект содержит данные, которые должны быть проверены. MFC передает эту `DDV_MinMaxMonth` ссылку, когда называется.

*refMinRange*<br/>
Разрешено минимальное значение даты/времени.

*refMaxRange*<br/>
Разрешено максимальное значение даты/времени.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxshort"></a><a name="ddv_minmaxshort"></a>DDV_MinMaxShort

Позвоните, `DDV_MinMaxShort` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

```cpp
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,
    short value,
    short minVal,
    short maxVal);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*minVal*<br/>
Минимальное значение (типа **короткий**) допускается.

*maxVal*<br/>
Максимальное значение (типа **короткий**) допускается.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxslider"></a><a name="ddv_minmaxslider"></a>DDV_MinMaxSlider

Позвоните, `DDV_MinMaxSlider` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

```cpp
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,
    DWORD value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md) Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на значение, подаваемый к проверке. Этот параметр удерживает или устанавливает текущее положение большого пальца слайдера.

*minVal*<br/>
Минимальное значение разрешено.

*maxVal*<br/>
Максимальное допустимое значение.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md). Для получения информации о элементах управления слайдер, [см.](../../mfc/using-csliderctrl.md)

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxuint"></a><a name="ddv_minmaxuint"></a>DDV_MinMaxUInt

Позвоните, `DDV_MinMaxUInt` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

```cpp
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,
    UINT value,
    UINT minVal,
    UINT maxVal);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*minVal*<br/>
Минимальное значение (типа UINT) разрешено.

*maxVal*<br/>
Разрешено максимальное значение (типа UINT).

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxulonglong"></a><a name="ddv_minmaxulonglong"></a>DDV_MinMaxULongLong

Позвоните, `DDV_MinMaxULongLong` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

```cpp
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,
    ULONGLONG value,
    ULONGLONG  minVal ,
    ULONGLONG  maxVal);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*minVal*<br/>
Минимальное значение (типа ULONGLONG) разрешено.

*maxVal*<br/>
Разрешено максимальное значение (типа ULONGLONG).

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdd_.h

## <a name="ddv_minmaxunsigned"></a>DDV_MinMaxUnsigned

Позвоните, `DDV_MinMaxUnsigned` чтобы убедиться, что значение в элементе управления, связанном с *значением,* падает между *minVal* и *maxVal.*

### <a name="syntax"></a>Синтаксис

```cpp
   void AFXAPI DDV_MinMaxUnsigned(
       CDataExchange* pDX,
       unsigned value,
       unsigned minVal,
       unsigned maxVal );
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект `CDataExchange`. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.

*value*<br/>
Ссылка на переменную члена диалогового окна, представления формы или элемента управления, с помощью которого проверяются данные.

*minVal*<br/>
Минимальное значение (типа **неподписанного)** разрешено.

*maxVal*<br/>
Максимальное значение (типа **неподписанного)** разрешено.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о DDV, см [Dialog обмена данными и валидации](../dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxdd_.h

## <a name="see-also"></a>См. также раздел

[Стандартные программы обмена данными диалоговых окон](standard-dialog-data-exchange-routines.md)<br/>
[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[DDX_Slider](standard-dialog-data-exchange-routines.md#ddx_slider)<br/>
[DDX_FieldSlider](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md#ddx_fieldslider)
