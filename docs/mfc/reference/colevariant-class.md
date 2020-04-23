---
title: Класс COleVariant
ms.date: 11/04/2016
f1_keywords:
- COleVariant
- AFXDISP/COleVariant
- AFXDISP/COleVariant::COleVariant
- AFXDISP/COleVariant::Attach
- AFXDISP/COleVariant::ChangeType
- AFXDISP/COleVariant::Clear
- AFXDISP/COleVariant::Detach
- AFXDISP/COleVariant::GetByteArrayFromVariantArray
- AFXDISP/COleVariant::SetString
helpviewer_keywords:
- COleVariant [MFC], COleVariant
- COleVariant [MFC], Attach
- COleVariant [MFC], ChangeType
- COleVariant [MFC], Clear
- COleVariant [MFC], Detach
- COleVariant [MFC], GetByteArrayFromVariantArray
- COleVariant [MFC], SetString
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
ms.openlocfilehash: 7d8abea39a9baa3f447ca0d5f3ab1183367d531f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753719"
---
# <a name="colevariant-class"></a>Класс COleVariant

Инкапсулирует тип данных [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) .

## <a name="syntax"></a>Синтаксис

```
class COleVariant : public tagVARIANT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeVariant::COleVariant](#colevariant)|Формирует объект `COleVariant`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeVariant::Attach](#attach)|Прикрепляет VARIANT `COleVariant`к .|
|[ColeVariant::ChangeType](#changetype)|Изменяет тип варианта этого `COleVariant` объекта.|
|[ColeVariant::Clear](#clear)|Очищает данный объект `COleVariant`.|
|[ColeVariant::Detach](#detach)|Отсоединяет VARIANT от и `COleVariant` возвращает VARIANT.|
|[ColeVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|Извлекает массив байта из существующего массива вариантов.|
|[ColeVariant::SetString](#setstring)|Устанавливает строку к определенному типу, как правило, ANSI.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[ColeVariant::оператор LPCVARIANT](#operator_lpcvariant)|Преобразует `COleVariant` значение в `LPCVARIANT`.|
|[ColeVariant::оператор LPVARIANT](#operator_lpvariant)|Преобразует `COleVariant` объект в `LPVARIANT`.|
|[ColeVariant::оператор](#operator_eq)|Копирует `COleVariant` значение.|
|[COleVariant::оператор](#operator_eq_eq)|Сравнивает `COleVariant` два значения.|
|[ColeVariant::оператор &lt; &lt;,&gt;&gt;](#operator_lt_lt__gt_gt)|Выводы `COleVariant` значения `CArchive` или `CDumpContext` и вводимые `COleVariant` объект из `CArchive`.|

## <a name="remarks"></a>Remarks

Этот тип данных используется в автоматизации OLE. В частности, структура [DISPPARAMS](/windows/win32/api/oaidl/ns-oaidl-dispparams) содержит указатель на массив структур VARIANT. Структура `DISPPARAMS` используется для передачи параметров [в IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke).

> [!NOTE]
> Этот класс происходит от `VARIANT` структуры. Это означает, что `COleVariant` вы можете пройти `VARIANT` в параметр, который `VARIANT` требует и что `COleVariant`данные членов структуры доступны холостых данных членов .

Два связанных класса MFC [COleCurrency](../../mfc/reference/colecurrency-class.md) и [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) инкапсулируют `VT_CY`варианты `VT_DATE`типов данных CURRENCY () и DATE (). Класс `COleVariant` широко используется в классах DAO; см. эти классы для типичного использования этого класса, [например, CDao-КуириДеф](../../mfc/reference/cdaoquerydef-class.md) и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Для получения дополнительной информации [см. VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy~r1), [DISPPARAMS](/windows/win32/api/oaidl/ns-oaidl-dispparams), и [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) записи в Windows SDK.

Для получения дополнительной `COleVariant` информации о классе и его использовании в автоматизации [Automation](../../mfc/automation.md)OLE, см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="colevariantattach"></a><a name="attach"></a>ColeVariant::Attach

Вызовите эту функцию, чтобы `COleVariant` прикрепить данный объект [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) к текущему объекту.

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Параметры

*varSrc*<br/>
Существующий `VARIANT` объект, который будет `COleVariant` присоединен к текущему объекту.

### <a name="remarks"></a>Remarks

Эта функция устанавливает VARTYPE *varSrc* VT_EMPTY.

Для получения дополнительной информации смотрите записи [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) и [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) в SDK Windows.

## <a name="colevariantcolevariant"></a><a name="colevariant"></a>ColeVariant::COleVariant

Формирует объект `COleVariant`.

```
COleVariant();
COleVariant(const VARIANT& varSrc);
COleVariant(const COleVariant& varSrc);
COleVariant(LPCVARIANT pSrc);
COleVariant(LPCTSTR lpszSrc);
COleVariant(LPCTSTR lpszSrc, VARTYPE vtSrc);
COleVariant(CString& strSrc);
COleVariant(BYTE nSrc);
COleVariant(short nSrc, VARTYPE vtSrc = VT_I2);
COleVariant(long lSrc,VARTYPE vtSrc = VT_I4);
COleVariant(const COleCurrency& curSrc);
COleVariant(float fltSrc);
COleVariant(double dblSrc);
COleVariant(const COleDateTime& timeSrc);
COleVariant(const CByteArray& arrSrc);
COleVariant(const CLongBinary& lbSrc);
COleVariant(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Параметры

*varSrc*<br/>
Существующий `COleVariant` `VARIANT` или объект, который должен `COleVariant` быть скопирован в новый объект.

*Psrc*<br/>
Указатель на `VARIANT` объект, который будет скопирован в новый `COleVariant` объект.

*lpszSrc*<br/>
Нулевая строка, которая будет `COleVariant` скопирована в новый объект.

*vtSrc*<br/>
Для `VARTYPE` нового `COleVariant` объекта.

*strSrc*<br/>
Объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) который должен быть `COleVariant` скопирован в новый объект.

