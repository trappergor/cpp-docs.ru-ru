---
title: "Класс CSimpleStringT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 0b60a7b5c58c33ed4d8be67e1de603ef5f711742
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="csimplestringt-class"></a>Класс CSimpleStringT
Этот класс представляет `CSimpleStringT` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename BaseType>
class CSimpleStringT
```  
  
### <a name="parameters"></a>Параметры  
 `BaseType`  
 Тип символа класса string. Ниже указаны доступные значения.  
  
- `char`(для символьных строк ANSI).  
  
- `wchar_t`(для символьных строк Юникода).  
  
- **TCHAR** (для символьных строк ANSI или Юникод).  

## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleStringT::PCXSTR](#pcxstr)|Указатель на строковую константу.|  
|[CSimpleStringT::PXSTR](#pxstr)|Указатель на строку.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleStringT::CSimpleStringT](#ctor)|Создает `CSimpleStringT` объекты различными способами.|  
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|Деструктор.|  

  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleStringT::Append](#append)|Добавляет `CSimpleStringT` объекта к существующему `CSimpleStringT` объекта.|  
|[CSimpleStringT::AppendChar](#appendchar)|Добавляет символ в существующий `CSimpleStringT` объекта.|  
|[CSimpleStringT::CopyChars](#copychars)|Копирует символ или символы в другую строку.|  
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|Копирует символ или символы на другую строку, в которой перекрываются буферы.|  
|[CSimpleStringT::Empty](#empty)|Принудительно строка имеет нулевую длину.|  
|[CSimpleStringT::FreeExtra](#freeextra)|Освобождает дополнительную память, выделенную ранее строкового объекта.|  
|[CSimpleStringT::GetAllocLength](#getalloclength)|Получает длину выделенного `CSimpleStringT` объекта.|  
|[CSimpleStringT::GetAt](#getat)|Возвращает символ в заданной позиции.|  
|[CSimpleStringT::GetBuffer](#getbuffer)|Возвращает указатель на символы в `CSimpleStringT`.|  
|[CSimpleStringT::GetBufferSetLength](#getbuffersetlength)|Возвращает указатель на символы в `CSimpleStringT`, усечено до указанной длины.|  
|[CSimpleStringT::GetLength](#getlength)|Возвращает количество символов в `CSimpleStringT` объекта.|  
|[CSimpleStringT::GetManager](#getmanager)|Возвращает значение, то диспетчер памяти `CSimpleStringT` объекта.|  
|[CSimpleStringT::GetString](#getstring)|Возвращает строку символов|  
|[CSimpleStringT::IsEmpty](#isempty)|Тесты ли `CSimpleStringT` объект не содержит символов.|  
|[CSimpleStringT::LockBuffer](#lockbuffer)|Отключает подсчет ссылок и защищает строки в буфере.|  
|[CSimpleStringT::Preallocate](#preallocate)|Выделяет определенный объем памяти для буфера символов.|  
|[CSimpleStringT::ReleaseBuffer](#releasebuffer)|Передает управление буфером, возвращаемым `GetBuffer`.|  
|[CSimpleStringT::ReleaseBufferSetLength](#releasebuffersetlength)|Передает управление буфером, возвращаемым `GetBuffer`.|  
|[CSimpleStringT::SetAt](#setat)|Задает символ в заданной позиции.|  
|[CSimpleStringT::SetManager](#setmanager)|Задает диспетчер памяти `CSimpleStringT` объекта.|  
|[CSimpleStringT::SetString](#setstring)|Задает строку `CSimpleStringT` объекта.|  
|[CSimpleStringT::StringLength](#stringlength)|Возвращает число символов в указанной строке.|  
|[CSimpleStringT::Truncate](#truncate)|Усекает строки до указанной длины.|  
|[CSimpleStringT::UnlockBuffer](#unlockbuffer)|Включает подсчет ссылок и освобождает строки в буфере.|  

### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleStringT::operator PCXSTR](#operator_pcxstr)|Прямой доступ к символов, сохраненных в `CSimpleStringT` объект в виде строки в стиле C.|  
|[CSimpleStringT::operator\[\]](#operator_at)|Возвращает символ в заданной позиции — оператор подстановки для `GetAt`.|  
|[CSimpleStringT::operator +=](#operator_add_eq)|Сцепляет новую строку в конец существующей строки.|  
|[CSimpleStringT::operator =](#operator_eq)|Присваивает новое значение для `CSimpleStringT` объекта.|  
  
### <a name="remarks"></a>Примечания  
 `CSimpleStringT`является базовым классом для различных классов строки, поддерживаемые Visual C++. Он предоставляет минимальную поддержку для управления памятью объект string и манипуляции базовый буфер. Для более сложных строковых объектов. в разделе [класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpstr.h  


## <a name="append"></a>CSimpleStringT::Append
Добавляет `CSimpleStringT` объекта к существующему `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void Append(const CSimpleStringT& strSrc); 
void Append(PCXSTR pszSrc, int nLength); 
void Append(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>Параметры  
 `strSrc`  
 `CSimpleStringT` Объект для добавления.  
  
 `pszSrc`  
 Указатель на строку, содержащую символы, которые требуется добавить.  
  
 `nLength`  
 Количество добавляемых знаков.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для добавления существующего `CSimpleStringT` объекта в другой `CSimpleStringT` объекта.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::Append`.  
  
```cpp  
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```
  
##  <a name="appendchar"></a>CSimpleStringT::AppendChar
Добавляет символ в существующий `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void AppendChar(XCHAR ch);
```  
#### <a name="parameters"></a>Параметры  
 *CH*  
 Символ для добавления  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для добавления указанный символ к концу существующего `CSimpleStringT` объекта.  
  
##  <a name="copychars"></a>CSimpleStringT::CopyChars  
 Копирует символ или символы `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
static void CopyChars(
  XCHAR* pchDest,
  const XCHAR* pchSrc, 
  int nChars) throw();
```  
#### <a name="parameters"></a>Параметры  
 `pchDest`  
 Указатель на строку символов.  
  
 `pchSrc`  
 Указатель на строку, содержащую символы, которые требуется скопировать.  
  
 `nChars`  
 Количество `pchSrc` копируемых знаков.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для копирования символов из `pchSrc` для `pchDest` строки.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::CopyChars`.  
  
```cpp  
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```
  
##  <a name="copycharsoverlapped"></a>CSimpleStringT::CopyCharsOverlapped
Копирует символ или символы `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
static void CopyCharsOverlapped(
  XCHAR* pchDest,
  const XCHAR* pchSrc,
  int nChars) throw(); 
```  
#### <a name="parameters"></a>Параметры  
 `pchDest`  
 Указатель на строку символов.  
  
 `pchSrc`  
 Указатель на строку, содержащую символы, которые требуется скопировать.  
  
 `nChars`  
 Количество `pchSrc` копируемых знаков.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для копирования символов из `pchSrc` для `pchDest` строки. В отличие от `CopyChars`, `CopyCharsOverlapped` обеспечивает безопасный метод копирования из символьных буферов, которые могут накладываться.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CSimpleStringT::CopyChars](#copychars), или исходный код для `CSimpleStringT::SetString` (находится в atlsimpstr.h).  
  
##  <a name="ctor"></a>CSimpleStringT::CSimpleStringT  
 Создает объект `CSimpleStringT`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr); 
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr); 
CSimpleStringT(const CSimpleStringT& strSrc); 
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw(); 
```  
#### <a name="parameters"></a>Параметры  
 `strSrc`  
 Существующий `CSimpleStringT` объект копируется это `CSimpleStringT` объекта.  
  
 `pchSrc`  
 Указатель на массив символов длиной `nLength`, не заканчивается на null.  
  
 `pszSrc`  
 Идентифицирующий копируется это `CSimpleStringT` объекта.  
  
 `nLength`  
 Число символов в `pch`.  
  
 `pStringMgr`  
 Указатель на диспетчер памяти `CSimpleStringT` объекта. Дополнительные сведения о `IAtlStringMgr` и управление памятью для `CSimpleStringT`, в разделе [управление памятью и CStringT](../memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Примечания  
 Создать новый `CSimpleStringT` объекта. Поскольку конструкторы копирования входных данных в новое хранилище, выделенное, это может привести к исключения памяти.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование `CSimpleStringT::CSimpleStringT` с помощью библиотеки ATL `typedef` `CSimpleString`. `CSimpleString`часто используемые специализации шаблона класса является `CSimpleStringT`.  
  
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

  
##  <a name="empty"></a>CSimpleStringT::Empty
Делает этот `CSimpleStringT` объекта пустую строку и освобождает память при необходимости.  
  
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
  
##  <a name="freeextra"></a>CSimpleStringT::FreeExtra
Освобождает дополнительную память, выделенную ранее в строке, но больше не нужны.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void FreeExtra(); 
```  
### <a name="remarks"></a>Примечания  
 Это следует уменьшить нагрузку на память, занятая строкового объекта. Метод перераспределяет буфера точная длина возвращенных [GetLength](#getlength).  
  
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
 Выходные данные этого примера выглядит следующим образом:  
  
 `Alloc length is 1031, String length is 1024`  
  
 `Alloc length is 1031, String length is 15`  
  
 `Alloc length is 15, String length is 15`  
  
##  <a name="getalloclength"></a>CSimpleStringT::GetAllocLength  
Получает длину выделенного `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
int GetAllocLength() const throw();  
```  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов, выделенных для этого объекта.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для определения количества символов, выделенных для этой `CSimpleStringT` объекта. В разделе [FreeExtra](#freeextra) пример вызова этой функции.  
  
##  <a name="getat"></a>CSimpleStringT::GetAt  
Возвращает один символ из `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
XCHAR GetAt(int iChar) const;
```  
#### <a name="parameters"></a>Параметры  
 `iChar`  
 Отсчитываемый от нуля индекс символа в `CSimpleStringT` объекта. `iChar` Параметр должен быть больше или равно 0 и меньше, чем значение, возвращаемое [GetLength](#getlength). В противном случае `GetAt` возникает исключение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `XCHAR` , Содержащее символ в указанной позиции в строке.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для возврата один символ, указанный `iChar`. Перегруженные нижнего индекса (`[]`) оператор является удобным псевдонимом для `GetAt`. Завершающий символ null адресуемый без создания исключения с помощью `GetAt`. Однако он не учитывается `GetLength`, и возвращаемое значение равно 0.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `CSimpleStringT::GetAt`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```
  
##  <a name="getbuffer"></a>CSimpleStringT::GetBuffer  
Возвращает указатель на буфер внутренних символов для `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
PXSTR GetBuffer(int nMinBufferLength); 
PXSTR GetBuffer();
```  
#### <a name="parameters"></a>Параметры  
 `nMinBufferLength`  
 Минимальное количество символов, которые могут содержаться в буфере символов. Это значение не учитывает пространство для завершающего нуль-символа.  
  
 Если `nMinBufferLength` больше, чем длина текущего буфера `GetBuffer` уничтожает текущего буфера и заменяет его с помощью буфера запрошенный размер обнуляется счетчик ссылок объекта. Если ранее был вызван [LockBuffer](#lockbuffer) на этот буфер потерять блокировки буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `PXSTR` Указатель на буфер объекта (завершающуюся значением null).  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для возврата содержимого буфера `CSimpleStringT` объект. Возвращенный `PXSTR` не является константой и поэтому позволяет прямое изменение `CSimpleStringT` содержимое.  
  
 Если вы используете указатель, возвращенный `GetBuffer` изменение содержимого строки, необходимо вызвать [ReleaseBuffer](#releasebuffer) перед использованием любых других `CSimpleStringT` методов-членов.  
  
 Адрес, возвращенный `GetBuffer` могут не работать после вызова `ReleaseBuffer` из-за дополнительных `CSimpleStringT` может привести к `CSimpleStringT` буфера перераспределить. Буфер не перераспределяется, если не изменить длину `CSimpleStringT`.  
  
 Буфер памяти будет автоматически высвобождается при `CSimpleStringT` объект удаляется.  
  
 Если можно хранить список длину строки самостоятельно, не должен добавлять завершающий символ null. Тем не менее, необходимо указать длину последней строки после отпускания буфера с `ReleaseBuffer`. Если добавить завершающий символ null, следует передать значение -1 (по умолчанию), в течение. `ReleaseBuffer`затем определяет длину буфера.  
  
 Если памяти недостаточно для удовлетворения `GetBuffer` запроса, этот метод создает исключение CMemoryException *.  
  
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
  
##  <a name="getbuffersetlength"></a>CSimpleStringT::GetBufferSetLength  
Возвращает указатель на буфер внутренних символов для `CSimpleStringT` объекта усечение или его длина растет, при необходимости точно соответствовать длине, указанной в `nLength`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
PXSTR GetBufferSetLength(int nLength);
```  
#### <a name="parameters"></a>Параметры  
 `nLength`  
 Точный размер получаемого `CSimpleStringT` символ буфера в символах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `PXSTR` указатель на буфер объекта (завершающуюся значением null).  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения указанной длины из внутреннего буфера `CSimpleStringT` объект. Возвращенный `PXSTR` указатель не `const` таким образом прямое изменение `CSimpleStringT` содержимое.  
  
 Если вы используете указатель, возвращенный [GetBufferSetLength](#getbuffersetlength) изменение содержимого строки, вызовите `ReleaseBuffer` обновление внутреннего состояния `CsimpleStringT` прежде чем использовать любой другой `CSimpleStringT` методы.  
  
 Адрес, возвращенный `GetBufferSetLength` могут не работать после вызова `ReleaseBuffer` из-за дополнительных `CSimpleStringT` может привести к `CSimpleStringT` буфера перераспределить. Буфер не перераспределяется, если не изменить длину `CSimpleStringT`.  
  
 Буфер памяти будет автоматически высвобождается при `CSimpleStringT` объект удаляется.  
  
 Если можно хранить список длину строки самостоятельно, не добавляет завершающий нуль-символ. Необходимо указать длину окончательную строку после отпускания буфера с помощью `ReleaseBuffer`. Если добавить знак завершения null при вызове `ReleaseBuffer`, передайте значение -1 (по умолчанию) в качестве длины для `ReleaseBuffer`, и `ReleaseBuffer` выполнит `strlen` в буфере, чтобы определить его длину.  
  
 Дополнительные сведения о подсчет ссылок см. в следующих статьях:  
  
- [Управление временем жизни объектов посредством подсчета ссылок](http://msdn.microsoft.com/library/windows/desktop/ms687260) в Windows SDK. 
  
- [Реализация подсчет ссылок](http://msdn.microsoft.com/library/windows/desktop/ms693431) в Windows SDK.
  
- [Правила для управления подсчет ссылок](http://msdn.microsoft.com/library/windows/desktop/ms692481) в Windows SDK.  
  
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
  
##  <a name="getlength"></a>CSimpleStringT::GetLength  
Возвращает количество символов в `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
int GetLength() const throw();  
```  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов в строке.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для возврата числа символов в объекте. Значение NULL не учитывается при подсчете.  
  
 Для многобайтовой кодировки (MBCS) `GetLength` счетчики каждый 8-разрядное символ, то есть руководитель и младший байт один Многобайтовый символ считаются за два байта. В разделе [FreeExtra](#freeextra) пример вызова этой функции.  
  
##  <a name="getmanager"></a>CSimpleStringT::GetManager  
Возвращает значение, то диспетчер памяти `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
IAtlStringMgr* GetManager() const throw();  
```  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на диспетчер памяти для `CSimpleStringT` объекта.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения памяти диспетчер используемый `CSimpleStringT` объекта. Дополнительные сведения о диспетчеры памяти и строковых объектов см. в разделе [управление памятью и CStringT](../memory-management-with-cstringt.md).  
  
##  <a name="getstring"></a>CSimpleStringT::GetString
Возвращает строку символов.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
PCXSTR GetString() const throw();
```  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку знаков, завершающуюся значением null.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения строки символов, связанной с `CSimpleStringT` объекта.  
  
> [!NOTE]
>  Возвращенный `PCXSTR` указатель `const` и не поддерживает прямое изменение `CSimpleStringT` содержимое.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::GetString`.  
  
```cpp  
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```
  
##  <a name="isempty"></a>CSimpleStringT::IsEmpty  
Тесты `CSimpleStringT` объект пустым условием.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool IsEmpty() const throw();  
```  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если `CSimpleStringT` объект имеет нулевую длину; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для определения, содержит ли объект пустая строка.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::IsEmpty`.  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```
  
##  <a name="lockbuffer"></a>CSimpleStringT::LockBuffer  
Отключает подсчет ссылок и защищает строки в буфере.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
PXSTR LockBuffer();
```  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CSimpleStringT` объект или строку, завершающуюся символом null.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для блокирования буфера из `CSimpleStringT` объекта. Путем вызова `LockBuffer`, создайте копию строки, на-1 для счетчика ссылок. Если значение счетчика ссылок равно -1, строка в буфере считается «заблокировано». В заблокированном состоянии строка защищен двумя способами:  
  
-   Не другая строка, можно получить ссылку на данные в заблокированной строке, даже если эта строка назначается заблокированные строки.  
  
-   Заблокированные строка никогда не будет ссылаться другой строкой, даже если другие строки копируется в заблокированной строке.  
  
 Блокировка строки в буфере, обеспечить монопольно строки в буфере останутся без изменений.  
  
 После завершения работы в `LockBuffer`, вызовите [UnlockBuffer](#unlockbuffer) сбросить счетчик ссылок на 1.  
  
> [!NOTE]
>  При вызове метода [GetBuffer](#getbuffer) на заблокированных буфера и вы установите `GetBuffer` параметр `nMinBufferLength` больше, чем длина текущего буфера, чтобы вы потеряете блокировки буфера. Вызов для `GetBuffer` уничтожает текущего буфера и заменяет его с помощью буфера запрошенный размер обнуляется счетчик ссылок.  
  
 Дополнительные сведения о подсчет ссылок см. в следующих статьях:  
  
- [Управление временем жизни объектов посредством подсчета ссылок](http://msdn.microsoft.com/library/windows/desktop/ms687260) в Windows SDK  
  
- [Реализация подсчет ссылок](http://msdn.microsoft.com/library/windows/desktop/ms693431) в Windows SDK  
  
- [Правила для управления подсчет ссылок](http://msdn.microsoft.com/library/windows/desktop/ms692481) в Windows SDK  
  
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
  
##  <a name="operator_at"></a>CSimpleStringT::operator\[\]  
Эта функция вызывается для доступа к отдельного символа в массиве символов.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
XCHAR operator[](int iChar) const;
```  
#### <a name="parameters"></a>Параметры  
 `iChar`  
 Отсчитываемый от нуля индекс символа в строке.  
  
### <a name="remarks"></a>Примечания  
 Перегруженные нижнего индекса (`[]`) оператор возвращает один символ, указанный с нуля индекс в массиве `iChar`. Этот оператор является удобным заменой [GetAt](#getat) функции-члена.  
  
> [!NOTE]
>  Можно использовать индекс (`[]`) оператор получить значение символа в `CSimpleStringT`, но его нельзя использовать, чтобы изменить значение символа в `CSimpleStringT`.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование **[CSimpleStringT::operator]**.  
  
```cpp  
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```
  
## <a name="operator_at"></a>CSimpleStringT::operator\[\]
Эта функция вызывается для доступа к отдельного символа в массиве символов.  
  
### <a name="syntax"></a>Синтаксис  
  
```   
XCHAR operator[](int iChar) const;
```  
  
### <a name="parameters"></a>Параметры  
 `iChar`  
 Отсчитываемый от нуля индекс символа в строке.  
  
### <a name="remarks"></a>Примечания  
 Перегруженные нижнего индекса (`[]`) оператор возвращает один символ, указанный с нуля индекс в массиве `iChar`. Этот оператор является удобным заменой [GetAt](#getat) функции-члена.  
  
> [!NOTE]
>  Можно использовать индекс (`[]`) оператор получить значение символа в `CSimpleStringT`, но его нельзя использовать, чтобы изменить значение символа в `CSimpleStringT`.  
  
  
##  <a name="operator_add_eq"></a>CSimpleStringT::operator +=  
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
 `pszSrc`  
 Указатель на строку, завершающуюся значением null.  
  
 `strSrc`  
 Указатель на существующий `CSimpleStringT` объекта.  
  
 *CH*  
 Символ значение для добавления.  
  
### <a name="remarks"></a>Примечания  
 Оператор принимает другой `CSimpleStringT` объекта или символ. Обратите внимание, что память исключения могут возникать при использовании этот оператор объединения, так как новое хранилище может быть выделен для символов, которые добавляются в этот `CSimpleStringT` объекта.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование **CSimpleStringT::operator +=**.  
  
```cpp  
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```
  
##  <a name="operator_eq"></a>CSimpleStringT::operator =  
Присваивает новое значение для `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
CSimpleStringT& operator =(PCXSTR pszSrc); 
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```  
#### <a name="parameters"></a>Параметры  
 `pszSrc`  
 Указатель на строку, завершающуюся значением null.  
  
 `strSrc`  
 Указатель на существующий `CSimpleStringT` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если строка назначения (слева) уже недостаточно велик для хранения новых данных, не новое выделение памяти не выполняется. Обратите внимание, что память исключения могут возникать при каждом использовании оператор присваивания, так как часто выделяется новая память для хранения результирующего `CSimpleStringT` объекта.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование **CSimpleStringT::operator =**.  
  
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
  
##  <a name="operator_pcxstr"></a>CSimpleStringT::operator PCXSTR  

 Прямой доступ к символов, сохраненных в `CSimpleStringT` объект в виде строки в стиле C.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
operator PCXSTR() const throw();
```  
### <a name="return-value"></a>Возвращаемое значение  
 Символ указатель строки данных.  
  
### <a name="remarks"></a>Примечания  
 Никакие символы копируются; возвращается только указатель. Следите за этим оператором. При изменении `CString` объекта после получения указателем символа, может вызвать перераспределение памяти, которое делает недействительными указателя.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование **CSimpleStringT::operator PCXSTR**.  
  
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
  
##  <a name="pcxstr"></a>CSimpleStringT::PCXSTR
Указатель на строковую константу.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;    
```  
##  <a name="preallocate"></a>CSimpleStringT::Preallocate  
Выделяет определенный объем байт для `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void Preallocate( int nLength);
```  
#### <a name="parameters"></a>Параметры  
 `nLength`  
 Точный размер получаемого `CSimpleStringT` символ буфера в символах.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы выделить определенный размер буфера для `CSimpleStringT` объекта.  
  
 `CSimpleStringT`приводит к возникновению ошибки `STATUS_NO_MEMORY` исключение, если не удалось выделить место для буфер символов. По умолчанию выполняется выделение памяти по функции WIN32 API `HeapAlloc` или `HeapReAlloc`.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::Preallocate`.  
  
```cpp  
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```
  
##  <a name="pxstr"></a>CSimpleStringT::PXSTR  
Указатель на строку.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;  
```  
##  <a name="releasebuffer"></a>CSimpleStringT::ReleaseBuffer  
Передает управление буфер, выделенный с [GetBuffer](#getbuffer).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void ReleaseBuffer(int nNewLength = -1);
```  
#### <a name="parameters"></a>Параметры  
 `nNewLength`  
 Новая длина строки в символах, без учета завершающего нуль-символа. Если строка имеет значение null, завершен, значение по умолчанию-1 задает `CSimpleStringT` размер для текущей длины строки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для повторно выделить или освободить буфер объекта string. Если вы знаете, что строки в буфере заканчивается на null, можно опустить `nNewLength` аргумент. Если строки не равно null завершен, используйте `nNewLength` для определения его длины. Адрес, возвращенный [GetBuffer](#getbuffer) является недопустимым после вызова `ReleaseBuffer` или любой другой `CSimpleStringT` операции.  
  
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
  
##  <a name="releasebuffersetlength"></a>CSimpleStringT::ReleaseBufferSetLength

Передает управление буфер, выделенный с [GetBuffer](#getbuffer).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void ReleaseBufferSetLength(int nNewLength);
```  
#### <a name="parameters"></a>Параметры  
 `nNewLength`  
 Длина освобождения, строки  
  
### <a name="remarks"></a>Примечания  
 Эта функция аналогична функционально [ReleaseBuffer](#releasebuffer) за исключением того, должен быть передан допустимую длину для создаваемого строкового объекта.  
  
##  <a name="setat"></a>CSimpleStringT::SetAt  
Задает один символ из `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void SetAt(int iChar, XCHAR ch);
```  
#### <a name="parameters"></a>Параметры  
 `iChar`  
 Отсчитываемый от нуля индекс символа в `CSimpleStringT` объекта. `iChar` Параметр должен быть больше или равно 0 и меньше, чем значение, возвращаемое [GetLength](#getlength).  
  
 *CH*  
 Новый символ.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для перезаписи символ, расположенный в `iChar`. Этот метод не увеличит строку, если `iChar` выходит за границы существующую строку.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::SetAt`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
``` 
  
##  <a name="setmanager"></a>CSimpleStringT::SetManager  
Указывает, то диспетчер памяти `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void SetManager(IAtlStringMgr* pStringMgr);
```  
#### <a name="parameters"></a>Параметры  
 `pStringMgr`  
 Указатель на новый диспетчер памяти.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для указания новой памяти используется диспетчер `CSimpleStringT` объекта. Дополнительные сведения о диспетчеры памяти и строковых объектов см. в разделе [управление памятью и CStringT](../memory-management-with-cstringt.md).  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::SetManager`.  
  
```cpp  
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```
  
##  <a name="setstring"></a>CSimpleStringT::SetString  
Задает строку `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void SetString(PCXSTR pszSrc, int nLength); 
void SetString(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>Параметры  
 `pszSrc`  
 Указатель на строку, завершающуюся значением null.  
  
 `nLength`  
 Число символов в `pszSrc`.  
  
### <a name="remarks"></a>Примечания  
 Скопируйте строку в `CSimpleStringT` объекта. `SetString`перезаписывает старые данные строки в буфере.  
  
 Обе версии `SetString` проверьте ли `pszSrc` является указателем null и если да, исключение **E_INVALIDARG** ошибки.  
  
 Один параметр версии `SetString` ожидает `pszSrc` на строку, завершающуюся символом null.  
  
 Два параметра версии `SetString` ожидает `pszSrc` представлять собой строку, завершающуюся значением null. Она использует `nLength` как длина строки, если она встречает значение NULL.  
  
 Два параметра версии `SetString` также проверяет ли `pszSrc` указывает на расположение в текущем буфере в `CSimpleStringT`. В этом случае специальные `SetString` использует функцию копирования памяти, которая не перезаписывает строковые данные, как он копирует строковые данные обратно в буфер.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::SetString`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```
  
##  <a name="stringlength"></a>CSimpleStringT::StringLength  
Возвращает число символов в указанной строке.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```  
#### <a name="parameters"></a>Параметры  
 `psz`  
 Указатель на строку, завершающуюся значением null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов в `psz`; без учета завершающего нуль-символа.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения количества символов в строке, на который указывает `psz`.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CSimpleStringT::StringLength`.  
  
```cpp  
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
``` 
  
##  <a name="truncate"></a>CSimpleStringT::Truncate
Усекает строки до новой длины.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void Truncate(int nNewLength);
```  
#### <a name="parameters"></a>Параметры  
 `nNewLength`  
 Новая длина строки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для усечения строки новую длину содержимого.  
  
> [!NOTE]
>  Это не влияет на выделенный длину буфера. Чтобы уменьшить или увеличить текущего буфера, в разделе [FreeExtra](#freeextra) и [Preallocate](#preallocate).  
  
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
  
##  <a name="unlockbuffer"></a>CSimpleStringT::UnlockBuffer
 Разблокирует буфер `CSimpleStringT` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void UnlockBuffer() throw();
```  
### <a name="remarks"></a>Примечания  
 Этот метод используется для сброса счетчика ссылок строки 1.  
  
 `CSimpleStringT` Автоматически вызывает деструктор `UnlockBuffer` чтобы убедиться, что буфер не заблокирован, когда вызывается деструктор. Пример этого метода см. в разделе [LockBuffer](#lockbuffer).  
  
##  <a name="dtor"></a>CSimpleStringT:: ~ CSimpleStringT
Уничтожает объект `CSimpleStringT`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
~CSimpleStringT() throw();
```  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для уничтожения `CSimpleStringT` объекта.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)
