---
title: '**`CStringT`** См'
description: Справочник по API для класса Microsoft ATL **`CStringT`**
ms.date: 11/13/2020
f1_keywords:
- CStringT
- ATLSTR/ATL::CStringT
- ATLSTR/ATL::CStringT::CStringT
- ATLSTR/ATL::CStringT::AllocSysString
- ATLSTR/ATL::CStringT::AnsiToOem
- ATLSTR/ATL::CStringT::AppendFormat
- ATLSTR/ATL::CStringT::Collate
- ATLSTR/ATL::CStringT::CollateNoCase
- ATLSTR/ATL::CStringT::Compare
- ATLSTR/ATL::CStringT::CompareNoCase
- ATLSTR/ATL::CStringT::Delete
- ATLSTR/ATL::CStringT::Find
- ATLSTR/ATL::CStringT::FindOneOf
- ATLSTR/ATL::CStringT::Format
- ATLSTR/ATL::CStringT::FormatMessage
- ATLSTR/ATL::CStringT::FormatMessageV
- ATLSTR/ATL::CStringT::FormatV
- ATLSTR/ATL::CStringT::GetEnvironmentVariable
- ATLSTR/ATL::CStringT::Insert
- ATLSTR/ATL::CStringT::Left
- ATLSTR/ATL::CStringT::LoadString
- ATLSTR/ATL::CStringT::MakeLower
- ATLSTR/ATL::CStringT::MakeReverse
- ATLSTR/ATL::CStringT::MakeUpper
- ATLSTR/ATL::CStringT::Mid
- ATLSTR/ATL::CStringT::OemToAnsi
- ATLSTR/ATL::CStringT::Remove
- ATLSTR/ATL::CStringT::Replace
- ATLSTR/ATL::CStringT::ReverseFind
- ATLSTR/ATL::CStringT::Right
- ATLSTR/ATL::CStringT::SetSysString
- ATLSTR/ATL::CStringT::SpanExcluding
- ATLSTR/ATL::CStringT::SpanIncluding
- ATLSTR/ATL::CStringT::Tokenize
- ATLSTR/ATL::CStringT::Trim
- ATLSTR/ATL::CStringT::TrimLeft
- ATLSTR/ATL::CStringT::TrimRight
- CSTRINGT/CStringT
- CSTRINGT/CStringT::CStringT
- CSTRINGT/CStringT::AllocSysString
- CSTRINGT/CStringT::AnsiToOem
- CSTRINGT/CStringT::AppendFormat
- CSTRINGT/CStringT::Collate
- CSTRINGT/CStringT::CollateNoCase
- CSTRINGT/CStringT::Compare
- CSTRINGT/CStringT::CompareNoCase
- CSTRINGT/CStringT::Delete
- CSTRINGT/CStringT::Find
- CSTRINGT/CStringT::FindOneOf
- CSTRINGT/CStringT::Format
- CSTRINGT/CStringT::FormatMessage
- CSTRINGT/CStringT::FormatMessageV
- CSTRINGT/CStringT::FormatV
- CSTRINGT/CStringT::GetEnvironmentVariable
- CSTRINGT/CStringT::Insert
- CSTRINGT/CStringT::Left
- CSTRINGT/CStringT::LoadString
- CSTRINGT/CStringT::MakeLower
- CSTRINGT/CStringT::MakeReverse
- CSTRINGT/CStringT::MakeUpper
- CSTRINGT/CStringT::Mid
- CSTRINGT/CStringT::OemToAnsi
- CSTRINGT/CStringT::Remove
- CSTRINGT/CStringT::Replace
- CSTRINGT/CStringT::ReverseFind
- CSTRINGT/CStringT::Right
- CSTRINGT/CStringT::SetSysString
- CSTRINGT/CStringT::SpanExcluding
- CSTRINGT/CStringT::SpanIncluding
- CSTRINGT/CStringT::Tokenize
- CSTRINGT/CStringT::Trim
- CSTRINGT/CStringT::TrimLeft
- CSTRINGT/CStringT::TrimRight
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.openlocfilehash: 80ea59b5f50fc9f430aa588a37e73d4526e3fd94
ms.sourcegitcommit: 07408df5f4b2cbf070d9bb4bb40d821bfd5d8a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "94703515"
---
# <a name="cstringt-class"></a>Класс CStringT

Этот класс представляет **`CStringT`** объект.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename BaseType, class StringTraits>
class CStringT :
    public CSimpleStringT<BaseType,
        _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>::c_bIsMFCDLLTraits>