*nSrc*, *lSrc* числовое значение, необходимое `COleVariant` для копирования в новый объект.

*vtSrc*<br/>
Для `VARTYPE` нового `COleVariant` объекта.

*curSrc*<br/>
Объект [COleCurrency,](../../mfc/reference/colecurrency-class.md) который будет скопирован в новый `COleVariant` объект.

*fltSrc*, *dblSrc*<br/>
Числовое значение, которое необходимо скопировать в новый объект `COleVariant`.

*timeSrc*<br/>
Объект [COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) который будет скопирован в новый `COleVariant` объект.

*arrSrc*<br/>
Объект [CByteArray,](../../mfc/reference/cbytearray-class.md) который будет скопирован в новый `COleVariant` объект.

*lbSrc*<br/>
[Объект CLongBinary,](../../mfc/reference/clongbinary-class.md) который будет скопирован в новый `COleVariant` объект.

*pidl*<br/>
Указатель на структуру [ITEMIDLIST,](/windows/win32/api/shtypes/ns-shtypes-itemidlist) которая будет `COleVariant` скопирована в новый объект.

### <a name="remarks"></a>Remarks

Все эти конструкторы `COleVariant` создают новые объекты, инициализированные к заданному значению. Ниже приводится краткое описание каждого из этих конструкторов.

- **ColeVariant()** Создает пустой `COleVariant` объект, VT_EMPTY.

- **COleVariant** *(varSrc* **)** Копирует `VARIANT` существующий `COleVariant` объект или объект. Тип variant сохранен.

- **COleVariant** *(pSrc* **)** Копирует `VARIANT` существующий `COleVariant` объект или объект. Тип variant сохранен.

- **ColeVariant** *(lpszSrc* **)** Копирует строку в новый объект, VT_BSTR (UNICODE).

- **ColeVariant (** *lpszSrc* **,** *vtSrc* **)** Копирует строку в новый объект. Параметр *vtSrc* должен быть VT_BSTR (UNICODE) или VT_BSTRT (ANSI).

- **COleVariant (** *strSrc* **)** Копирует строку в новый объект, VT_BSTR (UNICODE).

- **COleVariant** *(nSrc* **)** Копирует 8-битный штат в новый объект, VT_UI1.

- **ColeVariant (** *nSrc* **,** *vtSrc* **)** Копирует 16-битный ряд (или значение Булеана) в новый объект. Параметр *vtSrc* должен быть VT_I2 или VT_BOOL.

- **ColeVariant (** *lSrc* **,** *vtSrc* **)** Копирует 32-битный ряд (или значение SCODE) в новый объект. Параметр *vtSrc* должен быть VT_I4, VT_ERROR или VT_BOOL.

- **COleVariant** *(curSrc* **)** Копирует `COleCurrency` значение в новый объект, VT_CY.

- **COleVariant** *(fltSrc* **)** Копирует 32-битное значение плавающей точки в новый объект, VT_R4.

