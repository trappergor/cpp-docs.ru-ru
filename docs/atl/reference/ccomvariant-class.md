---
title: Класс CComVariant | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89b1dbfe9dcf00582f5f8736a4706a18439b51c6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042550"
---
# <a name="ccomvariant-class"></a>Класс CComVariant

Этот класс заключает в оболочку тип VARIANT, предоставляя члена, указывающий тип данных, которые хранятся.

## <a name="syntax"></a>Синтаксис

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComVariant::CComVariant](#ccomvariant)|Конструктор.|
|[CComVariant:: ~ CComVariant](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComVariant::Attach](#attach)|Присоединяет типа VARIANT в `CComVariant` объекта.|
|[CComVariant::ChangeType](#changetype)|Преобразует `CComVariant` объекта в новый тип.|
|[CComVariant::Clear](#clear)|Очищает `CComVariant` объекта.|
|[CComVariant::Copy](#copy)|Копирует типа VARIANT в `CComVariant` объекта.|
|[CComVariant::CopyTo](#copyto)|Копирует содержимое объекта `CComVariant` объекта.|
|[CComVariant::Detach](#detach)|Отсоединяет базовый ВАРИАНТ из `CComVariant` объекта.|
|[CComVariant::GetSize](#getsize)|Возвращает размер в байтах содержимого `CComVariant` объекта.|
|[CComVariant::ReadFromStream](#readfromstream)|Загружает свойства типа VARIANT из потока.|
|[CComVariant::SetByRef](#setbyref)|Инициализирует `CComVariant` и устанавливает `vt` члена VT_BYREF.|
|[CComVariant::WriteToStream](#writetostream)|Сохраняет базовый ВАРИАНТ в поток.|

### <a name="public-operators"></a>Открытые операторы

|||
|-|-|
|[CComVariant::operator <](#operator_lt)|Указывает, является ли `CComVariant` объект меньше указанного ВАРИАНТА.|
|[CComVariant::operator >](#operator_gt)|Указывает, является ли `CComVariant` объект больше, чем указанный тип VARIANT.|
|[оператор! =](#operator_neq)|Указывает, является ли `CComVariant` не совпадает с указанным ВАРИАНТОМ.|
|[оператор =](#operator_eq)|Присваивает значение свойству `CComVariant` объекта.|
|[оператор ==](#operator_eq_eq)|Указывает, является ли `CComVariant` объект равен указанного ВАРИАНТА.|

## <a name="remarks"></a>Примечания

`CComVariant` заключает в оболочку тип VARIANT и VARIANTARG, состоящий из объединения и член, указывающий тип данных, хранящихся в объединении. Варианты обычно используются в службе автоматизации.

`CComVariant` является производным от типа VARIANT, чтобы его можно использовать везде, где можно использовать свойства типа VARIANT. К примеру, можно использовать макрос V_VT для извлечения типа `CComVariant` или использовать `vt` член непосредственно так же, как с помощью свойства типа VARIANT.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>Требования

**Заголовок:** atlcomcli.h

##  <a name="attach"></a>  CComVariant::Attach

Безопасно очищает текущее содержимое `CComVariant` объекта, копируется *pSrc* в этом объекте, в затем задает значение типа variant *pSrc* значение VT_EMPTY.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>Параметры

*pSrc*<br/>
[in] Указывает на [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) для присоединения к объекту.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Владение данные, хранящиеся в *pSrc* передается `CComVariant` объекта.

##  <a name="ccomvariant"></a>  CComVariant::CComVariant

Каждый конструктор обрабатывает Потокобезопасная инициализация `CComVariant` путем вызова метода `VariantInit` функции Win32 или установив значение и тип в соответствии с параметров, передаваемых объекта.

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
[in] `CComVariant` Или ВАРИАНТ, используемый для инициализации `CComVariant` объекта. Содержимое данного типа источника копируются в место назначения без преобразования.

*lpszSrc*<br/>
[in] Символьная строка, используемая для инициализации `CComVariant` объекта. Можно передать LPCOLESTR версию конструктора или в строку ANSI до версии LPCSTR строкой с завершающим нулевым символом символ двухбайтовых символов (Юникод). В любом случае строка преобразуется в Юникод BSTR, выделенные с помощью `SysAllocString`. Тип `CComVariant` объект будет VT_BSTR.

*bSrc*<br/>
[in] **Bool** используется для инициализации `CComVariant` объекта. **Bool** аргумент преобразовывается VARIANT_BOOL перед сохранением. Тип `CComVariant` объект будет VT_BOOL.

*nSrc*<br/>
[in] **Int**, **БАЙТОВ**, **короткие**, **long**, longlong приведенным к ПУСТОМУ, ULONGLONG, **unsigned short**, **unsigned long**, или **unsigned int** используется для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 или VT_UI4, соответственно.

*vtSrc*<br/>
[in] Тип variant. Если первый аргумент принимает значение **int**, допустимые типы: VT_I4 и VT_INT. Если первый аргумент принимает значение **long**, допустимые типы: VT_I4 и VT_ERROR. Если первый аргумент принимает значение **двойные**, допустимые типы: VT_R8 и VT_DATE. Если первый аргумент принимает значение **unsigned int**, допустимые типы: VT_UI4 и VT_UINT.

*fltSrc*<br/>
[in] **Float** используется для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет VT_R4.

*dblSrc*<br/>
[in] **Двойные** используется для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет VT_R8.

*cySrc*<br/>
[in] `CY` Используется для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет VT_CY.

*pSrc*<br/>
[in] `IDispatch` Или `IUnknown` указатель, используемый для инициализации `CComVariant` объекта. `AddRef` будет вызван в указателе на интерфейс. Тип `CComVariant` объект будет VT_DISPATCH или VT_UNKNOWN, соответственно.

Или, SAFERRAY указатель, используемый для инициализации `CComVariant` объекта. Экземпляр массива SAFEARRAY сохраняется в `CComVariant` объекта. Тип `CComVariant` объект будет представлять собой сочетание исходного типа SAFEARRAY и VT_ARRAY.

*cSrc*<br/>
[in] **Char** используется для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет VT_I1.

*bstrSrc*<br/>
[in] BSTR, используемый для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет VT_BSTR.

### <a name="remarks"></a>Примечания

Деструктор управляет освобождением путем вызова [CComVariant::Clear](#clear).

##  <a name="dtor"></a>  CComVariant:: ~ CComVariant

Деструктор

```
~CComVariant() throw();
```

### <a name="remarks"></a>Примечания

Этот метод управляет освобождением путем вызова [CComVariant::Clear](#clear).

##  <a name="changetype"></a>  CComVariant::ChangeType

Преобразует `CComVariant` объекта в новый тип.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>Параметры

*vtNew*<br/>
[in] Новый тип для `CComVariant` объекта.

*pSrc*<br/>
[in] Указатель на значение VARIANT, значение которого будут преобразованы в новый тип. Значение по умолчанию имеет значение NULL, значение `CComVariant` объект будет преобразован на месте.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если передать значение *pSrc*, `ChangeType` будет использовать этот ВАРИАНТ в качестве источника для преобразования. В противном случае `CComVariant` объекта будет источником.

##  <a name="clear"></a>  CComVariant::Clear

Очищает `CComVariant` путем вызова метода `VariantClear` функции Win32.

```
HRESULT Clear();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Автоматически вызывает деструктор `Clear`.

##  <a name="copy"></a>  CComVariant::Copy

Освобождает `CComVariant` и назначает его копию указанного ВАРИАНТА.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>Параметры

*pSrc*<br/>
[in] Указатель на [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) для копирования.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="copyto"></a>  CComVariant::CopyTo

Копирует содержимое объекта `CComVariant` объекта.

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>Параметры

*pstrDest*<br/>
Указывает на строку BSTR, получит копию содержимого `CComVariant` объекта.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`CComVariant` Объект должен быть типа VT_BSTR.

##  <a name="detach"></a>  CComVariant::Detach

Отсоединяет базовый ВАРИАНТ из `CComVariant` и устанавливает тип объекта значение VT_EMPTY.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>Параметры

*pDest*<br/>
[out] Возвращает базовое значение VARIANT объекта.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Обратите внимание, что содержимое ВАРИАНТА ссылается *pDest* автоматически очищается перед присваиванием значение и тип вызывающего `CComVariant` объекта.

##  <a name="getsize"></a>  CComVariant::GetSize

Для вариантов простой фиксированного размера, этот метод возвращает **sizeof** базовый тип данных плюс **sizeof(VARTYPE)**.

```
ULONG GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер в байтах текущее содержимое `CComVariant` объекта.

### <a name="remarks"></a>Примечания

Если ВАРИАНТ содержит указатель интерфейса `GetSize` запрашивает `IPersistStream` или `IPersistStreamInit`. Если в случае успешного выполнения возвращает значение младшие 32 бита значения, возвращенного `GetSizeMax` плюс **sizeof** CLSID и **sizeof(VARTYPE)**. Если указатель интерфейса равно NULL, `GetSize` возвращает **sizeof** плюс CLSID **sizeof(VARTYPE)**. Если общий размер больше, чем ULONG_MAX `GetSize` возвращает **sizeof(VARTYPE)** указывает на ошибку.

Во всех остальных случаях временный ВАРИАНТ типа VT_BSTR приводится из текущего типа VARIANT. Длина этого BSTR вычисляется как размер длину строки, а также длину строки, сам плюс размер нуль-символ плюс **sizeof(VARTYPE)**. Если ВАРИАНТ не может быть преобразован к ВАРИАНТ типа VT_BSTR, `GetSize` возвращает **sizeof(VARTYPE)**.

Размер, возвращаемый этим методом совпадает с количеством байт [CComVariant::WriteToStream](#writetostream) успешно условиях.

##  <a name="operator_eq"></a>  CComVariant::operator =

Присваивает значение и соответствующий тип для `CComVariant` объекта.

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
[in] `CComVariant` Или [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) присвоить `CComVariant` объекта. Содержимое данного типа источника копируются в место назначения без преобразования.

*bstrSrc*<br/>
[in] BSTR, присваиваемое `CComVariant` объекта. Тип `CComVariant` объект будет VT_BSTR.

*lpszSrc*<br/>
[in] Символьная строка должна назначаться `CComVariant` объекта. Можно передать LPCOLESTR версии оператора или строки ANSI до версии LPCSTR строкой с завершающим нулевым символом символ двухбайтовых символов (Юникод). В любом случае строка преобразуется в Юникод BSTR, выделенные с помощью `SysAllocString`. Тип `CComVariant` объект будет VT_BSTR.

*bSrc*<br/>
[in] **Bool** присвоить `CComVariant` объекта. **Bool** аргумент преобразовывается VARIANT_BOOL перед сохранением. Тип `CComVariant` объект будет VT_BOOL.

*nSrc*<br/>
[in] **Int**, BYTE, **короткие**, **long**, longlong приведенным к ПУСТОМУ, ULONGLONG, **unsigned short**, **unsigned long**, или **unsigned int** присвоить `CComVariant` объекта. Тип `CComVariant` объект будет VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 или VT_UI4, соответственно.

*fltSrc*<br/>
[in] **Float** присвоить `CComVariant` объекта. Тип `CComVariant` объект будет VT_R4.

*dblSrc*<br/>
[in] **Двойные** присвоить `CComVariant` объекта. Тип `CComVariant` объект будет VT_R8.

*cySrc*<br/>
[in] `CY` Присвоить `CComVariant` объекта. Тип `CComVariant` объект будет VT_CY.

*pSrc*<br/>
[in] `IDispatch` Или `IUnknown` указатель должен назначаться `CComVariant` объекта. `AddRef` будет вызван в указателе на интерфейс. Тип `CComVariant` объект будет VT_DISPATCH или VT_UNKNOWN, соответственно.

Или, SAFEARRAY указатель должен назначаться `CComVariant` объекта. Экземпляр массива SAFEARRAY сохраняется в `CComVariant` объекта. Тип `CComVariant` объект будет представлять собой сочетание исходного типа SAFEARRAY и VT_ARRAY.

*cSrc*<br/>
[in] Char, присваиваемое `CComVariant` объекта. Тип `CComVariant` объект будет VT_I1.

##  <a name="operator_eq_eq"></a>  CComVariant::operator ==

Указывает, является ли `CComVariant` объект равен указанного ВАРИАНТА.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение TRUE, если значение и тип *varSrc* равны значение и тип, соответственно, из `CComVariant` объекта. В противном случае — значение FALSE. Оператор использует языковой стандарт пользователя по умолчанию для выполнения сравнения.

Оператор сравнивает только значение типа variant. Она сравнивает строки, целые числа и чисел с плавающей запятой, но не массивы или записи.

##  <a name="operator_neq"></a>  CComVariant::operator! =

Указывает, является ли `CComVariant` не совпадает с указанным ВАРИАНТОМ.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение TRUE, если тип или значение *varSrc* не равно значению или тип, соответственно, из `CComVariant` объекта. В противном случае — значение FALSE. Оператор использует языковой стандарт пользователя по умолчанию для выполнения сравнения.

Оператор сравнивает только значение типа variant. Она сравнивает строки, целые числа и чисел с плавающей запятой, но не массивы или записи.

##  <a name="operator_lt"></a>  CComVariant::operator &lt;

Указывает, является ли `CComVariant` объект меньше указанного ВАРИАНТА.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение TRUE, если значение `CComVariant` объект меньше, чем значение *varSrc*. В противном случае — значение FALSE. Оператор использует языковой стандарт пользователя по умолчанию для выполнения сравнения.

##  <a name="operator_gt"></a>  CComVariant::operator &gt;

Указывает, является ли `CComVariant` объект больше, чем указанный тип VARIANT.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение TRUE, если значение `CComVariant` объект больше, чем значение *varSrc*. В противном случае — значение FALSE. Оператор использует языковой стандарт пользователя по умолчанию для выполнения сравнения.

##  <a name="readfromstream"></a>  CComVariant::ReadFromStream

Задает базовый ВАРИАНТ на значение VARIANT, содержащихся в заданном потоке.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
[in] Указатель на [IStream](/windows/desktop/api/objidl/nn-objidl-istream) интерфейса на поток, содержащий данные.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`ReadToStream` требуется предыдущего вызова [WriteToStream](#writetostream).

##  <a name="setbyref"></a>  CComVariant::SetByRef

Инициализирует `CComVariant` и устанавливает `vt` члена VT_BYREF.

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип VARIANT, например, BSTR **int**, или **char**.

*pT*<br/>
Указатель, используемый для инициализации `CComVariant` объекта.

### <a name="remarks"></a>Примечания

`SetByRef` является шаблоном функции, который инициализирует `CComVariant` объекта к указателю *pT* и задает `vt` члена VT_BYREF. Пример:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

##  <a name="writetostream"></a>  CComVariant::WriteToStream

Сохраняет базовый ВАРИАНТ в поток.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
[in] Указатель на [IStream](/windows/desktop/api/objidl/nn-objidl-istream) интерфейса в потоке.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)