```

#### <a name="parameters"></a>Параметры

*`BaseType`*\
Символьный тип класса String. Может применяться один из перечисленных ниже типов.

- **`char`** (для строк символов ANSI).

- **`wchar_t`** (для символьных строк Юникода).

- **`TCHAR`** (для символьных строк ANSI и Юникод).

*`StringTraits`*\
Определяет, требуется ли для класса строк поддержка библиотеки C Run-Time (CRT) и где находятся строковые ресурсы. Может применяться один из перечисленных ниже типов.

- **`StrTraitATL<wchar_t | char | TCHAR, ChTraitsCRT<wchar_t | char | TCHAR>>`**

   Класс требует поддержки CRT и ищет строки ресурсов в модуле, указанном `m_hInstResource` (членом класса модуля приложения).

- **`StrTraitATL<wchar_t | char | TCHAR, ChTraitsOS<wchar_t | char |TCHAR>>`**

   Класс не требует поддержки CRT и ищет строки ресурсов в модуле, указанном `m_hInstResource` (членом класса модуля приложения).

- **`StrTraitMFC<wchar_t | char | TCHAR, ChTraitsCRT<wchar_t | char | TCHAR>>`**

   Класс требует поддержки CRT и ищет строки ресурсов с помощью стандартного алгоритма поиска MFC.

- **`StrTraitMFC<wchar_t | char | TCHAR, ChTraitsOS<wchar_t | char | TCHAR>>`**

   Класс не требует поддержки CRT и ищет строки ресурсов с помощью стандартного алгоритма поиска MFC.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[`CStringT::CStringT`](#cstringt)|Конструирует **`CStringT`** объект различными способами.|
|[`CStringT::~CStringT`](#_dtorcstringt)|Уничтожает **`CStringT`** объект.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[`CStringT::AllocSysString`](#allocsysstring)|Выделяет `BSTR` **`CStringT`** данные из данных.|
|[`CStringT::AnsiToOem`](#ansitooem)|Выполняет преобразование на месте из набора символов ANSI в набор символов OEM.|
|[`CStringT::AppendFormat`](#appendformat)|Добавляет форматированные данные к существующему **`CStringT`** объекту.|
|[`CStringT::Collate`](#collate)|Сравнивает две строки (с учетом регистра, использует сведения, относящиеся к языку).|
|[`CStringT::CollateNoCase`](#collatenocase)|Сравнивает две строки (без учета регистра, использует сведения, зависящие от локали).|
|[`CStringT::Compare`](#compare)|Сравнивает две строки (с учетом регистра).|
|[`CStringT::CompareNoCase`](#comparenocase)|Сравнивает две строки (без учета регистра).|
|[`CStringT::Delete`](#delete)|Удаляет символ или символы из строки.|
|[`CStringT::Find`](#find)|Находит символ или подстроку в более длинной строке.|
|[`CStringT::FindOneOf`](#findoneof)|Находит первый соответствующий символ из набора.|
|[`CStringT::Format`](#format)|Форматирует строку как `sprintf` есть.|
|[`CStringT::FormatMessage`](#formatmessage)|Форматирует строку сообщения.|
|[`CStringT::FormatMessageV`](#formatmessagev)|Форматирует строку сообщения с помощью переменного списка аргументов.|
|[`CStringT::FormatV`](#formatv)|Форматирует строку, используя переменный список аргументов.|
|[`CStringT::GetEnvironmentVariable`](#getenvironmentvariable)|Присваивает строке значение указанной переменной среды.|
|[`CStringT::Insert`](#insert)|Вставляет в строку один символ или подстроку с заданным индексом.|
|[`CStringT::Left`](#left)|Извлекает левую часть строки.|
|[`CStringT::LoadString`](#loadstring)|Загружает существующий **`CStringT`** объект из ресурса Windows.|
|[`CStringT::MakeLower`](#makelower)|Преобразует все символы в этой строке в символы нижнего регистра.|
|[`CStringT::MakeReverse`](#makereverse)|Изменяет направление строки на противоположную.|
|[`CStringT::MakeUpper`](#makeupper)|Преобразует все символы в этой строке в символы верхнего регистра.|
|[`CStringT::Mid`](#mid)|Извлекает среднюю часть строки.|
|[`CStringT::OemToAnsi`](#oemtoansi)|Выполняет преобразование на месте из набора символов OEM в кодировку ANSI.|
|[`CStringT::Remove`](#remove)|Удаляет указанные символы из строки.|
|[`CStringT::Replace`](#replace)|Заменяет указанные символы другими символами.|
|[`CStringT::ReverseFind`](#reversefind)|Находит символ в более длинной строке; начинается с конца.|
|[`CStringT::Right`](#right)|Извлекает правую часть строки.|
|[`CStringT::SetSysString`](#setsysstring)|Устанавливает существующий `BSTR` объект с данными из **`CStringT`** объекта.|
|[`CStringT::SpanExcluding`](#spanexcluding)|Извлекает из строки символы, начиная с первого символа, которые не входят в набор символов, определяемый параметром `pszCharSet` .|
|[`CStringT::SpanIncluding`](#spanincluding)|Извлекает подстроку, содержащую только символы в наборе.|
|[`CStringT::Tokenize`](#tokenize)|Извлекает указанные токены в целевой строке.|
|[`CStringT::Trim`](#trim)|Обрезает все начальные и конечные символы пробела из строки.|
|[`CStringT::TrimLeft`](#trimleft)|Обрезает начальные символы пробела из строки.|
|[`CStringT::TrimRight`](#trimright)|Обрезает пробелы в конце строки.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[`CStringT::operator =`](#operator_eq)|Присваивает новое значение **`CStringT`** объекту.|
|[`CStringT::operator +`](#operator_add)|Сцепляет две строки, символ и строку.|
|[`CStringT::operator +=`](#operator_add_eq)|Сцепляет новую строку до конца существующей строки.|
|[`CStringT::operator ==`](#operator_eq_eq)|Определяет логическую равенство двух строк.|
|[`CStringT::operator !=`](#operator_neq)|Определяет, являются ли две строки логически равными.|
|[`CStringT::operator <`](#operator_lt)|Определяет, является ли строка в левой части оператора меньше, чем строка с правой стороны.|
|[`CStringT::operator >`](#operator_gt)|Определяет, что строка в левой части оператора больше, чем строка с правой стороны.|
|[`CStringT::operator <=`](#operator_lt_eq)|Определяет, является ли строка в левой части оператора меньше или равна строке в правой части.|
|[`CStringT::operator >=`](#operator_gt_eq)|Определяет, является ли строка в левой части оператора больше или равна строке в правой части.|

## <a name="remarks"></a>Комментарии

**`CStringT`** наследует от [класса ксимплестрингт](../../atl-mfc-shared/reference/csimplestringt-class.md). Дополнительные функции, такие как обработка символов, упорядочение и поиск, реализуются с помощью **`CStringT`** .

> [!NOTE]
> **`CStringT`** объекты способны создавать исключения. Это происходит, когда **`CStringT`** по какой-либо причине объекту не хватает памяти.

**`CStringT`** Объект состоит из последовательности символов с переменной длиной. **`CStringT`** предоставляет функции и операторы, используя синтаксис, аналогичный базовому. Операторы объединения и сравнения, а также упрощенное управление памятью упрощают **`CStringT`** использование объектов, чем обычные массивы символов.

> [!NOTE]
> Несмотря на то **`CStringT`** , что можно создавать экземпляры, содержащие внедренные символы NULL, для них рекомендуется использовать. Вызов методов и операторов для **`CStringT`** объектов, содержащих внедренные символы NULL, может привести к непредвиденным результатам.

Используя разные сочетания `BaseType` `StringTraits` параметров и, **`CStringT`** объекты могут поступать в следующие типы, которые были предопределены библиотеками ATL.

При использовании в приложении ATL:

`CString`, `CStringA` и `CStringW` экспортируются из библиотеки DLL MFC (MFC90.DLL), никогда не из пользовательских библиотек DLL. Это делается для предотвращения **`CStringT`** неоднократного определения.

> [!NOTE]
> Если в коде содержится обходной путь для ошибок компоновщика, описанный в разделе [Экспорт строковых классов с помощью CStringT](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md), следует удалить этот код. Он больше не требуется.

В приложениях на основе MFC доступны следующие типы строк:

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CStringA`|Строка типа символов ANSI с поддержкой CRT.|
|`CStringW`|Строка типа символов Юникода с поддержкой CRT.|
|`CString`|Типы символов ANSI и Юникод с поддержкой CRT.|

В проектах, где определено, доступны следующие типы строк `ATL_CSTRING_NO_CRT` :

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CAtlStringA`|Строка типа символов ANSI без поддержки CRT.|
|`CAtlStringW`|Строка типа символов Юникода без поддержки CRT.|
|`CAtlString`|Типы символов ANSI и Юникод без поддержки CRT.|

В проектах, где не определено, доступны следующие типы строк `ATL_CSTRING_NO_CRT` :

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CAtlStringA`|Строка типа символов ANSI с поддержкой CRT.|
|`CAtlStringW`|Строка типа символов Юникода с поддержкой CRT.|
|`CAtlString`|Типы символов ANSI и Юникод с поддержкой CRT.|

`CString` объекты также имеют следующие характеристики.

- **`CStringT`** объекты могут увеличиваться из-за операций объединения.

- **`CStringT`** объекты следуют за семантикой значений. Представьте себе **`CStringT`** объект как фактическую строку, а не указатель на строку.

- Можно свободно заменять **`CStringT`** объекты для `PCXSTR` аргументов функции.

