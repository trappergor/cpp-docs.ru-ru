---
title: Класс CComVariant
ms.date: 11/04/2016
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
ms.openlocfilehash: 9a84d91e20242fb206d1d3f71fcb3dd207561f62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327231"
---
# <a name="ccomvariant-class"></a>Класс CComVariant

Этот класс обертывает тип VARIANT, предоставляя участнику, указывающему тип хранящихся данных.

## <a name="syntax"></a>Синтаксис

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComVariant::CComVariant](#ccomvariant)|Конструктор.|
|[CComVariant:::CComVariant](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComVariant::Прикрепите](#attach)|Прикрепляет VARIANT `CComVariant` к объекту.|
|[CComVariant::ChangeType](#changetype)|Преобразует `CComVariant` объект в новый тип.|
|[CComVariant::Clear](#clear)|Очищает `CComVariant` объект.|
|[CComVariant::Copy](#copy)|Копирует VARIANT на `CComVariant` объект.|
|[CComVariant::Copyto](#copyto)|Копирует содержимое `CComVariant` объекта.|
|[CComVariant::Detach](#detach)|Отсоединяет основной ВАРИАНТ с `CComVariant` объекта.|
|[CComVariant::GetSize](#getsize)|Возвращает размер байтов содержимого `CComVariant` объекта.|
|[CComVariant::ReadFromStream](#readfromstream)|Загружает VARIANT из потока.|
|[CComVariant::SetByRef](#setbyref)|Инициализирует `CComVariant` объект `vt` и устанавливает, чтобы член VT_BYREF.|
|[CComVariant::WriteTostream](#writetostream)|Сохраняет базовый VARIANT в потоке.|

### <a name="public-operators"></a>Открытые операторы

|||
|-|-|
|[CComVariant::оператор <](#operator_lt)|Указывает, `CComVariant` меньше ли объекта, чем указанный VARIANT.|
|[CComVariant::оператор >](#operator_gt)|Указывает, `CComVariant` является ли объект больше, чем указанный VARIANT.|
|[оператор !](#operator_neq)|Указывает, `CComVariant` не равен ли объект указанному VARIANT.|
|[Оператор](#operator_eq)|Присваивает `CComVariant` объекту значение.|
|[оператор](#operator_eq_eq)|Указывает, `CComVariant` равен ли объект указанному VARIANT.|

## <a name="remarks"></a>Remarks

`CComVariant`обертывания типа VARIANT и VARIANTARG, который состоит из союза и члена, указывающего тип данных, хранящихся в союзе. VARIANTs обычно используются в автоматизации.

`CComVariant`вытекает из типа VARIANT, поэтому его можно использовать везде, где можно использовать VARIANT. Вы можете, например, использовать V_VT макрос `CComVariant` для извлечения `vt` типа или вы можете получить доступ к члену непосредственно так же, как вы можете с VARIANT.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>Требования

**Заголовок:** atlcomcli.h

## <a name="ccomvariantattach"></a><a name="attach"></a>CComVariant::Прикрепите

Безопасно очищает текущее содержимое `CComVariant` объекта, копирует содержимое *pSrc* в этот объект, а затем устанавливает тип *варианта pSrc* для VT_EMPTY.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>Параметры

*Psrc*<br/>
(в) Указывает на [VARIANT,](/windows/win32/api/oaidl/ns-oaidl-variant) который будет прикреплен к объекту.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Владение данными, хранятся *pSrc,* передается объекту. `CComVariant`

## <a name="ccomvariantccomvariant"></a><a name="ccomvariant"></a>CComVariant::CComVariant

Каждый конструктор обрабатывает безопасную `CComVariant` инициализацию `VariantInit` объекта, вызывая функцию Win32 или устанавливая значение и тип объекта в соответствии с пройдеными параметрами.

```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```

### <a name="parameters"></a>Параметры

*varSrc*<br/>
(в) Вариант `CComVariant` или VARIANT используется `CComVariant` для инициализации объекта. Содержимое исходного варианта копируется в пункт назначения без преобразования.

*lpszSrc*<br/>
(в) Строка символов, используемая для инициализации `CComVariant` объекта. Вы можете передать строку символов с нулевым завершением (Unicode) в версию конструктора LPCOLESTR или строку ANSI в версию LPCSTR. В любом случае строка преобразуется в Unicode BSTR, выделенный с помощью. `SysAllocString` Тип `CComVariant` объекта будет VT_BSTR.

*bSrc*<br/>
(в) **Бул** используется для инициализации `CComVariant` объекта. Аргумент **bool** преобразуется в VARIANT_BOOL перед хранением. Тип `CComVariant` объекта будет VT_BOOL.

*nSrc*<br/>
(в) **Int**, **BYTE**, **короткий,** **длинный**, LONGLONG, ULONGLONG, **неподписанный короткий,** **неподписанный длинный,** или **неподписанный int** используется для инициализации `CComVariant` объекта. Тип `CComVariant` объекта будет VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 или VT_UI4 соответственно.

*vtSrc*<br/>
(в) Тип варианта. Когда первый параметр **int,** действительные типы VT_I4 и VT_INT. Когда первый параметр **длинный,** допустимые типы VT_I4 и VT_ERROR. Когда первый параметр **двойной,** допустимые типы VT_R8 и VT_DATE. Когда первый параметр **не подписан int,** допустимые типы VT_UI4 и VT_UINT.

*fltSrc*<br/>
(в) **Поплавок** используется `CComVariant` для инициализации объекта. Тип `CComVariant` объекта будет VT_R4.

*dblSrc*<br/>
(в) **Двойной** используется для `CComVariant` инициализации объекта. Тип `CComVariant` объекта будет VT_R8.

*cySrc*<br/>
(в) Используется `CY` для инициализации `CComVariant` объекта. Тип `CComVariant` объекта будет VT_CY.

*Psrc*<br/>
(в) `IDispatch` Указатель `IUnknown` или указатель, `CComVariant` используемый для инициализации объекта. `AddRef`будет вызван на указатель интерфейса. Тип `CComVariant` объекта будет VT_DISPATCH или VT_UNKNOWN, соответственно.

Или указатель SAFERRAY, используемый `CComVariant` для инициализации объекта. Копия SAFEARRAY хранится в `CComVariant` объекте. Тип `CComVariant` объекта будет комбинацией оригинального типа SAFEARRAY и VT_ARRAY.

*cSrc*<br/>
(в) **Символ** используется для инициализации `CComVariant` объекта. Тип `CComVariant` объекта будет VT_I1.

*bstrSrc*<br/>
(в) BSTR используется для инициализации `CComVariant` объекта. Тип `CComVariant` объекта будет VT_BSTR.

### <a name="remarks"></a>Remarks

Деструктор управляет очисткой, позвонив [в CComVariant::Clear](#clear).

## <a name="ccomvariantccomvariant"></a><a name="dtor"></a>CComVariant:::CComVariant

Деструктор

```
~CComVariant() throw();
```

### <a name="remarks"></a>Remarks

Этот метод управляет очисткой, позвонив [в CComVariant::Clear](#clear).

## <a name="ccomvariantchangetype"></a><a name="changetype"></a>CComVariant::ChangeType

Преобразует `CComVariant` объект в новый тип.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>Параметры

*vtNew*<br/>
(в) Новый тип `CComVariant` для объекта.

*Psrc*<br/>
(в) Указатель на VARIANT, значение которого будет преобразовано в новый тип. Значение по умолчанию null, то есть `CComVariant` объект будет преобразован на месте.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Если вы передаете значение для `ChangeType` *pSrc,* будет использовать этот VARIANT в качестве источника для преобразования. В противном `CComVariant` случае, объект будет источником.

## <a name="ccomvariantclear"></a><a name="clear"></a>CComVariant::Clear

Очищает `CComVariant` объект, вызывая `VariantClear` функцию Win32.

```
HRESULT Clear();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Деструктор автоматически `Clear`вызывает .

## <a name="ccomvariantcopy"></a><a name="copy"></a>CComVariant::Copy

Освобождает `CComVariant` объект, а затем назначает ему копию указанного VARIANT.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>Параметры

*Psrc*<br/>
(в) Указатель на [VARIANT,](/windows/win32/api/oaidl/ns-oaidl-variant) который будет скопирован.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccomvariantcopyto"></a><a name="copyto"></a>CComVariant::Copyto

Копирует содержимое `CComVariant` объекта.

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>Параметры

*pstrDest*<br/>
Указывает на BSTR, который получит копию `CComVariant` содержимого объекта.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Объект `CComVariant` должен быть типа VT_BSTR.

## <a name="ccomvariantdetach"></a><a name="detach"></a>CComVariant::Detach

Отделяет базовый VARIANT от `CComVariant` объекта и устанавливает тип объекта на VT_EMPTY.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>Параметры

*pDest*<br/>
(ваут) Возвращает базовое значение VARIANT объекта.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Обратите внимание, что содержимое VARIANT, на который ссылается *pDest,* будет автоматически `CComVariant` очищено перед присвоением значения и типа вызываемого объекта.

## <a name="ccomvariantgetsize"></a><a name="getsize"></a>CComVariant::GetSize

Для простого фиксированного размера VARIANTs этот метод возвращает **размер базового** типа данных плюс **sizeof (VARTYPE).**

```
ULONG GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер байтов текущего содержимого `CComVariant` объекта.

### <a name="remarks"></a>Remarks

Если VARIANT содержит указатель `GetSize` интерфейса, `IPersistStream` `IPersistStreamInit`запросы на или . В случае успеха значение возврата представляет собой низкозаказ 32 `GetSizeMax` бита значения, возвращенного плюс **размер** CLSID и **sizeof (VARTYPE).** Если указатель интерфейса `GetSize` NULL, возвращает **размер** CLSID плюс **sizeof (VARTYPE)**. Если общий размер больше `GetSize` ULONG_MAX, возвращает **размер (VARTYPE),** который указывает на ошибку.

Во всех остальных случаях временный ВАРИАНТ типа VT_BSTR принуждается к текущему ВАРИАНТу. Длина этого BSTR рассчитывается как размер длины строки плюс длина самой строки плюс размер нулевого символа плюс **sizeof (VARTYPE)**. Если VARIANT не может быть принужден к `GetSize` ВАРИАНТтипа типа VT_BSTR, возвращает **sizeof (VARTYPE)**.

Размер, возвращенный этим методом, соответствует количеству байтов, используемых [CComVariant::WriteToStream](#writetostream) в успешных условиях.

## <a name="ccomvariantoperator-"></a><a name="operator_eq"></a>CComVariant::оператор

Присваивает объекту `CComVariant` значение и соответствующий тип.

```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```

### <a name="parameters"></a>Параметры

*varSrc*<br/>
(в) Вариант `CComVariant` или [ВАРИАНТ,](/windows/win32/api/oaidl/ns-oaidl-variant) назначенный `CComVariant` объекту. Содержимое исходного варианта копируется в пункт назначения без преобразования.

*bstrSrc*<br/>
(в) BSTR, который будет назначен `CComVariant` объекту. Тип `CComVariant` объекта будет VT_BSTR.

*lpszSrc*<br/>
(в) Строка символов, которая `CComVariant` будет назначена объекту. Вы можете передать строку символов с нулевым завершением (Unicode) в версию оператора LPCOLESTR или строку ANSI в версию LPCSTR. В любом случае строка преобразуется в Unicode `SysAllocString`BSTR, выделенный с помощью. Тип `CComVariant` объекта будет VT_BSTR.

*bSrc*<br/>
(в) **Bool,** который будет назначен `CComVariant` объекту. Аргумент **bool** преобразуется в VARIANT_BOOL перед хранением. Тип `CComVariant` объекта будет VT_BOOL.

*nSrc*<br/>
(в) **Int**, BYTE, **короткий,** **длинный**, LONGLONG, ULONG, **неподписанный короткий,** **неподписанный длинный,** или **неподписанный int,** который будет назначен `CComVariant` объекту. Тип `CComVariant` объекта будет VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 или VT_UI4 соответственно.

*fltSrc*<br/>
(в) **Поплавок,** который `CComVariant` будет назначен объекту. Тип `CComVariant` объекта будет VT_R4.

*dblSrc*<br/>
(в) **Двойной,** который будет `CComVariant` назначен объекту. Тип `CComVariant` объекта будет VT_R8.

*cySrc*<br/>
(в) Назначено `CY` объекту. `CComVariant` Тип `CComVariant` объекта будет VT_CY.

*Psrc*<br/>
(в) `IDispatch` Указатель `IUnknown` или указатель, который `CComVariant` будет назначен объекту. `AddRef`будет вызван на указатель интерфейса. Тип `CComVariant` объекта будет VT_DISPATCH или VT_UNKNOWN, соответственно.

Или указатель SAFEARRAY, который будет `CComVariant` назначен объекту. Копия SAFEARRAY хранится в `CComVariant` объекте. Тип `CComVariant` объекта будет комбинацией оригинального типа SAFEARRAY и VT_ARRAY.

*cSrc*<br/>
(в) Символ, который будет назначен `CComVariant` объекту. Тип `CComVariant` объекта будет VT_I1.

## <a name="ccomvariantoperator-"></a><a name="operator_eq_eq"></a>CComVariant::оператор

Указывает, `CComVariant` равен ли объект указанному VARIANT.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Remarks

Возвращает TRUE, если значение и тип *varSrc* равны значению и `CComVariant` типу, соответственно, объекта. В противном случае — значение FALSE. Оператор использует локал из локального платежа пользователя по умолчанию для выполнения сравнения.

Оператор сравнивает только значение типов вариантов. Он сравнивает строки, целые число и плавающие точки, но не массивы или записи.

## <a name="ccomvariantoperator-"></a><a name="operator_neq"></a>CComVariant::оператор !

Указывает, `CComVariant` не равен ли объект указанному VARIANT.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Remarks

Возвращает TRUE, если значение или тип *varSrc* не равен значению или `CComVariant` типу, соответственно, объекта. В противном случае — значение FALSE. Оператор использует локал из локального платежа пользователя по умолчанию для выполнения сравнения.

Оператор сравнивает только значение типов вариантов. Он сравнивает строки, целые число и плавающие точки, но не массивы или записи.

## <a name="ccomvariantoperator-lt"></a><a name="operator_lt"></a>CComVariant:оператор&lt;

Указывает, `CComVariant` меньше ли объекта, чем указанный VARIANT.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Remarks

Возвращает TRUE, если `CComVariant` значение объекта меньше значения *varSrc.* В противном случае — значение FALSE. Оператор использует локал из локального платежа пользователя по умолчанию для выполнения сравнения.

## <a name="ccomvariantoperator-gt"></a><a name="operator_gt"></a>CComVariant:оператор&gt;

Указывает, `CComVariant` является ли объект больше, чем указанный VARIANT.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Remarks

Возвращает TRUE, если `CComVariant` значение объекта больше, чем значение *varSrc.* В противном случае — значение FALSE. Оператор использует локал из локального платежа пользователя по умолчанию для выполнения сравнения.

## <a name="ccomvariantreadfromstream"></a><a name="readfromstream"></a>CComVariant::ReadFromStream

Устанавливает базовый VARIANT на VARIANT, содержащийся в указанном потоке.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
(в) Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) в потоке, содержащем данные.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

`ReadToStream`требует предыдущего вызова [WriteToStream](#writetostream).

## <a name="ccomvariantsetbyref"></a><a name="setbyref"></a>CComVariant::SetByRef

Инициализирует `CComVariant` объект `vt` и устанавливает, чтобы член VT_BYREF.

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип VARIANT, например, BSTR, **Int**, или **char**.

*Pt*<br/>
Указатель используется для инициализации `CComVariant` объекта.

### <a name="remarks"></a>Remarks

`SetByRef`— это шаблон функции, `CComVariant` который инициализирует объект `vt` к указателю *pT* и устанавливает член к VT_BYREF. Пример:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

## <a name="ccomvariantwritetostream"></a><a name="writetostream"></a>CComVariant::WriteTostream

Сохраняет базовый VARIANT в потоке.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
(в) Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) в потоке.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
