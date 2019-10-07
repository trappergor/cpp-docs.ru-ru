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
ms.openlocfilehash: b4c157435aaffab5f1315fd4636f55f9d4e0d5b4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496864"
---
# <a name="ccomvariant-class"></a>Класс CComVariant

Этот класс служит оболочкой для типа VARIANT, предоставляя член, указывающий тип хранимых данных.

## <a name="syntax"></a>Синтаксис

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CComVariant:: CComVariant](#ccomvariant)|Конструктор.|
|[CComVariant:: ~ CComVariant](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComVariant:: Attach](#attach)|Присоединяет вариант к `CComVariant` объекту.|
|[CComVariant:: ChangeType](#changetype)|`CComVariant` Преобразует объект в новый тип.|
|[CComVariant:: Clear](#clear)|`CComVariant` Очищает объект.|
|[CComVariant:: Copy](#copy)|Копирует вариант в `CComVariant` объект.|
|[CComVariant:: CopyTo](#copyto)|Копирует содержимое `CComVariant` объекта.|
|[CComVariant::D етач](#detach)|Отсоединяет базовый вариант от `CComVariant` объекта.|
|[CComVariant:: DataSize](#getsize)|Возвращает размер содержимого `CComVariant` объекта в байтах.|
|[CComVariant:: Реадфромстреам](#readfromstream)|Загружает вариант из потока.|
|[CComVariant:: Сетбиреф](#setbyref)|Инициализирует `vt` объект и задает для элемента значение VT_BYREF. `CComVariant`|
|[CComVariant:: Вритетостреам](#writetostream)|Сохраняет базовый вариант в потоке.|

### <a name="public-operators"></a>Открытые операторы

|||
|-|-|
|[CComVariant:: operator <](#operator_lt)|Указывает, меньше `CComVariant` ли объект, чем указанный вариант.|
|[CComVariant:: operator >](#operator_gt)|Указывает, больше `CComVariant` ли объект, чем указанный вариант.|
|[operator! =](#operator_neq)|Указывает, `CComVariant` не равен ли объект указанному варианту.|
|[Оператор =](#operator_eq)|Присваивает значение `CComVariant` объекту.|
|[Оператор = =](#operator_eq_eq)|Указывает, равен `CComVariant` ли объект заданному варианту.|

## <a name="remarks"></a>Примечания

`CComVariant`заключает в оболочку тип VARIANT и VARIANTARG, состоящий из объединения и члена, указывающего тип данных, хранящихся в объединении. Варианты обычно используются в автоматизации.

`CComVariant`является производным от типа VARIANT, поэтому его можно использовать везде, где можно использовать вариант. Например, можно использовать макрос V_VT для извлечения типа `CComVariant` объекта или `vt` получить доступ к члену напрямую, как это можно сделать с вариантом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>Требования

**Заголовок:** atlcomcli. h

##  <a name="attach"></a>CComVariant:: Attach

Безопасно очищает текущее содержимое `CComVariant` объекта, копирует содержимое *pSrc* в этот объект, а затем устанавливает для типа Variant *pSrc* значение VT_EMPTY.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>Параметры

*pSrc*<br/>
окне Указывает на [вариант](/windows/win32/api/oaidl/ns-oaidl-variant) , который должен быть присоединен к объекту.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Владение данными, удерживаемыми *pSrc* , передается `CComVariant` в объект.

##  <a name="ccomvariant"></a>CComVariant:: CComVariant

Каждый конструктор обрабатывает надежную инициализацию `CComVariant` объекта путем `VariantInit` вызова функции Win32 или установки значения и типа объекта в соответствии с передаваемыми параметрами.

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

*варсрк*<br/>
окне Вариант `CComVariant` или, используемый для `CComVariant` инициализации объекта. Содержимое исходного варианта копируется в место назначения без преобразования.

*лпсзсрк*<br/>
окне Символьная строка, используемая для `CComVariant` инициализации объекта. В ЛПКОЛЕСТР версии конструктора или строки ANSI в версию LPCSTR можно передать строку двухбайтовых символов (Юникод), заканчивающуюся нулем. В любом случае строка преобразуется в Юникод BSTR, выделенный с `SysAllocString`помощью. Тип `CComVariant` объекта будет VT_BSTR.

*бсрк*<br/>
окне **Логическое** значение, используемое для `CComVariant` инициализации объекта. Перед сохранением аргумент **bool** преобразуется в VARIANT_BOOL. Тип `CComVariant` объекта будет VT_BOOL.

*нсрк*<br/>
окне Дляинициализации объектаиспользуетсятипint,Byte,Short,Long,лонглонг,улонглонг,неподписанноекороткоеибеззнаковое`CComVariant` **целое** число. `CComVariant` Объект будет иметь тип VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 или VT_UI4 соответственно.

*втсрк*<br/>
окне Тип варианта. Если первый параметр имеет **тип int**, допустимыми ТИПАМИ являются VT_I4 и VT_INT. Если первый параметр имеет тип **Long**, допустимыми ТИПАМИ являются VT_I4 и VT_ERROR. Если первый параметр имеет тип **Double**, допустимыми ТИПАМИ являются VT_R8 и VT_DATE. Если первым параметром является **целое число без знака**, допустимые типы — VT_UI4 и VT_UINT.

*флтсрк*<br/>
окне `CComVariant` Объект **float** , используемый для инициализации объекта. Тип `CComVariant` объекта будет VT_R4.

*дблсрк*<br/>
окне Значение **типа Double** , используемое `CComVariant` для инициализации объекта. Тип `CComVariant` объекта будет VT_R8.

*цисрк*<br/>
окне `CComVariant` Объект `CY` , используемый для инициализации объекта. Тип `CComVariant` объекта будет VT_CY.

*pSrc*<br/>
окне Указатель или `IUnknown` , `IDispatch` используемый для инициализации объекта.`CComVariant` `AddRef`будет вызываться для указателя интерфейса. Тип `CComVariant` объекта будет VT_DISPATCH или VT_UNKNOWN соответственно.

Или указатель саферрай, используемый для инициализации `CComVariant` объекта. Копия массива SafeArray хранится в `CComVariant` объекте. Тип `CComVariant` объекта будет сочетанием исходного типа SafeArray и VT_ARRAY.

*ксрк*<br/>
окне **Символ** , используемый для инициализации `CComVariant` объекта. Тип `CComVariant` объекта будет VT_I1.

*бстрсрк*<br/>
окне `CComVariant` Объект BSTR, используемый для инициализации объекта. Тип `CComVariant` объекта будет VT_BSTR.

### <a name="remarks"></a>Примечания

Деструктор управляет очисткой, вызывая [CComVariant:: Clear](#clear).

##  <a name="dtor"></a>CComVariant:: ~ CComVariant

Деструктор

```
~CComVariant() throw();
```

### <a name="remarks"></a>Примечания

Этот метод управляет очисткой путем вызова [CComVariant:: Clear](#clear).

##  <a name="changetype"></a>CComVariant:: ChangeType

`CComVariant` Преобразует объект в новый тип.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>Параметры

*втнев*<br/>
окне Новый тип для `CComVariant` объекта.

*pSrc*<br/>
окне Указатель на вариант, значение которого будет преобразовано в новый тип. Значение по умолчанию — NULL, означающее `CComVariant` , что объект будет преобразован на месте.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если передать значение для *pSrc*, `ChangeType` будет использовать этот вариант в качестве источника для преобразования. В противном случае объект будет источником. `CComVariant`

##  <a name="clear"></a>CComVariant:: Clear

Очищает объект, вызывая функцию `VariantClear` Win32. `CComVariant`

```
HRESULT Clear();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Деструктор автоматически вызывает `Clear`.

##  <a name="copy"></a>CComVariant:: Copy

`CComVariant` Освобождает объект и присваивает ему копию указанного варианта.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>Параметры

*pSrc*<br/>
окне Указатель на копируемый объект [Variant](/windows/win32/api/oaidl/ns-oaidl-variant) .

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="copyto"></a>CComVariant:: CopyTo

Копирует содержимое `CComVariant` объекта.

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>Параметры

*пстрдест*<br/>
Указывает на BSTR, который получит копию содержимого `CComVariant` объекта.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`CComVariant` Объект должен иметь тип VT_BSTR.

##  <a name="detach"></a>CComVariant::D етач

Отсоединяет базовый вариант от `CComVariant` объекта и устанавливает тип объекта VT_EMPTY.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>Параметры

*пдест*<br/>
заполняет Возвращает базовое значение типа VARIANT объекта.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Обратите внимание, что содержимое варианта, на которое ссылается *пдест* , будет автоматически очищаться перед присвоением значения и типа вызывающего `CComVariant` объекта.

##  <a name="getsize"></a>CComVariant:: DataSize

Для типов Variant с простым фиксированным размером этот метод возвращает значение **sizeof** базового типа данных и **sizeof (VarType)** .

```
ULONG GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер в байтах текущего содержимого `CComVariant` объекта.

### <a name="remarks"></a>Примечания

Если вариант содержит указатель интерфейса, `GetSize` запросы для `IPersistStream` или `IPersistStreamInit`. В случае успеха возвращаемое значение является младшим младшим значением 32, возвращаемым методом `GetSizeMax` , а **sizeof** — CLSID и **sizeof (VarType)** . Если указатель интерфейса имеет значение null, `GetSize` функция возвращает значение **sizeof** CLSID и **sizeof (VarType)** . Если общий размер больше ULONG_MAX, `GetSize` возвращает значение **sizeof (VarType)** , которое указывает на ошибку.

Во всех остальных случаях временный вариант типа VT_BSTR приводится к текущему ВАРИАНТу. Длина этой BSTR вычисляется как размер длины строки плюс длина строки, а также размер символа NULL плюс **sizeof (VarType)** . Если вариант не может быть приведен к типу Variant типа VT_BSTR, `GetSize` функция возвращает **sizeof (VarType)** .

Размер, возвращенный этим методом, соответствует числу байтов, используемых [CComVariant:: вритетостреам](#writetostream) в условиях успешного выполнения.

##  <a name="operator_eq"></a>CComVariant:: operator =

Присваивает `CComVariant` объекту значение и соответствующий тип.

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

*варсрк*<br/>
[in] `CComVariant` или [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), который должен `CComVariant` быть назначен объекту. Содержимое исходного варианта копируется в место назначения без преобразования.

*бстрсрк*<br/>
окне Значение BSTR, присваиваемое `CComVariant` объекту. Тип `CComVariant` объекта будет VT_BSTR.

*лпсзсрк*<br/>
окне Символьная строка, назначаемая `CComVariant` объекту. В ЛПКОЛЕСТР версию оператора или строку ANSI можно передать версию LPCSTR в виде расширенной строки символов с нулевым значением (Юникод). В любом случае строка преобразуется в Юникод BSTR, выделенный с помощью `SysAllocString`. Тип `CComVariant` объекта будет VT_BSTR.

*бсрк*<br/>
окне **Логическое** значение, присваиваемое `CComVariant` объекту. Перед сохранением аргумент **bool** преобразуется в VARIANT_BOOL. Тип `CComVariant` объекта будет VT_BOOL.

*нсрк*<br/>
окне **Целочисленное значение, целое**, **короткое**, **длинное**, лонглонг, улонглонг, неподписанное **короткое**или неподписанное **целое** **число, которое**должно быть назначено `CComVariant` объекту. `CComVariant` Объект будет иметь тип VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 или VT_UI4 соответственно.

*флтсрк*<br/>
окне `CComVariant` Объект **float** , который будет назначен объекту. Тип `CComVariant` объекта будет VT_R4.

*дблсрк*<br/>
окне Значение **типа Double** , присваиваемое `CComVariant` объекту. Тип `CComVariant` объекта будет VT_R8.

*цисрк*<br/>
окне `CComVariant` Объект `CY` , назначаемый объекту. Тип `CComVariant` объекта будет VT_CY.

*pSrc*<br/>
окне Указатель `IDispatch` или `IUnknown` ,`CComVariant` который должен быть назначен объекту. `AddRef`будет вызываться для указателя интерфейса. Тип `CComVariant` объекта будет VT_DISPATCH или VT_UNKNOWN соответственно.

Или — указатель SAFEARRAY, назначаемый `CComVariant` объекту. Копия массива SafeArray хранится в `CComVariant` объекте. Тип `CComVariant` объекта будет сочетанием исходного типа SafeArray и VT_ARRAY.

*ксрк*<br/>
окне Символ, присваиваемый `CComVariant` объекту. Тип `CComVariant` объекта будет VT_I1.

##  <a name="operator_eq_eq"></a>CComVariant:: operator = =

Указывает, равен `CComVariant` ли объект заданному варианту.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение true, если значение и тип *варсрк* равны значению и типу, соответственно, `CComVariant` объекта. В противном случае — значение FALSE. Оператор использует локаль пользователя по умолчанию для выполнения сравнения.

Оператор сравнивает только значения типов Variant. Он сравнивает строки, целые числа и плавающие точки, но не массивы или записи.

##  <a name="operator_neq"></a>CComVariant:: operator! =

Указывает, `CComVariant` не равен ли объект указанному варианту.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение true, если значение или тип *варсрк* не равны значению или типу `CComVariant` объекта, соответственно. В противном случае — значение FALSE. Оператор использует локаль пользователя по умолчанию для выполнения сравнения.

Оператор сравнивает только значения типов Variant. Он сравнивает строки, целые числа и плавающие точки, но не массивы или записи.

##  <a name="operator_lt"></a>CComVariant:: operator&lt;

Указывает, меньше `CComVariant` ли объект, чем указанный вариант.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение true, если значение `CComVariant` объекта меньше значения параметра *варсрк*. В противном случае — значение FALSE. Оператор использует локаль пользователя по умолчанию для выполнения сравнения.

##  <a name="operator_gt"></a>CComVariant:: operator&gt;

Указывает, больше `CComVariant` ли объект, чем указанный вариант.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение true, если значение `CComVariant` объекта больше значения параметра *варсрк*. В противном случае — значение FALSE. Оператор использует локаль пользователя по умолчанию для выполнения сравнения.

##  <a name="readfromstream"></a>CComVariant:: Реадфромстреам

Задает базовый вариант для варианта, содержащегося в указанном потоке.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>Параметры

*пстреам*<br/>
окне Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) в потоке, содержащем данные.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`ReadToStream`требуется предыдущий вызов [вритетостреам](#writetostream).

##  <a name="setbyref"></a>CComVariant:: Сетбиреф

Инициализирует `vt` объект и задает для элемента значение VT_BYREF. `CComVariant`

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип VARIANT, например BSTR, **int**или **char**.

*Лутор*<br/>
Указатель, используемый для инициализации `CComVariant` объекта.

### <a name="remarks"></a>Примечания

`SetByRef`— Это шаблон функции, который инициализирует `CComVariant` объект по указателю *PT* и устанавливает `vt` для элемента значение VT_BYREF. Например:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

##  <a name="writetostream"></a>CComVariant:: Вритетостреам

Сохраняет базовый вариант в потоке.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>Параметры

*пстреам*<br/>
окне Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) в потоке.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
