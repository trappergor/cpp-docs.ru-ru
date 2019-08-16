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
ms.openlocfilehash: 0676f4896401ab777570666236c4639ad94c3a05
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503054"
---
# <a name="colevariant-class"></a>Класс COleVariant

Инкапсулирует тип данных [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) .

## <a name="syntax"></a>Синтаксис

```
class COleVariant : public tagVARIANT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COleVariant:: COleVariant](#colevariant)|Создает объект `COleVariant`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleVariant:: Attach](#attach)|Присоединяет вариант к `COleVariant`.|
|[COleVariant:: ChangeType](#changetype)|Изменяет тип Variant этого `COleVariant` объекта.|
|[COleVariant:: Clear](#clear)|Очищает данный объект `COleVariant`.|
|[COleVariant::D етач](#detach)|Отсоединяет вариант от `COleVariant` типа и возвращает вариант.|
|[COleVariant:: Жетбитеаррайфромвариантаррай](#getbytearrayfromvariantarray)|Извлекает массив байтов из существующего массива Variant.|
|[COleVariant:: SetString](#setstring)|Присваивает строке определенный тип, обычно ANSI.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[COleVariant:: operator ЛПКВАРИАНТ](#operator_lpcvariant)|`COleVariant` Преобразует значение`LPCVARIANT`в.|
|[COleVariant:: operator ЛПВАРИАНТ](#operator_lpvariant)|`COleVariant` Преобразует объект`LPVARIANT`в.|
|[COleVariant:: operator =](#operator_eq)|`COleVariant` Копирует значение.|
|[COleVariant:: operator = =](#operator_eq_eq)|Сравнивает два `COleVariant` значения.|
|[COleVariant:: operator &lt;, &lt;&gt;&gt;](#operator_lt_lt__gt_gt)|`CDumpContext` `CArchive` `COleVariant` Выводит `CArchive` значение в или и, а также вводит объект из. `COleVariant`|

## <a name="remarks"></a>Примечания

Этот тип данных используется в OLE-автоматизации. В частности, структура [DISPPARAMS](/windows/win32/api/oaidl/ns-oaidl-tagdispparams) содержит указатель на массив вариативных структур. Структура используется для передачи параметров в [IDispatch:: Invoke.](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) `DISPPARAMS`

> [!NOTE]
> Этот класс является производным от `VARIANT` структуры. Это означает, что можно передать `COleVariant` в параметр, который вызывает метод `VARIANT` для и что элементы `VARIANT` данных структуры являются доступными элементами `COleVariant`данных.

Два связанных класса MFC [COleCurrency](../../mfc/reference/colecurrency-class.md) и [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) инкапсулируют типы данных Variant Currency ( `VT_CY`) и Date ( `VT_DATE`). Класс широко используется в классах DAO; см. следующие классы для типичного использования этого класса, например [кдаокуеридеф](../../mfc/reference/cdaoquerydef-class.md) и [CDaoRecordset.](../../mfc/reference/cdaorecordset-class.md) `COleVariant`

Дополнительные сведения см. в записях [типа Variant](/windows/win32/api/oaidl/ns-oaidl-variant), [Currency](/windows/win32/api/wtypes/ns-wtypes-cy), [DISPPARAMS](/windows/win32/api/oaidl/ns-oaidl-tagdispparams)и [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) в Windows SDK.

Дополнительные сведения `COleVariant` о классе и его использовании в OLE Automation см. в разделе "Передача параметров в OLE Automation" статьи [Автоматизация](../../mfc/automation.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="attach"></a>COleVariant:: Attach

Вызовите эту функцию, чтобы присоединить заданный объект [Variant](/windows/win32/api/oaidl/ns-oaidl-variant) к текущему `COleVariant` объекту.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Параметры

*варсрк*<br/>
Существующий `VARIANT` объект, который будет присоединен к текущему `COleVariant` объекту.

### <a name="remarks"></a>Примечания

Эта функция задает для VARTYPE *варсрк* значение VT_EMPTY.

Дополнительные сведения см. в записях [типа Variant](/windows/win32/api/oaidl/ns-oaidl-variant) и [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) в Windows SDK.

##  <a name="colevariant"></a>COleVariant:: COleVariant

Создает объект `COleVariant`.

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

*варсрк*<br/>
Существующий `COleVariant` объект или `VARIANT` , который будет скопирован в новый `COleVariant` объект.

*pSrc*<br/>
Указатель на `VARIANT` объект, который будет скопирован в новый `COleVariant` объект.

*лпсзсрк*<br/>
Строка, завершающаяся нулем, для копирования в новый `COleVariant` объект.

*втсрк*<br/>
`VARTYPE` Для нового`COleVariant` объекта.

*стрсрк*<br/>
Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , который будет скопирован в новый `COleVariant` объект.

*нсрк*, *лсрк* числовое значение, которое должно быть скопировано `COleVariant` в новый объект.

*втсрк*<br/>
`VARTYPE` Для нового`COleVariant` объекта.

*курсрк*<br/>
Объект [COleCurrency](../../mfc/reference/colecurrency-class.md) , который необходимо скопировать в новый `COleVariant` объект.

*флтсрк*, *дблсрк*<br/>
Числовое значение, которое необходимо скопировать в новый объект `COleVariant`.

*тимесрк*<br/>
Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , который необходимо скопировать в новый `COleVariant` объект.

*аррсрк*<br/>
Объект [CByteArray](../../mfc/reference/cbytearray-class.md) , который будет скопирован в новый `COleVariant` объект.

*лбсрк*<br/>
Объект [CLongBinary](../../mfc/reference/clongbinary-class.md) , который необходимо скопировать в новый `COleVariant` объект.

*пидл*<br/>
Указатель на структуру [итемидлист](/windows/win32/api/shtypes/ns-shtypes-itemidlist) , которая должна быть скопирована в новый `COleVariant` объект.

### <a name="remarks"></a>Примечания

Все эти конструкторы создают новые `COleVariant` объекты, инициализированные с указанным значением. Ниже приведено краткое описание каждого из этих конструкторов.

- **COleVariant ()** Создает пустой `COleVariant` объект VT_EMPTY.

- **COleVariant (** *варсрк* **)** Копирует существующий `VARIANT` объект или `COleVariant` . Тип variant сохранен.

- **COleVariant (** *pSrc* **)** Копирует существующий `VARIANT` объект или `COleVariant` . Тип variant сохранен.

- **COleVariant (** *лпсзсрк* **)** Копирует строку в новый объект VT_BSTR (UNICODE).

- **COleVariant (** *лпсзсрк* **,** *втсрк* **)** Копирует строку в новый объект. Параметр *втсрк* должен быть VT_BSTR (Unicode) или VT_BSTRT (ANSI).

- **COleVariant (** *стрсрк* **)** Копирует строку в новый объект VT_BSTR (UNICODE).

- **COleVariant (** *нсрк* **)** Копирует 8-разрядное целое число в новый объект VT_UI1.

- **COleVariant (** *нсрк* **,** *втсрк* **)** Копирует 16-разрядное целое число (или логическое значение) в новый объект. Параметр *втсрк* должен быть VT_I2 или VT_BOOL.

- **COleVariant (** *лсрк* **,** *втсрк* **)** Копирует 32-разрядное целое число (или SCODE значение) в новый объект. Параметр *втсрк* должен иметь значение VT_I4, VT_ERROR или VT_BOOL.

- **COleVariant (** *курсрк* **)** `COleCurrency` Копирует значение в новый объект VT_CY.

- **COleVariant (** *флтсрк* **)** Копирует 32-разрядное значение с плавающей запятой в новый объект VT_R4.

- **COleVariant (** *дблсрк* **)** Копирует 64-разрядное значение с плавающей запятой в новый объект VT_R8.

- **COleVariant (** *тимесрк* **)** `COleDateTime` Копирует значение в новый объект VT_DATE.

- **COleVariant (** *аррсрк* **)** `CByteArray` Копирует объект в новый объект VT_EMPTY.

- **COleVariant (** *лбсрк* **)** `CLongBinary` Копирует объект в новый объект VT_EMPTY.

Дополнительные сведения о SCODE см. в разделе [структура кодов ошибок COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

##  <a name="changetype"></a>COleVariant:: ChangeType

Преобразует тип значения Variant в этом `COleVariant` объекте.

```
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>Параметры