- Пользовательское управление памятью для буферов строк. Дополнительные сведения см. в разделе [Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="cstringt-predefined-types"></a>Предопределенные типы CStringT

Поскольку **`CStringT`** использует аргумент шаблона для определения типа символа ( [wchar_t](../../c-runtime-library/standard-types.md) или [char](../../c-runtime-library/standard-types.md)), типы параметров метода могут быть сложными в моменты времени. Для упрощения этой проблемы набор предопределенных типов определяется и используется во всем **`CStringT`** классе. В следующей таблице перечислены различные типы.

|Имя|Описание|
|----------|-----------------|
|`XCHAR`|Одиночный символ ( **`wchar_t`** или **`char`** ) с тем же типом символов, что и у **`CStringT`** объекта.|
|`YCHAR`|Один символ ( **`wchar_t`** или **`char`** ) с противоположным типом символа в качестве **`CStringT`** объекта.|
|`PXSTR`|Указатель на символьную строку ( **`wchar_t`** или **`char`** ) с тем же типом символов, что и в объекте * * * * * * * `CStringT` * *.|
|`PYSTR`|Указатель на символьную строку ( **`wchar_t`** или **`char`** ) с противоположным типом символа в качестве **`CStringT`** объекта.|
|`PCXSTR`|Указатель на **`const`** символьную строку ( **`wchar_t`** или **`char`** ) с тем же типом символов, что и у **`CStringT`** объекта.|
|`PCYSTR`|Указатель на **`const`** символьную строку ( **`wchar_t`** или **`char`** ) с противоположным типом символа в качестве **`CStringT`** объекта.|

> [!NOTE]
> Код, который ранее использовал недокументированные методы `CString` (например, `AssignCopy` ), должен быть заменен кодом, который использует приведенные ниже документированные методы **`CStringT`** (например, `GetBuffer` или `ReleaseBuffer` ). Эти методы наследуются от `CSimpleStringT` .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ксимплестрингт](../../atl-mfc-shared/reference/csimplestringt-class.md)

**`CStringT`**

## <a name="requirements"></a>Требования

|Заголовок|Назначение|
|------------|-------------|
|CStringT. h|Строковые объекты только MFC|
|atlstr. h|Объекты-строки, не относящиеся к MFC|

## <a name="cstringtallocsysstring"></a><a name="allocsysstring"></a> `CStringT::AllocSysString`

Выделяет строку типа, совместимую с автоматизацией `BSTR` , и копирует в **`CStringT`** нее содержимое объекта, включая завершающий нуль-символ.

```cpp
BSTR AllocSysString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Вновь выделенная строка.

### <a name="remarks"></a>Комментарии

В программах MFC создается [класс CMemoryException](../../mfc/reference/cmemoryexception-class.md) , если недостаточно памяти. В программах ATL создается исключение [катлексцептион](../../atl/reference/catlexception-class.md) . Эта функция обычно используется для возврата строк для автоматизации.

Как правило, если эта строка передается в COM-функцию в качестве `[in]` параметра, то для этого необходимо, чтобы вызывающий объект освободит строку. Это можно сделать с помощью [сисфристринг](/windows/win32/api/oleauto/nf-oleauto-sysfreestring), как описано в Windows SDK. Дополнительные сведения см. в разделе [выделение и освобождение памяти для BSTR](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).

Дополнительные сведения о функциях выделения OLE в Windows см. в разделе [сисаллокстринг](/windows/win32/api/oleauto/nf-oleauto-sysallocstring) в Windows SDK.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CStringT::AllocSysString`.

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

## <a name="cstringtansitooem"></a><a name="ansitooem"></a> `CStringT::AnsiToOem`

Преобразует все символы в этом **`CStringT`** объекте из набора символов ANSI в набор символов OEM.

```cpp
void AnsiToOem();
```

### <a name="remarks"></a>Комментарии

Функция недоступна, если `_UNICODE` определен.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

## <a name="cstringtappendformat"></a><a name="appendformat"></a> `CStringT::AppendFormat`

Добавляет форматированные данные к существующему **`CStringT`** объекту.

```cpp
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>Параметры

*`pszFormat`*\
Строка управления форматированием.

*`nFormatID`*\
Строковый идентификатор ресурса, содержащий строку управления форматированием.

*`argument`*\
Необязательные аргументы.

### <a name="remarks"></a>Комментарии

Эта функция форматирует и добавляет ряд символов и значений в **`CStringT`** . Каждый необязательный аргумент (при его наличии) преобразуется и добавляется в соответствии с соответствующей спецификацией формата в *`pszFormat`* или из строкового ресурса, определенного параметром *`nFormatID`* .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

## <a name="cstringtcollate"></a><a name="collate"></a> `CStringT::Collate`

Сравнивает две строки с помощью функции Generic-Text `_tcscoll` .

```cpp
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*`psz`*\
Другая строка, используемая для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны, < 0, если этот **`CStringT`** объект меньше *`psz`* , или > 0, если этот **`CStringT`** объект больше *`psz`* .

### <a name="remarks"></a>Комментарии

