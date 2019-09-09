---
title: Класс Ксимплестрингт
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
ms.openlocfilehash: c033346b7a687a1c6778ad23e30ee0e73c787ad8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491450"
---
# <a name="csimplestringt-class"></a>Класс Ксимплестрингт

Этот класс представляет `CSimpleStringT` объект.

## <a name="syntax"></a>Синтаксис

```
template <typename BaseType>
class CSimpleStringT
```

### <a name="parameters"></a>Параметры

*BaseType*<br/>
Символьный тип класса String. Ниже указаны доступные значения.

- **тип char** (для строк символов ANSI).

- **wchar_t** (для символьных строк Юникода).

- TCHAR (для символьных строк ANSI и Unicode).

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|[Ксимплестрингт::P ККССТР](#pcxstr)|Указатель на константную строку.|
|[Ксимплестрингт::P КССТР](#pxstr)|Указатель на строку.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ксимплестрингт:: Ксимплестрингт](#ctor)|`CSimpleStringT` Конструирует объекты различными способами.|
|[Ксимплестрингт:: ~ Ксимплестрингт](#dtor)|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ксимплестрингт:: Append](#append)|Добавляет объект к существующему `CSimpleStringT`объекту. `CSimpleStringT`|
|[Ксимплестрингт:: Аппендчар](#appendchar)|Добавляет символ к существующему `CSimpleStringT` объекту.|
|[Ксимплестрингт:: Копичарс](#copychars)|Копирует символ или символы в другую строку.|
|[Ксимплестрингт:: Копичарсоверлаппед](#copycharsoverlapped)|Копирует символ или символы в другую строку, в которой буферы перекрываются.|
|[Ксимплестрингт:: Empty](#empty)|Принуждает строку иметь нулевую длину.|
|[Ксимплестрингт:: Фриекстра](#freeextra)|Освобождает все дополнительные памяти, ранее выделенные строковым объектом.|
|[Ксимплестрингт:: Жеталлокленгс](#getalloclength)|Извлекает выделенную длину `CSimpleStringT` объекта.|
|[Ксимплестрингт:: GetAt](#getat)|Возвращает символ в заданной позиции.|
|[Ксимплестрингт:: buffer](#getbuffer)|Возвращает указатель на символы в `CSimpleStringT`.|
|[Ксимплестрингт:: Жетбуфферсетленгс](#getbuffersetlength)|Возвращает указатель на символы в `CSimpleStringT`, усечение до указанной длины.|
|[Ксимплестрингт:: DATALENGTH](#getlength)|Возвращает количество символов в `CSimpleStringT` объекте.|
|[Ксимплестрингт:: Manage](#getmanager)|Возвращает диспетчер `CSimpleStringT` памяти объекта.|
|[Ксимплестрингт:: GetString](#getstring)|Получает строку символов|
|[Ксимплестрингт:: IsEmpty](#isempty)|Проверяет, `CSimpleStringT` содержит ли объект символы.|
|[Ксимплестрингт:: Локкбуффер](#lockbuffer)|Отключает подсчет ссылок и защищает строку в буфере.|
|[Ксимплестрингт::P перераспределение](#preallocate)|Выделяет заданный объем памяти для символьного буфера.|
|[Ксимплестрингт:: Релеасебуффер](#releasebuffer)|Освобождает управление буфером, `GetBuffer`возвращенным.|
|[Ксимплестрингт:: Релеасебуфферсетленгс](#releasebuffersetlength)|Освобождает управление буфером, `GetBuffer`возвращенным.|
|[Ксимплестрингт:: SetAt](#setat)|Задает символ в заданной позиции.|
|[Ксимплестрингт:: Сетманажер](#setmanager)|Задает диспетчер `CSimpleStringT` памяти объекта.|
|[Ксимплестрингт:: SetString](#setstring)|Задает строку `CSimpleStringT` объекта.|
|[Ксимплестрингт:: StringLength](#stringlength)|Возвращает число символов в указанной строке.|
|[Ксимплестрингт:: TRUNCATE](#truncate)|Усекает строку до указанной длины.|
|[Ксимплестрингт:: Унлоккбуффер](#unlockbuffer)|Включает подсчет ссылок и освобождает строку в буфере.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Ксимплестрингт:: operator ПККССТР](#operator_pcxstr)|Прямой доступ к символам, хранящимся в `CSimpleStringT` объекте, в виде строки в стиле C.|
|[Ксимплестрингт:: operator\[\]](#operator_at)|Возвращает символ в заданной позиции — подстановку оператора для `GetAt`.|
|[Ксимплестрингт:: operator + =](#operator_add_eq)|Сцепляет новую строку до конца существующей строки.|
|[Ксимплестрингт:: operator =](#operator_eq)|Присваивает новое значение `CSimpleStringT` объекту.|

### <a name="remarks"></a>Примечания

`CSimpleStringT`является базовым классом для различных строковых классов, поддерживаемых визуальным C++объектом. Он обеспечивает минимальную поддержку управления памятью строкового объекта и базовых операций с буфером. Дополнительные сведения о строковых объектах см. в разделе [класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="requirements"></a>Требования

**Заголовок:** атлсимпстр. h

## <a name="append"></a>Ксимплестрингт:: Append

Добавляет объект к существующему `CSimpleStringT`объекту. `CSimpleStringT`

### <a name="syntax"></a>Синтаксис

```
void Append(const CSimpleStringT& strSrc);
void Append(PCXSTR pszSrc, int nLength);
void Append(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Параметры

*стрсрк*<br/>
Добавляемый `CSimpleStringT` объект.

*псзсрк*<br/>
Указатель на строку, содержащую символы, которые необходимо добавить.

*нленгс*<br/>
Количество добавляемых знаков.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы добавить `CSimpleStringT` существующий объект в `CSimpleStringT` другой объект.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::Append`.

```cpp
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

##  <a name="appendchar"></a>Ксимплестрингт:: Аппендчар

Добавляет символ к существующему `CSimpleStringT` объекту.

### <a name="syntax"></a>Синтаксис

```
void AppendChar(XCHAR ch);
```

#### <a name="parameters"></a>Параметры

*ch*<br/>
Добавляемый символ

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы добавить указанный символ в конец существующего `CSimpleStringT` объекта.

##  <a name="copychars"></a>Ксимплестрингт:: Копичарс

Копирует символ или символы в `CSimpleStringT` объект.

### <a name="syntax"></a>Синтаксис

```
static void CopyChars(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Параметры

*пчдест*<br/>
Указатель на символьную строку.

*пчсрк*<br/>
Указатель на строку, содержащую копируемые символы.

*типы nChar*<br/>
Число *пчсрк* символов для копирования.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы скопировать символы из *пчсрк* в строку *пчдест* .

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::CopyChars`.

```cpp
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```

##  <a name="copycharsoverlapped"></a>Ксимплестрингт:: Копичарсоверлаппед

Копирует символ или символы в `CSimpleStringT` объект.

### <a name="syntax"></a>Синтаксис

```
static void CopyCharsOverlapped(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Параметры

*пчдест*<br/>
Указатель на символьную строку.

*пчсрк*<br/>
Указатель на строку, содержащую копируемые символы.

*типы nChar*<br/>
Число *пчсрк* символов для копирования.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы скопировать символы из *пчсрк* в строку *пчдест* . В отличие `CopyChars`от `CopyCharsOverlapped` , предоставляет надежный метод для копирования из символьных буферов, которые могут быть перекрывающиеся.

### <a name="example"></a>Пример

См. пример для [ксимплестрингт:: копичарс](#copychars)или исходный код для `CSimpleStringT::SetString` (находится в атлсимпстр. h).

##  <a name="ctor"></a>Ксимплестрингт:: Ксимплестрингт

Создает объект `CSimpleStringT`.

### <a name="syntax"></a>Синтаксис

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr);
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr);
CSimpleStringT(const CSimpleStringT& strSrc);
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw();
```

#### <a name="parameters"></a>Параметры

*стрсрк*<br/>
Существующий `CSimpleStringT` объект, который будет скопирован в этот `CSimpleStringT` объект.

*пчсрк*<br/>
Указатель на массив символов длины *нленгс*, а не NULL.

*псзсрк*<br/>
Строка, завершающаяся нулем, для копирования в этот `CSimpleStringT` объект.

*нленгс*<br/>
Число символов в `pch`.

*пстрингмгр*<br/>
Указатель на диспетчер `CSimpleStringT` памяти объекта. Дополнительные сведения о `IAtlStringMgr` и управлении памятью для `CSimpleStringT`см. в разделе [Управление памятью и CStringT](../memory-management-with-cstringt.md).

### <a name="remarks"></a>Примечания

Создайте новый `CSimpleStringT` объект. Поскольку конструкторы копируют входные данные в новое выделенное хранилище, могут возникнуть исключения памяти.

### <a name="example"></a>Пример

В следующем примере показано использование `CSimpleStringT::CSimpleStringT` с помощью **определения типа** `CSimpleString`ATL. `CSimpleString`— Это часто используемая специализация шаблона `CSimpleStringT`класса.

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

##  <a name="empty"></a>Ксимплестрингт:: Empty

Делает этот `CSimpleStringT` объект пустой строкой и освобождает память соответствующим образом.

### <a name="syntax"></a>Синтаксис

```
void Empty() throw();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в [разделе строки: Очистка](../cstring-exception-cleanup.md)исключения CString.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::Empty`.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

##  <a name="freeextra"></a>Ксимплестрингт:: Фриекстра

Освобождает все дополнительные памяти, которые ранее были выделены строкой, но больше не нужны.

### <a name="syntax"></a>Синтаксис

```
void FreeExtra();
```

### <a name="remarks"></a>Примечания

Это должно уменьшить издержки памяти, потребляемые строковым объектом. Метод перераспределяет буфер до точной длины, возвращаемой методом [DATALENGTH](#getlength).

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

Выходные данные этого примера выглядят следующим образом:

```Output
Alloc length is 1031, String length is 1024
Alloc length is 1031, String length is 15
Alloc length is 15, String length is 15
```

##  <a name="getalloclength"></a>Ксимплестрингт:: Жеталлокленгс

Извлекает выделенную длину `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```
int GetAllocLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Количество символов, выделенных для данного объекта.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы определить количество символов, выделенных `CSimpleStringT` для данного объекта. Пример вызова этой функции см. в разделе [фриекстра](#freeextra) .

##  <a name="getat"></a>Ксимплестрингт:: GetAt

Возвращает один символ из `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```
XCHAR GetAt(int iChar) const;
```

#### <a name="parameters"></a>Параметры

*ичар*<br/>
Отсчитываемый от нуля индекс символа в `CSimpleStringT` объекте. Параметр *ичар* должен быть больше или равен 0 и меньше значения, возвращаемого методом [DATALENGTH](#getlength). В противном случае создаст исключение. `GetAt`

### <a name="return-value"></a>Возвращаемое значение

Значение `XCHAR` типа, содержащее символ в указанной позиции в строке.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить один символ, заданный параметром *ичар*. Оператор перегруженного индекса ( **[]** ) является удобным псевдонимом для `GetAt`. Конечный символ NULL можно устранить без создания исключения с помощью `GetAt`. Однако он не учитывается `GetLength`, а возвращаемое значение равно 0.

### <a name="example"></a>Пример

В следующем примере показано, как использовать `CSimpleStringT::GetAt`.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

##  <a name="getbuffer"></a>Ксимплестрингт:: buffer

Возвращает указатель на внутренний буфер символов для `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```
PXSTR GetBuffer(int nMinBufferLength);
PXSTR GetBuffer();
```

#### <a name="parameters"></a>Параметры

*нминбуфферленгс*<br/>
Минимальное число символов, которое может хранить буфер символов. Это значение не включает пробел для нулевого терминатора.

Если *нминбуфферленгс* больше, чем длина текущего буфера, `GetBuffer` уничтожает текущий буфер, заменяет его буфером запрошенного размера и сбрасывает значение счетчика ссылок на объект равным нулю. Если ранее вы вызвали [локкбуффер](#lockbuffer) в этом буфере, блокировка буфера будет утрачена.

### <a name="return-value"></a>Возвращаемое значение

`PXSTR` Указатель на символьный буфер (заканчивающийся нулем).

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы вернуть содержимое `CSimpleStringT` буфера объекта. Возвращаемое `PXSTR` значение не является константой и, следовательно, допускает непосредственное `CSimpleStringT` изменение содержимого.

Если для изменения содержимого строки используется указатель `GetBuffer` , возвращенный методом, необходимо вызвать метод [релеасебуффер](#releasebuffer) , прежде чем использовать другие `CSimpleStringT` методы члена.

Адрес, возвращенный `GetBuffer` методом, может быть недействительным после `ReleaseBuffer` вызова, `CSimpleStringT` так как `CSimpleStringT` дополнительные операции могут привести к повторному выделению буфера. Если не изменить длину объекта `CSimpleStringT`, буфер не будет перераспределен.

Буферная память автоматически освобождается при `CSimpleStringT` уничтожении объекта.

Если вы следите за длиной строки самостоятельно, не следует добавлять завершающий нуль символ. Однако необходимо указать конечную длину строки при освобождении буфера с помощью `ReleaseBuffer`. При добавлении завершающего нуль-символа необходимо передать значение 1 (по умолчанию) для длины. `ReleaseBuffer`затем определяет длину буфера.

Если недостаточно памяти для удовлетворения `GetBuffer` запроса, этот метод создает исключение CMemoryException *.

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

##  <a name="getbuffersetlength"></a>Ксимплестрингт:: Жетбуфферсетленгс

Возвращает указатель на внутренний буфер символов для `CSimpleStringT` объекта, усекает или увеличивая его длину, если это необходимо, чтобы точно соответствовать длине, указанной в *нленгс*.

### <a name="syntax"></a>Синтаксис

```
PXSTR GetBufferSetLength(int nLength);
```

#### <a name="parameters"></a>Параметры

*нленгс*<br/>
Точный размер `CSimpleStringT` символьного буфера в символах.

### <a name="return-value"></a>Возвращаемое значение

`PXSTR` Указатель на символьный буфер (заканчивающийся нулем).

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить указанную длину внутреннего буфера `CSimpleStringT` объекта. Возвращаемый `PXSTR` указатель не является **константой** и, таким образом, `CSimpleStringT` допускает непосредственное изменение содержимого.

При использовании указателя, возвращенного функцией [жетбуфферсетленгс](#getbuffersetlength) для изменения содержимого строки, вызовите `ReleaseBuffer` метод, чтобы обновить внутреннее состояние `CsimpleStringT` перед использованием любых других `CSimpleStringT` методов.

Адрес, возвращенный `GetBufferSetLength` методом, может быть недействительным после `ReleaseBuffer` вызова, `CSimpleStringT` так как `CSimpleStringT` дополнительные операции могут привести к повторному выделению буфера. Если не изменить длину объекта `CSimpleStringT`, буфер не переназначится.

Буферная память автоматически освобождается при `CSimpleStringT` уничтожении объекта.

Если вы следите за длиной строки самостоятельно, не добавляйте завершающий нуль символ. Необходимо указать конечную длину строки при освобождении буфера с помощью `ReleaseBuffer`. `ReleaseBuffer`Если при вызове `strlen` применяет завершающий нуль-символ (значение по умолчанию) для `ReleaseBuffer`длины, а `ReleaseBuffer` в буфере — для определения его длины.

Дополнительные сведения о подсчете ссылок см. в следующих статьях:

- [Управление жизненным циклом объектов с помощью подсчета ссылок](/windows/win32/com/managing-object-lifetimes-through-reference-counting) в Windows SDK.

- [Реализация подсчета ссылок](/windows/win32/com/implementing-reference-counting) в Windows SDK.

- [Правила управления счетчиками ссылок](/windows/win32/com/rules-for-managing-reference-counts) в Windows SDK.

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

##  <a name="getlength"></a>Ксимплестрингт:: DATALENGTH

Возвращает количество символов в `CSimpleStringT` объекте.

### <a name="syntax"></a>Синтаксис

```
int GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Число символов в строке.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить количество символов в объекте. Число не включает терминатор null.

Для многобайтовых кодировок (MBCS) `GetLength` подсчитывает каждый 8-разрядный символ, то есть ведущий и младший байт в одном многобайтовой кодировке считаются двумя байтами. Пример вызова этой функции см. в разделе [фриекстра](#freeextra) .

##  <a name="getmanager"></a>Ксимплестрингт:: Manage

Возвращает диспетчер `CSimpleStringT` памяти объекта.

### <a name="syntax"></a>Синтаксис

```
IAtlStringMgr* GetManager() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на диспетчер памяти для `CSimpleStringT` объекта.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить диспетчер памяти, используемый `CSimpleStringT` объектом. Дополнительные сведения о диспетчерах памяти и строковых объектах см. в разделе [Управление памятью и CStringT](../memory-management-with-cstringt.md).

##  <a name="getstring"></a>Ксимплестрингт:: GetString

Извлекает строку символов.

### <a name="syntax"></a>Синтаксис

```
PCXSTR GetString() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку символов, завершающуюся нулем.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить строку символов, связанную с `CSimpleStringT` объектом.

> [!NOTE]
>  Возвращаемый `PCXSTR` указатель является **константой** и не `CSimpleStringT` допускает прямого изменения содержимого.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::GetString`.

```cpp
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

##  <a name="isempty"></a>Ксимплестрингт:: IsEmpty

`CSimpleStringT` Проверяет объект на наличие пустого условия.

### <a name="syntax"></a>Синтаксис

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, `CSimpleStringT` если объект имеет нулевую длину; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы определить, содержит ли объект пустую строку.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::IsEmpty`.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

##  <a name="lockbuffer"></a>Ксимплестрингт:: Локкбуффер

Отключает подсчет ссылок и защищает строку в буфере.

### <a name="syntax"></a>Синтаксис

```
PXSTR LockBuffer();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CSimpleStringT` объект или строку, завершающуюся нулем.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы заблокировать буфер `CSimpleStringT` объекта. Вызывая `LockBuffer`метод, вы создаете копию строки со значением-1 для счетчика ссылок. Если значение счетчика ссылок равно-1, то строка в буфере считается в состоянии "заблокировано". В заблокированном состоянии строка защищена двумя способами:

- Никакая другая строка не может получить ссылку на данные в заблокированной строке, даже если эта строка назначена заблокированной строке.

- Заблокированная строка никогда не будет ссылаться на другую строку, даже если другая строка копируется в Заблокированную строку.

Заключив строку в буфер, вы гарантируете, что монопольное хранение строки в буфере останется неизменным.

После завершения работы `LockBuffer`вызовите [унлоккбуффер](#unlockbuffer) , чтобы сбросить счетчик ссылок до 1.

> [!NOTE]
>  Если [вызвать метод](#getbuffer) DATALENGTH в заблокированном буфере и задать `GetBuffer` для параметра `nMinBufferLength` значение больше, чем длина текущего буфера, блокировка буфера будет утрачена. Такой вызов `GetBuffer` уничтожает текущий буфер, заменяет его буфером запрошенного размера и сбрасывает значение счетчика ссылок в ноль.

Дополнительные сведения о подсчете ссылок см. в следующих статьях:

- [Управление жизненным циклом объектов с помощью подсчета ссылок](/windows/win32/com/managing-object-lifetimes-through-reference-counting) в Windows SDK

- [Реализация подсчета ссылок](/windows/win32/com/implementing-reference-counting) в Windows SDK

- [Правила управления счетчиками ссылок](/windows/win32/com/rules-for-managing-reference-counts) в Windows SDK

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

##  <a name="operator_at"></a>Ксимплестрингт:: operator\[\]

Вызывайте эту функцию для доступа к одному символу массива символов.

### <a name="syntax"></a>Синтаксис

```
XCHAR operator[](int iChar) const;
```

#### <a name="parameters"></a>Параметры

*ичар*<br/>
Отсчитываемый от нуля индекс символа в строке.

### <a name="remarks"></a>Примечания

Оператор перегруженного индекса ( **[]** ) возвращает один символ, заданный индексом, начинающимся с нуля, в *ичар*. Этот оператор удобен для замены функции-члена [GetAt](#getat) .

> [!NOTE]
>  Оператор "индекс" ( **[]** ) можно использовать для получения значения символа в `CSimpleStringT`, но его нельзя использовать для изменения значения символа в. `CSimpleStringT`

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::operator []`.

```cpp
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="operator_at"></a>Ксимплестрингт:: operator\[\]

Вызывайте эту функцию для доступа к одному символу массива символов.

### <a name="syntax"></a>Синтаксис

```
XCHAR operator[](int iChar) const;
```

### <a name="parameters"></a>Параметры

*ичар*<br/>
Отсчитываемый от нуля индекс символа в строке.

### <a name="remarks"></a>Примечания

Оператор перегруженного индекса ( **[]** ) возвращает один символ, заданный индексом, начинающимся с нуля, в *ичар*. Этот оператор удобен для замены функции-члена [GetAt](#getat) .

> [!NOTE]
>  Оператор "индекс" ( **[]** ) можно использовать для получения значения символа в `CSimpleStringT`, но его нельзя использовать для изменения значения символа в. `CSimpleStringT`

##  <a name="operator_add_eq"></a>Ксимплестрингт:: operator + =

Присоединяет новую строку или символ к концу существующей строки.

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

*псзсрк*<br/>
Указатель на строку, завершающуюся нулем.

*стрсрк*<br/>
Указатель на существующий `CSimpleStringT` объект.

*ch*<br/>
Символ значение для добавления.

### <a name="remarks"></a>Примечания

Оператор принимает другой `CSimpleStringT` объект или символ. Обратите внимание, что при использовании этого оператора объединения могут возникать исключения памяти, так как для символов, добавляемых в `CSimpleStringT` этот объект, может быть выделено новое хранилище.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::operator +=`.

```cpp
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

##  <a name="operator_eq"></a>Ксимплестрингт:: operator =

Присваивает новое значение `CSimpleStringT` объекту.

### <a name="syntax"></a>Синтаксис

```
CSimpleStringT& operator =(PCXSTR pszSrc);
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```

#### <a name="parameters"></a>Параметры

*псзсрк*<br/>
Указатель на строку, завершающуюся нулем.

*стрсрк*<br/>
Указатель на существующий `CSimpleStringT` объект.

### <a name="remarks"></a>Примечания

Если строка назначения (левая часть) уже достаточно велика для хранения новых данных, выделение памяти не выполняется. Обратите внимание, что исключения памяти могут возникать при использовании оператора присваивания, поскольку для хранения результирующего `CSimpleStringT` объекта часто выделяется новое хранилище.

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

##  <a name="operator_pcxstr"></a>Ксимплестрингт:: operator ПККССТР

Прямой доступ к символам, хранящимся в `CSimpleStringT` объекте, в виде строки в стиле C.

### <a name="syntax"></a>Синтаксис

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель символа на данные строки.

### <a name="remarks"></a>Примечания

Символы не копируются; возвращается только указатель. Будьте внимательны с этим оператором. Если изменить `CString` объект после получения указателя на символ, может быть вызвано перераспределение памяти, которое сделает указатель недействительным.

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

##  <a name="pcxstr"></a>Ксимплестрингт::P ККССТР

Указатель на константную строку.

### <a name="syntax"></a>Синтаксис

```
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;
```

##  <a name="preallocate"></a>Ксимплестрингт::P перераспределение

Выделяет заданный объем байтов для `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```
void Preallocate( int nLength);
```

#### <a name="parameters"></a>Параметры

*нленгс*<br/>
Точный размер `CSimpleStringT` символьного буфера в символах.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы выделить конкретный размер буфера для `CSimpleStringT` объекта.

`CSimpleStringT`создает исключение STATUS_NO_MEMORY, если не удается выделить место для символьного буфера. По умолчанию выделение памяти выполняется функциями `HeapAlloc` API Win32 или. `HeapReAlloc`

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::Preallocate`.

```cpp
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```

##  <a name="pxstr"></a>Ксимплестрингт::P КССТР

Указатель на строку.

### <a name="syntax"></a>Синтаксис

```
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;
```

##  <a name="releasebuffer"></a>Ксимплестрингт:: Релеасебуффер

Освобождает управление буфером, выделенным методом " [buffer](#getbuffer)".

### <a name="syntax"></a>Синтаксис

```
void ReleaseBuffer(int nNewLength = -1);
```

#### <a name="parameters"></a>Параметры

*нневленгс*<br/>
Новая длина строки в символах без учета терминатора null. Если строка завершается нулем, значение по умолчанию-1 задает `CSimpleStringT` размер, равный текущей длине строки.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы перераспределить или освободить буфер строкового объекта. Если известно, что строка в буфере завершается нулем, аргумент *нневленгс* можно опустить. Если строка не завершается нулем, используйте *нневленгс* , чтобы указать ее длину. Адрес, возвращенный методом [onbuffer](#getbuffer) , является недопустимым `ReleaseBuffer` после вызова или `CSimpleStringT` любой другой операции.

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

##  <a name="releasebuffersetlength"></a>Ксимплестрингт:: Релеасебуфферсетленгс

Освобождает управление буфером, выделенным методом " [buffer](#getbuffer)".

### <a name="syntax"></a>Синтаксис

```
void ReleaseBufferSetLength(int nNewLength);
```

#### <a name="parameters"></a>Параметры

*нневленгс*<br/>
Длина освобожденной строки

### <a name="remarks"></a>Примечания

Эта функция функционально похожа на [релеасебуффер](#releasebuffer) , за исключением того, что необходимо передать допустимую длину для объекта String.

##  <a name="setat"></a>Ксимплестрингт:: SetAt

Задает один символ из `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```
void SetAt(int iChar, XCHAR ch);
```

#### <a name="parameters"></a>Параметры

*ичар*<br/>
Отсчитываемый от нуля индекс символа в `CSimpleStringT` объекте. Параметр *ичар* должен быть больше или равен 0 и меньше значения, возвращаемого методом [DATALENGTH](#getlength).

*ch*<br/>
Новый символ.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы перезаписать символ, расположенный по адресу *ичар*. Этот метод не увеличит строку, если *ичар* превышает границы существующей строки.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::SetAt`.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

##  <a name="setmanager"></a>Ксимплестрингт:: Сетманажер

Указывает диспетчер `CSimpleStringT` памяти объекта.

### <a name="syntax"></a>Синтаксис

```
void SetManager(IAtlStringMgr* pStringMgr);
```

#### <a name="parameters"></a>Параметры

*пстрингмгр*<br/>
Указатель на новый диспетчер памяти.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы указать новый диспетчер памяти, используемый `CSimpleStringT` объектом. Дополнительные сведения о диспетчерах памяти и строковых объектах см. в разделе [Управление памятью и CStringT](../memory-management-with-cstringt.md).

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::SetManager`.

```cpp
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

##  <a name="setstring"></a>Ксимплестрингт:: SetString

Задает строку `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```
void SetString(PCXSTR pszSrc, int nLength);
void SetString(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Параметры

*псзсрк*<br/>
Указатель на строку, завершающуюся нулем.

*нленгс*<br/>
Число символов в *псзсрк*.

### <a name="remarks"></a>Примечания

Скопируйте строку в `CSimpleStringT` объект. `SetString`перезаписывает более старые строковые данные в буфер.

Обе версии `SetString` проверяют, является ли *псзсрк* пустым указателем, и если это так, вызовите ошибку E_INVALIDARG.

Версия с одним параметром, `SetString` *псзсрк* , должна указывать на строку, завершающуюся нулем.

Версия `SetString` с двумя параметрами также ждет, что *псзсрк* является строкой, завершающейся нулем. В нем используется *нленгс* в качестве длины строки, если только в начале не встретится символ завершения null.

Версия `SetString` с двумя параметрами также проверяет, указывает ли *псзсрк* на расположение в текущем буфере в `CSimpleStringT`. В этом особом случае `SetString` использует функцию копирования в памяти, которая не перезаписывает строковые данные при копировании строковых данных обратно в буфер.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::SetString`.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```

##  <a name="stringlength"></a>Ксимплестрингт:: StringLength

Возвращает число символов в указанной строке.

### <a name="syntax"></a>Синтаксис

```
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```

#### <a name="parameters"></a>Параметры

*псз*<br/>
Указатель на строку, завершающуюся нулем.

### <a name="return-value"></a>Возвращаемое значение

Число символов в *ПСЗ*; не считая знак завершения null.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить количество символов в строке, на которую указывает *ПСЗ*.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CSimpleStringT::StringLength`.

```cpp
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
```

##  <a name="truncate"></a>Ксимплестрингт:: TRUNCATE

Усекает строку до новой длины.

### <a name="syntax"></a>Синтаксис

```
void Truncate(int nNewLength);
```

#### <a name="parameters"></a>Параметры

*нневленгс*<br/>
Новая длина строки.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы усечь содержимое строки до новой длины.

> [!NOTE]
>  Это не влияет на выделенную длину буфера. Сведения о том, как уменьшить или увеличить текущий буфер, см. в разделе [фриекстра](#freeextra) и предварительное [выделение](#preallocate).

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

##  <a name="unlockbuffer"></a>Ксимплестрингт:: Унлоккбуффер

Разблокирует буфер `CSimpleStringT` объекта.

### <a name="syntax"></a>Синтаксис

```
void UnlockBuffer() throw();
```

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы сбросить счетчик ссылок строки до 1.

Деструктор автоматически вызывает метод `UnlockBuffer` , чтобы гарантировать, что буфер не блокируется при вызове деструктора. `CSimpleStringT` Пример этого метода см. в разделе [локкбуффер](#lockbuffer).

##  <a name="dtor"></a>Ксимплестрингт:: ~ Ксимплестрингт

Уничтожает объект `CSimpleStringT`.

### <a name="syntax"></a>Синтаксис

```
~CSimpleStringT() throw();
```

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы `CSimpleStringT` уничтожить объект.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