*VarType*<br/>
Объект VarType для этого `COleVariant` объекта.

*pSrc*<br/>
Указатель на объект [Variant](/windows/win32/api/oaidl/ns-oaidl-variant) для преобразования. Если это значение равно null, этот `COleVariant` объект используется в качестве источника для преобразования.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в записях [типа Variant](/windows/win32/api/oaidl/ns-oaidl-variant), [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)и [вариантчанжетипе](/windows/win32/api/oleauto/nf-oleauto-variantchangetype) в Windows SDK.

##  <a name="clear"></a>COleVariant:: Clear

Очищает `VARIANT`.

```
void Clear();
```

### <a name="remarks"></a>Примечания

Этот параметр задает для объекта VARTYPE значение VT_EMPTY. `COleVariant` Деструктор вызывает эту функцию.

Дополнительные сведения см. в разделе `VARIANT`, VarType и `VariantClear` записях в Windows SDK.

##  <a name="detach"></a>COleVariant::D етач

Отсоединяет базовый объект [Variant](/windows/win32/api/oaidl/ns-oaidl-variant) от этого `COleVariant` объекта.

```
VARIANT Detach();
```

### <a name="remarks"></a>Примечания

Эта функция задает для `COleVariant` объекта VarType значение VT_EMPTY.

> [!NOTE]
>  После вызова `Detach`вызывающий объект отвечает за вызов `VariantClear` в результирующей `VARIANT` структуре.