Универсальная текстовая функция `_tcscoll` , определенная в файле Tchar. H, сопоставляется либо с, либо, в зависимости от кодировки `strcoll` `wcscoll` `_mbscoll` , определенной во время компиляции. Каждая функция учитывает регистр строк в соответствии с используемой в настоящий момент кодовой страницей. Дополнительные сведения см. в разделе [strcoll, вксколл, _mbscoll, _strcoll_l, _wcscoll_l _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

## <a name="cstringtcollatenocase"></a><a name="collatenocase"></a> `CStringT::CollateNoCase`

Сравнивает две строки с помощью функции Generic-Text `_tcscoll` .

```cpp
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*`psz`*\
Другая строка, используемая для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны (без учета регистра), < 0, если этот **`CStringT`** объект меньше *`psz`* (без учета регистра), или > 0, если этот **`CStringT`** объект больше *`psz`* (без учета регистра).

### <a name="remarks"></a>Комментарии

Универсальная текстовая функция `_tcscoll` , определенная в файле Tchar. H, сопоставляется либо с, либо, в зависимости от кодировки `stricoll` `wcsicoll` `_mbsicoll` , определенной во время компиляции. Каждая функция выполняет сравнение строк без учета регистра в соответствии с используемой в настоящий момент кодовой страницей. Дополнительные сведения см. в разделе [strcoll, вксколл, _mbscoll, _strcoll_l, _wcscoll_l _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

## <a name="cstringtcompare"></a><a name="compare"></a> `CStringT::Compare`

Сравнивает две строки (с учетом регистра).

```cpp
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>Параметры

*`psz`*\
Другая строка, используемая для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны, < 0, если этот **`CStringT`** объект меньше *`psz`* , или > 0, если этот **`CStringT`** объект больше *`psz`* .

### <a name="remarks"></a>Комментарии

Универсальная текстовая функция `_tcscmp` , определенная в файле Tchar. H, сопоставляется либо с, либо, в зависимости от кодировки `strcmp` `wcscmp` `_mbscmp` , определенной во время компиляции. Каждая функция выполняет сравнение строк с учетом регистра и не влияет на языковой стандарт. Дополнительные сведения см. в разделе [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).

Если строка содержит внедренные значения NULL, в целях сравнения строка считается усеченной по первому внедренному символу null.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CStringT::Compare`.

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

## <a name="cstringtcomparenocase"></a><a name="comparenocase"></a> `CStringT::CompareNoCase`

Сравнивает две строки (без учета регистра).

```cpp
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*`psz`*\
Другая строка, используемая для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны (без учета регистра), <0, если этот **`CStringT`** объект меньше *`psz`* (без учета регистра), или >0, если этот **`CStringT`** объект больше *`psz`* (без учета регистра).

### <a name="remarks"></a>Комментарии

Универсальная текстовая функция `_tcsicmp` , определенная в файле Tchar. H, сопоставляется либо с `_stricmp` , либо, в зависимости от кодировки `_wcsicmp` `_mbsicmp` , определенной во время компиляции. Каждая функция выполняет сравнение строк без учета регистра. Сравнение зависит от LC_CTYPEного аспекта языкового стандарта, но не LC_COLLATE. Дополнительные сведения см. в разделе [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

## <a name="cstringtcstringt"></a><a name="cstringt"></a> `CStringT::CStringT`

Конструирует **`CStringT`** объект.

```cpp
CStringT() throw() :
    CThisSimpleString(StringTraits::GetDefaultManager());

explicit CStringT(IAtlStringMgr* pStringMgr) throw() :
    CThisSimpleString( pStringMgr);

CStringT(const VARIANT& varSrc);

CStringT(const VARIANT& varSrc, IAtlStringMgr* pStringMgr);

CStringT(const CStringT& strSrc) :
    CThisSimpleString( strSrc);

operator CSimpleStringT<
                    BaseType,
                    !_CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                    :: c_bIsMFCDLLTraits> &()

template <bool bMFCDLL>
CStringT(const CSimpleStringT<BaseType, bMFCDLL>& strSrc) :
    CThisSimpleString( strSrc);

template <class SystemString>
CStringT(SystemString^ pString) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(const YCHAR* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(LPCSTR pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CStringT(LPCWSTR pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(const unsigned char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

/*CSTRING_EXPLICIT*/ CStringT(char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(unsigned char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const unsigned char* pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(char ch, int nLength = 1) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t ch, int nLength = 1) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength) :
    CThisSimpleString( pch, nLength, StringTraits::GetDefaultManager());

CStringT(const YCHAR* pch, int nLength) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength, AtlStringMgr* pStringMgr) :
    CThisSimpleString( pch, nLength, pStringMgr);

CStringT(const YCHAR* pch, int nLength, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);
```

### <a name="parameters"></a>Параметры

*`pch`*\
Указатель на массив символов длины *нленгс*, а не заканчивающийся символом NULL.

*`nLength`*\
Число символов в *PCH*.

*`ch`*\
Один символ.

*`pszSrc`*\
Строка, завершающаяся нулем, для копирования в этот **`CStringT`** объект.

*`pStringMgr`*\
Указатель на диспетчер памяти для **`CStringT`** объекта. Дополнительные сведения о `IAtlStringMgr` и управлении памятью для **`CStringT`** см. в разделе [Управление памятью с помощью CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

*`strSrc`*\
Существующий **`CStringT`** объект, который будет скопирован в этот **`CStringT`** объект. Дополнительные сведения о `CThisString` и см `CThisSimpleString` . в разделе "Примечания".

*`varSrc`*\
Объект Variant, который необходимо скопировать в этот **`CStringT`** объект.

*`BaseType`*\
Символьный тип класса String. Может применяться один из перечисленных ниже типов.

**`char`** (для строк символов ANSI).

**`wchar_t`** (для символьных строк Юникода).

`TCHAR` (для символьных строк ANSI и Юникод).

*`bMFCDLL`*\
Логическое значение, указывающее, является ли проект DLL-библиотекой MFC ( `TRUE` ) или нет ( `FALSE` ).

*`SystemString`*\
Должен быть `System::String` , а проект должен быть скомпилирован с помощью `/clr` .

*`pString`*\
Маркер для **`CStringT`** объекта.

### <a name="remarks"></a>Комментарии

Поскольку конструкторы копируют входные данные в новое выделенное хранилище, могут возникнуть исключения памяти. Некоторые из этих конструкторов действуют как функции преобразования. Это позволяет заменить, например, **`LPTSTR`** место, где **`CStringT`** ожидается объект.

- **`CStringT`**( `LPCSTR` `lpsz` ): Формирует Юникод **`CStringT`** из строки ANSI. Этот конструктор также можно использовать для загрузки строкового ресурса, как показано в примере ниже.

- `CStringT(``LPCWSTR` `lpsz` ): Конструирует объект **`CStringT`** из строки в Юникоде.

- **`CStringT`**( `const unsigned char*` `psz` ): Позволяет создать объект **`CStringT`** из указателя на **`unsigned char`** .

> [!NOTE]
> Определите ` _CSTRING_DISABLE_NARROW_WIDE_CONVERSION` макрос, чтобы отключить неявное преобразование строк между строками ANSI и Юникод. Макрос исключает из конструкторов компиляции, поддерживающих преобразование.

*`strSrc`* Параметр может быть либо объектом, **`CStringT`** либо `CThisSimpleString` . Для **`CStringT`** используйте один из экземпляров по умолчанию ( `CString` , `CStringA` или `CStringW` ); для `CThisSimpleString` Используйте **`this`** указатель. `CThisSimpleString` объявляет экземпляр [класса ксимплестрингт](../../atl-mfc-shared/reference/csimplestringt-class.md), который представляет собой класс строк меньшего размера с менее встроенными функциями, чем **`CStringT`** класс.

Оператор перегрузки `CSimpleStringT<>&()` конструирует **`CStringT`** объект из `CSimpleStringT` объявления.

> [!NOTE]
> Несмотря на то **`CStringT`** , что можно создавать экземпляры, содержащие внедренные символы NULL, для них рекомендуется использовать. Вызов методов и операторов для **`CStringT`** объектов, содержащих внедренные символы NULL, может привести к непредвиденным результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

## <a name="cstringtcstringt"></a><a name="_dtorcstringt"></a> `CStringT::~CStringT`

Уничтожает **`CStringT`** объект.

```cpp
~CStringT() throw();
```

### <a name="remarks"></a>Комментарии

Уничтожает **`CStringT`** объект.

## <a name="cstringtdelete"></a><a name="delete"></a> `CStringT::Delete`

Удаляет символ или символы из строки, начинающейся с символа по указанному индексу.

```cpp
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>Параметры

*`iIndex`*\
Отсчитываемый от нуля индекс первого символа в **`CStringT`** объекте, который необходимо удалить.

*`nCount`*\
Число удаляемых символов.

### <a name="return-value"></a>Возвращаемое значение

Длина измененной строки.

### <a name="remarks"></a>Комментарии

Если *`nCount`* длиннее, чем строка, оставшаяся часть строки будет удалена.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output
Before: Soccer is best,
    but hockey is quicker!
After: Soccer best,
    but hockey is quicker!
```

## <a name="cstringtfind"></a><a name="find"></a> `CStringT::Find`

Ищет в этой строке первое совпадение символа или подстроки.

```cpp
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>Параметры

*`pszSub`*\
Подстрока для поиска.

*`iStart`*\
Индекс символа в строке, с которого начинается поиск, или значение 0, чтобы начать с начала.

*`ch`*\
Один символ для поиска.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первого символа в этом **`CStringT`** объекте, который соответствует запрошенной подстроке или символам;-1, если не найдена подстрока или символ.

### <a name="remarks"></a>Комментарии

Функция перегружена, чтобы принимать как одиночные символы (аналогично функции времени выполнения `strchr` ), так и строки (аналогично `strstr` ).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

## <a name="cstringtfindoneof"></a><a name="findoneof"></a> `CStringT::FindOneOf`

Ищет в этой строке первый символ, совпадающий с любым символом, содержащимся в *`pszCharSet`* .

```cpp
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>Параметры

*`pszCharSet`*\
Строка, содержащая символы для сопоставления.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первого символа в этой строке, который также имеет значение *`pszCharSet`* ;-1, если совпадений нет.

### <a name="remarks"></a>Комментарии

Находит первое вхождение любого из символов в *`pszCharSet`* .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

## <a name="cstringtformat"></a><a name="format"></a> `CStringT::Format`

Записывает форматированные данные в, **`CStringT`** точно так же, как [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) форматирует данные в массив символов в стиле C.

```cpp
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>Параметры

*`nFormatID`*\
Строковый идентификатор ресурса, содержащий строку управления форматированием.

*`pszFormat`*\
Строка управления форматированием.

*`argument`*\
Необязательные аргументы.

### <a name="remarks"></a>Комментарии

Эта функция форматирует и сохраняет ряд символов и значений в **`CStringT`** . Каждый необязательный аргумент (при его наличии) преобразуется и выводится в соответствии с соответствующей спецификацией формата в *`pszFormat`* или из строкового ресурса, определенного параметром *`nFormatID`* .

Вызов завершится ошибкой, если сам строковый объект предлагается в качестве параметра для `Format` . Например, следующий код приведет к непредсказуемым результатам:

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

Дополнительные сведения см. в разделе [Синтаксис описания формата: функции printf и wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

## <a name="cstringtformatmessage"></a><a name="formatmessage"></a> `CStringT::FormatMessage`

Форматирует строку сообщения.

```cpp
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>Параметры

*`nFormatID`*\
Строковый идентификатор ресурса, содержащий неформатированный текст сообщения.

*`pszFormat`*\
Указывает на строку управления форматированием. Он будет проверяться на наличие вставок и отформатировано соответствующим образом. Строка формата похожа на строки формата в стиле *printf*-Style, за исключением того, что она позволяет вставлять параметры в произвольный порядок.

*`argument`*\
Необязательные аргументы.

### <a name="remarks"></a>Комментарии

Для функции требуется определение сообщения в качестве входных данных. Определение сообщения определяется *`pszFormat`* или из строкового ресурса, определенного параметром *`nFormatID`* . Функция копирует форматированный текст сообщения в **`CStringT`** объект, обрабатывая все внедренные последовательности вставки по запросу.

> [!NOTE]
> `FormatMessage` пытается выделить системную память для вновь отформатированной строки. В случае сбоя этой попытки автоматически создается исключение памяти.

Каждая Вставка должна иметь соответствующий параметр после *`pszFormat`* *`nFormatID`* параметра или. В тексте сообщения для динамического форматирования сообщения поддерживаются несколько escape-последовательностей. Дополнительные сведения см. в описании функции [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) Windows в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

## <a name="cstringtformatmessagev"></a><a name="formatmessagev"></a> `CStringT::FormatMessageV`

Форматирует строку сообщения с помощью переменного списка аргументов.

```cpp
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>Параметры

*`pszFormat`*\
Указывает на строку управления форматированием. Он будет проверяться на наличие вставок и отформатировано соответствующим образом. Строка формата похожа на строки формата в стиле функции времени выполнения `printf` , за исключением того, что она позволяет вставлять параметры в произвольный порядок.

*`pArgList`*\
Указатель на список аргументов.

### <a name="remarks"></a>Комментарии

Функции требуется определение сообщения в качестве входных данных, определяемое *`pszFormat`* . Функция копирует форматированный текст сообщения и переменный список аргументов в **`CStringT`** объект, обрабатывая все внедренные последовательности вставки по запросу.

> [!NOTE]
> `FormatMessageV` вызывает метод [CStringT:: FormatMessage](#formatmessage), который пытается выделить системную память для вновь отформатированной строки. В случае сбоя этой попытки автоматически создается исключение памяти.

Дополнительные сведения см. в описании функции [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) Windows в Windows SDK.

## <a name="cstringtformatv"></a><a name="formatv"></a> `CStringT::FormatV`

Форматирует строку сообщения с помощью переменного списка аргументов.

```cpp
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>Параметры

*`pszFormat`*\
Указывает на строку управления форматированием. Он будет проверяться на наличие вставок и отформатировано соответствующим образом. Строка формата похожа на строки формата в стиле функции времени выполнения `printf` , за исключением того, что она позволяет вставлять параметры в произвольный порядок.

*`args`*\
Указатель на список аргументов.

### <a name="remarks"></a>Комментарии

Записывает отформатированную строку и переменный список аргументов в **`CStringT`** строку таким же образом, чтобы `vsprintf_s` форматировать данные в массив символов в стиле C.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

## <a name="cstringtgetenvironmentvariable"></a><a name="getenvironmentvariable"></a> `CStringT::GetEnvironmentVariable`

Присваивает строке значение указанной переменной среды.

```cpp
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>Параметры

*`pszVar`*\
Указатель на строку, завершающуюся нулем, которая указывает переменную среды.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Комментарии

Получает значение указанной переменной из блока среды вызывающего процесса. Значение в виде строки символов, завершающейся нулем.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

## <a name="cstringtinsert"></a><a name="insert"></a> `CStringT::Insert`

Вставляет в строку один символ или подстроку с заданным индексом.

```cpp
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>Параметры

*`iIndex`*\
Индекс символа, перед которым будет выполнена вставка.

*`psz`*\
Указатель на подстроку для вставки.

*`ch`*\
Вставляемый символ.

### <a name="return-value"></a>Возвращаемое значение

Длина измененной строки.

### <a name="remarks"></a>Комментарии

*`iIndex`* Параметр определяет первый символ, который будет перемещен, чтобы освободить место для символа или подстроки. Если *ниндекс* равен нулю, вставка выполняется перед всей строкой. Если *ниндекс* превышает длину строки, функция объединит текущую строку и новый материал, предоставленный либо либо *`ch`* *`psz`* .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

## <a name="cstringtleft"></a><a name="left"></a> `CStringT::Left`

Извлекает крайние левые *`nCount`* символы из этого **`CStringT`** объекта и возвращает копию извлеченной подстроки.

```cpp
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>Параметры

*`nCount`*\
Число символов, извлекаемых из этого **`CStringT`** объекта.

### <a name="return-value"></a>Возвращаемое значение

**`CStringT`** Объект, содержащий копию указанного диапазона символов. Возвращаемый **`CStringT`** объект может быть пустым.

### <a name="remarks"></a>Комментарии

Если *`nCount`* превышает длину строки, извлекается вся строка. Функция `Left` аналогична функции `Left` в языке Basic.

Для многобайтовых кодировок (MBCS) *`nCount`* обрабатывает каждую 8-разрядную последовательность как символ, поэтому *`nCount`* возвращает число многобайтовых символов, умноженное на два.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

## <a name="cstringtloadstring"></a><a name="loadstring"></a> `CStringT::LoadString`

Считывает строковый ресурс Windows, идентифицируемый *NID*, в существующий **`CStringT`** объект.

```cpp
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>Параметры

*`hInstance`*\
Маркер экземпляра модуля.

*`nID`*\
Идентификатор ресурса строки Windows.

*`wLanguageID`*\
Язык строкового ресурса.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если загрузка ресурса прошла успешно; в противном случае — 0.

### <a name="remarks"></a>Комментарии

Загружает строковый ресурс (*NID*) из указанного модуля (*HINSTANCE*), используя указанный язык (*влангуаже*).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

## <a name="cstringtmakelower"></a><a name="makelower"></a> `CStringT::MakeLower`

Преобразует **`CStringT`** объект в строку нижнего регистра.

```cpp
CStringT& MakeLower();
```

### <a name="return-value"></a>Возвращаемое значение

Результирующая строка в нижнем регистре.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

## <a name="cstringtmakereverse"></a><a name="makereverse"></a> `CStringT::MakeReverse`

Изменяет порядок символов в объекте на обратный **`CStringT`** .

```cpp
CStringT& MakeReverse();
```

### <a name="return-value"></a>Возвращаемое значение

Полученная Обратная строка.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

## <a name="cstringtmakeupper"></a><a name="makeupper"></a> `CStringT::MakeUpper`

Преобразует **`CStringT`** объект в строку в верхнем регистре.

```cpp
CStringT& MakeUpper();
```

### <a name="return-value"></a>Возвращаемое значение

Итоговая строка в верхнем регистре.

### <a name="remarks"></a>Remarks

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

## <a name="cstringtmid"></a><a name="mid"></a> `CStringT::Mid`

Извлекает подстроку *`nCount`* символов длины из этого **`CStringT`** объекта, начиная с позиции (с *`iFirst`* отсчетом от нуля).

```cpp
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>Параметры

*`iFirst`*\
Отсчитываемый от нуля индекс первого символа в этом **`CStringT`** объекте, который должен быть включен в извлеченную подстроку.

*`nCount`*\
Число символов, извлекаемых из этого **`CStringT`** объекта. Если этот параметр не указан, то извлекается остальная часть строки.

### <a name="return-value"></a>Возвращаемое значение

**`CStringT`** Объект, содержащий копию указанного диапазона символов. Возвращаемый **`CStringT`** объект может быть пустым.

### <a name="remarks"></a>Комментарии

Функция возвращает копию извлеченной подстроки. `Mid` функция аналогична базовой функции Mid (за исключением того, что индексы в базовых основаны на единицу).

Для многобайтовых кодировок (MBCS) *`nCount`* ссылается на каждый 8-разрядный символ, т. е. ведущий и младший байт в одном многобайтовой кодировке считаются двумя символами.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

## <a name="cstringtoemtoansi"></a><a name="oemtoansi"></a> `CStringT::OemToAnsi`

Преобразует все символы в этом **`CStringT`** объекте из набора символов OEM в кодировку ANSI.

```cppcpp
void OemToAnsi();
```

### <a name="remarks"></a>Комментарии

Эта функция недоступна `_UNICODE` , если определена.

### <a name="example"></a>Пример

См. пример для [CStringT:: анситуем](#ansitooem).

## <a name="cstringtoperator-"></a><a name="operator_eq"></a> `CStringT::operator =`

Назначает новое значение строке.

```cpp
CStringT& operator=(const CStringT& strSrc);

template<bool bMFCDLL>
CStringT& operator=(const CSimpleStringT<BaseType, bMFCDLL>& str);
CStringT& operator=(PCXSTR pszSrc);
CStringT& operator=(PCYSTR pszSrc);
CStringT& operator=(const unsigned char* pszSrc);
CStringT& operator=(XCHAR ch);
CStringT& operator=(YCHAR ch);
CStringT& operator=(const VARIANT& var);
```

### <a name="parameters"></a>Параметры

*`strSrc`*\
Объект, **`CStringT`** присваиваемый этой строке.

*`str`*\
Ссылка на объект `CThisSimpleString`.

*`bMFCDLL`*\
Логическое значение, указывающее, является ли проект библиотекой DLL MFC.

*`BaseType`*\
Базовый тип строки.

*`var`*\
Объект Variant, присваиваемый этой строке.

*`ch`*\
Символ ANSI или Unicode, присваиваемый строке.

*`pszSrc`*\
Указатель на исходную строку, которой присваивается значение.

### <a name="remarks"></a>Комментарии

Оператор присваивания принимает другой **`CStringT`** объект, указатель на символ или один символ. Исключения памяти могут возникать при использовании этого оператора, так как может быть выделено новое хранилище.

Дополнительные сведения о см `CThisSimpleString` . в подразделе "Примечания" раздела [CStringT:: CStringT](#cstringt).

> [!NOTE]
> Несмотря на то **`CStringT`** , что можно создавать экземпляры, содержащие внедренные символы NULL, для них рекомендуется использовать. Вызов методов и операторов для **`CStringT`** объектов, содержащих внедренные символы NULL, может привести к непредвиденным результатам.

## <a name="cstringtoperator-"></a><a name="operator_add"></a> `CStringT::operator +`

Сцепляет две строки или символ и строку.

```cpp
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```

### <a name="parameters"></a>Параметры

*`ch1`*\
Символ ANSI или Unicode для сцепления со строкой.

*`ch2`*\
Символ ANSI или Unicode для сцепления со строкой.

*`str1`*\
Объект **`CStringT`** для сцепления со строкой или символом.

*`str2`*\
Объект **`CStringT`** для сцепления со строкой или символом.

*`psz1`*\
Указатель на строку, завершающуюся нулем, для сцепления со строкой или символом.

*`psz2`*\
Указатель на строку, которую необходимо сцепить со строкой или символом.

### <a name="remarks"></a>Комментарии

Существует семь форм перегруженных `CStringT::operator+` функций функции. Первая версия объединяет два существующих **`CStringT`** объекта. Следующие два сцепления **`CStringT`** объекта и строки с завершающим нулем. Следующие два сцепления **`CStringT`** объекта и СИМВОЛА ANSI. Последние два присоединяются к **`CStringT`** объекту и символу Юникода.

> [!NOTE]
> Несмотря на то **`CStringT`** , что можно создавать экземпляры, содержащие внедренные символы NULL, для них рекомендуется использовать. Вызов методов и операторов для **`CStringT`** объектов, содержащих внедренные символы NULL, может привести к непредвиденным результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_add_eq"></a> `CStringT::operator +=`

Сцепляет символы в конец строки.

```cpp
CStringT& operator+=(const CThisSimpleString& str);

template<bool bMFCDLL>
CStringT& operator+=(const const CSimpleStringT<BaseType, bMFCDLL>& str);

template<int t_nSize>
CStringT& operator+=(const CStaticString<XCHAR, t_nSize>& strSrc);
CStringT& operator+=(PCXSTR pszSrc);
CStringT& operator+=(PCYSTR pszSrc);
CStringT& operator+=(char ch);
CStringT& operator+=(unsigned char ch);
CStringT& operator+=(wchar_t ch);
CStringT& operator+=(const VARIANT& var);
```

### <a name="parameters"></a>Параметры

*`str`*\
Ссылка на объект `CThisSimpleString`.

*`bMFCDLL`*\
Логическое значение, указывающее, является ли проект библиотекой DLL MFC.

*`BaseType`*\
Базовый тип строки.

*`var`*\
Объект Variant для сцепления с этой строкой.

*`ch`*\
Символ ANSI или Unicode для сцепления со строкой.

*`pszSrc`*\
Указатель на исходную строку, в которой выполняется сцепление.

*`strSrc`*\
Объект **`CStringT`** для сцепления с этой строкой.

### <a name="remarks"></a>Комментарии

Оператор принимает другой **`CStringT`** объект, указатель на символ или один символ. Исключения памяти могут возникать при использовании этого оператора объединения, так как для символов, добавляемых в этот объект, можно выделить новое хранилище **`CStringT`** .

Дополнительные сведения о см `CThisSimpleString` . в подразделе "Примечания" раздела [CStringT:: CStringT](#cstringt).

> [!NOTE]
> Несмотря на то **`CStringT`** , что можно создавать экземпляры, содержащие внедренные символы NULL, для них рекомендуется использовать. Вызов методов и операторов для **`CStringT`** объектов, содержащих внедренные символы NULL, может привести к непредвиденным результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_eq_eq"></a> `CStringT::operator ==`

Определяет, являются ли две строки логически равными.

```cpp
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>Параметры

*`ch1`*\
Символ ANSI или Unicode для сравнения.

*`ch2`*\
Символ ANSI или Unicode для сравнения.

*`str1`*\
**`CStringT`** Для сравнения.

*`str2`*\
**`CStringT`** Для сравнения.

*`psz1`*\
Указатель на строку, завершающуюся нулем, для сравнения.

*`psz2`*\
Указатель на строку, завершающуюся нулем, для сравнения.

### <a name="remarks"></a>Комментарии

Проверяет, равна ли строка или символ в левой части строке или символу справа, и возвращает `TRUE` или `FALSE` соответственно.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_neq"></a> `CStringT::operator !=`

Определяет, логически не равны ли две строки.

```cpp
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>Параметры

*`ch1`*\
Символ ANSI или Unicode для сцепления со строкой.

*`ch2`*\
Символ ANSI или Unicode для сцепления со строкой.

*`str1`*\
**`CStringT`** Для сравнения.

*`str2`*\
**`CStringT`** Для сравнения.

*`psz1`*\
Указатель на строку, завершающуюся нулем, для сравнения.

*`psz2`*\
Указатель на строку, завершающуюся нулем, для сравнения.

### <a name="remarks"></a>Комментарии

Проверяет, не равен ли строка или символ в левой части строке или символу справа.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_lt"></a> `CStringT::operator <`

Определяет, меньше ли строка в левой части оператора, чем строка с правой стороны.

```cpp
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*`str1`*\
**`CStringT`** Для сравнения.

*`str2`*\
**`CStringT`** Для сравнения.

*`psz1`*\
Указатель на строку, завершающуюся нулем, для сравнения.

*`psz2`*\
Указатель на строку, завершающуюся нулем, для сравнения.

### <a name="remarks"></a>Комментарии

Лексикографическом сравнение строк, символ по символу до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_gt"></a> `CStringT::operator >`

Определяет, больше ли строка в левой части оператора, чем строка с правой стороны.

```cpp
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*`str1`*\
**`CStringT`** Для сравнения.

*`str2`*\
**`CStringT`** Для сравнения.

*`psz1`*\
Указатель на строку, завершающуюся нулем, для сравнения.

*`psz2`*\
Указатель на строку, завершающуюся нулем, для сравнения.

### <a name="remarks"></a>Комментарии

Лексикографическом сравнение строк, символ по символу до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_lt_eq"></a> `CStringT::operator <=`

Определяет, является ли строка в левой части оператора меньше или равна строке в правой части.

```cpp
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*`str1`*\
**`CStringT`** Для сравнения.

*`str2`*\
**`CStringT`** Для сравнения.

*`psz1`*\
Указатель на строку, завершающуюся нулем, для сравнения.

*`psz2`*\
Указатель на строку, завершающуюся нулем, для сравнения.

### <a name="remarks"></a>Комментарии

Лексикографическом сравнение строк, символ по символу до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_gt_eq"></a> `CStringT::operator >=`

Определяет, является ли строка в левой части оператора больше или равна строке в правой части.

```cpp
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*`str1`*\
**`CStringT`** Для сравнения.

*`str2`*\
**`CStringT`** Для сравнения.

*`psz1`*\
Указатель на строку для сравнения.

*`psz2`*\
Указатель на строку для сравнения.

### <a name="remarks"></a>Комментарии

Лексикографическом сравнение строк, символ по символу до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

## <a name="cstringtremove"></a><a name="remove"></a> `CStringT::Remove`

Удаляет все экземпляры указанного символа из строки.

```cpp
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>Параметры

*`chRemove`*\
Символ, удаляемый из строки.

### <a name="return-value"></a>Возвращаемое значение

Число символов, удаленных из строки. Нуль, если строка не изменяется.

### <a name="remarks"></a>Комментарии

При сравнении символов учитывается регистр.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

## <a name="cstringtreplace"></a><a name="replace"></a> `CStringT::Replace`

Существует две версии `Replace` . Первая версия заменяет одну или несколько копий подстроки с помощью другой подстроки. Обе подстроки завершаются нулем. Вторая версия заменяет одну или несколько копий символа, используя другой символ. Обе версии работают с символьными данными, хранящимися в **`CStringT`** .

```cpp
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>Параметры

*`pszOld`*\
Указатель на строку, завершающуюся нулем, которую необходимо заменить на *`pszNew`* .

*`pszNew`*\
Указатель на строку, завершающуюся нулем, которая заменяет *`pszOld`* .

*`chOld`*\
Символ, который должен быть заменен *`chNew`* .

*`chNew`*\
Символ, заменяющий *`chOld`* .

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество замененных экземпляров символа или подстроки или нуль, если строка не изменяется.

### <a name="remarks"></a>Комментарии

`Replace` может изменить длину строки, так как она *`pszNew`* *`pszOld`* не должна иметь одинаковую длину, и несколько копий старой подстроки можно изменить на новую. Функция выполняет совпадение с учетом регистра.

Примеры **`CStringT`** экземпляров: `CString` , `CStringA` и `CStringW` .

Для `CStringA` `Replace` параметр работает с символами ANSI или многобайтовой кодировкой (MBCS). Для `CStringW` службы `Replace` работает с расширенными символами.

Для `CString` тип данных character выбирается во время компиляции в зависимости от того, определены ли константы в следующей таблице.

|Определенная константа|Символьный тип данных|
|----------------------|-------------------------|
|`_UNICODE`|Расширенные символы|
|`_MBCS`|Многобайтовые символы|
|Нет|Однобайтовые символы|
|Оба|Не определено.|

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

## <a name="cstringtreversefind"></a><a name="reversefind"></a> `CStringT::ReverseFind`

Поиск **`CStringT`** последнего совпадения символа в этом объекте.

```cpp
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>Параметры

*`ch`*\
Искомый символ.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс последнего символа в этом **`CStringT`** объекте, соответствующего запрошенному символу, или значение-1, если символ не найден.

### <a name="remarks"></a>Комментарии

Функция аналогична функции времени выполнения `strrchr` .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

## <a name="cstringtright"></a><a name="right"></a> `CStringT::Right`

Извлекает последние (то есть самые правые) *`nCount`* символы из этого **`CStringT`** объекта и возвращает копию извлеченной подстроки.

```cpp
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>Параметры

*`nCount`*\
Число символов, извлекаемых из этого **`CStringT`** объекта.

### <a name="return-value"></a>Возвращаемое значение

**`CStringT`** Объект, содержащий копию указанного диапазона символов. Возвращаемый **`CStringT`** объект может быть пустым.

### <a name="remarks"></a>Комментарии

Если *`nCount`* превышает длину строки, извлекается вся строка. `Right` функция аналогична базовой `Right` функции (за исключением того, что индексы в Basic отсчитываются от нуля).

Для многобайтовых кодировок (MBCS) *`nCount`* ссылается на каждый 8-разрядный символ, т. е. ведущий и младший байт в одном многобайтовой кодировке считаются двумя символами.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

## <a name="cstringtsetsysstring"></a><a name="setsysstring"></a> `CStringT::SetSysString`

Перераспределяет объект, **`BSTR`** на который указывает, *`pbstr`* и копирует в него содержимое **`CStringT`** объекта, включая символ null.

```cpp
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>Параметры

*`pbstr`*\
Указатель на символьную строку.

### <a name="return-value"></a>Возвращаемое значение

Новая строка.

### <a name="remarks"></a>Комментарии

В зависимости от содержимого **`CStringT`** объекта значение, на **`BSTR`** которое ссылается объект, *`pbstr`* может измениться. Функция вызывает исключение, `CMemoryException` если недостаточно памяти.

Эта функция обычно используется для изменения значения строк, передаваемых по ссылке для службы автоматизации.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

## <a name="cstringtspanexcluding"></a><a name="spanexcluding"></a> `CStringT::SpanExcluding`

Извлекает из строки символы, начиная с первого символа, которые не входят в набор символов, определяемый параметром *`pszCharSet`* .

```cpp
CStringT SpanExcluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Параметры

*`pszCharSet`*\
Строка, интерпретируемая как набор символов.

### <a name="return-value"></a>Возвращаемое значение

Подстрока, содержащая символы в строке, не содержащиеся в *`pszCharSet`* , начиная с первого символа в строке и заканчивая первым символом в строке, который также находится в (т. е. *`pszCharSet`* начиная с первого символа в строке и до, но исключая первый символ в найденной строке *`pszCharSet`* ). Он возвращает всю строку, если *`pszCharSet`* в строке не найден символ.

### <a name="remarks"></a>Комментарии

`SpanExcluding` Извлекает и возвращает все символы перед первым вхождением символа из *`pszCharSet`* (иными словами, символ из *`pszCharSet`* и все символы, следующие за ним в строке, не возвращаются). Если *`pszCharSet`* в строке не найден символ, `SpanExcluding` возвращается вся строка.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

## <a name="cstringtspanincluding"></a><a name="spanincluding"></a> `CStringT::SpanIncluding`

Извлекает из строки символы, начиная с первого символа, которые находятся в наборе символов, определяемых параметром *`pszCharSet`* .

```cpp
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Параметры

*`pszCharSet`*\
Строка, интерпретируемая как набор символов.

### <a name="return-value"></a>Возвращаемое значение

Подстрока, содержащая символы в строке, *`pszCharSet`* начиная с первого символа в строке и заканчивая при обнаружении символа в строке, не содержащейся в *`pszCharSet`* . `SpanIncluding` Возвращает пустую подстроку, если первый символ в строке отсутствует в указанном наборе.

### <a name="remarks"></a>Комментарии

Если первый символ строки не находится в кодировке, `SpanIncluding` возвращается пустая строка. В противном случае возвращается последовательность последовательных символов, находящиеся в наборе.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

## <a name="cstringttokenize"></a><a name="tokenize"></a> `CStringT::Tokenize`

Находит следующий токен в целевой строке

```cpp
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const;
```

### <a name="parameters"></a>Параметры

*`pszTokens`*\
Строка, содержащая разделители токенов. Порядок этих разделителей не важен.

*`iStart`*\
Отсчитываемый от нуля индекс, с которого начинается поиск.

### <a name="return-value"></a>Возвращаемое значение

**`CStringT`** Объект, содержащий текущее значение токена.

### <a name="remarks"></a>Комментарии

`Tokenize`Функция находит следующий токен в целевой строке. Набор символов в *псзтокенс* указывает возможные разделители для найденных токенов. При каждом вызове `Tokenize` функции начинается с *`iStart`* , пропускает начальные разделители и возвращает **`CStringT`** объект, содержащий текущий токен, который представляет собой строку символов вплоть до следующего символа-разделителя. Значение *`iStart`* обновляется до позиции, следующей за завершающим символом-разделителем, или – 1, если достигнут конец строки. Дополнительные токены могут быть разбиты из оставшейся части целевой строки на последовательность вызовов `Tokenize` , используя для наблюдения за *`iStart`* тем, где в строке находится следующий токен для считывания. Если маркеров больше нет, функция возвратит пустую строку и *`iStart`* будет иметь значение-1.

В отличие от функций CRT, таких как [`strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l`](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md) , `Tokenize` не изменяет целевую строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>Комментарии

Выходные данные этого примера выглядят следующим образом:

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

## <a name="cstringttrim"></a><a name="trim"></a> `CStringT::Trim`

Обрезает начальные и конечные символы из строки.

```cpp
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>Параметры

*`chTarget`*\
Целевой символ для усечения.

*`pszTargets`*\
Указатель на строку, содержащую целевые символы для усечения. Все начальные и конечные вхождения символов в *`pszTargets`* будут обрезаны из **`CStringT`** объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обрезанную строку.

### <a name="remarks"></a>Комментарии

Удаляет все начальные и конечные вхождения одного из следующих элементов:

- Символ, заданный параметром *`chTarget`* .

- Все символы, найденные в строке, указанной параметром *`pszTargets`* .

- Бель.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>Комментарии

Выходные данные этого примера выглядят следующим образом:

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

## <a name="cstringttrimleft"></a><a name="trimleft"></a> `CStringT::TrimLeft`

Обрезает начальные символы из строки.

```cpp
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>Параметры

*`chTarget`*\
Целевой символ для усечения.

*`pszTargets`*\
Указатель на строку, содержащую целевые символы для усечения. Все ведущие вхождения символов в *`pszTargets`* будут обрезаны из **`CStringT`** объекта.

### <a name="return-value"></a>Возвращаемое значение

Результирующая усеченная строка.

### <a name="remarks"></a>Комментарии

Удаляет все начальные и конечные вхождения одного из следующих элементов:

- Символ, заданный параметром *`chTarget`* .

- Все символы, найденные в строке, указанной параметром *`pszTargets`* .

- Бель.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

## <a name="cstringttrimright"></a><a name="trimright"></a> `CStringT::TrimRight`

Обрезает конечные символы из строки.

```cpp
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>Параметры

*`chTarget`*\
Целевой символ для усечения.

*`pszTargets`*\
Указатель на строку, содержащую целевые символы для усечения. Все завершающие вхождения символов в *`pszTargets`* будут обрезаны из **`CStringT`** объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает **`CStringT`** объект, содержащий обрезанную строку.

### <a name="remarks"></a>Комментарии

Удаляет конечные вхождения одного из следующих элементов:

- Символ, заданный параметром *`chTarget`* .

- Все символы, найденные в строке, указанной параметром *`pszTargets`* .

- Бель.

`CStringT& TrimRight(XCHAR chTarget)`Версия принимает один символьный параметр и удаляет все копии этого символа из конца **`CStringT`** строковых данных. Он начинается с конца строки и работает в направлении к началу. Она останавливается при обнаружении другого символа или при **`CStringT`** нехватке символьных данных.

`CStringT& TrimRight(PCXSTR pszTargets)`Версия принимает строку, завершающуюся нулем, которая содержит все различные символы для поиска. Он удаляет все копии этих символов в **`CStringT`** объекте. Он начинается в конце строки и работает в направлении к началу. Она останавливается при обнаружении символа, не находящейся в целевой строке, или при **`CStringT`** отсутствии символьных данных. Он не пытается сопоставить всю целевую строку с подстрокой в конце **`CStringT`** .

Для `CStringT& TrimRight()` версии не требуются параметры. Все конечные пробелы в конце строки обрезаются **`CStringT`** . Символы пробела могут быть разрывами строк, пробелами или символами табуляции.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>См. также

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)\
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)\
[Класс Ксимплестрингт](../../atl-mfc-shared/reference/csimplestringt-class.md)
