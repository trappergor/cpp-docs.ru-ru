---
title: Класс CComBSTR
ms.date: 11/04/2016
f1_keywords:
- CComBSTR
- ATLBASE/ATL::CComBSTR
- ATLBASE/ATL::CComBSTR::CComBSTR
- ATLBASE/ATL::CComBSTR::Append
- ATLBASE/ATL::CComBSTR::AppendBSTR
- ATLBASE/ATL::CComBSTR::AppendBytes
- ATLBASE/ATL::CComBSTR::ArrayToBSTR
- ATLBASE/ATL::CComBSTR::AssignBSTR
- ATLBASE/ATL::CComBSTR::Attach
- ATLBASE/ATL::CComBSTR::BSTRToArray
- ATLBASE/ATL::CComBSTR::ByteLength
- ATLBASE/ATL::CComBSTR::Copy
- ATLBASE/ATL::CComBSTR::CopyTo
- ATLBASE/ATL::CComBSTR::Detach
- ATLBASE/ATL::CComBSTR::Empty
- ATLBASE/ATL::CComBSTR::Length
- ATLBASE/ATL::CComBSTR::LoadString
- ATLBASE/ATL::CComBSTR::ReadFromStream
- ATLBASE/ATL::CComBSTR::ToLower
- ATLBASE/ATL::CComBSTR::ToUpper
- ATLBASE/ATL::CComBSTR::WriteToStream
- ATLBASE/ATL::CComBSTR::m_str
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
ms.openlocfilehash: 52e8472e315932978af38d405c753b0a62fcbe45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475651"
---
# <a name="ccombstr-class"></a>Класс CComBSTR

Этот класс является оболочкой для [BSTR](/previous-versions/windows/desktop/automat/bstr)s.

## <a name="syntax"></a>Синтаксис

