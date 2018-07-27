---
title: Класс CSimpleStringT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::PCXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::PXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::Append
- ATLSIMPSTR/ATL::CSimpleStringT::AppendChar
- ATLSIMPSTR/ATL::CSimpleStringT::CopyChars
- ATLSIMPSTR/ATL::CSimpleStringT::CopyCharsOverlapped
- ATLSIMPSTR/ATL::CSimpleStringT::Empty
- ATLSIMPSTR/ATL::CSimpleStringT::FreeExtra
- ATLSIMPSTR/ATL::CSimpleStringT::GetAllocLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetAt
- ATLSIMPSTR/ATL::CSimpleStringT::GetBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::GetBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetManager
- ATLSIMPSTR/ATL::CSimpleStringT::GetString
- ATLSIMPSTR/ATL::CSimpleStringT::IsEmpty
- ATLSIMPSTR/ATL::CSimpleStringT::LockBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::Preallocate
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::SetAt
- ATLSIMPSTR/ATL::CSimpleStringT::SetManager
- ATLSIMPSTR/ATL::CSimpleStringT::SetString
- ATLSIMPSTR/ATL::CSimpleStringT::StringLength
- ATLSIMPSTR/ATL::CSimpleStringT::Truncate
- ATLSIMPSTR/ATL::CSimpleStringT::UnlockBuffer
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da0cd0df9311d11b30c3ef42d8492c71cb78abb4
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883636"
---
# <a name="csimplestringt-class"></a>Класс CSimpleStringT
Этот класс представляет `CSimpleStringT` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename BaseType>
class CSimpleStringT
```  
  
### <a name="parameters"></a>Параметры  
 *BaseType*  
 Тип символа класса string. Ниже указаны доступные значения.  
  
- **char** (для символьных строк ANSI).  
  
- **wchar_t** (для символьных строк в Юникоде).  
  
- TCHAR (для символьных строк ANSI и Юникода).  

## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSimpleStringT::PCXSTR](#pcxstr)|Указатель на строковую константу.|  
|[CSimpleStringT::PXSTR](#pxstr)|Указатель на строку.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSimpleStringT::CSimpleStringT](#ctor)|Создает `CSimpleStringT` объекты различными способами.|  
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|Деструктор.|  

  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSimpleStringT::Append](#append)|Добавляет `CSimpleStringT` объекта к существующему `CSimpleStringT` объекта.|  
|[CSimpleStringT::AppendChar](#appendchar)|Добавляет символ в существующий `CSimpleStringT` объекта.|  
|[CSimpleStringT::CopyChars](#copychars)|Копирует символ или символы в другую.|  
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|Копирует символ или символы на другую строку, в которой пересекаются буферы.|  
|[CSimpleStringT::Empty](#empty)|Заставляет строка имеет нулевую длину.|  
|[CSimpleStringT::FreeExtra](#freeextra)|Освобождает все дополнительная память, выделенную ранее строковым объектом.|  
|[CSimpleStringT::GetAllocLength](#getalloclength)|Получает выделенный длину `CSimpleStringT` объекта.|  
|[CSimpleStringT::GetAt](#getat)|Возвращает символ в заданной позиции.|  
|[CSimpleStringT::GetBuffer](#getbuffer)|Возвращает указатель на символы в `CSimpleStringT`.|  
|[CSimpleStringT::GetBufferSetLength](#getbuffersetlength)|Возвращает указатель на символы в `CSimpleStringT`, усечение до указанной длины.|  
|[CSimpleStringT::GetLength](#getlength)|Возвращает количество символов в `CSimpleStringT` объекта.|  
|[CSimpleStringT::GetManager](#getmanager)|Получает диспетчер памяти `CSimpleStringT` объекта.|  
|[CSimpleStringT::GetString](#getstring)|Получает строку символов|  
|[CSimpleStringT::IsEmpty](#isempty)|Тесты ли `CSimpleStringT` объект не содержит символов.|  
|[CSimpleStringT::LockBuffer](#lockbuffer)|Отключает подсчет ссылок и защищает строки в буфере.|  
|[CSimpleStringT::Preallocate](#preallocate)|Выделяет определенным объемом памяти для буфера символов.|  
|[CSimpleStringT::ReleaseBuffer](#releasebuffer)|Управление буфером, возвращаемым `GetBuffer`.|  
|[CSimpleStringT::ReleaseBufferSetLength](#releasebuffersetlength)|Управление буфером, возвращаемым `GetBuffer`.|  
|[CSimpleStringT::SetAt](#setat)|Задает символ в заданной позиции.|  
|[CSimpleStringT::SetManager](#setmanager)|Задает диспетчер памяти `CSimpleStringT` объекта.|  
|[CSimpleStringT::SetString](#setstring)|Задает строку `CSimpleStringT` объекта.|  
|[CSimpleStringT::StringLength](#stringlength)|Возвращает число символов в указанной строке.|  
|[CSimpleStringT::Truncate](#truncate)|Усекает строку до указанной длины.|  
|[CSimpleStringT::UnlockBuffer](#unlockbuffer)|Обеспечивает подсчет ссылок и освобождает строку в буфере.|  

### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSimpleStringT::operator PCXSTR](#operator_pcxstr)|Напрямую обращается к символов, сохраненных в `CSimpleStringT` объект в виде строки C-стиля.|  
|[CSimpleStringT::operator\[\]](#operator_at)|Возвращает символ в заданной позиции — оператор подстановки для `GetAt`.|  
|[CSimpleStringT::operator +=](#operator_add_eq)|Сцепляет новую строку в конец существующей строки.|  
|[CSimpleStringT::operator =](#operator_eq)|Назначает новое значение для `CSimpleStringT` объекта.|  
  
### <a name="remarks"></a>Примечания  
 `CSimpleStringT` является базовым классом для различных строковых классов, поддерживаемых Visual C++. Он предоставляет минимальную поддержку для управления памятью строковый объект и основные буфером. Для более сложных строковых объектов, см. в разделе [класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpstr.h  


## <a name="append"></a> CSimpleStringT::Append
Добавляет `CSimpleStringT` объекта к существующему `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void Append(const CSimpleStringT& strSrc); 
void Append(PCXSTR pszSrc, int nLength); 
void Append(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>Параметры  
 *strSrc*  
 `CSimpleStringT` Объект для добавления.  
  
 *pszSrc*  
 Указатель на строку, содержащую символы, которые требуется добавить.  
  
 *nLength*  
 Количество добавляемых знаков.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для добавления существующего `CSimpleStringT` объект с другим объектом `CSimpleStringT` объекта.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::Append`.  
  
```cpp  
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```
  
##  <a name="appendchar"></a> CSimpleStringT::AppendChar
Добавляет символ в существующий `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void AppendChar(XCHAR ch);
```  
#### <a name="parameters"></a>Параметры  
 *ch*  
 Символ для добавления  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию, чтобы добавить заданный знак в конец существующего `CSimpleStringT` объекта.  
  
##  <a name="copychars"></a> CSimpleStringT::CopyChars  
 Копирует символ или символы, `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
static void CopyChars(
  XCHAR* pchDest,
  const XCHAR* pchSrc, 
  int nChars) throw();
```  
#### <a name="parameters"></a>Параметры  
 *pchDest*  
 Указатель на строку символов.  
  
 *pchSrc*  
 Указатель на строку, содержащую символы, которые требуется скопировать.  
  
 *nChars*  
 Число *pchSrc* копируемых символов.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы скопировать символы из *pchSrc* для *pchDest* строка.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::CopyChars`.  
  
```cpp  
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```
  
##  <a name="copycharsoverlapped"></a>  CSimpleStringT::CopyCharsOverlapped
Копирует символ или символы, `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
static void CopyCharsOverlapped(
  XCHAR* pchDest,
  const XCHAR* pchSrc,
  int nChars) throw(); 
```  
#### <a name="parameters"></a>Параметры  
 *pchDest*  
 Указатель на строку символов.  
  
 *pchSrc*  
 Указатель на строку, содержащую символы, которые требуется скопировать.  
  
 *nChars*  
 Число *pchSrc* копируемых символов.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы скопировать символы из *pchSrc* для *pchDest* строка. В отличие от `CopyChars`, `CopyCharsOverlapped` предоставляет безопасный метод копирования из символьных буферов, которые могут накладываться.  
  
### <a name="example"></a>Пример  
 См. в примере [CSimpleStringT::CopyChars](#copychars), или исходный код для `CSimpleStringT::SetString` (находится в atlsimpstr.h).  
  
##  <a name="ctor"></a>  CSimpleStringT::CSimpleStringT  
 Создает объект `CSimpleStringT`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr); 
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr); 
CSimpleStringT(const CSimpleStringT& strSrc); 
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw(); 
```  
#### <a name="parameters"></a>Параметры  
 *strSrc*  
 Существующий `CSimpleStringT` объект, который необходимо скопировать в это `CSimpleStringT` объекта.  
  
 *pchSrc*  
 Указатель на массив символов длиной *nLength*, не заканчивается на null.  
  
 *pszSrc*  
 Заканчивающуюся нулем строку, который необходимо скопировать в это `CSimpleStringT` объекта.  
  
 *nLength*  
 Число символов в `pch`.  
  
 *pStringMgr*  
 Указатель на диспетчер памяти `CSimpleStringT` объекта. Дополнительные сведения о `IAtlStringMgr` и управление памятью для `CSimpleStringT`, см. в разделе [управление памятью и CStringT](../memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Примечания  
 Создать новый `CSimpleStringT` объекта. Так как конструкторы копируют входные данные в новый объем выделенного хранилища, это может привести к памяти исключения.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование `CSimpleStringT::CSimpleStringT` с помощью ATL **typedef** `CSimpleString`. `CSimpleString` является часто используемые специализацией шаблона класса `CSimpleStringT`.  
  
```cpp  
CSimpleString s1(pMgr);
// Empty string
CSimpleString s2(_T("cat"), pMgr);
// From a C string literal

