---
title: "CComBSTR-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 604e3b9841ab628343a48e72612d2e50e85913f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccombstr-class"></a>CComBSTR-класс
Этот класс является оболочкой для `BSTR`s.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComBSTR
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComBSTR::CComBSTR](#ccombstr)|Конструктор.|  
|[CComBSTR:: ~ CComBSTR](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComBSTR::Append](#append)|Добавляет строку к `m_str`.|  
|[CComBSTR::AppendBSTR](#appendbstr)|Добавляет `BSTR` для `m_str`.|  
|[CComBSTR::AppendBytes](#appendbytes)|Добавляет указанное число байтов для `m_str`.|  
|[CComBSTR::ArrayToBSTR](#arraytobstr)|Создает `BSTR` из первый символ каждого элемента в safearray и прикрепляет его к `CComBSTR` объекта.|  
|[CComBSTR::AssignBSTR](#assignbstr)|Назначает `BSTR` для `m_str`.|  
|[CComBSTR::Attach](#attach)|Присоединяет `BSTR` для `CComBSTR` объекта.|  
|[CComBSTR::BSTRToArray](#bstrtoarray)|Отсчитываемый от нуля одномерный массив safearray, где каждый элемент массива является символ из создает `CComBSTR` объекта.|  
|[CComBSTR::ByteLength](#bytelength)|Возвращает длину `m_str` в байтах.|  
|[CComBSTR::Copy](#copy)|Возвращает копию объекта `m_str`.|  
|[CComBSTR::CopyTo](#copyto)|Возвращает копию `m_str` через **[out]** параметр|  
|[CComBSTR::Detach](#detach)|Отсоединяет `m_str` из `CComBSTR` объекта.|  
|[CComBSTR::Empty](#empty)|Освобождает `m_str`.|  
|[CComBSTR::Length](#length)|Возвращает длину `m_str`.|  
|[CComBSTR::LoadString](#loadstring)|Загружает ресурс строки.|  
|[CComBSTR::ReadFromStream](#readfromstream)|Загружает `BSTR` объекта из потока.|  
|[CComBSTR::ToLower](#tolower)|Преобразует строку в нижний регистр.|  
|[CComBSTR::ToUpper](#toupper)|Преобразует строку в верхний регистр.|  
|[CComBSTR::WriteToStream](#writetostream)|Сохраняет `m_str` в поток.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComBSTR::operator BSTR](#operator_bstr)|Приведение `CComBSTR` объект `BSTR`.|  
|[CComBSTR::operator!](#operator_not)|Возвращает `true` или `false`, в зависимости от ли `m_str`— `NULL`.|  
|[CComBSTR::operator! =](#operator_neq)|Сравнивает `CComBSTR` со строкой.|  
|[CComBSTR::operator &](#operator_amp)|Возвращает адрес `m_str`.|  
|[CComBSTR::operator +=](#operator_add_eq)|Добавляет `CComBSTR` объекту.|  
|[CComBSTR::operator <](#operator_lt)|Сравнивает `CComBSTR` со строкой.|  
|[CComBSTR::operator =](#operator_eq)|Присваивает значение свойству `m_str`.|  
|[CComBSTR::operator ==](#operator_eq_eq)|Сравнивает `CComBSTR` со строкой.|  
|[CComBSTR::operator >](#operator_gt)|Сравнивает `CComBSTR` со строкой.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComBSTR::m_str](#m_str)|Содержит `BSTR` связанных с `CComBSTR` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CComBSTR` Класс является оболочкой для `BSTR`s, который представляют собой префикс длины строки. Длина хранится в виде целого числа в расположении памяти, предшествующий данные в строке.  
  
 Объект [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) завершается нуль символом после последнего подсчета символов, но также может содержать символы null, внедренный в строке. Длина строки определяется количество символов, не первого нуль-символа.  
  
> [!NOTE]
>  `CComBSTR` Класс предоставляет ряд элементов (конструкторы, операторы присваивания и операторы сравнения), которые принимают в качестве аргументов строки ANSI или Юникод. ANSI версии этих функций менее эффективным, чем их аналоги Юникода, так как временные строки в Юникоде часто создаются внутренним образом. Для повышения эффективности использования версии Юникода, где это возможно.  
  
> [!NOTE]
>  Например, из-за поведение улучшенные подстановки, реализованные в Visual Studio .NET, код `bstr = L"String2" + bstr;`, которой может быть скомпилированные в предыдущих версиях необходимо реализовывать как `bstr = CStringW(L"String2") + bstr`.  
  
 Список предупреждения при использовании `CComBSTR`, в разделе [программирование с использованием CComBSTR](../../atl/programming-with-ccombstr-atl.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="append"></a>CComBSTR::Append  
 Добавляет либо `lpsz` или `BSTR` членом `bstrSrc` для [m_str](#m_str).  
  
```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bstrSrc`  
 [in] Объект `CComBSTR` добавляемый объект.  
  
 *CH*  
 [in] Добавляемый символ.  
  
 `lpsz`  
 [in] Добавляемая строка нуль-символом. Можно передать в строку Юникода с помощью **LPCOLESTR** перегрузка или строки ANSI через `LPCSTR` версии.  
  
 `nLen`  
 [in] Количество символов из `lpsz` для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`на успех или любой стандарт `HRESULT` значение ошибки.  
  
### <a name="remarks"></a>Примечания  
 Строки ANSI преобразуются в Юникод до добавлялась.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]  
  
##  <a name="appendbstr"></a>CComBSTR::AppendBSTR  
 Добавляет указанный `BSTR` для [m_str](#m_str).  
  
```
HRESULT AppendBSTR(BSTR p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 [in] Объект `BSTR` для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`на успех или любой стандарт `HRESULT` значение ошибки.  
  
### <a name="remarks"></a>Примечания  
 Не передавайте обычной строки расширенных символов в этот метод. Компилятор не возникнут ошибки времени выполнения и перехватывать ошибки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]  
  
##  <a name="appendbytes"></a>CComBSTR::AppendBytes  
 Добавляет указанное число байтов для [m_str](#m_str) без преобразования.  
  
```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpsz`  
 [in] Указатель на массив байтов для добавления.  
  
 `p`  
 [in] Число байтов для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`на успех или любой стандарт `HRESULT` значение ошибки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]  
  
##  <a name="arraytobstr"></a>CComBSTR::ArrayToBSTR  
 Освобождает любую существующую строку, которые содержатся в `CComBSTR` объекта, а затем создает `BSTR` из первый символ каждого элемента в safearray и прикрепляет его к `CComBSTR` объекта.  
  
```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pSrc`  
 [in] Массив safearray, содержащий элементы, используемые для создания строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`на успех или любой стандарт `HRESULT` значение ошибки.  
  
##  <a name="assignbstr"></a>CComBSTR::AssignBSTR  
 Назначает `BSTR` для [m_str](#m_str).  
  
```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bstrSrc`  
 [in] Объект `BSTR` присвоить текущего `CComBSTR` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`на успех или любой стандарт `HRESULT` значение ошибки.  
  
##  <a name="attach"></a>CComBSTR::Attach  
 Присоединяет `BSTR` для `CComBSTR` , задавая [m_str](#m_str) члена *src*.  
  
```
void Attach(BSTR src) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *src*  
 [in] `BSTR` Для прикрепления к объекту.  
  
### <a name="remarks"></a>Примечания  
 Не передавайте обычной строки расширенных символов в этот метод. Компилятор не возникнут ошибки времени выполнения и перехватывать ошибки.  
  
> [!NOTE]
>  Если этот метод проверяет `m_str` не является **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="bstrtoarray"></a>CComBSTR::BSTRToArray  
 Отсчитываемый от нуля одномерный массив safearray, где каждый элемент массива является символ из создает `CComBSTR` объекта.  
  
```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ppArray`  
 [out] Указатель на массив safearray, используемый для хранения результатов функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`на успех или любой стандарт `HRESULT` значение ошибки.  
  
##  <a name="bytelength"></a>CComBSTR::ByteLength  
 Возвращает число байтов в `m_str`, без учета завершающего символа null.  
  
```
unsigned int ByteLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина [m_str](#m_str) элемента в байтах.  
  
### <a name="remarks"></a>Примечания  
 Возвращает 0, если `m_str` — **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]  
  
##  <a name="ccombstr"></a>CComBSTR::CComBSTR  
 Конструктор. Конструктор по умолчанию присваивает [m_str](#m_str) члена **NULL**.  
  
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
 `nSize`  
 [входные данные] Число символов для копирования из `sz` или начальный размер `CComBSTR` в символах.  
  
 `sz`  
 [входные данные] Строка для копирования. Версия Юникода указывает **LPCOLESTR**; версия ANSI указывает `LPCSTR`.  
  
 `pSrc`  
 [входные данные] Строка для копирования. Версия Юникода указывает **LPCOLESTR**; версия ANSI указывает `LPCSTR`.  
  
 *src*  
 [входные данные] Объект `CComBSTR`.  
  
 `guid`  
 [in] Ссылку на **GUID** структуры.  
  
### <a name="remarks"></a>Примечания  
 Конструктор копирования присваивает `m_str` с копией `BSTR` членом *src*. **REFGUID** конструктор преобразует **GUID** в строку с помощью **StringFromGUID2** и сохраняет результат.  
  
 Другие конструкторы присваивают `m_str` копию указанной строки. Если передать значение для `nSize`, только `nSize` символов будут скопированы с завершающим нулевым символом.  
  
 `CComBSTR` поддерживает семантику перемещения. Можно использовать конструктор перемещения (принимающий ссылку rvalue ( `&&`) для создания нового объекта, который использует те же базовые данные, что и старый объект, передаваемый как аргумент, без необходимости копировать объект.  
  
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
  
##  <a name="copy"></a>CComBSTR::Copy  
 Выделяет и возвращает копию `m_str`.  
  
```
BSTR Copy() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копия [m_str](#m_str) член. Если `m_str` — **NULL**, возвращает **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]  
  
##  <a name="copyto"></a>CComBSTR::CopyTo  
 Выделяет и возвращает копию [m_str](#m_str) через параметр.  
  
```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pbstr*  
 [out] Адрес `BSTR` возврата строку, выделенную этим методом.  
  
 `pvarDest`  
 [out] Адрес **VARIANT** возврата строку, выделенную этим методом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT` значение, указывающее, успех или сбой копирования.  
  
### <a name="remarks"></a>Примечания  
 После вызова этого метода **VARIANT** , на который указывает `pvarDest` будет иметь тип `VT_BSTR`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]  
  
##  <a name="detach"></a>CComBSTR::Detach  
 Отсоединяет [m_str](#m_str) из `CComBSTR` и устанавливает `m_str` для **NULL**.  
  
```
BSTR Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `BSTR` Связанных с `CComBSTR` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]  
  
##  <a name="empty"></a>CComBSTR::Empty  
 Освобождает [m_str](#m_str) член.  
  
```
void Empty() throw();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]  
  
##  <a name="length"></a>CComBSTR::Length  
 Возвращает количество символов в `m_str`, без учета завершающего символа null.  
  
```
unsigned int Length() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина [m_str](#m_str) член.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]  
  
##  <a name="loadstring"></a>CComBSTR::LoadString  
 Загружает строку ресурса, указанного в `nID` и сохраняет его в этот объект.  
  
```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```  
  
### <a name="parameters"></a>Параметры  
 В разделе [LoadString](http://msdn.microsoft.com/library/windows/desktop/ms647486) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если строка является загружен успешно; в противном случае, возвращает **false**.  
  
### <a name="remarks"></a>Примечания  
 Первая функция загружает ресурс из модуля, идентифицируемого по через `hInst` параметра. Вторая функция загружает ресурс из модуля ресурсов, связанных с [CComModule](../../atl/reference/ccommodule-class.md)-производный объект, используемый в этом проекте.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]  
  
##  <a name="m_str"></a>CComBSTR::m_str  
 Содержит `BSTR` связанных с `CComBSTR` объекта.  
  
```
BSTR m_str;
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]  
  
##  <a name="operator_bstr"></a>CComBSTR::operator BSTR  
 Приведение `CComBSTR` объект `BSTR`.  
  
```  
operator BSTR() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Можно передать `CComBSTR` объектов функции, которые имеют **[in] BSTR** параметров.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CComBSTR::m_str](#m_str).  
  
##  <a name="operator_not"></a>CComBSTR::operator!  
 Проверяет, является ли `BSTR` имеет значение NULL.  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если [m_str](#m_str) член является **NULL**; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор проверяет только значение NULL, а не для пустой строки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="operator_neq"></a>CComBSTR::operator! =  
 Возвращает логическое отрицание [оператор ==](#operator_eq_eq).  
  
```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bstrSrc`  
 [входные данные] Объект `CComBSTR`.  
  
 `pszSrc`  
 [in] Строка нулем.  
  
 `nNull`  
 [in] Должно быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если сравниваемые элемента не равно `CComBSTR` объекта; в противном случае возвращает **false**.  
  
### <a name="remarks"></a>Примечания  
 `CComBSTR`s текстового сравниваются в контексте языкового стандарта по умолчанию. Оператор сравнения окончательного просто сравнивает автономной строки на соответствие **NULL**.  
  
##  <a name="operator_amp"></a>CComBSTR::operator&amp;  
 Возвращает адрес `BSTR` хранятся в [m_str](#m_str) член.  
  
```
BSTR* operator&() throw();
```  
  
### <a name="remarks"></a>Примечания  
 `CComBstr operator &`специальные утверждение связанной с ней для определения утечки памяти. Программа установит `m_str` инициализируется. Это утверждение был создан для выявления ситуаций, когда программист использует `& operator` для присвоения нового значения для `m_str` член без освобождения памяти первого выделение `m_str`. Если `m_str` равно NULL, программа предполагает, еще не было выделить, m_str. В этом случае программа не будет утверждать.  
  
 Это утверждение не включен по умолчанию. Определение `ATL_CCOMBSTR_ADDRESS_OF_ASSERT` для включения данного утверждения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]  
  
##  <a name="operator_add_eq"></a>CComBSTR::operator +=  
 Добавляет строку к `CComBSTR` объекта.  
  
```
CComBSTR& operator+= (const CComBSTR& bstrSrc);  
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `bstrSrc`  
 [in] Объект `CComBSTR` добавляемый объект.  
  
 `pszSrc`  
 [in] Добавляемая строка нулем.  
  
### <a name="remarks"></a>Примечания  
 `CComBSTR`s текстового сравниваются в контексте языкового стандарта по умолчанию. **LPCOLESTR** сравнение выполняется с помощью `memcmp` на необработанных данных в каждой строке. `LPCSTR` Сравнение выполняется таким же образом после временную копию Юникода `pszSrc` был создан. Оператор сравнения окончательного просто сравнивает автономной строки на соответствие **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]  
  
##  <a name="operator_lt"></a>CComBSTR::operator&lt;  
 Сравнивает `CComBSTR` со строкой.  
  
```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если элемент сравниваемых меньше, чем `CComBSTR` объекта; в противном случае возвращает **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение выполняется с помощью языкового стандарта по умолчанию.  
  
##  <a name="operator_eq"></a>CComBSTR::operator =  
 Наборы [m_str](#m_str) член с копией `pSrc` или с копией `BSTR` членом *src*. Оператор присваивания перемещения перемещает `src` не копируя его.   
  
```
CComBSTR& operator= (const CComBSTR& src);  
CComBSTR& operator= (LPCOLESTR pSrc);  
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```  
  
### <a name="remarks"></a>Примечания  
 `pSrc` Указывает либо **LPCOLESTR** для версии Юникода или `LPCSTR` для версий ANSI.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CComBSTR::Copy](#copy).  
  
##  <a name="operator_eq_eq"></a>CComBSTR::operator ==  
 Сравнивает `CComBSTR` со строкой. `CComBSTR`s текстового сравниваются в контексте языкового стандарта по умолчанию.  
  
```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bstrSrc`  
 [входные данные] Объект `CComBSTR`.  
  
 `pszSrc`  
 [in] Строка нулем.  
  
 `nNull`  
 [in] Должно быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если сравниваемые элемент равен `CComBSTR` объекта; в противном случае возвращает **false**.  
  
### <a name="remarks"></a>Примечания  
 Оператор сравнения окончательного просто сравнивает автономной строки на соответствие **NULL**.  
  
##  <a name="operator_gt"></a>CComBSTR::operator&gt;  
 Сравнивает `CComBSTR` со строкой.  
  
```
bool operator>(const CComBSTR& bstrSrc) const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если сравниваемые элемент больше, чем `CComBSTR` объекта; в противном случае возвращает **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение выполняется с помощью языкового стандарта по умолчанию.  
  
##  <a name="readfromstream"></a>CComBSTR::ReadFromStream  
 Наборы [m_str](#m_str) члена `BSTR` содержащихся в указанном потоке.  
  
```
HRESULT ReadFromStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pStream`  
 [in] Указатель на [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) интерфейса на поток, содержащий данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 **ReadToStream** требуется содержимое потока в текущей позиции совместимы с форматом данных, записанного с помощью вызова [WriteToStream](#writetostream).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]  
  
##  <a name="tolower"></a>CComBSTR::ToLower  
 Преобразует автономной строку в нижний регистр.  
  
```
HRESULT ToLower() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 В разделе **CharLowerBuff** Дополнительные сведения о том, как выполняется преобразование.  
  
##  <a name="toupper"></a>CComBSTR::ToUpper  
 Преобразует автономной строку в верхний регистр.  
  
```
HRESULT ToUpper() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 В разделе **CharUpperBuff** Дополнительные сведения о том, как выполняется преобразование.  
  
##  <a name="writetostream"></a>CComBSTR::WriteToStream  
 Сохраняет [m_str](#m_str) член в поток.  
  
```
HRESULT WriteToStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pStream`  
 [in] Указатель на [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) интерфейса в потоке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Можно повторно создать BSTR из содержимого потока с помощью [ReadFromStream](#readfromstream) функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [ATL и MFC макросы преобразования строк](string-conversion-macros.md)