- **ColeVariant (** *dblSrc* **)** Копирует 64-битное значение плавающей точки в новый объект, VT_R8.

- **COleVariant** *(timeSrc* **)** Копирует `COleDateTime` значение в новый объект, VT_DATE.

- **ColeVariant** *(arrSrc* **)** Копирует `CByteArray` объект в новый объект, VT_EMPTY.

- **ColeVariant** *(lbSrc* **)** Копирует `CLongBinary` объект в новый объект, VT_EMPTY.

Для получения дополнительной информации о SCODE, [см. Структура кодов ошибки COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

## <a name="colevariantchangetype"></a><a name="changetype"></a>ColeVariant::ChangeType

Преобразует значение типа варианта `COleVariant` в этом объекте.

```cpp
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>Параметры

*вартип*<br/>
VARTYPE для `COleVariant` этого объекта.

*Psrc*<br/>
Указатель на объект [VARIANT,](/windows/win32/api/oaidl/ns-oaidl-variant) который будет преобразован. Если это значение NULL, этот `COleVariant` объект используется в качестве источника для преобразования.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации, [см. VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum), и [VariantChangeType](/windows/win32/api/oleauto/nf-oleauto-variantchangetype) записи в Windows SDK.

## <a name="colevariantclear"></a><a name="clear"></a>ColeVariant::Clear

Очищает `VARIANT`.

```cpp
void Clear();
```

### <a name="remarks"></a>Remarks

Это устанавливает VARTYPE для этого объекта на VT_EMPTY. Деструктор `COleVariant` вызывает эту функцию.

Для получения дополнительной `VARIANT`информации `VariantClear` см.

## <a name="colevariantdetach"></a><a name="detach"></a>ColeVariant::Detach

Отсоединяет основной объект [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) от `COleVariant` этого объекта.

```
VARIANT Detach();
```

### <a name="remarks"></a>Remarks

Эта функция устанавливает VARTYPE `COleVariant` для этого объекта на VT_EMPTY.

> [!NOTE]
> После `Detach`вызова, это ответственность абонента, `VariantClear` чтобы вызвать в результате `VARIANT` структуры.

Для получения дополнительной информации, [см. VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum), и [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) записи в Windows SDK.

## <a name="colevariantgetbytearrayfromvariantarray"></a><a name="getbytearrayfromvariantarray"></a>ColeVariant::GetByteArrayFromVariantArray

Извлекает массив байта из существующего массива вариантов

```cpp
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>Параметры

*Байт*<br/>
Ссылка на существующий объект [CByteArray.](../../mfc/reference/cbytearray-class.md)

## <a name="colevariantoperator-lpcvariant"></a><a name="operator_lpcvariant"></a>ColeVariant::оператор LPCVARIANT

Этот оператор литья возвращает структуру, `VARIANT` `COleVariant` ценность которой скопирована с этого объекта.

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>Remarks

## <a name="colevariantoperator-lpvariant"></a><a name="operator_lpvariant"></a>ColeVariant::оператор LPVARIANT

Вызовите этого оператора литья, чтобы получить доступ к базовой `VARIANT` структуре для этого `COleVariant` объекта.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Remarks

> [!CAUTION]
> Изменение значения в `VARIANT` структуре, доступ к которым указателем, возвращенному `COleVariant` этой функцией, изменит значение этого объекта.

## <a name="colevariantoperator-"></a><a name="operator_eq"></a>ColeVariant::оператор

Эти перегруженные операторы назначения копируют `COleVariant` исходное значение в этом объекте.

```
const COleVariant& operator=(const VARIANT& varSrc);
const COleVariant& operator=(LPCVARIANT pSrc);
const COleVariant& operator=(const COleVariant& varSrc);
const COleVariant& operator=(const LPCTSTR lpszSrc);
const COleVariant& operator=(const CString& strSrc);
const COleVariant& operator=(BYTE nSrc);
const COleVariant& operator=(short nSrc);
const COleVariant& operator=(long lSrc);
const COleVariant& operator=(const COleCurrency& curSrc);
const COleVariant& operator=(float fltSrc);
const COleVariant& operator=(double dblSrc);
const COleVariant& operator=(const COleDateTime& dateSrc);
const COleVariant& operator=(const CByteArray& arrSrc);
const COleVariant& operator=(const CLongBinary& lbSrc);
```

### <a name="remarks"></a>Remarks

Краткое описание каждого оператора:

- **оператор No** *(varSrc* **)** Копирует существующий `COleVariant` VARIANT или объект в этот объект.

- **оператор** *(pSrc* **)** Копирует объект VARIANT, доступ к объекту, доступ к нему со *стороны pSrc.*

- **оператор** *(lpszSrc* **)** Копирует нулевую строку в этот объект и устанавливает VARTYPE для VT_BSTR.

- **оператор** *(strSrc* **)** Копирует объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) в этот объект и устанавливает VARTYPE на VT_BSTR.