Дополнительные сведения см. в записях [типа Variant](/windows/win32/api/oaidl/ns-oaidl-variant), [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)и [вариантклеар](/windows/win32/api/oleauto/nf-oleauto-variantclear) в Windows SDK.

##  <a name="getbytearrayfromvariantarray"></a>COleVariant:: Жетбитеаррайфромвариантаррай

Извлекает массив байтов из существующего массива вариантов

```
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>Параметры

*байт*<br/>
Ссылка на существующий объект [CByteArray](../../mfc/reference/cbytearray-class.md) .

##  <a name="operator_lpcvariant"></a>COleVariant:: operator ЛПКВАРИАНТ

Этот оператор приведения возвращает `VARIANT` структуру, значение которой копируется из `COleVariant` этого объекта.

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>Примечания

##  <a name="operator_lpvariant"></a>COleVariant:: operator ЛПВАРИАНТ

Вызовите этот оператор приведения, чтобы `VARIANT` получить доступ к `COleVariant` базовой структуре для этого объекта.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Примечания

> [!CAUTION]
> Изменение значения в `VARIANT` структуре, к которой обращается указатель, возвращенное этой функцией, приведет к изменению `COleVariant` значения этого объекта.

##  <a name="operator_eq"></a>COleVariant:: operator =

Эти перегруженные операторы присваивания копируют исходное значение в этот `COleVariant` объект.

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

### <a name="remarks"></a>Примечания

Краткое описание каждого оператора приведено ниже.

- **operator = (** *варсрк* **)** Копирует существующий вариант или `COleVariant` объект в этот объект.

- **operator = (** *pSrc* **)** Копирует объект VARIANT, к которому обращается *pSrc* , в этот объект.

- **operator = (** *лпсзсрк* **)** Копирует строку, завершающуюся нулем, в этот объект и устанавливает для VARTYPE значение VT_BSTR.

- **operator = (** *стрсрк* **)** Копирует объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) в этот объект и ЗАДАЕТ для VarType значение VT_BSTR.

- **operator = (** *нсрк* **)** Копирует 8-или 16-разрядное целочисленное значение в этот объект. Если *нсрк* является 8-битным значением, то VarType этого параметра устанавливается в значение VT_UI1. Если *нсрк* — 16-разрядное значение, а VarType — VT_BOOL, то он сохраняется. в противном случае для него задается значение VT_I2.

- **operator = (** *лсрк* **)** Копирует 32-разрядное целочисленное значение в этот объект. Если значение VARTYPE для этого параметра — VT_ERROR, оно сохраняется; в противном случае для него задается значение VT_I4.

- **operator = (** *курсрк* **)** Копирует объект [COleCurrency](../../mfc/reference/colecurrency-class.md) в этот объект и ЗАДАЕТ для VarType значение VT_CY.

- **operator = (** *флтсрк* **)** Копирует 32-разрядное значение с плавающей запятой в этот объект и задает VT_R4 в качестве значения переменной VARTYPE.

- **operator = (** *дблсрк* **)** Копирует 64-разрядное значение с плавающей запятой в этот объект и задает VT_R8 в качестве значения переменной VARTYPE.

- **operator = (** *датесрк* **)** Копирует объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) в этот объект и ЗАДАЕТ для VarType значение VT_DATE.

- **operator = (** *аррсрк* **)** Копирует объект [CByteArray](../../mfc/reference/cbytearray-class.md) в этот `COleVariant` объект.

- **operator = (** *лбсрк* **)** Копирует объект [CLongBinary](../../mfc/reference/clongbinary-class.md) в этот `COleVariant` объект.

Дополнительные сведения см. в записях [типа Variant](/windows/win32/api/oaidl/ns-oaidl-variant) и [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) в Windows SDK.

##  <a name="operator_eq_eq"></a>COleVariant:: operator = =

Этот оператор сравнивает два значения типа Variant и возвращает ненулевое значение, если они равны. в противном случае — 0.

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

##  <a name="operator_lt_lt__gt_gt"></a>COleVariant:: operator &lt;, &lt;&gt;&gt;

`CdumpContext` `CArchive` `COleVariant` Выводит `CArchive` значение в или и, а также вводит объект из. `COleVariant`

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

### <a name="remarks"></a>Примечания

Оператор `COleVariant` вставки ( **\<)поддерживаетдампыихранение\<** в архиве. Оператор извлечения ( **>>** ) поддерживает загрузку из архива.

##  <a name="setstring"></a>COleVariant:: SetString

Задает для строки конкретный тип.

```
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>Параметры

