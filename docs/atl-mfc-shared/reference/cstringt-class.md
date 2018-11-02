---
title: Класс CStringT
ms.date: 10/18/2018
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
ms.openlocfilehash: 28b2f929e9f8695904bcd3f02dd2d315ab3ca349
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483412"
---
# <a name="cstringt-class"></a>Класс CStringT

Этот класс представляет `CStringT` объекта.

## <a name="syntax"></a>Синтаксис

```

template<typename BaseType, class StringTraits>
class CStringT :
public CSimpleStringT<BaseType,
                      _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                      ::c_bIsMFCDLLTraits>

```

#### <a name="parameters"></a>Параметры

*BaseType*<br/>
Тип символа класса string. Ниже указаны доступные значения.

- **char** (для символьных строк ANSI).

- **wchar_t** (для символьных строк в Юникоде).

- TCHAR (для символьных строк ANSI и Юникода).

*StringTraits*<br/>
Определяет, должен ли класс string поддержка библиотек времени выполнения C (CRT) и где расположены строковые ресурсы. Ниже указаны доступные значения.

- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**

   Требует поддержки CRT и поиск ресурсов строк в модуль, указанный параметром `m_hInstResource` (член класса модуля приложения).

- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**

   Класс не требуется поддержка CRT и поиск ресурсов строк в модуль, указанный параметром `m_hInstResource` (член класса модуля приложения).

- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**

   Класс требуется поддержка CRT и ищет строки ресурсов, используя стандартный алгоритм поиска MFC.

- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**

   Класс не требуется поддержка CRT и ищет строки ресурсов, используя стандартный алгоритм поиска MFC.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStringT::CStringT](#cstringt)|Создает `CStringT` объект по-разному.|
|[CStringT:: ~ CStringT](#_dtorcstringt)|Уничтожает объект `CStringT`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStringT::AllocSysString](#allocsysstring)|Выделяет строку BSTR из `CStringT` данных.|
|[CStringT::AnsiToOem](#ansitooem)|Производится преобразование на месте из кодировки ANSI в набор символов OEM.|
|[CStringT::AppendFormat](#appendformat)|Добавляет форматированных данных в существующий `CStringT` объекта.|
|[CStringT::Collate](#collate)|Сравнивает две строки (регистр, зависящие от языкового стандарта использует).|
|[CStringT::CollateNoCase](#collatenocase)|Сравнивает две строки (без учета регистра, зависящие от языкового стандарта использует).|
|[CStringT::Compare](#compare)|Сравнивает две строки (с учетом регистра).|
|[CStringT::CompareNoCase](#comparenocase)|Сравнивает две строки (без учета регистра).|
|[CStringT::Delete](#delete)|Удаляет символ или символы из строки.|
|[CStringT::Find](#find)|Находит символ или подстроку в строку большего размера.|
|[CStringT::FindOneOf](#findoneof)|Находит первый соответствующий символ из набора.|
|[CStringT::Format](#format)|Форматирует строку в качестве `sprintf` does.|
|[CStringT::FormatMessage](#formatmessage)|Форматирует строку сообщения.|
|[CStringT::FormatMessageV](#formatmessagev)|Форматирует строку сообщения, используя переменное число аргументов.|
|[CStringT::FormatV](#formatv)|Форматирует строки с использованием переменный список аргументов.|
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Задает строку, чтобы значение указанной переменной среды.|
|[CStringT::Insert](#insert)|Вставляет один символ или подстроку по заданному индексу в строке.|
|[CStringT::Left](#left)|Извлекает левую часть строки.|
|[CStringT::LoadString](#loadstring)|Загружает существующий `CStringT` из ресурса Windows.|
|[CStringT::MakeLower](#makelower)|Преобразует все символы в эту строку в символы нижнего регистра.|
|[CStringT::MakeReverse](#makereverse)|Отменяет строку.|
|[CStringT::MakeUpper](#makeupper)|Преобразует все символы в эту строку в верхний регистр.|
|[CStringT::Mid](#mid)|Извлекает средней части строки.|
|[CStringT::OemToAnsi](#oemtoansi)|Производится преобразование на месте из набора для набора символов ANSI символов OEM.|
|[CStringT::Remove](#remove)|Удаляет указанных символов из строки.|
|[CStringT::Replace](#replace)|Заменяет указанный символы и другие символы.|
|[CStringT::ReverseFind](#reversefind)|Находит символ в строку большего размера; начинается с конца.|
|[CStringT::Right](#right)|Извлекает правую часть строки.|
|[CStringT::SetSysString](#setsysstring)|Задает существующий объект BSTR с данными из `CStringT` объекта.|
|[CStringT::SpanExcluding](#spanexcluding)|Извлекает символы из строки, начиная с первого символа, не вошедших в набор символов, идентифицируемый `pszCharSet`.|
|[CStringT::SpanIncluding](#spanincluding)|Извлекает подстроку, которая содержит только символы в наборе.|
|[CStringT::Tokenize](#tokenize)|Извлекает указанный маркеры в целевой строке.|
|[CStringT::Trim](#trim)|Удаляет все начальные и конечные пробелы из строки.|
|[CStringT::TrimLeft](#trimleft)|Обрезка начальные пробелы из строки.|
|[CStringT::TrimRight](#trimright)|Обрезка конечные символы пробела в строке.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор =](#operator_eq)|Назначает новое значение для `CStringT` объекта.|
|[CStringT::operator +](#operator_add)|Сцепляет две строки или символ и строку.|
|[CStringT::operator +=](#operator_add_eq)|Сцепляет новую строку в конец существующей строки.|
|[CStringT::operator ==](#operator_eq_eq)|Определяет, логически равны ли две строки.|
|[CStringT::operator! =](#operator_neq)|Определяет, являются ли две строки логически не равны.|
|[CStringT::operator &lt;](#operator_lt)|Определяет, является ли строка в левой части оператора меньше, чем к строке справа от оператора.|
|[CStringT::operator &gt;](#operator_gt)|Определяет, является ли строка слева от оператора больше, чем к строке справа от оператора.|
|[CStringT::operator &lt;=](#operator_lt_eq)|Определяет, является ли строка в левой части оператора меньше или равны строке справа от оператора.|
|[CStringT::operator &gt;=](#operator_gt_eq)|Определяет, является ли строка слева от оператора больше или равны строке справа от оператора.|

## <a name="remarks"></a>Примечания

`CStringT` наследует от [класс CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md). Расширенные функции, такие как символ манипуляции, упорядочение и поиск, реализуются `CStringT`.

> [!NOTE]
> `CStringT` объекты способны исключения. Это происходит, когда `CStringT` объекта не хватает памяти для какой-либо причине.

Объект `CStringT` объект состоит из последовательности переменной длины из символов. `CStringT` предоставляет функции и операторы, используя синтаксис аналогичен Basic. Объединение и операторы сравнения, вместе с управления памятью упрощенный, `CStringT` проще в использовании, чем обычный символ массивов объектов.

> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляров, которые содержат внедренные символы null, мы не рекомендуем включать его. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы null может привести к непредвиденным результатам.

С помощью различных сочетаний `BaseType` и `StringTraits` параметров, `CStringT` объектов можно поставляются в следующие типы, которые являются предопределенные библиотек ATL.

При использовании в приложении ATL:

`CString`, `CStringA`, и `CStringW` экспортируются из библиотеки DLL MFC (MFC90. Библиотека DLL), никогда не от пользователя библиотеки DLL. Это делается во избежание `CStringT` из определен несколько раз.

> [!NOTE]
>  Если код содержит инструкции по решению для ошибки компоновщика, которые описаны в [Экспорт CStringT с помощью классов строка](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md), следует удалить этот код. Больше не используется.

В приложениях MFC доступны следующие строки:

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CStringA`|Знак ANSI введите строку с поддержкой CRT.|
|`CStringW`|Символ Юникода типа string с поддержкой CRT.|
|`CString`|ANSI и Юникод символьных типов с поддержкой CRT.|

Следующие строки доступны в проектах, где определяется ATL_CSTRING_NO_CRT:

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CAtlStringA`|Знак ANSI введите строку без поддержки CRT.|
|`CAtlStringW`|Символ Юникода типа string, не поддерживающих CRT.|
|`CAtlString`|ANSI и Юникод символьные типы без поддержки CRT.|

Следующие строки доступны в проектах, где ATL_CSTRING_NO_CRT не определен:

|Тип CStringT|Объявление|
|-------------------|-----------------|
|`CAtlStringA`|Знак ANSI введите строку с поддержкой CRT.|
|`CAtlStringW`|Символ Юникода типа string с поддержкой CRT.|
|`CAtlString`|ANSI и Юникод символьных типов с поддержкой CRT.|

`CString` объекты также имеют следующие характеристики:

- `CStringT` объекты могут увеличиваться в результате операции объединения.

- `CStringT` объекты следуют «value семантики.» Можно рассматривать `CStringT` объект как фактический строку, а не как указатель на строку.

- Можно свободно использовать `CStringT` объектов для `PCXSTR` аргументы функций.

- Управление памятью пользовательских для буферы строк. Дополнительные сведения см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="cstringt-predefined-types"></a>CStringT предопределенных типов

Так как `CStringT` использует аргумент шаблона, чтобы определить тип символа (либо [wchar_t](../../c-runtime-library/standard-types.md) или [char](../../c-runtime-library/standard-types.md)) поддерживается, типы параметров метода, может быть затруднена время от времени. Чтобы упростить эту проблему, определяется и используется на протяжении всего набора предопределенных типов `CStringT` класса. В следующей таблице перечислены различные типы:

|name|Описание|
|----------|-----------------|
|`XCHAR`|Один символ (либо **wchar_t** или **char**) с помощью символа совпадает с типом `CStringT` объекта.|
|`YCHAR`|Один символ (либо **wchar_t** или **char**) с противоположной символьным типом как `CStringT` объекта.|
|`PXSTR`|Указатель на строку символов (либо **wchar_t** или **char**) с помощью символа совпадает с типом `CStringT` объекта.|
|`PYSTR`|Указатель на строку символов (либо **wchar_t** или **char**) с противоположной символьным типом как `CStringT` объекта.|
|`PCXSTR`|Указатель на **const** строка символов (либо **wchar_t** или **char**) с помощью символа совпадает с типом `CStringT` объекта.|
|`PCYSTR`|Указатель на **const** строка символов (либо **wchar_t** или **char**) с противоположной символьным типом как `CStringT` объекта.|

> [!NOTE]
>  Код, который ранее использовал недокументированные методы `CString` (такие как `AssignCopy`) необходимо заменить код, который использует следующие методы документированных `CStringT` (такие как `GetBuffer` или `ReleaseBuffer`). Эти методы наследуются от `CSimpleStringT`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>Требования

|Header|Используйте для|
|------------|-------------|
|CStringT.h|MFC-только для строковых объектов|
|atlstr.h|Не-MFC строковых объектов|

##  <a name="allocsysstring"></a>  CStringT::AllocSysString

Выделяет строку совместимые с автоматизацией типа BSTR и копирует содержимое объекта `CStringT` объекта, включая завершающий нуль-символ.

```
BSTR AllocSysString() const;
```

### <a name="return-value"></a>Возвращаемое значение

Только что выделенную строку.

### <a name="remarks"></a>Примечания

В приложениях MFC [класс CMemoryException](../../mfc/reference/cmemoryexception-class.md) возникает исключение, если существует нехватки памяти. В программах ATL [CAtlException](../../atl/reference/catlexception-class.md) возникает исключение. Эта функция обычно используется для возврата строки для автоматизации.

Обычно если эта строка передается в функцию COM как [in] параметр, то это требует, чтобы освободить строку участник. Это можно сделать с помощью [SysFreeString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysfreestring), как описано в пакете Windows SDK. Дополнительные сведения см. в разделе [распределение и освобождение памяти для BSTR](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).

Дополнительные сведения о функции выделения OLE в Windows, см. в разделе [SysAllocString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysallocstring) в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CStringT::AllocSysString`.

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

##  <a name="ansitooem"></a>  CStringT::AnsiToOem

Преобразует все символы в этом `CStringT` объекта из кодировки ANSI в набор символов OEM.

```
void AnsiToOem();
```

### <a name="remarks"></a>Примечания

Функция недоступна, если определяется _UNICODE.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

##  <a name="appendformat"></a>  CStringT::AppendFormat

Добавляет форматированных данных в существующий `CStringT` объекта.

```
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>Параметры

*pszFormat*<br/>
Строка управления форматом.

*nFormatID*<br/>
Строковый идентификатор ресурса, содержащего строку управления форматом.

*Аргумент*<br/>
Необязательные аргументы.

### <a name="remarks"></a>Примечания

Эта функция форматирует и добавляет серию символов и значений в `CStringT`. Каждый необязательный аргумент (если есть) преобразуется и добавляется в соответствии со спецификацией формата в *pszFormat* или из строкового ресурса, идентифицируемый *nFormatID*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

##  <a name="collate"></a>  CStringT::Collate

Сравнивает две строки с использованием универсальная текстовая функция `_tcscoll`.

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*psz*<br/>
Другая строка, используемый для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны, < 0, если это `CStringT` объект меньше, чем *psz*, или > 0, если это `CStringT` объект больше, чем *psz*.

### <a name="remarks"></a>Примечания

Универсальная текстовая функция `_tcscoll`, который определен в TCHAR. H, сопоставляется либо `strcoll`, `wcscoll`, или `_mbscoll`в зависимости от набор символов, которое определяется во время компиляции. Каждая функция выполняет сравнение с учетом регистра строк согласно кодовой странице, в настоящее время используется. Дополнительные сведения см. в разделе [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

##  <a name="collatenocase"></a>  CStringT::CollateNoCase

Сравнивает две строки с использованием универсальная текстовая функция `_tcscoll`.

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*psz*<br/>
Другая строка, используемый для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны (без учета регистра букв), < 0, если это `CStringT` объект меньше, чем *psz* (без учета регистра), или > 0, если это `CStringT` объект больше, чем *psz* (без учета регистра).

### <a name="remarks"></a>Примечания

Универсальная текстовая функция `_tcscoll`, который определен в TCHAR. H, сопоставляется либо `stricoll`, `wcsicoll`, или `_mbsicoll`в зависимости от набор символов, которое определяется во время компиляции. Каждая функция выполняет сравнение без учета регистра строк, в соответствии с кодовой странице в настоящий момент. Дополнительные сведения см. в разделе [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

##  <a name="compare"></a>  CStringT::Compare

Сравнивает две строки (с учетом регистра).

```
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>Параметры

*psz*<br/>
Другая строка, используемый для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны, < 0, если это `CStringT` объект меньше, чем *psz*, или > 0, если это `CStringT` объект больше, чем *psz*.

### <a name="remarks"></a>Примечания

Универсальная текстовая функция `_tcscmp`, который определен в TCHAR. H, сопоставляется либо `strcmp`, `wcscmp`, или `_mbscmp`в зависимости от набор символов, которое определяется во время компиляции. Каждая функция выполняет сравнение с учетом регистра строк и не зависит от языкового стандарта. Дополнительные сведения см. в разделе [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).

Если строка содержит внедренные значения NULL, для сравнения строки считается усечено до первого внедренный символ null.

### <a name="example"></a>Пример

В следующем примере показано использование функции `CStringT::Compare`.

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

##  <a name="comparenocase"></a>  CStringT::CompareNoCase

Сравнивает две строки (без учета регистра).

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Параметры

*psz*<br/>
Другая строка, используемый для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны (без учета регистра), < 0, если это `CStringT` объект меньше, чем *psz* (без учета регистра), или > 0, если это `CStringT` объект больше, чем *psz* (без учета регистра).

### <a name="remarks"></a>Примечания

Универсальная текстовая функция `_tcsicmp`, который определен в TCHAR. H, сопоставляется либо `_stricmp`, `_wcsicmp` или `_mbsicmp`в зависимости от набор символов, которое определяется во время компиляции. Каждая функция выполняет сравнение без учета регистра строк. Сравнение зависит от LC_CTYPE аспектом языкового стандарта, но не LC_COLLATE. Дополнительные сведения см. в разделе [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

##  <a name="cstringt"></a>  CStringT::CStringT

Создает объект `CStringT`.

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

*PCH*<br/>
Указатель на массив символов длиной *nLength*, не оканчивается символом null.

*nLength*<br/>
Число символов в *pch*.

*ch*<br/>
Один символ.

*pszSrc*<br/>
Заканчивающуюся нулем строку, который необходимо скопировать в это `CStringT` объекта.

*pStringMgr*<br/>
Указатель на диспетчер памяти для `CStringT` объекта. Дополнительные сведения о `IAtlStringMgr` и управление памятью для `CStringT`, см. в разделе [управление памятью с помощью CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

*strSrc*<br/>
Существующий `CStringT` объект, который необходимо скопировать в это `CStringT` объекта. Дополнительные сведения о `CThisString` и `CThisSimpleString`, см. в разделе "Примечания".

*varSrc*<br/>
Объект variant, который необходимо скопировать в это `CStringT` объекта.

*BaseType*<br/>
Тип символа класса string. Ниже указаны доступные значения.

**char** (для символьных строк ANSI).

**wchar_t** (для символьных строк в Юникоде).

TCHAR (для символьных строк ANSI и Юникода).

*bMFCDLL*<br/>
Логическое значение, указывающее, является ли проект библиотеки DLL MFC (TRUE) или нет (FALSE).

*SystemString*<br/>
Должен быть `System::String`, и проект должен быть скомпилирован с параметром/CLR.

*pString*<br/>
Дескриптор для `CStringT` объекта.

### <a name="remarks"></a>Примечания

Поскольку конструкторы копируют входные данные в новый объем выделенного хранилища, следует иметь в виду, что память, может привести к исключения. Обратите внимание на то, что некоторые из этих конструкторов выступать в качестве функции преобразования. Это позволяет заменить, например, LPTSTR где `CStringT` ожидается объект.

- `CStringT`( `LPCSTR` `lpsz` ): Создает Юникода `CStringT` строки ANSI. Этот конструктор также можно использовать для загрузки строковый ресурс, как показано в следующем примере.

- `CStringT(` `LPCWSTR` `lpsz` ): Создает `CStringT` строки Юникода.

- `CStringT`( `const unsigned char*` `psz` ): Позволяет создавать `CStringT` из указателя в **unsigned char**.

> [!NOTE]
>  Определите макрос _CSTRING_DISABLE_NARROW_WIDE_CONVERSION, чтобы отключить строку неявное преобразование между строк ANSI и Юникод. Макрос исключаются из компиляции конструкторов, которые поддерживают преобразование.

Обратите внимание, что *strSrc* параметр может быть либо `CStringT` или `CThisSimpleString` объекта. Для `CStringT`, используйте один из его экземпляров по умолчанию (`CString`, `CStringA`, или `CStringW`); для `CThisSimpleString`, использовать **это** указатель. `CThisSimpleString` Объявляет экземпляр [класс CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), меньшего размера класса строка с менее встроенных функциональных возможностей, чем `CStringT` класса.

Перегрузка оператора `CSimpleStringT<>&()` создает `CStringT` объекта из `CSimpleStringT` объявления.

> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляров, которые содержат внедренные символы null, мы не рекомендуем включать его. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы null может привести к непредвиденным результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

##  <a name="_dtorcstringt"></a>  CStringT:: ~ CStringT

Уничтожает `CStringT` объекта.

```
~CStringT() throw();
```

### <a name="remarks"></a>Примечания

Уничтожает `CStringT` объекта.

##  <a name="delete"></a>  CStringT::Delete

Удаляет символ или символы из строки, начиная с символом, расположенным по указанному индексу.

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
Отсчитываемый от нуля индекс первого символа в `CStringT` удаляемого объекта.

*nCount*<br/>
Число удаляемых символов.

### <a name="return-value"></a>Возвращаемое значение

Длина измененная строка.

### <a name="remarks"></a>Примечания

Если *nCount* длиннее, чем строка, оставшаяся часть строки будут удалены.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output
Before: Soccer is best,
    but hockey is quicker!
After: Soccer best,
    but hockey is quicker!
```

##  <a name="find"></a>  CStringT::Find

Ищет первое совпадение символа или подстроки данной строки.

```
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>Параметры

*pszSub*<br/>
Подстрока для поиска.

*iStart*<br/>
Индекс символа в строке, чтобы начать поиск с или 0, чтобы начать с самого начала.

*ch*<br/>
Один символ для поиска.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первого символа в этом `CStringT` , соответствующий запрашиваемой подстроки или символы; -1, если подстрока или символ не найден.

### <a name="remarks"></a>Примечания

Функция перегружен, чтобы принять оба одного символа (подобно функции времени выполнения `strchr`) и строки (аналогичную `strstr`).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

##  <a name="findoneof"></a>  CStringT::FindOneOf

Выполняет поиск первого символа, который соответствует любому символу, содержащихся в этой строке *pszCharSet*.

```
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>Параметры

*pszCharSet*<br/>
Строка, содержащая символы для сопоставления.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первого символа в данной строке, которая присутствует также в *pszCharSet*; -1, если совпадения нет.

### <a name="remarks"></a>Примечания

Находит первое вхождение символы в *pszCharSet*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

##  <a name="format"></a>  CStringT::Format

Записывает форматированные данные `CStringT` в том же образом, как [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) форматы данных в стиле C массив символов.

```
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>Параметры

*nFormatID*<br/>
Строковый идентификатор ресурса, содержащего строку управления форматом.

*pszFormat*<br/>
Строка управления форматом.

*Аргумент*<br/>
Необязательные аргументы.

### <a name="remarks"></a>Примечания

Эта функция форматирует и сохраняет серию символов и значений в `CStringT`. Каждый необязательный аргумент (если есть) преобразуется и выводится согласно соответствующей спецификации формата в *pszFormat* или из строкового ресурса, идентифицируемый *nFormatID*.

Вызов завершится ошибкой, если сам объект строка предоставляется в качестве параметра `Format`. Например следующий код приведет к непредсказуемым результатам:

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

Дополнительные сведения см. в разделе [Синтаксис описания формата: функции printf и wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

##  <a name="formatmessage"></a>  CStringT::FormatMessage

Форматирует строку сообщения.

```
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>Параметры

*nFormatID*<br/>
Строковый идентификатор ресурса, содержащий текст неформатированного сообщения.

*pszFormat*<br/>
Указывает на строку управления форматом. Его поиск для вставок и соответствующим образом в формате. Строка формата подобна функции времени выполнения *printf*-стиль строки формата, за исключением того, он допускает использование параметров должны быть вставлены в произвольном порядке.

*Аргумент*<br/>
Необязательные аргументы.

### <a name="remarks"></a>Примечания

Функция требует определения сообщения как входные данные. Определение сообщения определяется *pszFormat* или из строкового ресурса, идентифицируемый *nFormatID*. Эта функция копирует текст отформатированное сообщение `CStringT` объекта, обработкой, внедренные вставить последовательности по запросу.

> [!NOTE]
> `FormatMessage` пытается выделить системную память для вновь форматируемой строки. Если эта попытка завершается неудачей, исключение памяти автоматически вызывается исключение.

Каждой операции вставки должен иметь соответствующий следующий параметр *pszFormat* или *nFormatID* параметра. В тексте сообщения несколько escape-последовательности поддерживаются для динамического форматирования сообщения. Дополнительные сведения см. в разделе Windows [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) функции в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

##  <a name="formatmessagev"></a>  CStringT::FormatMessageV

Форматирует строку сообщения, используя переменное число аргументов.

```
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>Параметры

*pszFormat*<br/>
Указывает на строку управления форматом. Его поиск для вставок и соответствующим образом в формате. Строка формата подобна функции времени выполнения `printf`-стиль строки формата, за исключением того, он допускает использование параметров должны быть вставлены в произвольном порядке.

*pArgList*<br/>
Указатель на список аргументов.

### <a name="remarks"></a>Примечания

Функция требует определения сообщения как входные данные, определяются *pszFormat*. Эта функция копирует текст форматированное сообщение и переменный список аргументов для `CStringT` объекта, обработкой, внедренные вставить последовательности по запросу.

> [!NOTE]
> `FormatMessageV` вызовы [CStringT::FormatMessage](#formatmessage), который пытается выделить системную память для вновь форматируемой строки. Если эта попытка завершается неудачей, исключение памяти автоматически вызывается исключение.

Дополнительные сведения см. в разделе Windows [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) функции в пакете Windows SDK.

##  <a name="formatv"></a>  CStringT::FormatV

Форматирует строку сообщения, используя переменное число аргументов.

```
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>Параметры

*pszFormat*<br/>
Указывает на строку управления форматом. Его поиск для вставок и соответствующим образом в формате. Строка формата подобна функции времени выполнения `printf`-стиль строки формата, за исключением того, он допускает использование параметров должны быть вставлены в произвольном порядке.

*аргументы*<br/>
Указатель на список аргументов.

### <a name="remarks"></a>Примечания

Записывает форматированную строку и переменный список аргументов для `CStringT` строку, в том же образом, как `vsprintf_s` форматы данных в стиле C массив символов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

##  <a name="getenvironmentvariable"></a>  CStringT::GetEnvironmentVariable

Задает строку, чтобы значение указанной переменной среды.

```
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>Параметры

*pszVar*<br/>
Указатель на заканчивающуюся нулем строку, который указывает переменную среды.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Получает значение указанной переменной из вызывающего процесса блок среды. Значение в виде заканчивающуюся нулем строку символов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

##  <a name="insert"></a>  CStringT::Insert

Вставляет один символ или подстроку по заданному индексу в строке.

```
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
Индекс символа, перед которым вставки будет выполняться.

*psz*<br/>
Указатель на подстроки, которую требуется вставить.

*ch*<br/>
Символ для вставки.

### <a name="return-value"></a>Возвращаемое значение

Длина измененная строка.

### <a name="remarks"></a>Примечания

*IIndex* параметр определяет первый символ, который будет перемещен, чтобы освободить место для символа или подстроки. Если *nIndex* равен нулю, вставка произойдет перед всю строку. Если *nIndex* больше, чем длина строки, функция будет объединения присутствует строки и новые материалы, предоставляемые либо *ch* или *psz*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

##  <a name="left"></a>  CStringT::Left

Извлекает крайнее левое *nCount* символов из этого `CStringT` объекта и возвращает копию извлеченной подстроки.

```
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>Параметры

*nCount*<br/>
Число символов, извлекаемых из данного объекта `CStringT`.

### <a name="return-value"></a>Возвращаемое значение

Объект `CStringT`, содержащий копию указанного диапазона символов. Возвращенный объект `CStringT` может быть пустым.

### <a name="remarks"></a>Примечания

Если *nCount* превышает длину строки, а затем извлекается вся строка. Функция `Left` аналогична функции `Left` в языке Basic.

Для многобайтовых кодировок (MBCS), *nCount* обрабатывает каждый 8-разрядную последовательность как один символ, так что *nCount* возвращает количество многобайтовых символов, умноженное на 2.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

##  <a name="loadstring"></a>  CStringT::LoadString

Считывает строку ресурса Windows, идентифицируемый *nID*, в существующую коллекцию `CStringT` объекта.

```
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Дескриптор экземпляра модуля.

*nID*<br/>
Идентификатор ресурса строки Windows.

*wLanguageID*<br/>
Язык строкового ресурса.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если загрузка ресурсов выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Загружает строку ресурсов (*nID*) из указанного модуля (*hInstance*) используя указанный язык (*wLanguage*).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

##  <a name="makelower"></a>  CStringT::MakeLower

Преобразует `CStringT` объекта в строку в нижнем регистре.

```
CStringT& MakeLower();
```

### <a name="return-value"></a>Возвращаемое значение

Результирующая строка нижнего регистра.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

##  <a name="makereverse"></a>  CStringT::MakeReverse

Изменяет порядок символов в `CStringT` объекта.

```
CStringT& MakeReverse();
```

### <a name="return-value"></a>Возвращаемое значение

Полученный в обратном порядке строки.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

##  <a name="makeupper"></a>  CStringT::MakeUpper

Преобразует `CStringT` объекта в строку в верхнем регистре.

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>Возвращаемое значение

Результирующая строка верхнего регистра.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

##  <a name="mid"></a>  CStringT::Mid

Извлекает подстроку длиной *nCount* символов из этого `CStringT` объекта, начиная с позиции *iFirst* (от нуля).

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>Параметры

*iFirst*<br/>
Отсчитываемый от нуля индекс первого символа в этом `CStringT` объекта, добавляемого в извлеченной подстроки.

*nCount*<br/>
Число символов, извлекаемых из данного объекта `CStringT`. Если этот параметр не задан, извлекается оставшейся части строки.

### <a name="return-value"></a>Возвращаемое значение

Объект `CStringT`, содержащий копию указанного диапазона символов. Обратите внимание, что возвращенный `CStringT` объект может быть пустым.

### <a name="remarks"></a>Примечания

Функция возвращает копию извлеченной подстроки. `Mid` аналогичен функция основные Mid (за исключением того, что индексы в Basic начинаются с 1).

Для многобайтовой кодировки (MBCS), *nCount* ссылается на каждый 8-разрядных символов, то есть старший и младший байт один Многобайтовый символ считаются за два символа.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

##  <a name="oemtoansi"></a>  CStringT::OemToAnsi

Преобразует все символы в этом `CStringT` объекта из набора для набора символов ANSI символов OEM.

```
void OemToAnsi();
```

### <a name="remarks"></a>Примечания

Эта функция доступна не в том случае, если определяется _UNICODE.

### <a name="example"></a>Пример

См. в примере [CStringT::AnsiToOem](#ansitooem).

##  <a name="operator_add"></a>  CStringT::operator +

Сцепляет две строки или символ и строку.

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

*гл. 1*<br/>
Символ ANSI или Юникода, для объединения со строкой.

*ch2*<br/>
Символ ANSI или Юникода, для объединения со строкой.

*str1*<br/>
Объект `CStringT` для объединения с строку или символ.

*str2*<br/>
Объект `CStringT` для объединения с строку или символ.

*psz1*<br/>
Указатель на заканчивающуюся нулем строку, для объединения с строку или символ.

*psz2*<br/>
Указатель на строку для объединения с строку или символ.

### <a name="remarks"></a>Примечания

Существует семь формы перегрузки `CStringT::operator+` функции. Первая версия объединяет две существующие `CStringT` объектов. Объединение двух следующих `CStringT` объекта и строку, завершающуюся символом null. Объединение двух следующих `CStringT` объекта и знак ANSI. Объединение двух последних `CStringT` объекта и символ Юникода.

> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляров, которые содержат внедренные символы null, мы не рекомендуем включать его. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы null может привести к непредвиденным результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

##  <a name="operator_add_eq"></a>  CStringT::operator +=

Сцепляет символы конца строки.

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

*str*<br/>
Ссылка на объект `CThisSimpleString`.

*bMFCDLL*<br/>
Логическое значение, показывающее, является ли проект MFC библиотеки DLL.

*BaseType*<br/>
Базовый тип строки.

*var*<br/>
Объект типа variant для объединения этой строки.

*ch*<br/>
Символ ANSI или Юникода, для объединения со строкой.

*pszSrc*<br/>
Указатель на исходную строку, объединяемых.

*strSrc*<br/>
Объект `CStringT` сцепляемых этой строки.

### <a name="remarks"></a>Примечания

Оператор принимает другой `CStringT` объекта, указатель на символ или один символ. Следует иметь в виду эту память, исключения могут возникать при использовании этот оператор объединения, так как для символов, добавленных к этому можно выделить новое хранилище `CStringT` объекта.

Сведения о `CThisSimpleString`, см. в разделе "Примечания" [CStringT::CStringT](#cstringt).

> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляров, которые содержат внедренные символы null, мы не рекомендуем включать его. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы null может привести к непредвиденным результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

##  <a name="operator_eq_eq"></a>  CStringT::operator ==

Определяет, логически равны ли две строки.

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

*гл. 1*<br/>
Символ ANSI или Юникода, для сравнения.

*ch2*<br/>
Символ ANSI или Юникода, для сравнения.

*str1*<br/>
Объект `CStringT` для сравнения.

*str2*<br/>
Объект `CStringT` для сравнения.

*psz1*<br/>
Указатель на заканчивающуюся нулем строку, для сравнения.

*psz2*<br/>
Указатель на заканчивающуюся нулем строку, для сравнения.

### <a name="remarks"></a>Примечания

Проверяет, является ли строку или символ, с левой стороны равно строку или символ, справа от оператора и возвращает TRUE или FALSE соответственно.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

##  <a name="operator_neq"></a>  CStringT::operator! =

Определяет, действительно ли две строки логически не равны.

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

*гл. 1*<br/>
Символ ANSI или Юникода, для объединения со строкой.

*ch2*<br/>
Символ ANSI или Юникода, для объединения со строкой.

*str1*<br/>
Объект `CStringT` для сравнения.

*str2*<br/>
Объект `CStringT` для сравнения.

*psz1*<br/>
Указатель на заканчивающуюся нулем строку, для сравнения.

*psz2*<br/>
Указатель на заканчивающуюся нулем строку, для сравнения.

### <a name="remarks"></a>Примечания

Проверяет строку или символ слева не равно строку или символ, справа от оператора.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

##  <a name="operator_lt"></a>  CStringT::operator &lt;

Определяет, является ли строка в левой части оператора меньше, чем строка в правой части.

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Объект `CStringT` для сравнения.

*str2*<br/>
Объект `CStringT` для сравнения.

*psz1*<br/>
Указатель на заканчивающуюся нулем строку, для сравнения.

*psz2*<br/>
Указатель на заканчивающуюся нулем строку, для сравнения.

### <a name="remarks"></a>Примечания

Лексикографическое сравнение между строками, символ за символом до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

##  <a name="operator_gt"></a>  CStringT::operator &gt;

Определяет, является ли строка слева от оператора больше, чем строка в правой части.

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Объект `CStringT` для сравнения.

*str2*<br/>
Объект `CStringT` для сравнения.

*psz1*<br/>
Указатель на заканчивающуюся нулем строку, для сравнения.

*psz2*<br/>
Указатель на заканчивающуюся нулем строку, для сравнения.

### <a name="remarks"></a>Примечания

Лексикографическое сравнение между строками, символ за символом до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

##  <a name="operator_lt_eq"></a>  CStringT::operator &lt;=

Определяет, является ли строка в левой части оператора меньше или равны строке справа от оператора.

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Объект `CStringT` для сравнения.

*str2*<br/>
Объект `CStringT` для сравнения.

*psz1*<br/>
Указатель на заканчивающуюся нулем строку, для сравнения.

*psz2*<br/>
Указатель на заканчивающуюся нулем строку, для сравнения.

### <a name="remarks"></a>Примечания

Лексикографическое сравнение между строками, символ за символом до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

##  <a name="operator_gt_eq"></a>  CStringT::operator &gt;=

Определяет, является ли строка слева от оператора больше или равны строке справа от оператора.

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Объект `CStringT` для сравнения.

*str2*<br/>
Объект `CStringT` для сравнения.

*psz1*<br/>
Указатель на строку для сравнения.

*psz2*<br/>
Указатель на строку для сравнения.

### <a name="remarks"></a>Примечания

Лексикографическое сравнение между строками, символ за символом до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

##  <a name="remove"></a>  CStringT::Remove

Удаляет все вхождения указанного символа в строке.

```
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>Параметры

*chRemove*<br/>
Символ, который необходимо удалить из строки.

### <a name="return-value"></a>Возвращаемое значение

Число символов, удаляется из строки. Нуль, если строка не изменяется.

### <a name="remarks"></a>Примечания

Сравнение символа чувствительны к регистру.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

##  <a name="replace"></a>  CStringT::Replace

Существуют две версии `Replace`. Первая версия заменяет одну или несколько копий подстроки, используя другой подстрокой. Обе подстроки, завершающаяся символом null. Вторая версия заменяет одну или несколько копий символа с помощью другого символа. Обе версии работают с символьные данные, хранящиеся в `CStringT`.

```
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>Параметры

*pszOld*<br/>
Указатель на заканчивающуюся нулем строку, заменяется *pszNew*.

*pszNew*<br/>
Указатель на заканчивающуюся нулем строку, которая заменяет *pszOld*.

*chOld*<br/>
Символ заменяется *chNew*.

*chNew*<br/>
Символ замены *chOld*.

### <a name="return-value"></a>Возвращаемое значение

Возвращает число экземпляров замененного символ или подстроку, или нуль, если строка не изменяется.

### <a name="remarks"></a>Примечания

`Replace` можно изменить длину строки, так как *pszNew* и *pszOld* нет необходимости иметь одинаковую длину и несколько копий старый подстроки можно изменить в новую. Функция выполняет совпадение с учетом регистра.

Примеры `CStringT` экземпляры являются `CString`, `CStringA`, и `CStringW`.

Для `CStringA`, `Replace` работает с ANSI или многобайтовая кодировка (MBCS). Для `CStringW`, `Replace` работает с расширенными символами.

Для `CString`, символьный тип данных выбирается во время компиляции, исходя ли определены константы в следующей таблице.

|Константа|Символьный тип данных|
|----------------------|-------------------------|
|_UNICODE|Расширенные символы|
|_MBCS|Многобайтовых символов|
|Ни|Однобайтовые символы|
|Оба значения|Не определено|

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

##  <a name="reversefind"></a>  CStringT::ReverseFind

Выполняет поиск этого `CStringT` объекта для сопоставления последнего символа.

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>Параметры

*ch*<br/>
Символ для поиска.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс последнего символа в этом `CStringT` объект, который соответствует запрошенной символ или значение -1, если символ не найден.

### <a name="remarks"></a>Примечания

Функция аналогична функции времени выполнения `strrchr`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

##  <a name="right"></a>  CStringT::Right

Извлекает последний (то есть крайний справа) *nCount* символов из этого `CStringT` объекта и возвращает копию извлеченной подстроки.

```
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>Параметры

*nCount*<br/>
Число символов, извлекаемых из данного объекта `CStringT`.

### <a name="return-value"></a>Возвращаемое значение

Объект `CStringT`, содержащий копию указанного диапазона символов. Обратите внимание, что возвращенный `CStringT` объект может быть пустым.

### <a name="remarks"></a>Примечания

Если *nCount* превышает длину строки, а затем извлекается вся строка. `Right` аналогичен базовый `Right` функции (за исключением того, что индексы в Basic отсчитываются от нуля).

Для многобайтовой кодировки (MBCS), *nCount* ссылается на каждый 8-разрядных символов, то есть старший и младший байт один Многобайтовый символ считаются за два символа.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

##  <a name="setsysstring"></a>  CStringT::SetSysString

Повторно выделяет строку BSTR, на которые указывают *pbstr* и копирует содержимое объекта `CStringT` объекта, включая нуль-символ.

```
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>Параметры

*pbstr*<br/>
Указатель на строку символов.

### <a name="return-value"></a>Возвращаемое значение

Новая строка.

### <a name="remarks"></a>Примечания

В зависимости от содержимого `CStringT` , значение строки BSTR ссылается *pbstr* можно изменить. Функция создает `CMemoryException` наличие нехватки памяти.

Эта функция обычно используется для изменения значения строк, передаваемый по ссылке для автоматизации.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

##  <a name="spanexcluding"></a>  CStringT::SpanExcluding

Извлекает символы из строки, начиная с первого символа, не вошедших в набор символов, идентифицируемый *pszCharSet*.

```
CStringT SpanExcluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Параметры

*pszCharSet*<br/>
Строка интерпретируется как набор символов.

### <a name="return-value"></a>Возвращаемое значение

Подстроки, содержащий символы в строке, не включенных в *pszCharSet*, начиная с первого символа в строке и заканчивая первого символа в строке, присутствует также в *pszCharSet* (то есть, начиная с первого символа в строке до, но за исключением первого символа в строке, которую можно найти *pszCharSet*). Он возвращает всю строку, если ни один знак из *pszCharSet* найдено в строке.

### <a name="remarks"></a>Примечания

`SpanExcluding` Извлекает и возвращает все символы, предшествующие первого экземпляра символа из *pszCharSet* (другими словами, символ из *pszCharSet* и все символы в строке, а не возвращается). Если ни один знак из *pszCharSet* находится в строке, а затем `SpanExcluding` возвращает всю строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

##  <a name="spanincluding"></a>  CStringT::SpanIncluding

Извлекает символы из строки, начиная с первого символа, в набор символов, идентифицируемый *pszCharSet*.

```
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>Параметры

*pszCharSet*<br/>
Строка интерпретируется как набор символов.

### <a name="return-value"></a>Возвращаемое значение

Подстроки, содержит символы в строке, которые находятся в *pszCharSet*, начиная с первого символа в строке и заканчивается, когда символ находится в строке, которая не находится в *pszCharSet*. `SpanIncluding` Возвращает пустой подстрокой, если первый символ в строке не находится в указанном наборе.

### <a name="remarks"></a>Примечания

Если первый символ строки не в наборе символов, то `SpanIncluding` возвращает пустую строку. В противном случае оно возвращает последовательность последовательных символов, которые входят в набор.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

##  <a name="tokenize"></a>  CStringT::Tokenize

Находит следующий токен в целевой строке

```
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const;
```

### <a name="parameters"></a>Параметры

*pszTokens*<br/>
Строка, содержащая разделители токенов. Порядок эти разделители не имеет значения.

*iStart*<br/>
Отсчитываемый от нуля индекс начала поиска.

### <a name="return-value"></a>Возвращаемое значение

Объект `CStringT` объект, содержащий значение текущего маркера.

### <a name="remarks"></a>Примечания

`Tokenize` Функция находит следующий токен в целевой строке. Набор символов в *pszTokens* указывает возможные разделители токен, который требуется найти. При каждом вызове `Tokenize` функции начинается с *iStart*, пропускает ведущие разделители и возвращает `CStringT` объект, содержащий текущий маркер, который является строкой символов до следующего символа разделителя. Значение *iStart* обновлены для позиции, следующей конечный символ разделителя, или значение -1, если достигнут конец строки. Дополнительные маркеры можно разбить из оставшейся части целевой строке ряд вызовов `Tokenize`, с использованием *iStart* для отслеживания where в строке следующий токен — для чтения. Когда дополнительные маркеры отсутствуют, функция возвратит пустую строку и *iStart* будет указано значение -1.

В отличие от CRT маркировки функции, такие как [функции strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), `Tokenize` не изменяет целевой строки.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>Примечания

Выходные данные из этого примера выглядит следующим образом:

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

##  <a name="trim"></a>  CStringT::Trim

Обрезка начальных и конечных символов из строки.

```
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>Параметры

*chTarget*<br/>
Конечный символ для усечения.

*pszTargets*<br/>
Указатель на строку, содержащую символы целевой для усечения. Все начальные и конечные вхождения символов в *pszTarget* будут удалены из `CStringT` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает Сокращенная строка.

### <a name="remarks"></a>Примечания

Удаляет все начальные и конечные вхождения одно из следующих:

- Символ, заданный параметром *chTarget*.

- Все символы, входящие в строкой, указанной параметром *pszTargets*.

- Пробел.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>Примечания

Выходные данные из этого примера выглядит следующим образом:

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

##  <a name="trimleft"></a>  CStringT::TrimLeft

Обрезка начальных символов из строки.

```
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>Параметры

*chTarget*<br/>
Конечный символ для усечения.

*pszTargets*<br/>
Указатель на строку, содержащую символы целевой для усечения. Все начальные вхождения символов в *pszTarget* будут удалены из `CStringT` объекта.

### <a name="return-value"></a>Возвращаемое значение

Результирующая строка, соответствующая символьная строка обрезается.

### <a name="remarks"></a>Примечания

Удаляет все начальные и конечные вхождения одно из следующих:

- Символ, заданный параметром *chTarget*.

- Все символы, входящие в строкой, указанной параметром *pszTargets*.

- Пробел.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

##  <a name="trimright"></a>  CStringT::TrimRight

Удаляет конечные знаки из строки.

```
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>Параметры

*chTarget*<br/>
Конечный символ для усечения.

*pszTargets*<br/>
Указатель на строку, содержащую символы целевой для усечения. Все конечные вхождения символов в *pszTarget* будут удалены из `CStringT` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CStringT` , содержащий Сокращенная строка.

### <a name="remarks"></a>Примечания

Удаляет конечные вхождения одно из следующих:

- Символ, заданный параметром *chTarget*.

- Все символы, входящие в строкой, указанной параметром *pszTargets*.

- Пробел.

`CStringT& TrimRight(XCHAR chTarget)` Версии принимает один параметр символ и удаляет все копии этого символа в конце `CStringT` строковые данные. Она начинается с конца строки и работает ближе к началу. Он останавливается, когда находит другой символ, или когда `CSTringT` символьных данных не хватает.

`CStringT& TrimRight(PCXSTR pszTargets)` Версия принимает нулем строка, содержащая все различных символов для поиска. Она удаляет все копии эти символы в `CStringT` объекта. Она начинается с конца строки и работает ближе к началу. Прекращается при обнаружении символ, который не находится в целевой строке, или при `CStringT` символьных данных не хватает. Он не пытается сопоставить строку весь target подстрокой, расположенной в конце `CStringT`.

`CStringT& TrimRight()` Версии не требует параметров. Он урезает любые конечные символы пробела в конце `CStringT` строка. Пробелы можно разрывы строк, пробелы или знаки табуляции.

-

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
[Класс CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)