- **оператор No** *(nSrc* **)** Копирует 8- или 16-битное значение в этом объекте. Если *значение nSrc* составляет 8-битное значение, ТО VARTYPE этого значения установлен на VT_UI1. Если *значение nSrc* составляет 16-битное значение, а VARTYPE это VT_BOOL, то оно сохраняется; в противном случае, он установлен на VT_I2.

- **оператор** *(lSrc* **)** Копирует 32-битное значение в этом объекте. Если VARTYPE этого VT_ERROR, он сохраняется; в противном случае, он установлен на VT_I4.

- **оператор no (** *curSrc* **)** Копирует объект [COleCurrency](../../mfc/reference/colecurrency-class.md) в этот объект и устанавливает VARTYPE на VT_CY.

- **оператор** *(fltSrc* **)** Копирует 32-битное значение плавающей точки в этот объект и устанавливает VARTYPE для VT_R4.

- **оператор no (** *dblSrc* **)** Копирует 64-битное значение плавающей точки в этот объект и устанавливает VARTYPE на VT_R8.

- **оператор** *(dateSrc* **)** Копирует объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) в этот объект и устанавливает VARTYPE для VT_DATE.

- **оператор** *(arrSrc* **)** Копирует объект [CByteArray](../../mfc/reference/cbytearray-class.md) `COleVariant` в этот объект.

- **оператор** *(lbSrc* **)** Копирует объект [CLongBinary](../../mfc/reference/clongbinary-class.md) `COleVariant` в этот объект.

Для получения дополнительной информации смотрите записи [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) и [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) в SDK Windows.

## <a name="colevariantoperator-"></a><a name="operator_eq_eq"></a>COleVariant::оператор

Этот оператор сравнивает два значения варианта и возвращает незеро, если они равны; в противном случае 0.

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

## <a name="colevariantoperator-ltlt-gtgt"></a><a name="operator_lt_lt__gt_gt"></a>ColeVariant::оператор &lt; &lt;,&gt;&gt;

Выводы `COleVariant` значения `CArchive` или `CdumpContext` и вводимые `COleVariant` объект из `CArchive`.

```
friend CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    OleVariant varSrc);

friend CArchive& AFXAPI operator<<(
    CArchive& ar,
    COleVariant varSrc);

friend CArchive& AFXAPI operator>>(
    CArchive& ar,
    COleVariant& varSrc);
```

### <a name="remarks"></a>Remarks

Оператор `COleVariant` вставки**\<** поддерживает диагностический демпинг и хранение в архиве. Извлечение**>>**() оператор поддерживает загрузку из архива.

## <a name="colevariantsetstring"></a><a name="setstring"></a>ColeVariant::SetString

Устанавливает строку к определенному типу.

```cpp
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>Параметры

*lpszSrc*<br/>
Нулевая строка, которая будет `COleVariant` скопирована в новый объект.

*VtSrc*<br/>
VARTYPE для нового `COleVariant` объекта.

### <a name="remarks"></a>Remarks

Параметр *vtSrc* должен быть VT_BSTR (UNICODE) или VT_BSTRT (ANSI). `SetString`обычно используется для установки строк в ANSI, так как по умолчанию для [конструктора COleVariant::COleVariant](#colevariant) с параметром строки или указателя строки и нет VARTYPE является UNICODE.

Запись DAO в сборке, не относясь к UNICODE, предполагает, что строки будут ANSI. Таким образом, для функций `COleVariant` DAO, которые используют объекты, если вы не создаете рекорд- и UNICODE, необходимо использовать **COleVariant::COleVariant** *(lpszSrc,* **,** *vtSrc)* **)** форму конструктора с *vtSrc,* установленным на VT_BSTRT (ANSI) или использовать `SetString` с *vtSrc,* чтобы VT_BSTRT, чтобы сделать строки ANSI. Например, `CDaoRecordset` функции [CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek) и [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) используют `COleVariant` объекты в качестве параметров. Эти объекты должны быть ANSI, если запись DAO не является UNICODE.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