*лпсзсрк*<br/>
Строка, завершающаяся нулем, для копирования в новый `COleVariant` объект.

*втсрк*<br/>
Объект VarType для нового `COleVariant` объекта.

### <a name="remarks"></a>Примечания

Параметр *втсрк* должен быть VT_BSTR (Unicode) или VT_BSTRT (ANSI). `SetString`обычно используется для задания строк в ANSI, так как по умолчанию для конструктора [COleVariant:: COleVariant](#colevariant) со строкой или параметром указателя строки, а значение VarType не равно Unicode.

Набор записей DAO в сборке, не поддерживающей Юникод, принимает строки как ANSI. Таким образом, для функций DAO, `COleVariant` использующих объекты, если не создается набор записей в Юникоде, необходимо использовать форму конструктора **COleVariant:: COleVariant (** *лпсзсрк* **,** *втсрк* **)** с *втсрк* , установленным в VT. _BSTRT (ANSI) или используйте `SetString` с параметром WITH *втсрк* значение VT_BSTRT для создания строк ANSI. Например, `CDaoRecordset` функции [CDaoRecordset:: Seek](../../mfc/reference/cdaorecordset-class.md#seek) и [CDaoRecordset:: сетфиелдвалуе](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) используют `COleVariant` объекты в качестве параметров. Эти объекты должны иметь значение ANSI, если набор записей DAO не является ЮНИКОДом.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
