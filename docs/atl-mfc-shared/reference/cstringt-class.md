---
title: Класс CStringT
ms.date: 03/27/2019
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
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
ms.openlocfilehash: 8fcce4c426cd99785d34dc080f238cc78cdfee36
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746706"
---
# <a name="cstringt-class"></a>Класс CStringT

Этот класс `CStringT` представляет объект.

## <a name="syntax"></a>Синтаксис

```
template<typename BaseType, class StringTraits>
class CStringT :
    public CSimpleStringT<BaseType,
        _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>::c_bIsMFCDLLTraits>
```

#### <a name="parameters"></a>Параметры

*BaseType*<br/>
Тип символа класса строки. Может применяться один из перечисленных ниже типов.

- **символ** (для строк anSI символов).

- **wchar_t** (для строк символов Unicode).

- TCHAR (для строк символов ANSI и Unicode).

*СтрингТрэйтс*<br/>
Определяет, нужна ли классу строк C Run-Time (CRT) Library и где находятся строки ресурсов. Может применяться один из перечисленных ниже типов.

- **StrtraitATL< wchar_t &#124;** **&#124;** **TCHAR, ChtraitsCRT< wchar_t** &#124; **&#124;** **tCHAR > >**

   Класс требует поддержки CRT и поиска строк ресурса в указанном модуле `m_hInstResource` (член класса модуля приложения).

- **StrtraitATL< wchar_t** &#124; &#124; **tCHAR, ChTraitsOS< wchar_t** &#124; **&#124;** **&#124; T > >CHAR** **char**

   Класс не требует поддержки CRT и поиска строк ресурса в указанном модуле `m_hInstResource` (член класса модуля приложения).

- **StrTraitMFC< wchar_t** &#124; &#124; **&#124;** **TCHAR, ChtraitsCRT< wchar_t** &#124; **&#124;** **tCHAR > >**

   Класс требует поддержки CRT и поиска строк ресурсов с помощью стандартного алгоритма поиска MFC.

