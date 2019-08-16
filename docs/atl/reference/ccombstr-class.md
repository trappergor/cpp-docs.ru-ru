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
ms.openlocfilehash: dd45c2ff9b43148e0fe27ebd410a2390a4d12ce2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497559"
---
# <a name="ccombstr-class"></a>Класс CComBSTR

Этот класс является оболочкой для [BSTR](/previous-versions/windows/desktop/automat/bstr)s.

## <a name="syntax"></a>Синтаксис

```
class CComBSTR
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CComBSTR:: CComBSTR](#ccombstr)|Конструктор.|
|[CComBSTR:: ~ CComBSTR](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComBSTR:: Append](#append)|Добавляет строку в `m_str`.|
|[CComBSTR:: Аппендбстр](#appendbstr)|Добавляет строку BSTR в `m_str`.|
|[CComBSTR:: Аппендбитес](#appendbytes)|Добавляет указанное число байтов в `m_str`.|
|[CComBSTR:: Аррайтобстр](#arraytobstr)|Создает строку BSTR из первого символа каждого элемента массива SafeArray и присоединяет его к `CComBSTR` объекту.|
|[CComBSTR:: Ассигнбстр](#assignbstr)|Присваивает значение BSTR для `m_str`.|
|[CComBSTR:: Attach](#attach)|Присоединяет BSTR к `CComBSTR` объекту.|
|[CComBSTR:: Бстртоаррай](#bstrtoarray)|Создает одномерный массив SafeArray, начинающийся с нуля, где каждый элемент массива является символом из `CComBSTR` объекта.|
|[CComBSTR:: ByteLength](#bytelength)|Возвращает длину `m_str` в байтах.|
|[CComBSTR:: Copy](#copy)|Возвращает копию `m_str`.|
|[CComBSTR:: CopyTo](#copyto)|Возвращает копию `m_str` с помощью параметра **[out]** .|
|[CComBSTR::D етач](#detach)|Отсоединяется `CComBSTR`отобъекта `m_str` .|
|[CComBSTR:: Empty](#empty)|`m_str`Бесплатно.|
|[CComBSTR:: Length](#length)|Возвращает длину `m_str`.|
|[CComBSTR:: Лоадстринг](#loadstring)|Загружает строковый ресурс.|
|[CComBSTR:: Реадфромстреам](#readfromstream)|Загружает объект BSTR из потока.|
|[CComBSTR:: ToLower](#tolower)|Преобразует строку в нижний регистр.|
|[CComBSTR:: ToUpper](#toupper)|Преобразует строку в верхний регистр.|
|[CComBSTR:: Вритетостреам](#writetostream)|Сохраняет `m_str` в поток.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CComBSTR:: operator BSTR](#operator_bstr)|`CComBSTR` Приводит объект к типу BSTR.|
|[CComBSTR:: operator!](#operator_not)|Возвращает значение true или false в зависимости от того `m_str`, имеет ли значение null.|
|[CComBSTR:: operator! =](#operator_neq)|`CComBSTR` Сравнивает со строкой.|
|[CComBSTR:: operator &](#operator_amp)|Возвращает адрес `m_str`.|
|[CComBSTR:: operator + =](#operator_add_eq)|Добавляет объект `CComBSTR` к объекту.|
|[CComBSTR:: operator <](#operator_lt)|`CComBSTR` Сравнивает со строкой.|
|[CComBSTR:: operator =](#operator_eq)|Присваивает значение `m_str`.|
|[CComBSTR:: operator = =](#operator_eq_eq)|`CComBSTR` Сравнивает со строкой.|
|[CComBSTR:: operator >](#operator_gt)|`CComBSTR` Сравнивает со строкой.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CComBSTR:: m_str](#m_str)|Содержит строку BSTR, связанную `CComBSTR` с объектом.|

## <a name="remarks"></a>Примечания

`CComBSTR` Класс является оболочкой для bstrs, которые являются строками с префиксом длины. Длина хранится в виде целого числа в области памяти, предшествующей данным в строке.

Символ [BSTR](/previous-versions/windows/desktop/automat/bstr) завершается нулем после последнего подсчета, но также может содержать символы NULL, внедренные в строку. Длина строки определяется числом символов, а не первым символом NULL.

> [!NOTE]
>  `CComBSTR` Класс предоставляет ряд элементов (конструкторы, операторы присваивания и операторы сравнения), которые принимают в качестве аргументов строки в кодировке ANSI или Юникод. Версии этих функций в кодировке ANSI менее эффективны, чем их аналоги в Юникоде, так как временные строки Юникода часто создаются внутренним образом. Для повышения эффективности используйте версии Юникода, где это возможно.

> [!NOTE]
>  Из-за улучшенного поведения поиска, реализованного в Visual Studio .NET, `bstr = L"String2" + bstr;`код, такой как, который мог быть скомпилирован в предыдущих выпусках `bstr = CStringW(L"String2") + bstr`, вместо этого должен быть реализован как.

Список предостережений при использовании `CComBSTR`см. в разделе [программирование с помощью CComBSTR](../../atl/programming-with-ccombstr-atl.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="append"></a>CComBSTR:: Append

Добавляет либо *лпсз* , либо элемент BSTR в *бстрсрк* в [m_str](#m_str).

```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```

### <a name="parameters"></a>Параметры

*бстрсрк*<br/>
окне Добавляемый `CComBSTR` объект.

*ch*<br/>
окне Добавляемый символ.

*лпсз*<br/>
окне Строка символов, заканчивающаяся нулем, для добавления. Строку Юникода можно передать с помощью перегрузки ЛПКОЛЕСТР или строки ANSI с помощью версии LPCSTR.

*нлен*<br/>
окне Число символов из *лпсз* для добавления.

### <a name="return-value"></a>Возвращаемое значение

S_OK при успешном выполнении или любое стандартное значение ошибки HRESULT.

### <a name="remarks"></a>Примечания

Строка ANSI будет преобразована в Юникод перед добавлением.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

##  <a name="appendbstr"></a>CComBSTR:: Аппендбстр

Добавляет указанный BSTR в [m_str](#m_str).

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
окне Добавляемая BSTR.

### <a name="return-value"></a>Возвращаемое значение

S_OK при успешном выполнении или любое стандартное значение ошибки HRESULT.

### <a name="remarks"></a>Примечания

Не передавайте в этот метод обычную строку расширенных символов. Компилятор не может перехватывать ошибки, возникающие во время выполнения.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

##  <a name="appendbytes"></a>CComBSTR:: Аппендбитес

Добавляет указанное число байтов в [m_str](#m_str) без преобразования.

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>Параметры

*лпсз*<br/>
окне Указатель на массив байтов для добавления.

*p*<br/>
окне Число байтов для добавления.

### <a name="return-value"></a>Возвращаемое значение

S_OK при успешном выполнении или любое стандартное значение ошибки HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

##  <a name="arraytobstr"></a>CComBSTR:: Аррайтобстр

Освобождает любую существующую строку, удерживаемую в `CComBSTR` объекте, а затем создает BSTR из первого символа каждого элемента в массиве SafeArray и присоединяет его `CComBSTR` к объекту.

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>Параметры

*pSrc*<br/>
окне Массив SafeArray, содержащий элементы, используемые для создания строки.

### <a name="return-value"></a>Возвращаемое значение

S_OK при успешном выполнении или любое стандартное значение ошибки HRESULT.

##  <a name="assignbstr"></a>CComBSTR:: Ассигнбстр

Присваивает [M_STR](#m_str)BSTR.

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>Параметры

*бстрсрк*<br/>
окне Значение BSTR, присваиваемое текущему `CComBSTR` объекту.

### <a name="return-value"></a>Возвращаемое значение

S_OK при успешном выполнении или любое стандартное значение ошибки HRESULT.

##  <a name="attach"></a>CComBSTR:: Attach

Присоединяет BSTR к `CComBSTR` объекту, устанавливая для элемента [m_str](#m_str) значение *src*.

```
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>Параметры