```
class CComBSTR
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComBSTR::CComBSTR](#ccombstr)|Конструктор.|
|[CComBSTR:: ~ CComBSTR](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComBSTR::Append](#append)|Добавляет строку в `m_str`.|
|[CComBSTR::AppendBSTR](#appendbstr)|Добавляет строку BSTR, чтобы `m_str`.|
|[CComBSTR::AppendBytes](#appendbytes)|Добавляет указанное число байтов для `m_str`.|
|[CComBSTR::ArrayToBSTR](#arraytobstr)|Создает строку BSTR с первого символа каждого элемента в массив safearray и присоединяет его к `CComBSTR` объекта.|
|[CComBSTR::AssignBSTR](#assignbstr)|Назначает BSTR в `m_str`.|
|[CComBSTR::Attach](#attach)|Присоединяет BSTR в `CComBSTR` объекта.|
|[CComBSTR::BSTRToArray](#bstrtoarray)|Создает отсчитываемый от нуля одномерный массив типа safearray, где каждый элемент массива является символ из `CComBSTR` объекта.|
|[CComBSTR::ByteLength](#bytelength)|Возвращает длину `m_str` в байтах.|
|[CComBSTR::Copy](#copy)|Возвращает копию объекта `m_str`.|
|[CComBSTR::CopyTo](#copyto)|Возвращает копию объекта `m_str` через **[out]** параметр|
|[CComBSTR::Detach](#detach)|Отсоединяет `m_str` из `CComBSTR` объекта.|
|[CComBSTR::Empty](#empty)|Освобождает `m_str`.|
|[CComBSTR::Length](#length)|Возвращает длину `m_str`.|
|[CComBSTR::LoadString](#loadstring)|Загружает строку ресурса.|
|[CComBSTR::ReadFromStream](#readfromstream)|Загружает объект BSTR из потока.|
|[CComBSTR::ToLower](#tolower)|Преобразует строку в нижний регистр.|
|[CComBSTR::ToUpper](#toupper)|Преобразует строку в верхний регистр.|
|[CComBSTR::WriteToStream](#writetostream)|Сохраняет `m_str` в поток.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CComBSTR::operator BSTR](#operator_bstr)|Приведения `CComBSTR` объекта на строку BSTR.|
|[CComBSTR::operator!](#operator_not)|Возвращает значение TRUE или FALSE, в зависимости от того, следует ли `m_str`имеет значение NULL.|
|[CComBSTR::operator! =](#operator_neq)|Сравнивает `CComBSTR` со строкой.|
|[CComBSTR::operator &](#operator_amp)|Возвращает адрес `m_str`.|
|[CComBSTR::operator +=](#operator_add_eq)|Добавляет `CComBSTR` к объекту.|
|[CComBSTR::operator <](#operator_lt)|Сравнивает `CComBSTR` со строкой.|
|[CComBSTR::operator =](#operator_eq)|Присваивает значение свойству `m_str`.|
|[CComBSTR::operator ==](#operator_eq_eq)|Сравнивает `CComBSTR` со строкой.|
|[CComBSTR::operator >](#operator_gt)|Сравнивает `CComBSTR` со строкой.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComBSTR::m_str](#m_str)|Содержит строку BSTR, связанные с `CComBSTR` объекта.|

## <a name="remarks"></a>Примечания

`CComBSTR` Класс является оболочкой для строк BSTR, которые представляют собой строки с префиксом. Длина сохраняется как целое число в области памяти выше данные в строке.

Объект [BSTR](/previous-versions/windows/desktop/automat/bstr) завершается нуль символом после последней инвентаризации символ, но также может содержать символы null, встроенные в строке. Длина строки определяется количество символов, не первый символ null.

> [!NOTE]
>  `CComBSTR` Класс предоставляет ряд членов (конструкторы, операторы присваивания и операторы сравнения), которые принимают строки ANSI или Юникод в качестве аргументов. ANSI версии этих функций менее эффективны, чем их аналоги Юникода, так как временные строки в Юникоде часто создаются внутренним образом. Для повышения эффективности используете версии Юникода, где это возможно.

> [!NOTE]
>  Например, из-за поведение улучшенные подстановки, реализованные в Visual Studio .NET, код `bstr = L"String2" + bstr;`, которой может скомпилирован в предыдущих выпусках необходимо реализовывать как `bstr = CStringW(L"String2") + bstr`.

Список предупреждения при использовании `CComBSTR`, см. в разделе [программирование с использованием CComBSTR](../../atl/programming-with-ccombstr-atl.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="append"></a>  CComBSTR::Append

Добавляет либо *lpsz* или BSTR членом *bstrSrc* для [m_str](#m_str).

```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```

### <a name="parameters"></a>Параметры

*bstrSrc*<br/>
[in] Объект `CComBSTR` добавляемый объект.

*ch*<br/>
[in] Добавляемый символ.

*lpsz*<br/>
[in] Строка символов с завершающим нулевым символом, для добавления. Вы можете передать строку Юникода через перегрузку LPCOLESTR или строка ANSI через LPCSTR версии.

*nLen*<br/>
[in] Число символов из *lpsz* для добавления.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK в случае успеха или любой стандартный значение HRESULT ошибки.

### <a name="remarks"></a>Примечания

В строку ANSI преобразуются в Юникод до, добавляемый.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

##  <a name="appendbstr"></a>  CComBSTR::AppendBSTR

Добавляет указанный строки BSTR [m_str](#m_str).

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
[in] BSTR, для добавления.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK в случае успеха или любой стандартный значение HRESULT ошибки.

### <a name="remarks"></a>Примечания

В этот метод не следует передавать обычной строки расширенных символов. Компилятор не может возникнут ошибки времени выполнения и обнаружения ошибок.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

##  <a name="appendbytes"></a>  CComBSTR::AppendBytes

Добавляет указанное число байтов для [m_str](#m_str) без преобразования.

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>Параметры

*lpsz*<br/>
[in] Указатель на массив байтов для добавления.

*p*<br/>
[in] Число байтов для добавления.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK в случае успеха или любой стандартный значение HRESULT ошибки.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

##  <a name="arraytobstr"></a>  CComBSTR::ArrayToBSTR

Освобождает любую существующую строку в `CComBSTR` объекта, затем создает BSTR с первого символа каждого элемента в массив safearray и присоединяет его к `CComBSTR` объекта.

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>Параметры

*pSrc*<br/>
[in] Массив safearray, содержащий элементы, используемые для создания строки.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK в случае успеха или любой стандартный значение HRESULT ошибки.

##  <a name="assignbstr"></a>  CComBSTR::AssignBSTR

Назначает BSTR в [m_str](#m_str).

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>Параметры

*bstrSrc*<br/>
[in] BSTR, чтобы назначить текущего `CComBSTR` объекта.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK в случае успеха или любой стандартный значение HRESULT ошибки.

##  <a name="attach"></a>  CComBSTR::Attach

Присоединяет BSTR в `CComBSTR` объекта, задав [m_str](#m_str) члена *src*.

```
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>Параметры