- **StrTraitMFC< wchar_t &#124;** **&#124;** **&#124; TCHAR, ChTraitsOS< wchar_t** &#124; &#124; **tCHAR > >** **char**

   Класс не требует поддержки CRT и поиска строк ресурсов с помощью стандартного алгоритма поиска MFC.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStringT::CstringT](#cstringt)|Строит `CStringT` объект различными способами.|
|[CStringT:::CstringT](#_dtorcstringt)|Уничтожает объект `CStringT` .|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStringT::AllocSysString](#allocsysstring)|Выделяет BSTR из `CStringT` данных.|
|[CStringT::AnsiToOem](#ansitooem)|Совершает преобразование на месте из набора символов ANSI в набор символов OEM.|
|[CStringT::ПриложениеФормат](#appendformat)|Приложения отформатированных данных к существующему `CStringT` объекту.|
|[CStringT::Коллат](#collate)|Сравнивает две строки (чувствительный к делу, использует информацию о локальной информации).|
|[CStringT::CollateNoCase](#collatenocase)|Сравнивает две строки (случай нечувствительный, использует информацию о локальной информации).|
|[CStringT::Сравните](#compare)|Сравнивает две строки (дело чувствительное).|
|[CStringT::CompareNoCase](#comparenocase)|Сравнивает две строки (случай нечувствительный).|
|[CStringT::Delete](#delete)|Удаляет символ или символ из строки.|
|[CStringT::Найти](#find)|Находит символ или подстроку внутри большой строки.|
|[Cstringt:Findoneof](#findoneof)|Находит первый подходящий символ из набора.|
|[CStringT::Формат](#format)|Форматы строки, как `sprintf` это делает.|
|[CStringT::FormatMessage](#formatmessage)|Форматирует строку сообщения.|
|[CStringT::FormatMessageV](#formatmessagev)|Форматирует строку сообщения с помощью списка переменных аргументов.|
|[CStringT::FormatV](#formatv)|Форматы строки с использованием переменного списка аргументов.|
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Устанавливает строку к значению заданной переменной среды.|
|[CStringT::Вставить](#insert)|Вставляет один символ или подстроку в данный индекс в строку.|
|[CStringT::Слева](#left)|Извлекает левую часть строки.|
|[CStringT::LoadString](#loadstring)|Загружает `CStringT` существующий объект из ресурса Windows.|
|[CStringT::MakeLower](#makelower)|Преобразует все символы в этой строке в нижние символы.|
|[CStringT::MakeReverse](#makereverse)|Обратный строки.|
|[CStringT::MakeUpper](#makeupper)|Преобразует все символы в этой строке в верхние символы.|
|[CStringT::Mid](#mid)|Извлекает среднюю часть строки.|
|[CStringT::OemToAnsi](#oemtoansi)|Совершает преобразование на месте из набора символов OEM в набор символов ANSI.|
|[CStringT::Удалить](#remove)|Удаляет указанные символы из строки.|
|[CStringT::Замена](#replace)|Заменяет указанные символы на другие символы.|
|[CStringT::Обратныйисточник](#reversefind)|Находит символ внутри большой строки; начинается с конца.|
|[CStringT::Право](#right)|Извлекает правую часть строки.|
|[CStringT::SetSysString](#setsysstring)|Устанавливает существующий объект BSTR `CStringT` с данными с объекта.|
|[CStringT::SpanExcluding](#spanexcluding)|Извлекает символы из строки, начиная с первого символа, которые `pszCharSet`не находятся в наборе символов, определенных .|
|[CStringT::SpanIncluding](#spanincluding)|Извлекает подстроку, содержащую только символы в наборе.|
|[Cstringt::Tokenize](#tokenize)|Экстракты указанных токенов в целевой строке.|
|[CStringT::Trim](#trim)|Обрезает все ведущие и задние символы белого пространства из строки.|
|[CStringT::Trimleft](#trimleft)|Обрезки ведущих символов whitespace из строки.|
|[CStringT::TrimRight](#trimright)|Обрезки задних символов белого пространства из строки.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[CStringT::оператор](#operator_eq)|Присваивает объекту `CStringT` новое значение.|
|[CStringT::оператор](#operator_add)|Конкатирует две строки или символ и строку.|
|[CStringT::оператор](#operator_add_eq)|Конкретирует новую строку до конца существующей строки.|
|[CStringT::оператор](#operator_eq_eq)|Определяет, логически ли две строки равны.|
|[CStringT::оператор !](#operator_neq)|Определяет, если две строки логически не равны.|
|[CStringT::оператор&lt;](#operator_lt)|Определяет, если строка на левой стороне оператора меньше, чем к строке на правой стороне.|
|[CStringT::оператор&gt;](#operator_gt)|Определяет, если строка на левой стороне оператора больше, чем к строке на правой стороне.|
|[CStringT::оператор&lt;=](#operator_lt_eq)|Определяет, если строка на левой стороне оператора меньше или равна строке на правой стороне.|
|[CStringT::оператор&gt;=](#operator_gt_eq)|Определяет, если строка на левой стороне оператора больше или равна строке на правой стороне.|

## <a name="remarks"></a>Remarks

`CStringT`наследует от [класса CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md). Расширенные функции, такие как манипуляция персонажами, `CStringT`заказ и поиск, реализованы.

> [!NOTE]
> `CStringT`объекты способны бросать исключения. Это происходит, `CStringT` когда объект иссякает из памяти по любой причине.

Объект `CStringT` состоит из последовательности символов с переменной длиной. `CStringT`предоставляет функции и операторов, использующих синтаксис, аналогичный базовому. Операторы конкатизации и сравнения, наряду с упрощенным управлением памятью, делают `CStringT` объекты проще в использовании, чем обычные массивы символов.

> [!NOTE]
> Хотя можно создавать `CStringT` экземпляры, содержащие встроенные символы null, мы рекомендуем против него. Методы вызова и `CStringT` операторы на объекты, содержащие встроенные нулевые символы, могут дать непреднамеренные результаты.

Используя различные комбинации `BaseType` `StringTraits` параметров, `CStringT` объекты могут поступать в следующих типах, которые были предопределены библиотеками ATL.

При использовании в приложении ATL:

`CString`, `CStringA`, `CStringW` и экспортируются из MFC DLL (MFC90. DLL), никогда от пользователя DLLs. Это делается `CStringT` для предотвращения умножения.

> [!NOTE]
> Если ваш код содержит обходной путь для ошибок ссылки, которые описаны в [классах экспорта строк с использованием CStringT,](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md)вы должны удалить этот код. Он больше не требуется.

Следующие типы строк доступны в приложениях на основе MFC:

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CStringA`|Строка типа ANSI с поддержкой CRT.|
|`CStringW`|Строка типа Unicode с поддержкой CRT.|
|`CString`|Типы символов ANSI и Unicode с поддержкой CRT.|

Следующие типы строк доступны в проектах, где определена ATL_CSTRING_NO_CRT:

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CAtlStringA`|Строка типа ANSI без поддержки CRT.|
|`CAtlStringW`|Строка типа Unicode без поддержки CRT.|
|`CAtlString`|Типы символов ANSI и Unicode без поддержки CRT.|

Следующие типы строк доступны в проектах, где ATL_CSTRING_NO_CRT не определено:

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CAtlStringA`|Строка типа ANSI с поддержкой CRT.|
|`CAtlStringW`|Строка типа Unicode с поддержкой CRT.|
|`CAtlString`|Типы символов ANSI и Unicode с поддержкой CRT.|

`CString`объекты также имеют следующие характеристики:

- `CStringT`объекты могут расти в результате конкатных операций.

- `CStringT`объекты следуют «семантике значений». Думайте об `CStringT` объекте как о фактической строке, а не как указатель на строку.

- Вы можете `CStringT` свободно `PCXSTR` заменить объекты для функциональных аргументов.

- Пользовательское управление памятью для буферов строк. Для получения дополнительной информации [см.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="cstringt-predefined-types"></a>Предопределенные типы CStringT

Поскольку `CStringT` для определения типа символов (поддерживаемого [wchar_t](../../c-runtime-library/standard-types.md) или [символа)](../../c-runtime-library/standard-types.md)используется аргумент шаблона, типы параметров метода иногда могут быть сложными. Для упрощения этой проблемы определяется и используется набор `CStringT` предопределенных типов во всем классе. В следующей таблице перечислены различные типы:

|Имя|Описание|
|----------|-----------------|
|`XCHAR`|Один символ **(wchar_t** или **символ)** с тем `CStringT` же типом символов, что и объект.|
|`YCHAR`|Один символ (либо **wchar_t,** так и **символ)** с противоположным типом символа в `CStringT` качестве объекта.|
|`PXSTR`|Указатель на строку символа (либо **wchar_t,** либо **символ)** с тем же типом символов, что и `CStringT` объект.|
|`PYSTR`|Указатель на строку символа (либо **wchar_t,** либо **символ)** с противоположным типом символа в `CStringT` качестве объекта.|
|`PCXSTR`|Указатель на строку **const** характер (либо **wchar_t** или **символ)** с тем же типом символа, `CStringT` как объект.|
|`PCYSTR`|Указатель на строку **const** характер (либо **wchar_t** или **символ)** с противоположным типом символа, `CStringT` как объект.|

> [!NOTE]
> Код, который ранее использовал `CString` незарегистрированные методы `AssignCopy`(например), должен быть `CStringT` заменен кодом, который использует следующие документированные методы (например, `GetBuffer` или `ReleaseBuffer`). Эти методы наследуются от `CSimpleStringT`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Csimplestringt](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>Требования

|Заголовок|Назначение|
|------------|-------------|
|cstringt.h|Объекты строки только для MFC|
|atlstr.h|Объекты строки, не относясь к MFC|

## <a name="cstringtallocsysstring"></a><a name="allocsysstring"></a>CStringT::AllocSysString

Выделяет совместимую с автоматизацией строку типа BSTR и `CStringT` копирует содержимое объекта в нее, включая термин null.

```
BSTR AllocSysString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Недавно выделенная строка.

### <a name="remarks"></a>Remarks

В программах MFC, [CMemoryException класс](../../mfc/reference/cmemoryexception-class.md) брошен, если недостаточно памяти существует. В программах ATL, [CAtlException](../../atl/reference/catlexception-class.md) брошен. Эта функция обычно используется для возврата строк для автоматизации.

Обычно, если эта строка передается функции COM в качестве параметра, то это требует, чтобы абонент освободил строку. Это можно сделать с помощью [SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring), как описано в Windows SDK. Для получения дополнительной информации [см.](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)

Для получения дополнительной информации о функциях распределения OLE в Windows, [см. SysAllocString](/windows/win32/api/oleauto/nf-oleauto-sysallocstring) в Windows SDK.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CStringT::AllocSysString`.

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

## <a name="cstringtansitooem"></a><a name="ansitooem"></a>CStringT::AnsiToOem

Преобразует все символы этого `CStringT` объекта из набора символов ANSI в набор символов OEM.

```cpp
void AnsiToOem();
```

### <a name="remarks"></a>Remarks

Функция недоступна, если _UNICODE определена.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

## <a name="cstringtappendformat"></a><a name="appendformat"></a>CStringT::ПриложениеФормат

Приложения отформатированных данных к существующему `CStringT` объекту.

```cpp
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>Параметры

*pszFormat*<br/>
Строка управления форматом.

*nФорматид*<br/>
Идентификатор строки ресурса, содержащий строку управления форматом.

*argument*<br/>
Необязательные аргументы.

### <a name="remarks"></a>Remarks

Эта функция форматирует и придатит ряд символов и значений `CStringT`в . Каждый дополнительный аргумент (если таковой имеется) преобразуется и пригоден в соответствии с соответствующей спецификацией формата в *pszFormat* или из строки ресурса, идентифицированного *nFormatID.*

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

## <a name="cstringtcollate"></a><a name="collate"></a>CStringT::Коллат

Сравнивает две строки с использованием функции `_tcscoll`общего текста.

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*Psz*<br/>
Другая строка используется для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Ноль, если строки идентичны, `CStringT` < 0, если этот объект меньше, чем *psz,* или > 0, если этот `CStringT` объект больше, чем *psz*.

### <a name="remarks"></a>Remarks

Функция общего `_tcscoll`текста, которая определена в TCHAR. H, карты `strcoll`либо `wcscoll`, `_mbscoll`, или , в зависимости от набора символов, который определяется во время компиляции. Каждая функция выполняет конкретное сравнение строк в соответствии с кодовой страницей, которая используется в настоящее время. Для получения дополнительной информации, [см strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

## <a name="cstringtcollatenocase"></a><a name="collatenocase"></a>CStringT::CollateNoCase

Сравнивает две строки с использованием функции `_tcscoll`общего текста.

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*Psz*<br/>
Другая строка используется для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Ноль, если строки идентичны (игнорирование `CStringT` случая), < 0, если этот объект `CStringT` меньше *PSZ* (игнорирование случая), или > 0, если этот объект больше, чем *psz* (игнорирование случая).

### <a name="remarks"></a>Remarks

Функция общего `_tcscoll`текста, которая определена в TCHAR. H, карты `stricoll`либо `wcsicoll`, `_mbsicoll`, или , в зависимости от набора символов, который определяется во время компиляции. Каждая функция выполняет нечувствительное сравнение строк, в соответствии с кодовой страницей, которая используется в настоящее время. Для получения дополнительной информации, [см strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

## <a name="cstringtcompare"></a><a name="compare"></a>CStringT::Сравните

Сравнивает две строки (дело чувствительное).

```
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>Параметры

*Psz*<br/>
Другая строка используется для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Ноль, если строки идентичны, `CStringT` < 0, если этот объект меньше, чем *psz,* или > 0, если этот `CStringT` объект больше, чем *psz*.

### <a name="remarks"></a>Remarks

Функция общего `_tcscmp`текста, которая определена в TCHAR. H, карты `strcmp`либо `wcscmp`, `_mbscmp`, или , в зависимости от набора символов, который определяется во время компиляции. Каждая функция выполняет чувствительное для случая сравнение строк и не зависит от локализации. Для получения дополнительной информации, [см strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).

Если строка содержит встроенные нули, для целей сравнения строка считается усеченной при первом встроенном нулевом символе.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CStringT::Compare`.

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

## <a name="cstringtcomparenocase"></a><a name="comparenocase"></a>CStringT::CompareNoCase

Сравнивает две строки (случай нечувствительный).

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*Psz*<br/>
Другая строка используется для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Ноль, если строки идентичны (игнорирование `CStringT` случая), <0, если этот объект `CStringT` меньше *PSZ* (игнорирование случая), или >0, если этот объект больше, чем *psz* (игнорирование случая).

### <a name="remarks"></a>Remarks

Функция общего `_tcsicmp`текста, которая определена в TCHAR. H, карты `_stricmp`либо `_wcsicmp` `_mbsicmp`, или , в зависимости от набора символов, который определяется во время компиляции. Каждая функция выполняет нечувствительное сравнение строк. Сравнение зависит от LC_CTYPE аспекта локализу, но не LC_COLLATE. Для получения дополнительной информации, см [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

## <a name="cstringtcstringt"></a><a name="cstringt"></a>CStringT::CstringT

Формирует объект `CStringT`.

```
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

*Pch*<br/>
Указатель на массив символов длины *nLength*, а не нулевой-завершены.

*nДлина*<br/>
Подсчет количества символов в *pch*.

*Ch*<br/>
Один символ.

*pszSrc*<br/>
Нулевая строка, которая будет `CStringT` скопирована в этот объект.

*pStringMgr*<br/>
Указатель на менеджер памяти `CStringT` объекта. Для получения `IAtlStringMgr` дополнительной информации `CStringT`и управления памятью для, см. [Управление памятью с CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

*strSrc*<br/>
Существующий `CStringT` объект, который должен `CStringT` быть скопирован в этот объект. Для получения `CThisString` дополнительной `CThisSimpleString`информации и , см.

*varSrc*<br/>
Вариант объекта, который будет `CStringT` скопирован в этот объект.

*BaseType*<br/>
Тип символа класса строки. Может применяться один из перечисленных ниже типов.

**символ** (для строк anSI символов).

**wchar_t** (для строк символов Unicode).

TCHAR (для строк символов ANSI и Unicode).

*bMFCDLL*<br/>
Boolean, который определяет, является ли проект MFC DLL (TRUE) или нет (FALSE).

*SystemString*<br/>
Должно `System::String`быть, и проект должен быть составлен с /clr.

*pString*<br/>
Ручка `CStringT` для объекта.

### <a name="remarks"></a>Remarks

Поскольку конструкторы копируют входные данные в новое выделенное хранилище, следует знать, что могут возникнуть исключения из памяти. Обратите внимание, что некоторые из этих конструкторов выступают в качестве функций преобразования. Это позволяет заменить, например, LPTSTR, где `CStringT` объект ожидается.

- `CStringT`( `LPCSTR` `lpsz` ): Строит Unicode `CStringT` из строки ANSI. Вы также можете использовать этот конструктор для загрузки ресурса строки, как показано в примере ниже.

- `CStringT(``LPCWSTR` Конструирует `CStringT` строку Unicode. `lpsz`

- `CStringT`(): `const unsigned char*` `psz` Позволяет построить `CStringT` от указателя до **неподписанного символа.**

> [!NOTE]
> Определите _CSTRING_DISABLE_NARROW_WIDE_CONVERSION макрос, чтобы отключить неявное преобразование строк между строками ANSI и Unicode. Макро исключает из конвейеров компиляции, поддерживающих преобразование.

Обратите внимание, что параметр *strSrc* может быть либо `CStringT` `CThisSimpleString` объектом. Для, `CStringT`использовать один из его моментов по умолчанию (`CString`, `CStringA`или `CStringW`); для, `CThisSimpleString`используйте **этот** указатель. `CThisSimpleString`объявляет экземпляр класса [CSimpleStringT,](../../atl-mfc-shared/reference/csimplestringt-class.md)который представляет собой меньший класс строк с `CStringT` менее встроенной функциональностью, чем класс.

Оператор перегрузки `CSimpleStringT<>&()` `CStringT` строит объект `CSimpleStringT` из декларации.

> [!NOTE]
> Хотя можно создавать `CStringT` экземпляры, содержащие встроенные символы null, мы рекомендуем против него. Методы вызова и `CStringT` операторы на объекты, содержащие встроенные нулевые символы, могут дать непреднамеренные результаты.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

## <a name="cstringtcstringt"></a><a name="_dtorcstringt"></a>CStringT:::CstringT

Уничтожает `CStringT` объект.

```
~CStringT() throw();
```

### <a name="remarks"></a>Remarks

Уничтожает `CStringT` объект.

## <a name="cstringtdelete"></a><a name="delete"></a>CStringT::Delete

Удаляет символ или символ ы из строки, начиная с персонажа в данном индексе.

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
Индекс нулевой основе первого символа в объекте `CStringT` для удаления.

*Ncount*<br/>
Количество символов, которые будут удалены.

### <a name="return-value"></a>Возвращаемое значение

Длина измененной строки.

### <a name="remarks"></a>Remarks

Если *nCount* длиннее строки, остальная часть строки будет удалена.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output
Before: Soccer is best,
    but hockey is quicker!
After: Soccer best,
    but hockey is quicker!
```

## <a name="cstringtfind"></a><a name="find"></a>CStringT::Найти

Поиск этой строки для первого совпадения персонажа или подстроки.

```
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>Параметры

*pszSub*<br/>
Подстрока для поиска.

*iStart*<br/>
Индекс персонажа в строке, чтобы начать поиск с, или 0, чтобы начать с самого начала.

*Ch*<br/>
Один символ для поиска.

### <a name="return-value"></a>Возвращаемое значение

Индекс на нулевой основе первого `CStringT` символа в этом объекте, который соответствует запрашиваемым подстрое или символам; -1, если подстрока или символ не найден.

### <a name="remarks"></a>Remarks

Функция перегружена, чтобы принимать как отдельные символы (по `strchr`аналогии с `strstr`функцией времени выполнения), так и строки (по аналогии с).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

## <a name="cstringtfindoneof"></a><a name="findoneof"></a>Cstringt:Findoneof

Поиск этой строки для первого символа, который соответствует любому символу, содержащемуся в *pszCharSet.*

```
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>Параметры

*pszCharSet*<br/>
Строка, содержащая символы для сопоставления.

### <a name="return-value"></a>Возвращаемое значение

Индекс на нулевой основе первого символа в этой строке, который также находится в *pszCharSet;* -1, если нет совпадений.

### <a name="remarks"></a>Remarks

Находит первое появление любого из символов в *pszCharSet*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

## <a name="cstringtformat"></a><a name="format"></a>CStringT::Формат

Записывает отформатированные данные `CStringT` таким же образом, чтобы [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) данные форматов в массив символов C-стиля.

```cpp
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>Параметры

*nФорматид*<br/>
Идентификатор строки ресурса, содержащий строку управления форматом.

*pszFormat*<br/>
Строка управления форматом.

*argument*<br/>
Необязательные аргументы.

### <a name="remarks"></a>Remarks

Эта функция форматирует и хранит ряд символов `CStringT`и значений в . Каждый дополнительный аргумент (если таковой имеется) преобразуется и выводится в соответствии с соответствующей спецификацией формата в *pszFormat* или из строки ресурса, идентифицированного *nFormatID.*

Вызов завершится неудачей, если сам объект `Format`строки предлагается в качестве параметра. Например, следующий код приведет к непредсказуемым результатам:

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

Дополнительные сведения см. в разделе [Синтаксис описания формата: функции printf и wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

## <a name="cstringtformatmessage"></a><a name="formatmessage"></a>CStringT::FormatMessage

Форматирует строку сообщения.

```cpp
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>Параметры

*nФорматид*<br/>
Идентификатор строки ресурса, содержащий неформатированный текст сообщения.

*pszFormat*<br/>
Указывает на строку управления форматом. Он будет отсканирован для вставок и отформатирован соответствующим образом. Строка формата аналогична строкам формата *printf-формата*выполнения, за исключением того, что она позволяет вставлять параметры в произвольном порядке.

*argument*<br/>
Необязательные аргументы.

### <a name="remarks"></a>Remarks

Функция требует определения сообщения как ввода. Определение сообщения определяется *pszFormat* или из строки ресурса, идентифицированного *nFormatID.* Функция копирует отформатированный текст `CStringT` сообщения объекту, обрабатывая любые встроенные последовательности вставок по запросу.

> [!NOTE]
> `FormatMessage`попытки выделить системную память для недавно отформатированных строк. Если эта попытка не удается, автоматически выбрасывается исключение памяти.

Каждая вставка должна иметь соответствующий параметр, следуя параметру *pszFormat* или *nFormatID.* В тексте сообщения поддерживается несколько последовательностей побега для динамического форматирования сообщения. Для получения дополнительной информации см. [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

## <a name="cstringtformatmessagev"></a><a name="formatmessagev"></a>CStringT::FormatMessageV

Форматирует строку сообщения с помощью списка переменных аргументов.

```cpp
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>Параметры

*pszFormat*<br/>
Указывает на строку управления форматом. Он будет отсканирован для вставок и отформатирован соответствующим образом. Строка формата аналогична строкам формата `printf`выполнения-времени, за исключением того, что она позволяет вставлять параметры в произвольном порядке.

*pArgList*<br/>
Указатель на список аргументов.

### <a name="remarks"></a>Remarks

Функция требует определения сообщения как ввода, определяемого *pszFormat*. Функция копирует отформатированный текст сообщения и переменный `CStringT` список аргументов объекту, обрабатывая любые встроенные последовательности вставок по запросу.

> [!NOTE]
> `FormatMessageV`вызывает [CStringT::FormatMessage](#formatmessage), который пытается выделить системную память для недавно отформатированных строк. Если эта попытка не удается, автоматически выбрасывается исключение памяти.

Для получения дополнительной информации см. [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage)

## <a name="cstringtformatv"></a><a name="formatv"></a>CStringT::FormatV

Форматирует строку сообщения с помощью списка переменных аргументов.

```cpp
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>Параметры

*pszFormat*<br/>
Указывает на строку управления форматом. Он будет отсканирован для вставок и отформатирован соответствующим образом. Строка формата аналогична строкам формата `printf`выполнения-времени, за исключением того, что она позволяет вставлять параметры в произвольном порядке.

*Args*<br/>
Указатель на список аргументов.

### <a name="remarks"></a>Remarks

Записывает отформатированную строку и переменный список аргументов к `CStringT` строке таким же образом, чтобы `vsprintf_s` они форматировались в массив символов c-стиля.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

## <a name="cstringtgetenvironmentvariable"></a><a name="getenvironmentvariable"></a>CStringT::GetEnvironmentVariable

Устанавливает строку к значению заданной переменной среды.

```
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>Параметры

*pszVar*<br/>
Указатель на строку с нулевым завершением, которая определяет переменную среды.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Извлекает значение указанной переменной из блока среды процесса вызова. Значение в виде нулевой строки символов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

## <a name="cstringtinsert"></a><a name="insert"></a>CStringT::Вставить

Вставляет один символ или подстроку в данный индекс в строку.

```
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
Индекс персонажа, перед которым будет происходить вставка.

*Psz*<br/>
Указатель на подстроку, которая будет вставлена.

*Ch*<br/>
Символ, который будет вставлен.

### <a name="return-value"></a>Возвращаемое значение

Длина измененной строки.

### <a name="remarks"></a>Remarks

Параметр *iIndex* определяет первый символ, который будет перемещен, чтобы освободить место для персонажа или подстроки. Если *nIndex* равен нулю, вставка произойдет до того, как вся строка. Если *nIndex* выше длины строки, функция будет concatenate настоящей строки и нового материала, предоставляемого либо *ch* или *PSZ*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

## <a name="cstringtleft"></a><a name="left"></a>CStringT::Слева

Извлекает из этого `CStringT` объекта самые левые символы *nCount* и возвращает копию извлеченной подстроки.

```
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>Параметры

*Ncount*<br/>
Число символов, извлекаемых из данного объекта `CStringT`.

### <a name="return-value"></a>Возвращаемое значение

Объект `CStringT`, содержащий копию указанного диапазона символов. Возвращенный объект `CStringT` может быть пустым.

### <a name="remarks"></a>Remarks

Если *nCount* превышает длину строки, то вся строка извлекается. Функция `Left` аналогична функции `Left` в языке Basic.

Для многобайных наборов символов (MBCS) *nCount* рассматривает каждую 8-битную последовательность как символ, так что *nCount* возвращает количество многобайных символов, умноженных на два.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

## <a name="cstringtloadstring"></a><a name="loadstring"></a>CStringT::LoadString

Читает ресурс строки Windows, идентифицированный *nID,* в существующий `CStringT` объект.

```
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Ручка к экземпляру модуля.

*nID*<br/>
Идентификатор строки Windows.

*wLanguageID*<br/>
Язык строки ресурса.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если нагрузка на ресурсы была успешной; в противном случае 0.

### <a name="remarks"></a>Remarks

Загружает строку ресурса *(nID*) из указанного модуля *(hInstance*) с помощью указанного языка *(wLanguage).*

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

## <a name="cstringtmakelower"></a><a name="makelower"></a>CStringT::MakeLower

Преобразует `CStringT` объект в строку нижнего регистра.

```
CStringT& MakeLower();
```

### <a name="return-value"></a>Возвращаемое значение

Полученная строка нижнего регистра.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

## <a name="cstringtmakereverse"></a><a name="makereverse"></a>CStringT::MakeReverse

Обратный порядок символов в `CStringT` объекте.

```
CStringT& MakeReverse();
```

### <a name="return-value"></a>Возвращаемое значение

Полученная обратная строка.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

## <a name="cstringtmakeupper"></a><a name="makeupper"></a>CStringT::MakeUpper

Преобразует `CStringT` объект в строку верхнего регистра.

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>Возвращаемое значение

Полученная верхняя строка.

### <a name="remarks"></a>Remarks

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

## <a name="cstringtmid"></a><a name="mid"></a>CStringT::Mid

Извлекает из этого `CStringT` объекта подстроку символов длины *nCount,* начиная с позиции *iFirst* (нулевая).

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>Параметры

*iFirst*<br/>
Индекс на нулевой основе первого `CStringT` символа в этом объекте, который должен быть включен в извлеченную подстроку.

*Ncount*<br/>
Число символов, извлекаемых из данного объекта `CStringT`. Если этот параметр не поставляется, то остальная часть строки извлекается.

### <a name="return-value"></a>Возвращаемое значение

Объект `CStringT`, содержащий копию указанного диапазона символов. Обратите внимание, `CStringT` что возвращенный объект может быть пустым.

### <a name="remarks"></a>Remarks

Функция возвращает копию извлеченной подстроки. `Mid`похож на функцию Basic Mid (за исключением того, что индексы в Basic основаны на одном).

Для наборов мультибайт символов (MBCS) *nCount* относится к каждому 8-битному символу; то есть, свинец и след байт в одном мультибайтном символе считаются двумя символами.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

## <a name="cstringtoemtoansi"></a><a name="oemtoansi"></a>CStringT::OemToAnsi

Преобразует все символы этого `CStringT` объекта из набора символов OEM в набор символов ANSI.

```cpp
void OemToAnsi();
```

### <a name="remarks"></a>Remarks

Эта функция недоступна, если _UNICODE определена.

### <a name="example"></a>Пример

Смотрите пример [для CStringT::AnsiToOem](#ansitooem).

## <a name="cstringtoperator-"></a><a name="operator_eq"></a>CStringT::оператор

Присваивает строке новое значение.

```
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

*strSrc*<br/>
A, `CStringT` чтобы назначить эту строку.

*Ул*<br/>
Ссылка на объект `CThisSimpleString`.

*bMFCDLL*<br/>
Булеан уточняет, является ли проект MFC DLL или нет.

*BaseType*<br/>
Тип основания строки.

*var*<br/>
Вариант объекта, чтобы назначить этой строке.

*Ch*<br/>
Символ ANSI или Unicode для присвоения строке.

*pszSrc*<br/>
Указатель на выделенную исходную строку.

### <a name="remarks"></a>Remarks

Оператор назначения принимает `CStringT` другой объект, указатель символов или один символ. Вы должны знать, что исключения памяти могут возникать всякий раз, когда вы используете этого оператора, потому что новое хранилище может быть выделено.

Для получения `CThisSimpleString`информации о , см. Замечания разделе [CStringT::CStringT](#cstringt).

> [!NOTE]
> Хотя можно создавать `CStringT` экземпляры, содержащие встроенные символы null, мы рекомендуем против него. Методы вызова и `CStringT` операторы на объекты, содержащие встроенные нулевые символы, могут дать непреднамеренные результаты.

## <a name="cstringtoperator-"></a><a name="operator_add"></a>CStringT::оператор

Конкатирует две строки или символ и строку.

```
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```

### <a name="parameters"></a>Параметры

*ch1*<br/>
Символ ANSI или Unicode для совмещения со строкой.

*ch2*<br/>
Символ ANSI или Unicode для совмещения со строкой.

*str1*<br/>
A `CStringT` для того чтобы concatenate с шнуром или характером.

*str2*<br/>
A `CStringT` для того чтобы concatenate с шнуром или характером.

*psz1*<br/>
Указатель на нулевую строку для совмещении со строкой или символом.

*psz2*<br/>
Указатель на строку, чтобы спутать со строкой или символом.

### <a name="remarks"></a>Remarks

Существует семь форм перегрузки функции. `CStringT::operator+` Первая версия конкатирует `CStringT` два существующих объекта. Следующие два concatenate `CStringT` объекта и нулевой-прекратить строку. Следующие два concatenate `CStringT` объекта и anANSI характер. Последние два concatenate `CStringT` объекта и unicode символ.

> [!NOTE]
> Хотя можно создавать `CStringT` экземпляры, содержащие встроенные символы null, мы рекомендуем против него. Методы вызова и `CStringT` операторы на объекты, содержащие встроенные нулевые символы, могут дать непреднамеренные результаты.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_add_eq"></a>CStringT::оператор

Конкатирует символы до конца строки.

```
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

*Ул*<br/>
Ссылка на объект `CThisSimpleString`.

*bMFCDLL*<br/>
Булеан уточняет, является ли проект MFC DLL или нет.

*BaseType*<br/>
Тип основания строки.

*var*<br/>
Вариант объекта для concatenate к этой строке.

*Ch*<br/>
Символ ANSI или Unicode для совмещения со строкой.

*pszSrc*<br/>
Указатель на исходную строку, сопутствуемую.

*strSrc*<br/>
A, `CStringT` чтобы примириться с этой строкой.

### <a name="remarks"></a>Remarks

Оператор принимает другой `CStringT` объект, указатель символов или один символ. Вы должны знать, что исключения памяти могут возникать всякий раз, когда вы используете `CStringT` этот оператор конкатации, потому что новое хранилище может быть выделено для символов, добавленных к этому объекту.

Для получения `CThisSimpleString`информации о , см. Замечания разделе [CStringT::CStringT](#cstringt).

> [!NOTE]
> Хотя можно создавать `CStringT` экземпляры, содержащие встроенные символы null, мы рекомендуем против него. Методы вызова и `CStringT` операторы на объекты, содержащие встроенные нулевые символы, могут дать непреднамеренные результаты.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_eq_eq"></a>CStringT::оператор

Определяет, являются ли две строки логически равными.

```
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>Параметры

*ch1*<br/>
Для сравнения символ ANSI или Unicode.

*ch2*<br/>
Для сравнения символ ANSI или Unicode.

*str1*<br/>
А `CStringT` для сравнения.

*str2*<br/>
А `CStringT` для сравнения.

*psz1*<br/>
Указатель на нулевую строку для сравнения.

*psz2*<br/>
Указатель на нулевую строку для сравнения.

### <a name="remarks"></a>Remarks

Тестирует ли строка или символ на левой стороне равно строке или символу на правой стороне, и возвращает true или FALSE соответственно.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_neq"></a>CStringT::оператор !

Определяет, являются ли две строки логически не равными.

```
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>Параметры

*ch1*<br/>
Символ ANSI или Unicode для совмещения со строкой.

*ch2*<br/>
Символ ANSI или Unicode для совмещения со строкой.

*str1*<br/>
А `CStringT` для сравнения.

*str2*<br/>
А `CStringT` для сравнения.

*psz1*<br/>
Указатель на нулевую строку для сравнения.

*psz2*<br/>
Указатель на нулевую строку для сравнения.

### <a name="remarks"></a>Remarks

Тесты, если строка или символ на левой стороне не равна строке или символу на правой стороне.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

## <a name="cstringtoperator-lt"></a><a name="operator_lt"></a>CStringT::оператор&lt;

Определяет, является ли строка на левой стороне оператора меньше, чем строка на правой стороне.

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
А `CStringT` для сравнения.

*str2*<br/>
А `CStringT` для сравнения.

*psz1*<br/>
Указатель на нулевую строку для сравнения.

*psz2*<br/>
Указатель на нулевую строку для сравнения.

### <a name="remarks"></a>Remarks

Лексикографическое сравнение строк, характер по характеру до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

## <a name="cstringtoperator-gt"></a><a name="operator_gt"></a>CStringT::оператор&gt;

Определяет, является ли строка на левой стороне оператора больше, чем строка на правой стороне.

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
А `CStringT` для сравнения.

*str2*<br/>
А `CStringT` для сравнения.

*psz1*<br/>
Указатель на нулевую строку для сравнения.

*psz2*<br/>
Указатель на нулевую строку для сравнения.

### <a name="remarks"></a>Remarks

Лексикографическое сравнение строк, характер по характеру до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

## <a name="cstringtoperator-lt"></a><a name="operator_lt_eq"></a>CStringT::оператор&lt;=

Определяет, является ли строка на левой стороне оператора меньше или равна строке на правой стороне.

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
А `CStringT` для сравнения.

*str2*<br/>
А `CStringT` для сравнения.

*psz1*<br/>
Указатель на нулевую строку для сравнения.

*psz2*<br/>
Указатель на нулевую строку для сравнения.

### <a name="remarks"></a>Remarks

Лексикографическое сравнение строк, характер по характеру до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

## <a name="cstringtoperator-gt"></a><a name="operator_gt_eq"></a>CStringT::оператор&gt;=

Определяет, является ли строка на левой стороне оператора больше или равна строке на правой стороне.

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
А `CStringT` для сравнения.

*str2*<br/>
А `CStringT` для сравнения.

*psz1*<br/>
Указатель на строку для сравнения.

*psz2*<br/>
Указатель на строку для сравнения.

### <a name="remarks"></a>Remarks

Лексикографическое сравнение строк, характер по характеру до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

## <a name="cstringtremove"></a><a name="remove"></a>CStringT::Удалить

Удаляет все экземпляры указанного символа из строки.

```
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>Параметры

*chRemove*<br/>
Персонаж, который будет удален из строки.

### <a name="return-value"></a>Возвращаемое значение

Количество символов удалено из строки. Ноль, если строка не изменена.

### <a name="remarks"></a>Remarks

Сравнения для характера чувствительны к случаю.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

## <a name="cstringtreplace"></a><a name="replace"></a>CStringT::Замена

Есть две версии `Replace`. Первая версия заменяет одну или несколько копий подстроки с помощью другой подстроки. Обе подстроки незавершены. Вторая версия заменяет одну или несколько копий персонажа с помощью другого символа. Обе версии работают на `CStringT`данных о символах, хранящихся в .

```
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>Параметры

*pszOld*<br/>
Указатель на нулевую строку, которая будет заменена *pszNew*.

*pszNew*<br/>
Указатель на нулевую строку, которая заменяет *pszOld.*

*chOld*<br/>
Персонаж, который будет заменен *chNew*.

*chNew*<br/>
Персонаж, заменяющий *chOld*.

### <a name="return-value"></a>Возвращаемое значение

Возвращает число замененных экземпляров символа или подстроки, или ноль, если строка не изменена.

### <a name="remarks"></a>Remarks

`Replace`может изменять длину строки, потому что *pszNew* и *pszOld* не должны быть одинаковой длины, и несколько копий старой подстроки могут быть изменены на новый. Функция выполняет матч, чувствительный к инциденту.

Примеры `CStringT` `CString`экземпляров, `CStringA`и `CStringW`.

`CStringA`Для, `Replace` работает с ANSI или мультибайт (MBCS) символов. Для `CStringW` `Replace` , работает с широкими символами.

Для `CString`, тип данных символа выбирается во время компиляции, в зависимости от того, определены ли константы в следующей таблице.

|Определено константа|Тип данных персонажей|
|----------------------|-------------------------|
|_UNICODE|Расширенные символы|
|_MBCS|Многобайтные символы|
|Нет|Однобайные символы|
|both|Не определено.|

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

## <a name="cstringtreversefind"></a><a name="reversefind"></a>CStringT::Обратныйисточник

Поиск `CStringT` этого объекта для последнего матча персонажа.

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>Параметры

*Ch*<br/>
Персонаж для поиска.

### <a name="return-value"></a>Возвращаемое значение

Индекс последнего символа на нулевом уровне, `CStringT` который соответствует запрашиваемому символу, или -1, если символ не найден.

### <a name="remarks"></a>Remarks

Функция аналогична функции `strrchr`времени выполнения.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

## <a name="cstringtright"></a><a name="right"></a>CStringT::Право

Извлекает последние (т.е. справа) *nCount* символов из этого `CStringT` объекта и возвращает копию извлеченных подстроки.

```
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>Параметры

*Ncount*<br/>
Число символов, извлекаемых из данного объекта `CStringT`.

### <a name="return-value"></a>Возвращаемое значение

Объект `CStringT`, содержащий копию указанного диапазона символов. Обратите внимание, `CStringT` что возвращенный объект может быть пустым.

### <a name="remarks"></a>Remarks

Если *nCount* превышает длину строки, то вся строка извлекается. `Right`похож на функцию Basic `Right` (за исключением того, что индексы в Basic на нулевом уровне).

Для наборов мультибайт символов (MBCS) *nCount* относится к каждому 8-битному символу; то есть, свинец и след байт в одном мультибайтном символе считаются двумя символами.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

## <a name="cstringtsetsysstring"></a><a name="setsysstring"></a>CStringT::SetSysString

Перераспределяет BSTR, на который указывает *pbstr,* `CStringT` и копирует содержимое объекта в него, включая символ NULL.

```
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>Параметры

*pbstr*<br/>
Указатель на строку персонажа.

### <a name="return-value"></a>Возвращаемое значение

Новая строка.

### <a name="remarks"></a>Remarks

В зависимости от `CStringT` содержимого объекта значение BSTR, на который ссылается *pbstr,* может меняться. Функция бросает, `CMemoryException` если недостаточно памяти существует.

Эта функция обычно используется для изменения значения строк, передаваемых ссылкой для Automation.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

## <a name="cstringtspanexcluding"></a><a name="spanexcluding"></a>CStringT::SpanExcluding

Извлекает символы из строки, начиная с первого символа, которые не входят в набор символов, идентифицированных *pszCharSet*.

```
CStringT SpanExcluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Параметры

*pszCharSet*<br/>
Строка интерпретируется как набор символов.

### <a name="return-value"></a>Возвращаемое значение

Подстрока, которая содержит символы в строке, которые не находятся в *pszCharSet*, начиная с первого символа в строке и заканчивая первым персонажем, найденным в строке, которая также находится в *pszCharSet* (то есть, начиная с первого персонажа в строке и до, но исключая первого персонажа в строке, которая находится *pszCharSet*). Он возвращает всю строку, если в строке нет символа в *pszCharSet.*

### <a name="remarks"></a>Remarks

`SpanExcluding`извлекает и возвращает все символы, предшествующие первому появлению персонажа из *pszCharSet* (другими словами, символ из *pszCharSet* и все символы, следующие за ним в строке, не возвращаются). Если в строке нет символа из *pszCharSet,* то `SpanExcluding` возвращается вся строка.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

## <a name="cstringtspanincluding"></a><a name="spanincluding"></a>CStringT::SpanIncluding

Извлекает символы из строки, начиная с первого символа, которые находятся в наборе символов, определенных *pszCharSet*.

```
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Параметры

*pszCharSet*<br/>
Строка интерпретируется как набор символов.

### <a name="return-value"></a>Возвращаемое значение

Подстрока, содержащая символы в строке, которые находятся в *pszCharSet*, начиная с первого символа в строке и заканчивая, когда символ находится в строке, которая не находится в *pszCharSet.* `SpanIncluding`возвращает пустую подстроку, если первый символ строки не находится в указанном наборе.

### <a name="remarks"></a>Remarks

Если первый символ строки не находится в `SpanIncluding` наборе символов, то возвращаетпустую строку. В противном случае он возвращает последовательность последовательных символов, которые находятся в наборе.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

## <a name="cstringttokenize"></a><a name="tokenize"></a>Cstringt::Tokenize

Поиск следующего маркера в целевой строке

```
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const;
```

### <a name="parameters"></a>Параметры

*pszTokens*<br/>
Строка, содержащая делимитед маркеров. Порядок этих делимитеров не имеет значения.

*iStart*<br/>
Для начала поиска индекс с нулевым уровнем.

### <a name="return-value"></a>Возвращаемое значение

Объект, `CStringT` содержащий текущее значение маркера.

### <a name="remarks"></a>Remarks

Функция `Tokenize` находит следующий маркер в целевой строке. Набор символов в *pszTokens* определяет возможные делимитемые маркеры, которые будут найдены. При каждом `Tokenize` вызове к функции начинается *с iStart,* `CStringT` пропускает ведущие делимитемые системы и возвращает объект, содержащий ток маркер, который представляет собой строку символов до следующего символа делимитера. Значение *iStart* обновляется в соответствии с положением после символа делимитемых окончаний или -1, если конец строки был достигнут. Больше токенов может быть разбито из оставшейся части целевой строки серией `Tokenize`вызовов, используя *iStart,* чтобы отслеживать, где в строке следующий маркер должен быть прочитан. Когда нет больше токенов, функция вернет пустую строку и *iStart* будет установлен на -1.

В отличие от функций токенизации CRT, таких как `Tokenize` [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l,](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)не изменяет целевую строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>Remarks

Выход из этого примера заключается в следующем:

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

## <a name="cstringttrim"></a><a name="trim"></a>CStringT::Trim

Обрезки ведущих и задних символов из строки.

```
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>Параметры

*chTarget*<br/>
Целевой символ, который будет обрезан.

*pszTargets*<br/>
Указатель на строку, содержащую целевые символы, которые должны быть обрезаны. Все ведущие и задние случаи символов в *pszTarget* будут обрезаны `CStringT` с объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обрезанную строку.

### <a name="remarks"></a>Remarks

Удаляет все ведущие и задние случаи одного из следующих:

- Характер, указанный *chTarget*.

- Все символы, найденные в строке, указанной *pszTargets*.

- Пробелы.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>Remarks

Выход из этого примера заключается в следующем:

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

## <a name="cstringttrimleft"></a><a name="trimleft"></a>CStringT::Trimleft

Обрезки ведущих персонажей из строки.

```
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>Параметры

*chTarget*<br/>
Целевой символ, который будет обрезан.

*pszTargets*<br/>
Указатель на строку, содержащую целевые символы, которые должны быть обрезаны. Все ведущие случаи символов в *pszTarget* будут `CStringT` обрезаны с объекта.

### <a name="return-value"></a>Возвращаемое значение

Полученная подстриженная строка.

### <a name="remarks"></a>Remarks

Удаляет все ведущие и задние случаи одного из следующих:

- Характер, указанный *chTarget*.

- Все символы, найденные в строке, указанной *pszTargets*.

- Пробелы.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

## <a name="cstringttrimright"></a><a name="trimright"></a>CStringT::TrimRight

Обрезки задних символов из строки.

```
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>Параметры

*chTarget*<br/>
Целевой символ, который будет обрезан.

*pszTargets*<br/>
Указатель на строку, содержащую целевые символы, которые должны быть обрезаны. Все задняющие случаи символов в *pszTarget* `CStringT` будут обрезаны с объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CStringT` объект, содержащий обрезанную строку.

### <a name="remarks"></a>Remarks

Удаляет запоздалые случаи одного из следующих:

- Характер, указанный *chTarget*.

- Все символы, найденные в строке, указанной *pszTargets*.

- Пробелы.

Версия `CStringT& TrimRight(XCHAR chTarget)` принимает один параметр символа и удаляет все копии `CStringT` этого символа из конца строки данных. Она начинается с конца строки и работает в сторону фронта. Он останавливается, когда находит `CSTringT` другой символ или когда заканчиваются данные о символе.

Версия `CStringT& TrimRight(PCXSTR pszTargets)` принимает строку с нулевым завершением, которая содержит все различные символы для поиска. Он удаляет все копии этих символов в объекте. `CStringT` Она начинается в конце строки и работает в направлении фронта. Он останавливается, когда находит символ, которого нет `CStringT` в целевой строке, или когда заканчиваются данные о символе. Он не пытается сопоставить всю целевую строку `CStringT`с подстрокой в конце .

Версия `CStringT& TrimRight()` не требует параметров. Он обрезает любые задние символы `CStringT` белого пространства с конца строки. Символы Whitespace могут быть разрывами строк, пробелами или вкладками.

-

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
[Класс CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)