CSimpleString s3(s2);
// Copy constructor
CSimpleString s4(s2 + _T(" ") + s3);

// From a string expression
CSimpleString s5(_T("xxxxxx"), 6, pMgr);
// s5 = "xxxxxx"   
```

  
##  <a name="empty"></a>  CSimpleStringT::Empty
Это делает `CSimpleStringT` объекта пустую строку и освобождает память, соответствующим образом.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void Empty() throw();  
```  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [строк: очистка исключений CString](../cstring-exception-cleanup.md).  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::Empty`.  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());  
```  
  
##  <a name="freeextra"></a>  CSimpleStringT::FreeExtra
Освобождает дополнительный память, выделенную ранее строкой, но больше не нужны.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void FreeExtra(); 
```  
### <a name="remarks"></a>Примечания  
 Это должно снизить число дополнительная нагрузка на память, занятая строковый объект. Метод повторно выделяет буфер для точная длина возвращенных [GetLength](#getlength).  
  
### <a name="example"></a>Пример  
```cpp  
CAtlString basestr;
IAtlStringMgr* pMgr;

pMgr= basestr.GetManager();
ASSERT(pMgr != NULL);

// Create a CSimpleString with 28 characters
CSimpleString str(_T("Many sports are fun to play."), 28, pMgr);
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// Assigning a smaller string won't cause CSimpleString to free its 
// memory, because it assumes the string will grow again anyway.
str = _T("Soccer is best!");
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// This call forces CSimpleString to release the extra 
// memory it doesn't need.
str.FreeExtra();
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());
```
  
### <a name="remarks"></a>Примечания  
 Выходные данные из этого примера выглядит следующим образом:  
  
 `Alloc length is 1031, String length is 1024`  
  
 `Alloc length is 1031, String length is 15`  
  
 `Alloc length is 15, String length is 15`  
  
##  <a name="getalloclength"></a>  CSimpleStringT::GetAllocLength  
Получает выделенный длину `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
int GetAllocLength() const throw();  
```  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов, выделенных для этого объекта.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для определения количества символов, выделенных для этого `CSimpleStringT` объекта. См. в разделе [FreeExtra](#freeextra) пример вызова этой функции.  
  
##  <a name="getat"></a>  CSimpleStringT::GetAt  
Возвращает один символ из `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
XCHAR GetAt(int iChar) const;
```  
#### <a name="parameters"></a>Параметры  
 *iChar*  
 Отсчитываемый от нуля индекс символа в `CSimpleStringT` объекта. *IChar* параметр должен быть больше или равно 0 и меньше, чем значение, возвращенное [GetLength](#getlength). В противном случае `GetAt` возникает исключение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `XCHAR` , Содержащий символ в указанной позиции в строке.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для возврата один символ, заданный параметром *iChar*. Перегруженный нижнего индекса (**[]**) оператор является удобным псевдонимом для `GetAt`. Знак завершения null будет обращаться без генерации исключения с помощью `GetAt`. Тем не менее, он не учитывается `GetLength`, и возвращаемое значение равно 0.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует, как использовать `CSimpleStringT::GetAt`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```
  
