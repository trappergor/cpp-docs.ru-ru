---
title: Класс CSimpleStringT
ms.date: 10/18/2018
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
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
ms.openlocfilehash: 76d418c4f063d5787209ea72e7c681013eb37801
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747030"
---
# <a name="csimplestringt-class"></a>Класс CSimpleStringT

Этот класс `CSimpleStringT` представляет объект.

## <a name="syntax"></a>Синтаксис

```
template <typename BaseType>
class CSimpleStringT
```

### <a name="parameters"></a>Параметры

*BaseType*<br/>
Тип символа класса строки. Может применяться один из перечисленных ниже типов.

- **символ** (для строк anSI символов).

- **wchar_t** (для строк символов Unicode).

- TCHAR (для строк символов ANSI и Unicode).

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CSimpleStringt::PXSTR](#pcxstr)|Указатель на постоянную строку.|
|[CSimpleStringT::PXSTR](#pxstr)|Указатель на строку.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSimpleStringt::CSimpleStringt](#ctor)|Строит `CSimpleStringT` объекты различными способами.|
|[CSimpleStringt:::CSimpleStringt](#dtor)|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleStringT::Приложение](#append)|Придатки `CSimpleStringT` объекта `CSimpleStringT` к существующему объекту.|
|[CSimpleStringT::AppendChar](#appendchar)|Придатки символа `CSimpleStringT` к существующему объекту.|
|[CSimpleStringT::CopyChars](#copychars)|Копирует символ или символ на другую строку.|
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|Копирует символ или символ на другую строку, в которой буферы перекрываются.|
|[CSimpleStringT::Пустой](#empty)|Силы строки иметь длину нуля.|
|[CSimpleStringt::FreeExtra](#freeextra)|Освобождает любую дополнительную память, ранее выделенную объектом строки.|
|[CSimpleStringT::GetAllocLength](#getalloclength)|Извлекает выделенную длину `CSimpleStringT` объекта.|
|[CSimpleStringt::GetAt](#getat)|Возвращает персонажа в заданную позицию.|
|[CSimpleStringT::GetBuffer](#getbuffer)|Возвращает указатель персонажам в `CSimpleStringT`.|
|[CSimpleStringt::GetBufferSetДлина](#getbuffersetlength)|Возвращает указатель символам `CSimpleStringT`в , усечение до указанной длины.|
|[CSimpleStringt::GetLength](#getlength)|Возвращает количество символов в `CSimpleStringT` объекте.|
|[CSimpleStringT::GetManager](#getmanager)|Извлекает менеджер памяти `CSimpleStringT` объекта.|
|[CSimpleStringT::GetString](#getstring)|Извлекает строку персонажа|
|[CSimpleStringt::Isempty](#isempty)|Тестирует, `CSimpleStringT` не содержит ли объект символов.|
|[CSimpleStringT::LockBuffer](#lockbuffer)|Отстраняет от счета ссылки и защищает строку в буфере.|
|[CSimpleStringT: :Pперераспределено](#preallocate)|Выделяет определенное количество памяти для буфера символов.|
|[CSimpleStringT::ReleaseBuffer](#releasebuffer)|Выпускает контроль буфера, `GetBuffer`возвращенного .|
|[CSimpleStringt::ReleaseBufferSetLength](#releasebuffersetlength)|Выпускает контроль буфера, `GetBuffer`возвращенного .|
|[CSimpleStringt::SetAt](#setat)|Устанавливает персонажа в заданной позиции.|
|[CSimpleStringT::SetManager](#setmanager)|Устанавливает диспетчер памяти `CSimpleStringT` объекта.|
|[CSimpleStringT::SetString](#setstring)|Устанавливает строку `CSimpleStringT` объекта.|
|[CSimpleStringT::Струнная длина](#stringlength)|Возвращает количество символов в указанной строке.|
|[CSimpleStringT::Truncate](#truncate)|Truncates строки к заданной длине.|
|[CSimpleStringT::UnlockBuffer](#unlockbuffer)|Позволяет считать ссылки и выпускает строку в буфере.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CSimpleStringT::оператор PCXSTR](#operator_pcxstr)|Непосредственно получает доступ к `CSimpleStringT` символам, хранящимся в объекте в виде строки C-стиля.|
|[CSimpleStringT::operator\[\]](#operator_at)|Возвращает персонажа на заданную позицию `GetAt`– замена оператора на .|
|[CSimpleStringT::оператор](#operator_add_eq)|Конкретирует новую строку до конца существующей строки.|
|[CSimpleStringT::оператор](#operator_eq)|Присваивает объекту `CSimpleStringT` новое значение.|

### <a name="remarks"></a>Remarks

`CSimpleStringT`является базовым классом для различных классов строк, поддерживаемых Visual C . Он обеспечивает минимальную поддержку для управления памятью объекта строки и основных манипуляций буфера. Для более продвинутых объектов строки [см.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="requirements"></a>Требования

**Заголовок:** atlsimpstr.h

## <a name="csimplestringtappend"></a><a name="append"></a>CSimpleStringT::Приложение

Придатки `CSimpleStringT` объекта `CSimpleStringT` к существующему объекту.

### <a name="syntax"></a>Синтаксис

```cpp
void Append(const CSimpleStringT& strSrc);
void Append(PCXSTR pszSrc, int nLength);
void Append(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Параметры

*strSrc*<br/>
Объект, `CSimpleStringT` который будет придатим.

*pszSrc*<br/>
Указатель на строку, содержащую символы, которые будут придатиться.

*nДлина*<br/>
Количество добавляемых знаков.

### <a name="remarks"></a>Remarks

Вызовите этот метод, `CSimpleStringT` чтобы `CSimpleStringT` привить существующий объект к другому объекту.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::Append`.

```cpp
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

## <a name="csimplestringtappendchar"></a><a name="appendchar"></a>CSimpleStringT::AppendChar

Придатки символа `CSimpleStringT` к существующему объекту.

### <a name="syntax"></a>Синтаксис

```cpp
void AppendChar(XCHAR ch);
```

#### <a name="parameters"></a>Параметры

*Ch*<br/>
Символ, который будет придатим

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы прибывать `CSimpleStringT` указанный символ к концу существующего объекта.

## <a name="csimplestringtcopychars"></a><a name="copychars"></a>CSimpleStringT::CopyChars

Копирует символ или символ `CSimpleStringT` ы на объект.

### <a name="syntax"></a>Синтаксис

```
static void CopyChars(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Параметры

*pchDest*<br/>
Указатель на строку персонажа.

*pchSrc*<br/>
Указатель на строку, содержащую символы, которые будут скопированы.

*nChars*<br/>
Количество символов *pchSrc,* которые будут скопированы.

### <a name="remarks"></a>Remarks

Вызовите этот метод для копирования символов из *pchSrc* на строку *pchDest.*

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::CopyChars`.

```cpp
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```

## <a name="csimplestringtcopycharsoverlapped"></a><a name="copycharsoverlapped"></a>CSimpleStringT::CopyCharsOverlapped

Копирует символ или символ `CSimpleStringT` ы на объект.

### <a name="syntax"></a>Синтаксис

```
static void CopyCharsOverlapped(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Параметры

*pchDest*<br/>
Указатель на строку персонажа.

*pchSrc*<br/>
Указатель на строку, содержащую символы, которые будут скопированы.

*nChars*<br/>
Количество символов *pchSrc,* которые будут скопированы.

### <a name="remarks"></a>Remarks

Вызовите этот метод для копирования символов из *pchSrc* на строку *pchDest.* В `CopyChars` `CopyCharsOverlapped` отличие от , обеспечивает безопасный метод копирования из буферов символов, которые могут быть перекрыты.

### <a name="example"></a>Пример

Смотрите пример [для CSimpleStringT::CopyChars](#copychars), или `CSimpleStringT::SetString` исходный код для (расположен в atlsimpstr.h).

## <a name="csimplestringtcsimplestringt"></a><a name="ctor"></a>CSimpleStringt::CSimpleStringt

Формирует объект `CSimpleStringT`.

### <a name="syntax"></a>Синтаксис

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr);
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr);
CSimpleStringT(const CSimpleStringT& strSrc);
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw();
```

#### <a name="parameters"></a>Параметры

*strSrc*<br/>
Существующий `CSimpleStringT` объект, который должен `CSimpleStringT` быть скопирован в этот объект.

*pchSrc*<br/>
Указатель на массив символов длины *nLength*, а не недействительным прекращено.

*pszSrc*<br/>
Нулевая строка, которая будет `CSimpleStringT` скопирована в этот объект.

*nДлина*<br/>
Подсчет количества символов в `pch`.

*pStringMgr*<br/>
Указатель на менеджер памяти `CSimpleStringT` объекта. Для получения `IAtlStringMgr` дополнительной информации `CSimpleStringT`и управления памятью для, см. [Управление памятью и CStringT](../memory-management-with-cstringt.md).

### <a name="remarks"></a>Remarks

Постройте `CSimpleStringT` новый объект. Поскольку конструкторы копируют входные данные в новое выделенное хранилище, могут возникнуть исключения из памяти.

### <a name="example"></a>Пример

Следующий пример демонстрирует использование `CSimpleStringT::CSimpleStringT` с помощью **ATL typedef** `CSimpleString`. `CSimpleString`является широко используемой специализацией `CSimpleStringT`шаблона класса.

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

## <a name="csimplestringtempty"></a><a name="empty"></a>CSimpleStringT::Пустой

Делает `CSimpleStringT` этот объект пустой строкой и освобождает память по мере необходимости.

### <a name="syntax"></a>Синтаксис

```cpp
void Empty() throw();
```

### <a name="remarks"></a>Remarks

Для получения дополнительной [информации см.](../cstring-exception-cleanup.md)

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::Empty`.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtfreeextra"></a><a name="freeextra"></a>CSimpleStringt::FreeExtra

Освобождает любую дополнительную память, ранее выделенную строкой, но больше не нужной.

### <a name="syntax"></a>Синтаксис

```cpp
void FreeExtra();
```

### <a name="remarks"></a>Remarks

Это должно уменьшить накладные расходы памяти, потребляемые объектом строки. Метод перераспределяет буфер до точной длины, возвращенной [GetLength.](#getlength)

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

### <a name="remarks"></a>Remarks

Выход из этого примера заключается в следующем:

```Output
Alloc length is 1031, String length is 1024
Alloc length is 1031, String length is 15
Alloc length is 15, String length is 15
```

## <a name="csimplestringtgetalloclength"></a><a name="getalloclength"></a>CSimpleStringT::GetAllocLength

Извлекает выделенную длину `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```
int GetAllocLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Количество символов, выделенных для этого объекта.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы определить `CSimpleStringT` количество символов, выделенных для этого объекта. [Например, FreeExtra](#freeextra) можно назвать эту функцию.

## <a name="csimplestringtgetat"></a><a name="getat"></a>CSimpleStringt::GetAt

Возвращает одного символа `CSimpleStringT` с объекта.

### <a name="syntax"></a>Синтаксис

```
XCHAR GetAt(int iChar) const;
```

#### <a name="parameters"></a>Параметры

*iChar*<br/>
Индекс персонажа на нулевом `CSimpleStringT` уровне в объекте. Параметр *iChar* должен быть больше или равен 0 и меньше значения, возвращенного [GetLength.](#getlength) В `GetAt` противном случае, будет генерировать исключение.

### <a name="return-value"></a>Возвращаемое значение

Элемент, `XCHAR` содержащий символ в указанном положении в строке.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы вернуть один символ, указанный *iChar.* Перегруженный подписочный оператор**является**удобным псевдонимом. `GetAt` Терминатор null является адресным без создания исключения `GetAt`с помощью . Тем не менее, `GetLength`он не учитывается, и возвращенное значение составляет 0.

### <a name="example"></a>Пример

Следующий пример показывает, `CSimpleStringT::GetAt`как использовать .

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

## <a name="csimplestringtgetbuffer"></a><a name="getbuffer"></a>CSimpleStringT::GetBuffer

Возвращает указатель во внутренний буфер `CSimpleStringT` символов для объекта.

### <a name="syntax"></a>Синтаксис

```
PXSTR GetBuffer(int nMinBufferLength);
PXSTR GetBuffer();
```

#### <a name="parameters"></a>Параметры

*nMinBufferLength*<br/>
Минимальное количество символов, которые может содержать буфер символов. Это значение не включает место для нулевого терминатора.

Если *nMinBufferLength* больше длины текущего `GetBuffer` буфера, уничтожает текущий буфер, заменяет его буфером запрашиваемого размера и сбрасывает количество ссылок объекта до нуля. Если вы ранее вызывали [LockBuffer](#lockbuffer) в этом буфере, вы теряете блокировку буфера.

### <a name="return-value"></a>Возвращаемое значение

Указатель `PXSTR` на буфер символов объекта (null-terminated).

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы `CSimpleStringT` вернуть содержимое буфера объекта. Возврат `PXSTR` не является постоянным и, следовательно, позволяет прямое изменение содержимого. `CSimpleStringT`

Если вы используете указатель, возвращенный `GetBuffer` для изменения содержимого строки, необходимо вызвать [ReleaseBuffer,](#releasebuffer) прежде чем использовать другие `CSimpleStringT` методы участника.

Адрес, возвращенный, `GetBuffer` может быть недействительным после вызова, `ReleaseBuffer` поскольку дополнительные `CSimpleStringT` операции могут привести к перераспределению `CSimpleStringT` буфера. Буфер не перераспределяется, если вы не `CSimpleStringT`измените длину .

Память буфера автоматически освобождается при уничтожении `CSimpleStringT` объекта.

Если вы отслеживаете длину строки самостоятельно, вы не должны прилагать окончание нулевой характер. Однако при освобождении буфера необходимо указать `ReleaseBuffer`окончательную длину строки. Если вы придаваете прекращение нулевого символа, вы должны пройти -1 (по умолчанию) для длины. `ReleaseBuffer`затем определяет длину буфера.

Если не хватает памяти, чтобы удовлетворить `GetBuffer` запрос, этот метод бросает CMemoryException.

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

## <a name="csimplestringtgetbuffersetlength"></a><a name="getbuffersetlength"></a>CSimpleStringt::GetBufferSetДлина

Возвращает указатель на внутренний буфер `CSimpleStringT` символов для объекта, усечение или увеличение его длины, если это необходимо, чтобы точно соответствовать длине, указанной в *nLength.*

### <a name="syntax"></a>Синтаксис

```
PXSTR GetBufferSetLength(int nLength);
```

#### <a name="parameters"></a>Параметры

*nДлина*<br/>
Точный размер `CSimpleStringT` буфера символов в символах.

### <a name="return-value"></a>Возвращаемое значение

Указатель `PXSTR` на буфер символов объекта (null-terminated).

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы получить заданную `CSimpleStringT` длину внутреннего буфера объекта. Возвращенный `PXSTR` указатель не является **конст и,** таким образом, позволяет прямое изменение содержимого. `CSimpleStringT`

Если вы используете указатель, возвращенный [GetBufferSetLength,](#getbuffersetlength) чтобы изменить содержимое строки, позвоните `ReleaseBuffer` для обновления внутреннего `CsimpleStringT` состояния, прежде чем использовать любые другие `CSimpleStringT` методы.

Адрес, возвращенный, `GetBufferSetLength` может быть недействительным после вызова, `ReleaseBuffer` поскольку дополнительные `CSimpleStringT` операции могут привести к перераспределению `CSimpleStringT` буфера. Буфер не переназначается, если вы не измените длину `CSimpleStringT`.

Память буфера автоматически освобождается при уничтожении `CSimpleStringT` объекта.

Если вы отслеживаете длину строки самостоятельно, не прилагайте окончание нулевой характер. При освобождении буфера необходимо указать окончательную длину строки с помощью `ReleaseBuffer`. Если вы придаваете прекращение нулевого `ReleaseBuffer`символа при вызове, пройдите `ReleaseBuffer`-1 `ReleaseBuffer` (по `strlen` умолчанию) для длины до, и выполнитна на буфере, чтобы определить его длину.

Для получения дополнительной информации о подсчете ссылок см.

- [Управление сроком службы объектов с помощью подсчета ссылок](/windows/win32/com/managing-object-lifetimes-through-reference-counting) в SDK Windows.

- [Реализация справочного подсчета](/windows/win32/com/implementing-reference-counting) в SDK Windows.

- [Правила управления справочным подсчетом](/windows/win32/com/rules-for-managing-reference-counts) в SDK Windows.

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

## <a name="csimplestringtgetlength"></a><a name="getlength"></a>CSimpleStringt::GetLength

Возвращает количество символов в `CSimpleStringT` объекте.

### <a name="syntax"></a>Синтаксис

```
int GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Количество символов в строке.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы вернуть количество символов в объекте. Подсчет не включает нулевой терминатор.

Для многобайтовых наборов `GetLength` символов (MBCS) подсчитывает каждый 8-битный символ; то есть, свинец и след байт в одном мультибайтном символе считаются двумя байтами. [Например, FreeExtra](#freeextra) можно назвать эту функцию.

## <a name="csimplestringtgetmanager"></a><a name="getmanager"></a>CSimpleStringT::GetManager

Извлекает менеджер памяти `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```
IAtlStringMgr* GetManager() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на менеджер памяти `CSimpleStringT` объекта.

### <a name="remarks"></a>Remarks

Вызовите этот метод для извлечения менеджера памяти, используемого объектом. `CSimpleStringT` Для получения дополнительной информации об менеджерах памяти и объектах строк [см. Управление памятью и CStringT.](../memory-management-with-cstringt.md)

## <a name="csimplestringtgetstring"></a><a name="getstring"></a>CSimpleStringT::GetString

Извлекает строку персонажа.

### <a name="syntax"></a>Синтаксис

```
PCXSTR GetString() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку символов с нулевым завершением.

### <a name="remarks"></a>Remarks

Вызов иметод для извлечения строки символов, связанной с объектом. `CSimpleStringT`

> [!NOTE]
> Возвращенный `PCXSTR` указатель является **конст** и `CSimpleStringT` не позволяет прямого изменения содержимого.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::GetString`.

```cpp
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

## <a name="csimplestringtisempty"></a><a name="isempty"></a>CSimpleStringt::Isempty

Тестирует `CSimpleStringT` объект на пустое состояние.

### <a name="syntax"></a>Синтаксис

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, `CSimpleStringT` если объект имеет 0 длину; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы определить, содержит ли объект пустую строку.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::IsEmpty`.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtlockbuffer"></a><a name="lockbuffer"></a>CSimpleStringT::LockBuffer

Отстраняет от счета ссылки и защищает строку в буфере.

### <a name="syntax"></a>Синтаксис

```
PXSTR LockBuffer();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CSimpleStringT` объект или строку с нулевым завершением.

### <a name="remarks"></a>Remarks

Вызовите этот метод, `CSimpleStringT` чтобы заблокировать буфер объекта. Позвонив, `LockBuffer`вы создаете копию строки, с -1 для подсчета ссылок. Когда значение эталонного значения -1 считается строкой в буфере в "заблокированном" состоянии. Находясь в заблокированном состоянии, строка защищена двумя способами:

- Никакая другая строка не может получить ссылку на данные в заблокированной строке, даже если эта строка назначена заблокированной строке.

- Заблокированная строка никогда не будет ссылаться на другую строку, даже если другая строка скопирована на заблокированную строку.

Зафиксировав строку в буфере, вы гарантируете, что эксклюзивное удержание строки в буфере останется нетронутым.

После того как `LockBuffer`вы закончили с, вызов [UnlockBuffer](#unlockbuffer) сбросить количество ссылок на 1.

> [!NOTE]
> Если вы вызовете [GetBuffer](#getbuffer) в заблокированном буфере и установите `GetBuffer` параметр `nMinBufferLength` больше длины текущего буфера, вы потеряете блокировку буфера. Такой призыв `GetBuffer` уничтожает текущий буфер, заменяет его буфером запрашиваемого размера и сбрасывает количество ссылок до нуля.

Для получения дополнительной информации о подсчете ссылок см.

- [Управление сроком службы объектов с помощью подсчета ссылок](/windows/win32/com/managing-object-lifetimes-through-reference-counting) в SDK Windows

- [Внедрение справочного подсчета](/windows/win32/com/implementing-reference-counting) в SDK Windows

- [Правила управления справочным подсчетом](/windows/win32/com/rules-for-managing-reference-counts) в SDK Windows

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

## <a name="csimplestringtoperator"></a><a name="operator_at"></a>CSimpleStringT::оператор\[\]

Вызовите эту функцию, чтобы получить доступ к одному символу массива символов.

### <a name="syntax"></a>Синтаксис

```
XCHAR operator[](int iChar) const;
```

#### <a name="parameters"></a>Параметры

*iChar*<br/>
Нулевой индекс персонажа в строке.

### <a name="remarks"></a>Remarks

Перегруженный подскрипт **()** оператор возвращает один символ, указанный индексом с нулевым уровнем в *iChar*. Этот оператор является удобной заменой функции участника [GetAt.](#getat)

> [!NOTE]
> Вы можете использовать оператор subscript **,** чтобы получить значение символа в `CSimpleStringT`, но вы не можете использовать `CSimpleStringT`его, чтобы изменить значение символа в .

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::operator []`.

```cpp
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="csimplestringtoperator-"></a><a name="operator_at"></a>CSimpleStringT::оператор\[\]

Вызовите эту функцию, чтобы получить доступ к одному символу массива символов.

### <a name="syntax"></a>Синтаксис

```
XCHAR operator[](int iChar) const;
```

### <a name="parameters"></a>Параметры

*iChar*<br/>
Нулевой индекс персонажа в строке.

### <a name="remarks"></a>Remarks

Перегруженный подскрипт **()** оператор возвращает один символ, указанный индексом с нулевым уровнем в *iChar*. Этот оператор является удобной заменой функции участника [GetAt.](#getat)

> [!NOTE]
> Вы можете использовать оператор subscript **,** чтобы получить значение символа в `CSimpleStringT`, но вы не можете использовать `CSimpleStringT`его, чтобы изменить значение символа в .

## <a name="csimplestringtoperator-"></a><a name="operator_add_eq"></a>CSimpleStringT::оператор

Присоединяется к новой строке или символу до конца существующей строки.

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

*pszSrc*<br/>
Указатель на нулевую строку.

*strSrc*<br/>
Указатель на существующий `CSimpleStringT` объект.

*Ch*<br/>
Символ значение для добавления.

### <a name="remarks"></a>Remarks

Оператор принимает другой `CSimpleStringT` объект или символ. Обратите внимание, что исключения памяти могут возникать при использовании этого оператора конкатации, поскольку новое хранилище может быть выделено для символов, добавленных к этому `CSimpleStringT` объекту.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::operator +=`.

```cpp
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

## <a name="csimplestringtoperator-"></a><a name="operator_eq"></a>CSimpleStringT::оператор

Присваивает объекту `CSimpleStringT` новое значение.

### <a name="syntax"></a>Синтаксис

```
CSimpleStringT& operator =(PCXSTR pszSrc);
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```

#### <a name="parameters"></a>Параметры

*pszSrc*<br/>
Указатель на нулевую строку.

*strSrc*<br/>
Указатель на существующий `CSimpleStringT` объект.

### <a name="remarks"></a>Remarks

Если строка назначения (левая сторона) уже достаточно велика для хранения новых данных, новое распределение памяти не выполняется. Обратите внимание, что исключения памяти могут возникать при использовании оператора `CSimpleStringT` назначения, поскольку для удержания полученного объекта часто выделяется новое хранилище.

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

## <a name="csimplestringtoperator-pcxstr"></a><a name="operator_pcxstr"></a>CSimpleStringT::оператор PCXSTR

Непосредственно получает доступ к `CSimpleStringT` символам, хранящимся в объекте в виде строки C-стиля.

### <a name="syntax"></a>Синтаксис

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель символов к данным строки.

### <a name="remarks"></a>Remarks

Символы не копируются; возвращается только указатель. Будьте осторожны с этим оператором. Если вы `CString` измените объект после получения указателя символов, вы можете вызвать перераспределение памяти, которое аннулирует указатель.

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

## <a name="csimplestringtpcxstr"></a><a name="pcxstr"></a>CSimpleStringt::PXSTR

Указатель на постоянную строку.

### <a name="syntax"></a>Синтаксис

```
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;
```

## <a name="csimplestringtpreallocate"></a><a name="preallocate"></a>CSimpleStringT: :Pперераспределено

Выделяет определенное количество байтов `CSimpleStringT` для объекта.

### <a name="syntax"></a>Синтаксис

```cpp
void Preallocate( int nLength);
```

#### <a name="parameters"></a>Параметры

*nДлина*<br/>
Точный размер `CSimpleStringT` буфера символов в символах.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы `CSimpleStringT` выделить определенный размер буфера для объекта.

`CSimpleStringT`генерирует STATUS_NO_MEMORY исключение, если он не в состоянии выделить место для буфера символов. По умолчанию выделение памяти выполняется `HeapAlloc` `HeapReAlloc`функциями WIN32 API или .

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::Preallocate`.

```cpp
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```

## <a name="csimplestringtpxstr"></a><a name="pxstr"></a>CSimpleStringT::PXSTR

Указатель на строку.

### <a name="syntax"></a>Синтаксис

```
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;
```

## <a name="csimplestringtreleasebuffer"></a><a name="releasebuffer"></a>CSimpleStringT::ReleaseBuffer

Выпускает контроль буфера, выделенного [GetBuffer](#getbuffer).

### <a name="syntax"></a>Синтаксис

```cpp
void ReleaseBuffer(int nNewLength = -1);
```

#### <a name="parameters"></a>Параметры

*nNewLength*<br/>
Новая длина строки в символах, не считая нулевой терминатор. Если строка недействительна, значение по `CSimpleStringT` умолчанию -1 устанавливает размер к текущей длине строки.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы перераспределить или высвободить буфер объекта строки. Если вы знаете, что строка в буфере недействительна, вы можете пропустить аргумент *nNewLength.* Если строка не будет отменена, используйте *nNewLength,* чтобы указать ее длину. Адрес, возвращенный [GetBuffer,](#getbuffer) является недействительным `ReleaseBuffer` после `CSimpleStringT` вызова или любой другой операции.

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

## <a name="csimplestringtreleasebuffersetlength"></a><a name="releasebuffersetlength"></a>CSimpleStringt::ReleaseBufferSetLength

Выпускает контроль буфера, выделенного [GetBuffer](#getbuffer).

### <a name="syntax"></a>Синтаксис

```cpp
void ReleaseBufferSetLength(int nNewLength);
```

#### <a name="parameters"></a>Параметры

*nNewLength*<br/>
Длина строки, выпускаемых

### <a name="remarks"></a>Remarks

Эта функция функционально похожа на [ReleaseBuffer,](#releasebuffer) за исключением того, что допустимая длина для объекта строки должна быть пройдена.

## <a name="csimplestringtsetat"></a><a name="setat"></a>CSimpleStringt::SetAt

Устанавливает один символ `CSimpleStringT` из объекта.

### <a name="syntax"></a>Синтаксис

```cpp
void SetAt(int iChar, XCHAR ch);
```

#### <a name="parameters"></a>Параметры

*iChar*<br/>
Индекс персонажа на нулевом `CSimpleStringT` уровне в объекте. Параметр *iChar* должен быть больше или равен 0 и меньше значения, возвращенного [GetLength.](#getlength)

*Ch*<br/>
Новый персонаж.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы перезаписать символ, расположенный на *iChar.* Этот метод не увеличит строку, если *iChar* превышает границы существующей строки.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::SetAt`.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

## <a name="csimplestringtsetmanager"></a><a name="setmanager"></a>CSimpleStringT::SetManager

Определяет менеджер памяти `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
void SetManager(IAtlStringMgr* pStringMgr);
```

#### <a name="parameters"></a>Параметры

*pStringMgr*<br/>
Указатель на новый менеджер памяти.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы указать новый менеджер памяти, используемый объектом. `CSimpleStringT` Для получения дополнительной информации об менеджерах памяти и объектах строк [см. Управление памятью и CStringT.](../memory-management-with-cstringt.md)

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::SetManager`.

```cpp
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

## <a name="csimplestringtsetstring"></a><a name="setstring"></a>CSimpleStringT::SetString

Устанавливает строку `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
void SetString(PCXSTR pszSrc, int nLength);
void SetString(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Параметры

*pszSrc*<br/>
Указатель на нулевую строку.

*nДлина*<br/>
Подсчет количества символов в *pszSrc*.

### <a name="remarks"></a>Remarks

Копирование строки `CSimpleStringT` в объект. `SetString`перезаписывает старые строки данных в буфере.

Обе версии `SetString` проверить, является ли *pszSrc* нулевой указатель, и если это так, бросить E_INVALIDARG ошибку.

Однопараметрная `SetString` версия ожидает, что *pszSrc* укажет на нулевую строку.

Двухпараметрная версия `SetString` также предполагает, что *pszSrc* будет нулевой строкой. Он использует *nLength* в качестве длины строки, если он сталкивается с нулевым терминатором в первую очередь.

Двухпараметрная версия `SetString` также проверяет, указывает ли *pszSrc* на `CSimpleStringT`место в текущем буфере в . В данном особом случае используется функция копирования памяти, `SetString` которая не перезаписывает данные строки при копировании данных строки обратно в буфер.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::SetString`.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```

## <a name="csimplestringtstringlength"></a><a name="stringlength"></a>CSimpleStringT::Струнная длина

Возвращает количество символов в указанной строке.

### <a name="syntax"></a>Синтаксис

```
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```

#### <a name="parameters"></a>Параметры

*Psz*<br/>
Указатель на нулевую строку.

### <a name="return-value"></a>Возвращаемое значение

Количество символов в *psz*; не считая нулевого терминатора.

### <a name="remarks"></a>Remarks

Вызов исчерпнивайте этот метод, чтобы получить количество символов в строке, на которую указывает *psz.*

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::StringLength`.

```cpp
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
```

## <a name="csimplestringttruncate"></a><a name="truncate"></a>CSimpleStringT::Truncate

Truncates строки на новую длину.

### <a name="syntax"></a>Синтаксис

```cpp
void Truncate(int nNewLength);
```

#### <a name="parameters"></a>Параметры

*nNewLength*<br/>
Новая длина строки.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы усечение содержимого строки на новую длину.

> [!NOTE]
> Это не влияет на выделенную длину буфера. Чтобы уменьшить или увеличить текущий буфер, [см. FreeExtra](#freeextra) и [Preallocate.](#preallocate)

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

## <a name="csimplestringtunlockbuffer"></a><a name="unlockbuffer"></a>CSimpleStringT::UnlockBuffer

Открывает буфер `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
void UnlockBuffer() throw();
```

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы сбросить количество ссылок строки до 1.

Деструктор `CSimpleStringT` автоматически `UnlockBuffer` вызывает, чтобы гарантировать, что буфер не заблокирован при вызове деструктора. Пример этого метода можно оперет., [LockBuffer](#lockbuffer).

## <a name="csimplestringtcsimplestringt"></a><a name="dtor"></a>CSimpleStringt:::CSimpleStringt

Уничтожает объект `CSimpleStringT` .

### <a name="syntax"></a>Синтаксис

```
~CSimpleStringT() throw();
```

### <a name="remarks"></a>Remarks

Вызовите этот `CSimpleStringT` метод, чтобы уничтожить объект.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