*src*<br/>
[in] BSTR, для прикрепления к объекту.

### <a name="remarks"></a>Примечания

В этот метод не следует передавать обычной строки расширенных символов. Компилятор не может возникнут ошибки времени выполнения и обнаружения ошибок.

> [!NOTE]
>  Этот метод будет утверждать, если `m_str` отлично от NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="bstrtoarray"></a>  CComBSTR::BSTRToArray

Создает отсчитываемый от нуля одномерный массив типа safearray, где каждый элемент массива является символ из `CComBSTR` объекта.

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>Параметры

*ppArray*<br/>
[out] Указатель на safearray, используемый для хранения результатов функции.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK в случае успеха или любой стандартный значение HRESULT ошибки.

##  <a name="bytelength"></a>  CComBSTR::ByteLength

Возвращает число байтов в `m_str`, за исключением завершающего нуль-символа.

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Длина [m_str](#m_str) элемента в байтах.

### <a name="remarks"></a>Примечания

Возвращает 0, если `m_str` имеет значение NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

##  <a name="ccombstr"></a>  CComBSTR::CComBSTR

Конструктор. Конструктор по умолчанию присваивает [m_str](#m_str) элемент NULL.

```
CComBSTR() throw();
CComBSTR(const CComBSTR& src);
CComBSTR(REFGUID  guid);
CComBSTR(int nSize);
CComBSTR(int nSize, LPCOLESTR sz);
CComBSTR(int nSize, LPCSTR sz);
CComBSTR(LPCOLESTR pSrc);
CComBSTR(LPCSTR pSrc);
CComBSTR(CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="parameters"></a>Параметры

*nSize*<br/>
[in] Число символов для копирования из *sz* или начальный размер в символах для `CComBSTR`.

*sz*<br/>
[входные данные] Строка для копирования. Версия Юникода указывает LPCOLESTR; версия ANSI указывает LPCSTR.

*pSrc*<br/>
[входные данные] Строка для копирования. Версия Юникода указывает LPCOLESTR; версия ANSI указывает LPCSTR.

*src*<br/>
[входные данные] Объект `CComBSTR`.

*Идентификатор GUID*<br/>
[in] Ссылку на `GUID` структуры.

### <a name="remarks"></a>Примечания

Конструктор копирования присваивает `m_str` на копию BSTR членом *src*. `REFGUID` Конструктор преобразует GUID в строку с помощью `StringFromGUID2` и сохраняет результат.

Другие конструкторы присваивают `m_str` копию указанной строки. Если передать значение *nSize*, тогда только *nSize* будут скопированы символы, а затем завершающий нуль-символ.

`CComBSTR` поддерживает семантику перемещения. Конструктор перемещения (принимающий ссылку rvalue (`&&`)) можно использовать, чтобы создать объект, который использует те же базовые данные, что и старый объект, передаваемый как аргумент, без необходимости копировать объект.

Деструктор освобождает строку, на которую указывает `m_str`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

##  <a name="dtor"></a>  CComBSTR:: ~ CComBSTR

Деструктор

```
~CComBSTR();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает строку, на которую указывает `m_str`.

##  <a name="copy"></a>  CComBSTR::Copy

Выделяет и возвращает копию объекта `m_str`.

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Копия [m_str](#m_str) член. Если `m_str` равен NULL, возвращается значение NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

##  <a name="copyto"></a>  CComBSTR::CopyTo

Выделяет и возвращает копию объекта [m_str](#m_str) через параметр.

```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```

### <a name="parameters"></a>Параметры

*pbstr*<br/>
[out] Адрес строку BSTR, в котором для возврата строки, выделенной с помощью этого метода.

*pvarDest*<br/>
[out] Адрес объекта типа VARIANT, в котором для возврата строки, выделенной с помощью этого метода.

### <a name="return-value"></a>Возвращаемое значение

Стандартный значение HRESULT, указывающее, успешно ли выполнен копии.

### <a name="remarks"></a>Примечания

После вызова этого метода, тип VARIANT, на которые указывают *pvarDest* будет иметь тип VT_BSTR.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

##  <a name="detach"></a>  CComBSTR::Detach

Отсоединяет [m_str](#m_str) из `CComBSTR` и устанавливает `m_str` значение NULL.

```
BSTR Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

BSTR, связанные с `CComBSTR` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

##  <a name="empty"></a>  CComBSTR::Empty

Освобождает [m_str](#m_str) член.

```
void Empty() throw();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

##  <a name="length"></a>  CComBSTR::Length

Возвращает количество символов в `m_str`, за исключением завершающего нуль-символа.

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Длина [m_str](#m_str) член.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

##  <a name="loadstring"></a>  CComBSTR::LoadString

Загружает строку ресурса, задаваемого *nID* и сохраняет его в этом объекте.

```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```

### <a name="parameters"></a>Параметры

См. в разделе [LoadString](/windows/desktop/api/winuser/nf-winuser-loadstringa) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если строка успешно загружены; в противном случае возвращает значение FALSE.

### <a name="remarks"></a>Примечания

Первая функция загружает ресурс из модуля, идентифицируемого по вы через *hInst* параметра. Вторая функция загружает ресурс из модуля ресурсов, связанных с [CComModule](../../atl/reference/ccommodule-class.md)-производный объект, используемый в этом проекте.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]

##  <a name="m_str"></a>  CComBSTR::m_str

Содержит строку BSTR, связанные с `CComBSTR` объекта.

```
BSTR m_str;
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

##  <a name="operator_bstr"></a>  CComBSTR::operator BSTR

Приведения `CComBSTR` объекта на строку BSTR.

```
operator BSTR() const throw();
```

### <a name="remarks"></a>Примечания

Вы можете передавать `CComBSTR` объектов функциям, которые имеют **[in] BSTR** параметров.

### <a name="example"></a>Пример

См. в примере [CComBSTR::m_str](#m_str).

##  <a name="operator_not"></a>  CComBSTR::operator!

Проверяет, является ли строка BSTR значение NULL.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если [m_str](#m_str) элемент является пустой; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот оператор проверяет только значения NULL, не для пустой строки.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="operator_neq"></a>  CComBSTR::operator! =

Возвращает логическое отрицание [оператор ==](#operator_eq_eq).

```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```

### <a name="parameters"></a>Параметры

*bstrSrc*<br/>
[входные данные] Объект `CComBSTR`.

*pszSrc*<br/>
[in] Строка с завершающим нулевым символом.

*nNull*<br/>
[in] Должен иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент с которым производится сравнение не равно `CComBSTR` ; в противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

`CComBSTR`s сравниваются в текстовой форме в контексте языка пользователя по умолчанию. Оператор сравнения окончательный просто сравнивает содержащуюся строку наличие значения NULL.

##  <a name="operator_amp"></a>  CComBSTR::operator &amp;

Возвращает адрес BSTR, хранящиеся в [m_str](#m_str) член.

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>Примечания

`CComBstr operator &` есть специальное утверждение, связанная с ним для выявления утечек памяти. Программа установит `m_str` член инициализируется. Это утверждение был создан для выявления ситуаций, когда программист использует `& operator` присвоить новое значение `m_str` член, не освобождая первый выделение `m_str`. Если `m_str` имеет значение NULL, то программа предполагает, что m_str не был выделен еще. В этом случае программа не будет утверждать.

Это утверждение не включена по умолчанию. Определите ATL_CCOMBSTR_ADDRESS_OF_ASSERT, чтобы включить это утверждение.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

##  <a name="operator_add_eq"></a>  CComBSTR::operator +=

Добавляет строку в `CComBSTR` объекта.

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>Параметры

*bstrSrc*<br/>
[in] Объект `CComBSTR` добавляемый объект.

*pszSrc*<br/>
[in] Добавляемая строка с завершающим нулевым символом.

### <a name="remarks"></a>Примечания

`CComBSTR`s сравниваются в текстовой форме в контексте языка пользователя по умолчанию. LPCOLESTR сравнение выполняется с помощью `memcmp` на основе необработанных данных в каждой строке. Сравнение LPCSTR выполняется так же после временных Юникода копия *pszSrc* будет создана. Оператор сравнения окончательный просто сравнивает содержащуюся строку наличие значения NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

##  <a name="operator_lt"></a>  CComBSTR::operator &lt;

Сравнивает `CComBSTR` со строкой.

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент сравниваемых меньше, чем `CComBSTR` ; в противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Сравнение выполняется с помощью языка пользователя по умолчанию.

##  <a name="operator_eq"></a>  CComBSTR::operator =

Наборы [m_str](#m_str) члена на копию *pSrc* или копию BSTR членом *src*. Оператор присваивания перемещения перемещает `src` не копируя его.

```
CComBSTR& operator= (const CComBSTR& src);
CComBSTR& operator= (LPCOLESTR pSrc);
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="remarks"></a>Примечания

*PSrc* параметр задает LPCOLESTR для версии Юникода или LPCSTR для версии ANSI.

### <a name="example"></a>Пример

См. в примере [CComBSTR::Copy](#copy).

##  <a name="operator_eq_eq"></a>  CComBSTR::operator ==

Сравнивает `CComBSTR` со строкой. `CComBSTR`s сравниваются в текстовой форме в контексте языка пользователя по умолчанию.

```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```

### <a name="parameters"></a>Параметры

*bstrSrc*<br/>
[входные данные] Объект `CComBSTR`.

*pszSrc*<br/>
[in] Строка с завершающим нулевым символом.

*nNull*<br/>
[in] Должен иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент сравниваемых равен `CComBSTR` ; в противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Оператор сравнения окончательный просто сравнивает содержащуюся строку наличие значения NULL.

##  <a name="operator_gt"></a>  CComBSTR::operator &gt;

Сравнивает `CComBSTR` со строкой.

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент сравниваемых больше, чем `CComBSTR` ; в противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Сравнение выполняется с помощью языка пользователя по умолчанию.

##  <a name="readfromstream"></a>  CComBSTR::ReadFromStream

Наборы [m_str](#m_str) элемент строку BSTR, содержащихся в заданном потоке.

```
HRESULT ReadFromStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
[in] Указатель на [IStream](/windows/desktop/api/objidl/nn-objidl-istream) интерфейса на поток, содержащий данные.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`ReadToStream` требуется содержимое потока в текущей позиции для обеспечения совместимости с форматом записывается с помощью вызова [WriteToStream](#writetostream).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

##  <a name="tolower"></a>  CComBSTR::ToLower

Преобразует содержащуюся строку в нижний регистр.

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

См. в разделе `CharLowerBuff` Дополнительные сведения о том, как выполняется преобразование.

##  <a name="toupper"></a>  CComBSTR::ToUpper

Преобразует содержащуюся строку в верхний регистр.

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

См. в разделе `CharUpperBuff` Дополнительные сведения о том, как выполняется преобразование.

##  <a name="writetostream"></a>  CComBSTR::WriteToStream

Сохраняет [m_str](#m_str) член в поток.

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
[in] Указатель на [IStream](/windows/desktop/api/objidl/nn-objidl-istream) интерфейса в потоке.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Можно повторно создать BSTR из содержимого потока с помощью [ReadFromStream](#readfromstream) функции.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[ATL и макросов преобразования MFC из строки](string-conversion-macros.md)