##  <a name="getbuffer"></a>  CSimpleStringT::GetBuffer  
Возвращает указатель на буфер внутренних символов для `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
PXSTR GetBuffer(int nMinBufferLength); 
PXSTR GetBuffer();
```  
#### <a name="parameters"></a>Параметры  
 *nMinBufferLength*  
 Минимальное число символов, содержащихся в буфере символов. Это значение не включает свободное место для завершающего нуль.  
  
 Если *nMinBufferLength* больше, чем длина буфера текущего `GetBuffer` уничтожает текущего буфера и заменяет его с буфером запрошенного размера обнуляется счетчик ссылок объекта. Если ранее был вызван [LockBuffer](#lockbuffer) данного буфера, вы потеряете блокировки буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `PXSTR` Указатель на буфер символов (нулем) объекта.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для возврата содержимого буфера `CSimpleStringT` объекта. Возвращенный `PXSTR` не является константой и поэтому позволяет прямое изменение `CSimpleStringT` содержимое.  
  
 Если вы используете указатель, возвращенный `GetBuffer` изменение содержимого строки, необходимо вызвать [ReleaseBuffer](#releasebuffer) прежде чем использовать любой другой `CSimpleStringT` методы членов.  
  
 Адрес, возвращенный `GetBuffer` после вызова могут оказаться недопустимыми `ReleaseBuffer` из-за дополнительных `CSimpleStringT` операции может привести к `CSimpleStringT` буфера перераспределить. Буфер не перераспределяется, если не изменить длину `CSimpleStringT`.  
  
 Буфер памяти будет автоматически освобождается при `CSimpleStringT` уничтожении объекта.  
  
 Если вы хранить список длину строки самостоятельно, следует не добавляет завершающий нуль-символ. Тем не менее, необходимо указать длину окончательной строки при освобождении буфер значением `ReleaseBuffer`. Если добавить знак завершения null, следует передавать значение -1 (по умолчанию) в качестве длины. `ReleaseBuffer` затем определяет длину буфера.  
  
 Если памяти недостаточно для удовлетворения `GetBuffer` запроса, этот метод вызывает исключение CMemoryException *.  
  
### <a name="example"></a>Пример  
```cpp  
CSimpleString s(_T("abcd"), pMgr);
LPTSTR pBuffer = s.GetBuffer(10);
int sizeOfBuffer = s.GetAllocLength();

// Directly access CSimpleString buffer
_tcscpy_s(pBuffer, sizeOfBuffer, _T("Hello"));
ASSERT(_tcscmp(s, _T("Hello")) == 0);
s.ReleaseBuffer();   
```
  
##  <a name="getbuffersetlength"></a>  CSimpleStringT::GetBufferSetLength  
Возвращает указатель на буфер внутренних символов для `CSimpleStringT` объекта, усечение или его длина растет, при необходимости должен совпадать с длиной, определяемой *nLength*.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
PXSTR GetBufferSetLength(int nLength);
```  
#### <a name="parameters"></a>Параметры  
 *nLength*  
 Точный размер `CSimpleStringT` символ буфера в символах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `PXSTR` указатель на буфер символов (нулем) объекта.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для извлечения указанной длины из внутреннего буфера объекта `CSimpleStringT` объекта. Возвращенный `PXSTR` указатель не **const** и таким образом, предусматривает прямое изменение `CSimpleStringT` содержимое.  
  
 Если вы используете указатель, возвращенный [GetBufferSetLength](#getbuffersetlength) Чтобы изменить содержимое строки, вызовите `ReleaseBuffer` для обновления внутреннего состояния `CsimpleStringT` прежде чем использовать любой другой `CSimpleStringT` методы.  
  
 Адрес, возвращенный `GetBufferSetLength` после вызова могут оказаться недопустимыми `ReleaseBuffer` из-за дополнительных `CSimpleStringT` операции может привести к `CSimpleStringT` буфера перераспределить. Буфер не перераспределяется, если не изменить длину `CSimpleStringT`.  
  
 Буфер памяти будет автоматически освобождается при `CSimpleStringT` уничтожении объекта.  
  
 Если вы хранить список длину строки самостоятельно, не добавляет завершающий нуль-символ. Необходимо указать длину окончательной строки при освобождении буфера с помощью `ReleaseBuffer`. Если при вызове добавляет завершающий нуль-символ `ReleaseBuffer`, передайте значение -1 (по умолчанию) в качестве длины для `ReleaseBuffer`, и `ReleaseBuffer` выполнит `strlen` в буфере, чтобы определить длину.  
  
 Дополнительные сведения о подсчете ссылок см. в следующих статьях:  
  
- [Управление временем существования объектов посредством подсчета ссылок](http://msdn.microsoft.com/library/windows/desktop/ms687260) в Windows SDK. 
  
- [Реализация подсчет ссылок](http://msdn.microsoft.com/library/windows/desktop/ms693431) в Windows SDK.
  
- [Правила для управления счетчиков ссылок](http://msdn.microsoft.com/library/windows/desktop/ms692481) в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::GetBufferSetLength`.  
  
```cpp  
CSimpleString str(pMgr);
LPTSTR pstr = str.GetBufferSetLength(3);
pstr[0] = _T('C');
pstr[1] = _T('u');
pstr[2] = _T('p');

// No need for trailing zero or call to ReleaseBuffer() 
// because GetBufferSetLength() set it for us.

str += _T(" soccer is best!");
ASSERT(_tcscmp(str, _T("Cup soccer is best!")) == 0);
```
  
##  <a name="getlength"></a>  CSimpleStringT::GetLength  
Возвращает количество символов в `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
int GetLength() const throw();  
```  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов в строке.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для возврата числа символов в объекте. Счетчик не включает завершающий нуль-символ.  
  
 Для многобайтовой кодировки (MBCS), `GetLength` счетчиков, каждый 8-разрядных символов, то есть старший и младший байт в один Многобайтовый символ, рассматриваются как два байта. См. в разделе [FreeExtra](#freeextra) пример вызова этой функции.  
  
##  <a name="getmanager"></a>  CSimpleStringT::GetManager  
Получает диспетчер памяти `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
IAtlStringMgr* GetManager() const throw();  
```  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на диспетчер памяти для `CSimpleStringT` объекта.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для извлечения память используется диспетчер `CSimpleStringT` объекта. Дополнительные сведения о диспетчеры памяти и строковых объектов, см. в разделе [управление памятью и CStringT](../memory-management-with-cstringt.md).  
  
##  <a name="getstring"></a>  CSimpleStringT::GetString
Получает строку символов.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
PCXSTR GetString() const throw();
```  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку символов с завершающим нулем.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для извлечения символьной строки, связанные с `CSimpleStringT` объекта.  
  
> [!NOTE]
>  Возвращенный `PCXSTR` указатель находится **const** и не поддерживает прямое изменение `CSimpleStringT` содержимое.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::GetString`.  
  
```cpp  
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```
  
##  <a name="isempty"></a>  CSimpleStringT::IsEmpty  
Тесты `CSimpleStringT` объект для пустое условие.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool IsEmpty() const throw();  
```  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если `CSimpleStringT` объект имеет 0 длины; в противном случае — FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для определения того, если объект содержит пустую строку.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::IsEmpty`.  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```
  
##  <a name="lockbuffer"></a>  CSimpleStringT::LockBuffer  
Отключает подсчет ссылок и защищает строки в буфере.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
PXSTR LockBuffer();
```  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CSimpleStringT` объект или строку, завершающуюся символом null.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для блокирования буфера из `CSimpleStringT` объекта. Путем вызова `LockBuffer`, создать копию строки, на-1 для счетчика ссылок. Когда значение счетчика ссылок равно -1, строка, содержащаяся в буфере считается «заблокировано». Хотя в заблокированном состоянии, строка защищен двумя способами:  
  
-   Нет другая строка можно получить ссылку на данные в заблокированной строке, даже если эта строка назначается заблокированной строки.  
  
-   Заблокированные строки никогда не будет ссылаться на другой строкой, даже если что-то другая строка копируется заблокированные строку.  
  
 Блокировка строки в буфере, убедитесь, что монопольную блокировку строки буфера не будут затронуты.  
  
 После завершения с `LockBuffer`, вызовите [UnlockBuffer](#unlockbuffer) сброшен счетчик ссылок на 1.  
  
> [!NOTE]
>  При вызове метода [GetBuffer](#getbuffer) на заблокированный буфер и вы установите `GetBuffer` параметр `nMinBufferLength` больше, чем длина текущего буфера, чтобы вы потеряете блокировки буфера. Такой вызов к `GetBuffer` уничтожает текущего буфера и заменяет его с буфером запрошенного размера обнуляется счетчик ссылок.  
  
 Дополнительные сведения о подсчете ссылок см. в следующих статьях:  
  
- [Управление временем существования объектов посредством подсчета ссылок](http://msdn.microsoft.com/library/windows/desktop/ms687260) в Windows SDK  
  
- [Реализация подсчет ссылок](http://msdn.microsoft.com/library/windows/desktop/ms693431) в Windows SDK  
  
- [Правила для управления счетчиков ссылок](http://msdn.microsoft.com/library/windows/desktop/ms692481) в Windows SDK  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::LockBuffer`.  
  
```cpp  
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```
  
##  <a name="operator_at"></a>  CSimpleStringT::operator\[\]  
Вызывайте эту функцию для доступа к символу одного массива знаков.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
XCHAR operator[](int iChar) const;
```  
#### <a name="parameters"></a>Параметры  
 *iChar*  
 Отсчитываемый от нуля индекс символа в строке.  
  
### <a name="remarks"></a>Примечания  
 Перегруженный нижнего индекса (**[]**) оператор возвращает символ определяется отсчитываемый от нуля индекс в *iChar*. Этот оператор является удобным заменой [GetAt](#getat) функция-член.  
  
> [!NOTE]
>  Можно использовать индекс (**[]**) оператор, чтобы получить это значение символа в `CSimpleStringT`, но его нельзя использовать для изменения значения символа в `CSimpleStringT`.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::operator []`.  
  
```cpp  
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```
  
## <a name="operator_at"></a>  CSimpleStringT::operator \[\]
Вызывайте эту функцию для доступа к символу одного массива знаков.  
  
### <a name="syntax"></a>Синтаксис  
  
```   
XCHAR operator[](int iChar) const;
```  
  
### <a name="parameters"></a>Параметры  
 *iChar*  
 Отсчитываемый от нуля индекс символа в строке.  
  
### <a name="remarks"></a>Примечания  
 Перегруженный нижнего индекса (**[]**) оператор возвращает символ определяется отсчитываемый от нуля индекс в *iChar*. Этот оператор является удобным заменой [GetAt](#getat) функция-член.  
  
> [!NOTE]
>  Можно использовать индекс (**[]**) оператор, чтобы получить это значение символа в `CSimpleStringT`, но его нельзя использовать для изменения значения символа в `CSimpleStringT`.  
  
  
##  <a name="operator_add_eq"></a>  CSimpleStringT::operator +=  
Присоединяет новую строку или символ в конец существующей строки.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
CSimpleStringT& operator +=(PCXSTR pszSrc); 
CSimpleStringT& operator +=(const CSimpleStringT& strSrc); 
template<int t_nSize>  
CSimpleStringT& operator+=(const CStaticString< XCHAR, t_nSize >& strSrc); 
CSimpleStringT& operator +=(char ch); 
CSimpleStringT& operator +=(unsigned char ch); 
CSimpleStringT& operator +=(wchar_t ch);
```  
#### <a name="parameters"></a>Параметры  
 *pszSrc*  
 Указатель на строку, завершающуюся символом null.  
  
 *strSrc*  
 Указатель на существующий `CSimpleStringT` объекта.  
  
 *ch*  
 Символ значение для добавления.  
  
### <a name="remarks"></a>Примечания  
 Оператор принимает другой `CSimpleStringT` объекта или символ. Обратите внимание, что память исключения могут возникать при использовании этот оператор объединения, так как новое хранилище может быть предоставлено для символов, добавленных к этому `CSimpleStringT` объекта.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::operator +=`.  
  
```cpp  
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```
  
##  <a name="operator_eq"></a>  CSimpleStringT::operator =  
Назначает новое значение для `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
CSimpleStringT& operator =(PCXSTR pszSrc); 
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```  
#### <a name="parameters"></a>Параметры  
 *pszSrc*  
 Указатель на строку, завершающуюся символом null.  
  
 *strSrc*  
 Указатель на существующий `CSimpleStringT` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если строка назначения (левой) уже достаточно большую для сохранения новых данных, выполняется выделение памяти не новых. Обратите внимание, что память исключения могут возникать при использовании оператор присваивания, так как часто выделяется новая память для хранения результирующего `CSimpleStringT` объекта.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::operator =`.  
  
```cpp  
CSimpleString s1(pMgr), s2(pMgr);
// Empty CSimpleStringT objects

s1 = _T("cat");
// s1 = "cat"
ASSERT(_tcscmp(s1, _T("cat")) == 0);

s2 = s1;               // s1 and s2 each = "cat"
ASSERT(_tcscmp(s2, _T("cat")) == 0);

s1 = _T("the ") + s1;      
// Or expressions
ASSERT(_tcscmp(s1, _T("the cat")) == 0);

s1 = _T("x");
// Or just individual characters
ASSERT(_tcscmp(s1, _T("x")) == 0);
```
  
##  <a name="operator_pcxstr"></a>  CSimpleStringT::operator PCXSTR  

 Напрямую обращается к символов, сохраненных в `CSimpleStringT` объект в виде строки C-стиля.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
operator PCXSTR() const throw();
```  
### <a name="return-value"></a>Возвращаемое значение  
 Символ указатель на строку данных.  
  
### <a name="remarks"></a>Примечания  
 Никакие символы не копируются; возвращается только указатель. Следите за тем, с помощью этого оператора. При изменении `CString` объекта после получения указателя символа, может привести к перераспределения памяти, который делает недействительным указатель.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::operator PCXSTR`.  
  
```cpp  
// If the prototype of a function is known to the compiler, 
// the PCXSTR cast operator may be invoked implicitly.

CSimpleString strSports(L"Soccer is Best!", pMgr);
WCHAR sz[1024];

wcscpy_s(sz, strSports);

// If the prototype isn't known or is a va_arg prototype, 
// you must invoke the cast operator explicitly. For example, 
// the va_arg part of a call to swprintf_s() needs the cast:

swprintf_s(sz, 1024, L"I think that %s!\n", (PCWSTR)strSports);

// While the format parameter is known to be an PCXSTR and 
// therefore doesn't need the cast:

swprintf_s(sz, 1024, strSports);

// Note that some situations are ambiguous. This line will 
// put the address of the strSports object to stdout:

wcout << strSports;

// while this line will put the content of the string out:

wcout << (PCWSTR)strSports;   
``` 
  
##  <a name="pcxstr"></a>  CSimpleStringT::PCXSTR
Указатель на строковую константу.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;    
```  
##  <a name="preallocate"></a>  CSimpleStringT::Preallocate  
Выделяет определенный объем байт для `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void Preallocate( int nLength);
```  
#### <a name="parameters"></a>Параметры  
 *nLength*  
 Точный размер `CSimpleStringT` символ буфера в символах.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы выделить определенный размер буфера для `CSimpleStringT` объекта.  
  
 `CSimpleStringT` создает исключение STATUS_NO_MEMORY, если не удалось выделить место для буфер символов. По умолчанию, выделение памяти выполняется функциями WIN32 API `HeapAlloc` или `HeapReAlloc`.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::Preallocate`.  
  
```cpp  
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```
  
##  <a name="pxstr"></a>  CSimpleStringT::PXSTR  
Указатель на строку.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;  
```  
##  <a name="releasebuffer"></a>  CSimpleStringT::ReleaseBuffer  
Управление буфер, выделенный с [GetBuffer](#getbuffer).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void ReleaseBuffer(int nNewLength = -1);
```  
#### <a name="parameters"></a>Параметры  
 *nNewLength*  
 Новая длина строки в символах, не считая завершающий нуль-символ. Если строка имеет значение null прервано, значение по умолчанию-1 задает `CSimpleStringT` размер к текущей длины строки.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для перераспределения или освободить буфер объекта string. Если вы знаете, что строка в буфере нулевым байтом, можно опустить *nNewLength* аргумент. Если строки не null завершается символом, используйте *nNewLength* для определения его длины. Адрес, возвращенный [GetBuffer](#getbuffer) является недопустимым после вызова `ReleaseBuffer` или любой другой `CSimpleStringT` операции.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::ReleaseBuffer`.  
  
```cpp  
const int bufferSize = 1024;
CSimpleString s(_T("abc"), pMgr);
LPTSTR p = s.GetBuffer(bufferSize);
_tcscpy_s(p, bufferSize, _T("abc"));

  // use the buffer directly
ASSERT(s.GetLength() == 3);

// String length = 3
s.ReleaseBuffer();

// Surplus memory released, p is now invalid.
ASSERT(s.GetLength() == 3);

// Length still 3
```
  
##  <a name="releasebuffersetlength"></a>  CSimpleStringT::ReleaseBufferSetLength

Управление буфер, выделенный с [GetBuffer](#getbuffer).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void ReleaseBufferSetLength(int nNewLength);
```  
#### <a name="parameters"></a>Параметры  
 *nNewLength*  
 Длина строки, которые выпускаются  
  
### <a name="remarks"></a>Примечания  
 Эта функция аналогична функционально [ReleaseBuffer](#releasebuffer) за исключением того, что должен быть передан допустимую длину для создаваемого строкового объекта.  
  
##  <a name="setat"></a>  CSimpleStringT::SetAt  
Задает один символ из `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void SetAt(int iChar, XCHAR ch);
```  
#### <a name="parameters"></a>Параметры  
 *iChar*  
 Отсчитываемый от нуля индекс символа в `CSimpleStringT` объекта. *IChar* параметр должен быть больше или равно 0 и меньше, чем значение, возвращенное [GetLength](#getlength).  
  
 *ch*  
 Новый символ.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы перезаписать начиная *iChar*. Этот метод не увеличит строки, если *iChar* выходит за границы существующей строки.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::SetAt`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
``` 
  
##  <a name="setmanager"></a>  CSimpleStringT::SetManager  
Указывает, то диспетчер памяти `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void SetManager(IAtlStringMgr* pStringMgr);
```  
#### <a name="parameters"></a>Параметры  
 *pStringMgr*  
 Указатель на новый диспетчер памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы указать новую память manager, используемые `CSimpleStringT` объекта. Дополнительные сведения о диспетчеры памяти и строковых объектов, см. в разделе [управление памятью и CStringT](../memory-management-with-cstringt.md).  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::SetManager`.  
  
```cpp  
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```
  
##  <a name="setstring"></a>  CSimpleStringT::SetString  
Задает строку `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void SetString(PCXSTR pszSrc, int nLength); 
void SetString(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>Параметры  
 *pszSrc*  
 Указатель на строку, завершающуюся символом null.  
  
 *nLength*  
 Число символов в *pszSrc*.  
  
### <a name="remarks"></a>Примечания  
 Скопируйте строку в `CSimpleStringT` объекта. `SetString` перезаписывает старые данные строки в буфере.  
  
 Обе версии `SetString` проверьте ли *pszSrc* является пустым указателем и если это так, выдавать ошибку E_INVALIDARG.  
  
 Один параметр версии `SetString` ожидает *pszSrc* указывал на строку, завершающуюся символом null.  
  
 Два параметра версии `SetString` также ожидает, что *pszSrc* в виде строки с завершающим нулем. Она использует *nLength* как длину строки, если он обнаруживает завершающий нуль-символ.  
  
 Два параметра версии `SetString` также проверяет ли *pszSrc* указывает на расположение, в настоящий момент буфер в `CSimpleStringT`. В нашем примере специальные `SetString` использует функцию копирования памяти, которая не перезаписывает строковые данные, как он копирует строковые данные обратно в свой буфер.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::SetString`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```
  
##  <a name="stringlength"></a>  CSimpleStringT::StringLength  
Возвращает число символов в указанной строке.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```  
#### <a name="parameters"></a>Параметры  
 *psz*  
 Указатель на строку, завершающуюся символом null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов в *psz*; не считая завершающий нуль-символ.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для получения числа знаков в строке, на которые указывают *psz*.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::StringLength`.  
  
```cpp  
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
``` 
  
##  <a name="truncate"></a>  CSimpleStringT::Truncate
Производит усечение строки новую длину.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void Truncate(int nNewLength);
```  
#### <a name="parameters"></a>Параметры  
 *nNewLength*  
 Новая длина строки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для усечения содержимое строки новую длину.  
  
> [!NOTE]
>  Это не влияет на выделенный длину буфера. Чтобы уменьшить или увеличить текущего буфера, см. в разделе [FreeExtra](#freeextra) и [Preallocate](#preallocate).  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::Truncate`.  
  
```cpp  
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
``` 
  
##  <a name="unlockbuffer"></a>  CSimpleStringT::UnlockBuffer
 Разблокирует буфер `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void UnlockBuffer() throw();
```  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы сбросить счетчик ссылок строки до 1.  
  
 `CSimpleStringT` Автоматически вызывает деструктор `UnlockBuffer` чтобы убедиться, что буфер не заблокирован при вызове деструктора. Пример этого метода, см. в разделе [LockBuffer](#lockbuffer).  
  
##  <a name="dtor"></a>  CSimpleStringT:: ~ CSimpleStringT
Уничтожает объект `CSimpleStringT`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
~CSimpleStringT() throw();
```  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для уничтожения `CSimpleStringT` объекта.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)