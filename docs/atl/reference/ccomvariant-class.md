---
title: "Класс CComVariant | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 67e5aeee2aaa96b143962beb0790e3854ff7de01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomvariant-class"></a>Класс CComVariant
Этот класс переносит `VARIANT` типа, предоставляя элемент, указывающий тип данных, хранящихся.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
cpp
class CComVariant : public tagVARIANT  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComVariant::CComVariant](#ccomvariant)|Конструктор.|  
|[CComVariant:: ~ CComVariant](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComVariant::Attach](#attach)|Присоединяет **VARIANT** для `CComVariant` объекта.|  
|[CComVariant::ChangeType](#changetype)|Преобразует `CComVariant` объекта в новый тип.|  
|[CComVariant::Clear](#clear)|Очищает `CComVariant` объекта.|  
|[CComVariant::Copy](#copy)|Копирует **VARIANT** для `CComVariant` объекта.|  
|[CComVariant::CopyTo](#copyto)|Копирует содержимое `CComVariant` объекта.|  
|[CComVariant::Detach](#detach)|Отсоединяет базовый **VARIANT** из `CComVariant` объекта.|  
|[CComVariant::GetSize](#getsize)|Возвращает размер в байтах содержимого `CComVariant` объекта.|  
|[CComVariant::ReadFromStream](#readfromstream)|Загружает **VARIANT** из потока.|  
|[CComVariant::SetByRef](#setbyref)|Инициализирует `CComVariant` и устанавливает **vt** члена **VT_BYREF**.|  
|[CComVariant::WriteToStream](#writetostream)|Сохраняет базовый **VARIANT** в поток.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|||  
|-|-|  
|[CComVariant::operator <](#operator_lt)|Указывает, является ли `CComVariant` объект меньше, чем заданный **VARIANT**.|  
|[CComVariant::operator >](#operator_gt)|Указывает, является ли `CComVariant` объект больше, чем заданный **VARIANT**.|  
|[оператор! =](#operator_neq)|Указывает, является ли `CComVariant` неравенство указанного объекта **VARIANT**.|  
|[оператор =](#operator_eq)|Присваивает значение свойству `CComVariant` объекта.|  
|[оператор ==](#operator_eq_eq)|Указывает, является ли `CComVariant` эквивалентны указанный объект **VARIANT**.|  
  
## <a name="remarks"></a>Примечания  
 `CComVariant`заключает в оболочку `VARIANT and VARIANTARG` тип, который состоит из объединения и элемент, указывающий тип данных, хранящихся в объединении. **VARIANT**s обычно используются для автоматизации.  
  
 `CComVariant`является производным от **VARIANT** типа таким образом, его можно использовать везде, где **VARIANT** может использоваться. Например, можно использовать **V_VT** макрос для извлечения типа `CComVariant` или использовать **vt** член непосредственно так же, как с **VARIANT**.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `tagVARIANT`  
  
 `CComVariant`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  
  
##  <a name="attach"></a>CComVariant::Attach  
 Безопасно удаляет текущее содержимое `CComVariant` объекта, копируется из `pSrc` этого объекта, в затем задает значение типа variant `pSrc` для `VT_EMPTY`.  
  
```
HRESULT Attach(VARIANT* pSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `pSrc`  
 [in] Указывает на [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) для присоединения к объекту.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Владение данные, хранящиеся в `pSrc` передается `CComVariant` объекта.  
  
##  <a name="ccomvariant"></a>CComVariant::CComVariant  
 Каждый конструктор обрабатывает безопасном инициализации `CComVariant` путем вызова метода `VariantInit` функции Win32 или установив значение и тип согласно параметрам переданного объекта.  
  
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
 *varSrc*  
 [in] `CComVariant` Или `VARIANT` используется для инициализации `CComVariant` объекта. Содержимое данного типа источника копируются в место назначения без преобразования.  
  
 `lpszSrc`  
 [in] Строка, используемая для инициализации `CComVariant` объекта. Можно передать нулем Интернете (Юникод) строка символов для **LPCOLESTR** версии конструктора или в строку ANSI для `LPCSTR` версии. В любом случае строка преобразуется в строку в Юникоде `BSTR` выделенной с помощью **SysAllocString**. Тип `CComVariant` объект будет `VT_BSTR`.  
  
 `bSrc`  
 [in] `bool` Используется для инициализации `CComVariant` объекта. `bool` Преобразовать аргумент **VARIANT_BOOL** перед сохранением. Тип `CComVariant` объект будет `VT_BOOL`.  
  
 `nSrc`  
 [in] `int`, **БАЙТОВ**, **короткие**, **длинные**, **longlong ПРИВЕДЕННЫМ**, **ULONGLONG**, **short без знака**, `unsigned long`, или `unsigned int` используется для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**,  **VT_UI4**, или **VT_UI4**соответственно.  
  
 `vtSrc`  
 [in] Тип variant. Если первый аргумент принимает значение `int`, допустимые типы: `VT_I4` и **VT_INT**. Если первый аргумент принимает значение **длинные**, допустимые типы: `VT_I4` и `VT_ERROR`. Если первый аргумент принимает значение **двойные**, допустимые типы: `VT_R8` и `VT_DATE`. Если первый аргумент принимает значение `unsigned int`, допустимые типы: **VT_UI4** и **VT_UINT**.  
  
 `fltSrc`  
 [in] **Float** используется для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет `VT_R4`.  
  
 `dblSrc`  
 [in] **Двойные** используется для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет `VT_R8`.  
  
 `cySrc`  
 [in] **CY** используется для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет `VT_CY`.  
  
 `pSrc`  
 [in] `IDispatch` Или **IUnknown** указатель, используемый для инициализации `CComVariant` объекта. `AddRef`будет вызван в указателе на интерфейс. Тип `CComVariant` объект будет **VT_DISPATCH** или **VT_UNKNOWN**соответственно.  
  
 Или **SAFERRAY** указатель, используемый для инициализации `CComVariant` объекта. Копия **SAFEARRAY** хранится в `CComVariant` объекта. Тип `CComVariant` объекта будет представлять собой сочетание исходный тип **SAFEARRAY** и **VT_ARRAY**.  
  
 `cSrc`  
 [in] `char` Используется для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет **VT_I1**.  
  
 `bstrSrc`  
 [in] Строки BSTR используется для инициализации `CComVariant` объекта. Тип `CComVariant` объект будет `VT_BSTR`.  
  
### <a name="remarks"></a>Примечания  
 Деструктор управляет очистки путем вызова [CComVariant::Clear](#clear).  
  
##  <a name="dtor"></a>CComVariant:: ~ CComVariant  
 Деструктор  
  
```
~CComVariant() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод управляет очистки путем вызова [CComVariant::Clear](#clear).  
  
##  <a name="changetype"></a>CComVariant::ChangeType  
 Преобразует `CComVariant` объекта в новый тип.  
  
```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `vtNew`  
 [in] Новый тип для `CComVariant` объекта.  
  
 `pSrc`  
 [in] Указатель на `VARIANT` , значение которого будут преобразованы в новый тип. Значение по умолчанию — **NULL**, то есть `CComVariant` объекта будет преобразован на месте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Если передать значение `pSrc`, `ChangeType` будет использовать это **VARIANT** как источник для преобразования. В противном случае `CComVariant` объекта будет источником.  
  
##  <a name="clear"></a>CComVariant::Clear  
 Очищает `CComVariant` путем вызова метода `VariantClear` функции Win32.  
  
```
HRESULT Clear();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Автоматически вызывает деструктор **снимите**.  
  
##  <a name="copy"></a>CComVariant::Copy  
 Освобождает `CComVariant` и назначает его копией указанного объекта **VARIANT**.  
  
```
HRESULT Copy(const VARIANT* pSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `pSrc`  
 [in] Указатель на [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="copyto"></a>CComVariant::CopyTo  
 Копирует содержимое `CComVariant` объекта.  
  
```
HRESULT CopyTo(BSTR* pstrDest);
```  
  
### <a name="parameters"></a>Параметры  
 *pstrDest*  
 Указывает на `BSTR` , получит копию содержимого `CComVariant` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 **CComVariant** объект должен иметь тип `VT_BSTR`.  
  
##  <a name="detach"></a>CComVariant::Detach  
 Отсоединяет базовый **VARIANT** из `CComVariant` объекта и задает тип объекта для `VT_EMPTY`.  
  
```
HRESULT Detach(VARIANT* pDest);
```  
  
### <a name="parameters"></a>Параметры  
 `pDest`  
 [out] Возвращает базовый `VARIANT` значение объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что содержимое `VARIANT` ссылается `pDest` автоматически очищается перед назначением значение и тип вызывающего объекта **CComVariant** объекта.  
  
##  <a name="getsize"></a>CComVariant::GetSize  
 Для простой фиксированного размера `VARIANT`s, этот метод возвращает `sizeof` базовый тип данных плюс `sizeof(VARTYPE)`.  
  
```
ULONG GetSize() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер в байтах текущее содержимое `CComVariant` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если `VARIANT` содержит указатель на интерфейс `GetSize` запрашивает `IPersistStream` или `IPersistStreamInit`. Если успешно, возвращается значение, возвращаемое младшие 32 бита `GetSizeMax` , а также `sizeof` `CLSID` и `sizeof(VARTYPE)`. Если указатель интерфейса `NULL`, `GetSize` возвращает `sizeof` `CLSID` , а также `sizeof(VARTYPE)`. Если общий размер больше, чем `ULONG_MAX`, `GetSize` возвращает `sizeof(VARTYPE)` что указывает на ошибку.  
  
 Во всех остальных случаях временную `VARIANT` типа `VT_BSTR` приводится из текущего `VARIANT`. Длина этого `BSTR` вычисляется как размер длину строки, а также длину самой строки плюс размер нуль-символ плюс `sizeof(VARTYPE)`. Если `VARIANT` не может быть преобразован к `VARIANT` типа `VT_BSTR`, `GetSize` возвращает `sizeof(VARTYPE)`.  
  
 Размер, возвращаемый этим методом совпадает с количеством байтов, использованных [CComVariant::WriteToStream](#writetostream) успешно условиях.  
  
##  <a name="operator_eq"></a>CComVariant::operator =  
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
 *varSrc*  
 [in] `CComVariant` Или [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) должен назначаться `CComVariant` объекта. Содержимое данного типа источника копируются в место назначения без преобразования.  
  
 `bstrSrc`  
 [in] BSTR, назначаемый `CComVariant` объекта. Тип `CComVariant` объект будет `VT_BSTR`.  
  
 `lpszSrc`  
 [in] Символьная строка должна назначаться `CComVariant` объекта. Можно передать нулем Интернете (Юникод) строка символов для **LPCOLESTR** версию оператора или строки ANSI для `LPCSTR` версии. В любом случае строка преобразуется в строку в Юникоде `BSTR` выделенной с помощью **SysAllocString**. Тип `CComVariant` объект будет `VT_BSTR`.  
  
 `bSrc`  
 [in] `bool` Должен назначаться `CComVariant` объекта. `bool` Преобразовать аргумент **VARIANT_BOOL** перед сохранением. Тип `CComVariant` объект будет `VT_BOOL`.  
  
 `nSrc`  
 [in] `int`, **БАЙТОВ**, **короткие**, **длинные**, **longlong ПРИВЕДЕННЫМ**, **ULONGLONG**, **short без знака**, `unsigned long`, или `unsigned int` должен назначаться `CComVariant` объекта. Тип `CComVariant` объект будет `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**,  **VT_UI4**, или **VT_UI4**соответственно.  
  
 `fltSrc`  
 [in] **Float** должен назначаться `CComVariant` объекта. Тип `CComVariant` объект будет `VT_R4`.  
  
 `dblSrc`  
 [in] **Двойные** должен назначаться `CComVariant` объекта. Тип `CComVariant` объект будет `VT_R8`.  
  
 `cySrc`  
 [in] **CY** должен назначаться `CComVariant` объекта. Тип `CComVariant` объект будет `VT_CY`.  
  
 `pSrc`  
 [in] `IDispatch` Или **IUnknown** указатель должен назначаться `CComVariant` объекта. `AddRef`будет вызван в указателе на интерфейс. Тип `CComVariant` объект будет **VT_DISPATCH** или **VT_UNKNOWN**соответственно.  
  
 Или **SAFEARRAY** указатель должен назначаться `CComVariant` объекта. Копия **SAFEARRAY** хранится в `CComVariant` объекта. Тип `CComVariant` объекта будет представлять собой сочетание исходный тип **SAFEARRAY** и **VT_ARRAY**.  
  
 `cSrc`  
 [in] Char для назначения `CComVariant` объекта. Тип `CComVariant` объект будет **VT_I1**.  
  
##  <a name="operator_eq_eq"></a>CComVariant::operator ==  
 Указывает, является ли `CComVariant` эквивалентны указанный объект **VARIANT**.  
  
```
bool operator==(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает **true** Если значение и тип *varSrc* равны значение и тип, соответственно, для `CComVariant` объекта. в противном случае **false**. Оператор использует языковой стандарт пользователя по умолчанию для выполнения сравнения.  
  
 Оператор сравнивает значение типы variant. Она сравнивает строки, целых чисел и чисел с плавающей запятой, но не массивы или записи.  
  
##  <a name="operator_neq"></a>CComVariant::operator! =  
 Указывает, является ли `CComVariant` неравенство указанного объекта **VARIANT**.  
  
```
bool operator!=(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает **true** Если значение или тип *varSrc* не равно значение или тип, соответственно, для `CComVariant` объекта. в противном случае **false**. Оператор использует языковой стандарт пользователя по умолчанию для выполнения сравнения.  
  
 Оператор сравнивает значение типы variant. Она сравнивает строки, целых чисел и чисел с плавающей запятой, но не массивы или записи.  
  
##  <a name="operator_lt"></a>CComVariant::operator&lt;  
 Указывает, является ли `CComVariant` объект меньше, чем заданный **VARIANT**.  
  
```
bool operator<(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает **true** Если значение `CComVariant` объект меньше, чем значение *varSrc*. в противном случае **false**. Оператор использует языковой стандарт пользователя по умолчанию для выполнения сравнения.  
  
##  <a name="operator_gt"></a>CComVariant::operator&gt;  
 Указывает, является ли `CComVariant` объект больше, чем заданный **VARIANT**.  
  
```
bool operator>(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает **true** Если значение `CComVariant` объект больше, чем значение *varSrc*. в противном случае **false**. Оператор использует языковой стандарт пользователя по умолчанию для выполнения сравнения.  
  
##  <a name="readfromstream"></a>CComVariant::ReadFromStream  
 Задает базовый **VARIANT** для **VARIANT** содержащихся в указанном потоке.  
  
```
HRESULT ReadFromStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Параметры  
 `pStream`  
 [in] Указатель на [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) интерфейса на поток, содержащий данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 **ReadToStream** требует предыдущего вызова [WriteToStream](#writetostream).  
  
##  <a name="setbyref"></a>CComVariant::SetByRef  
 Инициализирует `CComVariant` и устанавливает **vt** члена **VT_BYREF**.  
  
```
template < typename T >
void SetByRef(T* pT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип **VARIANT**, например, `BSTR`, `int`, или `char`.  
  
 *pT*  
 Указатель, используемый для инициализации `CComVariant` объекта.  
  
### <a name="remarks"></a>Примечания  
 `SetByRef`является шаблоном функции, который инициализирует `CComVariant` объекта к указателю *pT* и задает **vt** члена **VT_BYREF**. Пример:  
  
 [!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]  
  
##  <a name="writetostream"></a>CComVariant::WriteToStream  
 Сохраняет базовый **VARIANT** в поток.  
  
```
HRESULT WriteToStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Параметры  
 `pStream`  
 [in] Указатель на [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) интерфейса в потоке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)