*src*<br/>
окне Объект BSTR, который необходимо присоединить к объекту.

### <a name="remarks"></a>Примечания

Не передавайте в этот метод обычную строку расширенных символов. Компилятор не может перехватывать ошибки, возникающие во время выполнения.

> [!NOTE]
>  Этот метод будет утверждать, `m_str` если не имеет значение null.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="bstrtoarray"></a>CComBSTR:: Бстртоаррай

Создает одномерный массив SafeArray, начинающийся с нуля, где каждый элемент массива является символом из `CComBSTR` объекта.

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>Параметры

*ппаррай*<br/>
заполняет Указатель на массив SafeArray, используемый для хранения результатов функции.

### <a name="return-value"></a>Возвращаемое значение

S_OK при успешном выполнении или любое стандартное значение ошибки HRESULT.

##  <a name="bytelength"></a>CComBSTR:: ByteLength

Возвращает число байтов в `m_str`, за исключением завершающего нуль символа.

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Длина элемента [m_str](#m_str) в байтах.

### <a name="remarks"></a>Примечания

Возвращает 0, `m_str` если имеет значение null.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

##  <a name="ccombstr"></a>CComBSTR:: CComBSTR

Конструктор. Конструктор по умолчанию присваивает элементу [m_str](#m_str) значение null.

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

*нсизе*<br/>
окне Число символов для копирования из *SZ* или начальный размер в символах для `CComBSTR`.

*SZ*<br/>
[входные данные] Строка для копирования. Версия Юникода определяет ЛПКОЛЕСТР. версия ANSI указывает LPCSTR.

*pSrc*<br/>
[входные данные] Строка для копирования. Версия Юникода определяет ЛПКОЛЕСТР. версия ANSI указывает LPCSTR.

*src*<br/>
[входные данные] Объект `CComBSTR`.

*устройства*<br/>
окне Ссылка на `GUID` структуру.

### <a name="remarks"></a>Примечания

Конструктор копий задает `m_str` копию элемента BSTR в *src*. Конструктор преобразует идентификатор GUID в строку с помощью `StringFromGUID2` и сохраняет результат. `REFGUID`

Другие конструкторы присваивают `m_str` копию указанной строки. Если передать значение для *нсизе*, будут скопированы только *нсизе* символы, за которыми следует завершающий нуль-символ.

`CComBSTR` поддерживает семантику перемещения. Конструктор перемещения (принимающий ссылку rvalue (`&&`)) можно использовать, чтобы создать объект, который использует те же базовые данные, что и старый объект, передаваемый как аргумент, без необходимости копировать объект.

Деструктор освобождает строку, на которую указывает `m_str`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

##  <a name="dtor"></a>CComBSTR:: ~ CComBSTR

Деструктор

```
~CComBSTR();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает строку, на которую указывает `m_str`.

##  <a name="copy"></a>CComBSTR:: Copy

Выделяет и возвращает копию `m_str`.

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Копия элемента [m_str](#m_str) . Если `m_str` имеет значение null, возвращает значение null.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

##  <a name="copyto"></a>CComBSTR:: CopyTo

Выделяет и возвращает копию [m_str](#m_str) через параметр.

```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```

### <a name="parameters"></a>Параметры

*пбстр*<br/>
заполняет Адрес строки BSTR, в которой возвращается строка, выделенная этим методом.

*пвардест*<br/>
заполняет Адрес варианта, в котором возвращается строка, выделенная этим методом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT, указывающее на успешное или неуспешное завершение копирования.

### <a name="remarks"></a>Примечания

После вызова этого метода вариант, на который указывает *пвардест* , будет иметь тип VT_BSTR.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

##  <a name="detach"></a>CComBSTR::D етач

Отсоединяет [m_str](#m_str) от `CComBSTR` объекта и устанавливает `m_str` в значение null.

```
BSTR Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

BSTR, связанный с `CComBSTR` объектом.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

##  <a name="empty"></a>CComBSTR:: Empty

Освобождает элемент [m_str](#m_str) .

```
void Empty() throw();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

##  <a name="length"></a>CComBSTR:: Length

Возвращает количество символов в `m_str`, за исключением завершающего нуль символа.

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Длина элемента [m_str](#m_str) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

##  <a name="loadstring"></a>CComBSTR:: Лоадстринг

Загружает строковый ресурс, заданный параметром *NID* , и сохраняет его в этом объекте.

```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```

### <a name="parameters"></a>Параметры

См. раздел [лоадстринг](/windows/win32/api/winuser/nf-winuser-loadstringw) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если строка успешно загружена; в противном случае возвращает значение FALSE.

### <a name="remarks"></a>Примечания

Первая функция загружает ресурс из модуля, указанного с помощью параметра *хинст* . Вторая функция загружает ресурс из модуля ресурсов, связанного с объектом, производным от [CComModule](../../atl/reference/ccommodule-class.md), который используется в этом проекте.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]

##  <a name="m_str"></a>CComBSTR:: m_str

Содержит строку BSTR, связанную `CComBSTR` с объектом.

```
BSTR m_str;
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

##  <a name="operator_bstr"></a>CComBSTR:: operator BSTR

`CComBSTR` Приводит объект к типу BSTR.

```
operator BSTR() const throw();
```

### <a name="remarks"></a>Примечания

Позволяет передавать `CComBSTR` объекты в функции, имеющие параметры **BSTR [in]** .

### <a name="example"></a>Пример

См. пример для [CComBSTR:: m_str](#m_str).

##  <a name="operator_not"></a>CComBSTR:: operator!

Проверяет, имеет ли строка BSTR значение NULL.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент [m_str](#m_str) имеет значение null; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот оператор проверяет только значение NULL, а не пустую строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="operator_neq"></a>CComBSTR:: operator! =

Возвращает логическое противоположное [оператору = =](#operator_eq_eq).

```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```

### <a name="parameters"></a>Параметры

*бстрсрк*<br/>
[входные данные] Объект `CComBSTR`.

*псзсрк*<br/>
окне Строка, завершающаяся нулем.

*Недопустимо*<br/>
окне Должен иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если сравниваемый элемент не равен `CComBSTR` объекту; в противном случае возвращает значение false.

### <a name="remarks"></a>Примечания

`CComBSTR`сравниваются в текстовом виде в контексте пользовательского языкового стандарта по умолчанию. Окончательный оператор сравнения просто сравнивает автономную строку со значением NULL.

##  <a name="operator_amp"></a>CComBSTR:: operator&amp;

Возвращает адрес BSTR, хранящегося в элементе [m_str](#m_str) .

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>Примечания

`CComBstr operator &`имеет специальное утверждение, связанное с ним, чтобы помочь определить утечки памяти. Программа будет утверждать при `m_str` инициализации элемента. Это утверждение было создано для того, чтобы выявлять ситуации, `& operator` когда программист использует для назначения нового `m_str` значения члену без высвобождения первого выделения `m_str`. Если `m_str` имеет значение null, программа предполагает, что m_str еще не выделена. В этом случае программа не будет утверждать.

Это утверждение не включено по умолчанию. Определите ATL_CCOMBSTR_ADDRESS_OF_ASSERT, чтобы включить это утверждение.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

##  <a name="operator_add_eq"></a>CComBSTR:: operator + =

Добавляет строку в `CComBSTR` объект.

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>Параметры

*бстрсрк*<br/>
окне Добавляемый `CComBSTR` объект.

*псзсрк*<br/>
окне Строка для добавления, заканчивающаяся нулем.

### <a name="remarks"></a>Примечания

`CComBSTR`сравниваются в текстовом виде в контексте пользовательского языкового стандарта по умолчанию. Сравнение лпколестр выполняется с использованием `memcmp` необработанных данных в каждой строке. Сравнение LPCSTR выполняется так же, как и после создания временной копии *псзсрк* в Юникоде. Окончательный оператор сравнения просто сравнивает автономную строку со значением NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

##  <a name="operator_lt"></a>CComBSTR:: operator&lt;

`CComBSTR` Сравнивает со строкой.

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если сравниваемый элемент меньше `CComBSTR` объекта; в противном случае возвращает значение false.

### <a name="remarks"></a>Примечания

Сравнение выполняется с использованием национальной настройки пользователя по умолчанию.

##  <a name="operator_eq"></a>CComBSTR:: operator =

Задает члену [m_str](#m_str) копию *pSrc* или копию элемента BSTR в *src*. Оператор присваивания перемещения перемещается `src` без копирования.

```
CComBSTR& operator= (const CComBSTR& src);
CComBSTR& operator= (LPCOLESTR pSrc);
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="remarks"></a>Примечания

Параметр *pSrc* указывает либо лпколестр для версий Юникода, либо LPCSTR для версий ANSI.

### <a name="example"></a>Пример

См. пример для [CComBSTR:: Copy](#copy).

##  <a name="operator_eq_eq"></a>CComBSTR:: operator = =

`CComBSTR` Сравнивает со строкой. `CComBSTR`сравниваются в текстовом виде в контексте пользовательского языкового стандарта по умолчанию.

```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```

### <a name="parameters"></a>Параметры

*бстрсрк*<br/>
[входные данные] Объект `CComBSTR`.

*псзсрк*<br/>
окне Строка, завершающаяся нулем.

*Недопустимо*<br/>
окне Должен иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если сравниваемый элемент равен `CComBSTR` объекту; в противном случае возвращает значение false.

### <a name="remarks"></a>Примечания

Окончательный оператор сравнения просто сравнивает автономную строку со значением NULL.

##  <a name="operator_gt"></a>CComBSTR:: operator&gt;

`CComBSTR` Сравнивает со строкой.

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если сравниваемый элемент больше, `CComBSTR` чем объект; в противном случае возвращает значение false.

### <a name="remarks"></a>Примечания

Сравнение выполняется с использованием национальной настройки пользователя по умолчанию.

##  <a name="readfromstream"></a>CComBSTR:: Реадфромстреам

Задает для элемента [m_str](#m_str) значение BSTR, содержащееся в указанном потоке.

```
HRESULT ReadFromStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Параметры

*пстреам*<br/>
окне Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) в потоке, содержащем данные.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`ReadToStream`требует, чтобы содержимое потока в текущей позиции было совместимо с форматом данных, записанным при помощи вызова [вритетостреам](#writetostream).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

##  <a name="tolower"></a>CComBSTR:: ToLower

Преобразует вложенную строку в нижний регистр.

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Дополнительные `CharLowerBuff` сведения о выполнении преобразования см. в разделе.

##  <a name="toupper"></a>CComBSTR:: ToUpper

Преобразует вложенную строку в верхний регистр.

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Дополнительные `CharUpperBuff` сведения о выполнении преобразования см. в разделе.

##  <a name="writetostream"></a>CComBSTR:: Вритетостреам

Сохраняет элемент [m_str](#m_str) в поток.

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Параметры

*пстреам*<br/>
окне Указатель на интерфейс [IStream](/windows/win32/api/objidl/nn-objidl-istream) в потоке.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Можно повторно создать строку BSTR из содержимого потока с помощью функции [реадфромстреам](#readfromstream) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Макросы преобразования строк ATL и MFC](string-conversion-macros.md)
