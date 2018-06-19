---
title: Класс CStringT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f8a66f87b3c4a2c6712a1db93f97361a25b6955
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366631"
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
 `BaseType`  
 Тип символа класса string. Ниже указаны доступные значения.  
  
- `char` (для символьных строк ANSI).  
  
- `wchar_t` (для символьных строк Юникода).  
  
- **TCHAR** (для символьных строк ANSI или Юникод).  
  
 `StringTraits`  
 Определяет, должен ли класс string поддержка библиотеки времени выполнения C (CRT) и где расположены строковые ресурсы. Ниже указаны доступные значения.  
  
- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Класс требуется поддержка CRT и поиск строк ресурса в модуль, указанный параметром `m_hInstResource` (член класса модуля приложения).  
  
- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Класс не требуется поддержка CRT и поиск строк ресурса в модуль, указанный параметром `m_hInstResource` (член класса модуля приложения).  
  
- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Класс требуется поддержка CRT и выполняет поиск строки ресурса, используя стандартный алгоритм поиска MFC.  
  
- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Класс не требуется поддержка CRT и ищет строки ресурса, используя стандартный алгоритм поиска MFC.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringT::CStringT](#cstringt)|Создает `CStringT` объекта различными способами.|  
|[CStringT:: ~ CStringT](#_dtorcstringt)|Уничтожает объект `CStringT`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringT::AllocSysString](#allocsysstring)|Выделяет `BSTR` из `CStringT` данных.|  
|[CStringT::AnsiToOem](#ansitooem)|Такое преобразование на месте из кодировки ANSI в набор символов OEM.|  
|[CStringT::AppendFormat](#appendformat)|Добавляет форматированных данных в существующий `CStringT` объекта.|  
|[CStringT::Collate](#collate)|Сравнивает две строки (регистр конфиденциальные, использует языкового стандарта).|  
|[CStringT::CollateNoCase](#collatenocase)|Сравнивает две строки (без учета регистра, использует языкового стандарта).|  
|[CStringT::Compare](#compare)|Сравнивает две строки (с учетом регистра).|  
|[CStringT::CompareNoCase](#comparenocase)|Сравнивает две строки (без учета регистра).|  
|[CStringT::Delete](#delete)|Удаление символа или символов из строки.|  
|[CStringT::Find](#find)|Находит символ или подстроку в длинной строке.|  
|[CStringT::FindOneOf](#findoneof)|Находит первый соответствующий символ из набора.|  
|[CStringT::Format](#format)|Форматирует строку как `sprintf` does.|  
|[CStringT::FormatMessage](#formatmessage)|Форматирует строку сообщения.|  
|[CStringT::FormatMessageV](#formatmessagev)|Форматирование строки сообщения при помощи переменное число аргументов.|  
|[CStringT::FormatV](#formatv)|Форматирует строку, используя переменный список аргументов.|  
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Задает строковое значение указанной переменной среды.|  
|[CStringT::Insert](#insert)|Вставляет символ или подстроку с указанным индексом в строке.|  
|[CStringT::Left](#left)|Извлекает левую часть строки.|  
|[CStringT::LoadString](#loadstring)|Загружает существующий `CStringT` из ресурса Windows.|  
|[CStringT::MakeLower](#makelower)|Преобразует все символы в строке в нижний регистр.|  
|[CStringT::MakeReverse](#makereverse)|Изменяет строку.|  
|[CStringT::MakeUpper](#makeupper)|Преобразует все символы в строке в верхний регистр.|  
|[CStringT::Mid](#mid)|Извлекает средней части строки.|  
|[CStringT::OemToAnsi](#oemtoansi)|Такое преобразование на месте из OEM кодировки набора знаков ANSI.|  
|[CStringT::Remove](#remove)|Удаляет указанный символов из строки.|  
|[CStringT::Replace](#replace)|Заменяет указанный символы и другие символы.|  
|[CStringT::ReverseFind](#reversefind)|Поиск символов в длинной строке; начинается с конца.|  
|[CStringT::Right](#right)|Извлекает в правой части строки.|  
|[CStringT::SetSysString](#setsysstring)|Задает существующий `BSTR` объект с данными из `CStringT` объекта.|  
|[CStringT::SpanExcluding](#spanexcluding)|Извлекает символы из строки, начиная с первого символа, не входящие в набор символов, которые идентифицируют `pszCharSet`.|  
|[CStringT::SpanIncluding](#spanincluding)|Извлекает подстроку, содержащая только символы в наборе.|  
|[CStringT::Tokenize](#tokenize)|Извлекает указанный токены в целевой строке.|  
|[CStringT::Trim](#trim)|Удаляет все начальные и конечные пробелы из строки.|  
|[CStringT::TrimLeft](#trimleft)|Обрезка начальные пробелы из строки.|  
|[CStringT::TrimRight](#trimright)|Обрезка конечные символы пробела в строке.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#operator_eq)|Присваивает новое значение для `CStringT` объекта.|  
|[CStringT::operator +](#operator_add)|Сцепляет две строки или символ и строку.|  
|[CStringT::operator +=](#operator_add_eq)|Сцепляет новую строку в конец существующей строки.|  
|[CStringT::operator ==](#operator_eq_eq)|Определяет, логически равны ли две строки.|  
|[CStringT::operator! =](#operator_neq)|Определяет, если две строки логически не равны.|  
|[CStringT::operator &lt;](#operator_lt)|Определяет, является ли строка в левой части оператора меньше, чем к строке справа от оператора.|  
|[CStringT::operator &gt;](#operator_gt)|Определяет, является ли строка слева от оператора больше, чем к строке справа от оператора.|  
|[CStringT::operator &lt;=](#operator_lt_eq)|Определяет, является ли строка в левой части оператора меньше или равным строке справа от оператора.|  
|[CStringT::operator &gt;=](#operator_gt_eq)|Определяет, является ли строка слева от оператора больше или равным строке справа от оператора.|  
  
## <a name="remarks"></a>Примечания  
 `CStringT` наследует от [CSimpleStringT класса](../../atl-mfc-shared/reference/csimplestringt-class.md). Дополнительные функции, такие как символ манипуляции, сортировки и поиска, реализуются `CStringT`.  
  
> [!NOTE]
> `CStringT` объекты способны создание исключений. Это происходит, когда `CStringT` объекта не хватает памяти для какой-либо причине.  
  
 Объект `CStringT` объект состоит из последовательности символов переменной длины. `CStringT` предоставляет функции и операторы, с помощью синтаксиса, аналогичного синтаксису Basic. Объединение и операторы сравнения, вместе с управления памятью упрощенный, делают `CStringT` проще, чем обычный символ массивы объектов.  
  
> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляры, которые содержат внедренные символы null, не рекомендуется его. Вызов методов и операторов для `CStringT` объектов, которые содержат внедренные символы null может привести к непредвиденным результатам.  
  
 С помощью комбинации `BaseType` и `StringTraits` параметров, `CStringT` объектов можно поставляются в следующие типы, которые являются предопределенные ATL библиотеками.  
  
 При использовании в приложении ATL:  
  
 `CString`, `CStringA`, и `CStringW` экспортируются из библиотеки DLL MFC (MFC90. Библиотека DLL), никогда не от пользователя библиотеки DLL. Это делается во избежание `CStringT` из которой определен несколько раз.  
  
> [!NOTE]
>  Если код содержит решения для ошибки компоновщика, которые описаны в [классы Linking Errors When You Import CString-Derived» (номер Q309801)](https://support.microsoft.com/help/309801/you-may-receive-an-lnk2019-error-message-when-you-build-a-visual-c-200), этот код можно удалить. Больше не используется.  
  
 В приложениях MFC доступны перечисленные ниже строки:  
  
|Тип CStringT|Объявление|  
|-------------------|-----------------|  
|`CStringA`|Знак ANSI введите строку с поддержкой CRT.|  
|`CStringW`|Знак Юникода типа string с поддержкой CRT.|  
|`CString`|ANSI и Юникод символьные типы с поддержкой CRT.|  
  
 Следующая строка типов, доступных в проектах where **ATL_CSTRING_NO_CRT** определяется:  
  
|Тип CStringT|Объявление|  
|-------------------|-----------------|  
|**CAtlStringA**|Знак ANSI типа string, не поддерживающих CRT.|  
|**CAtlStringW**|Знак Юникода типа string, не поддерживающих CRT.|  
|**CAtlString**|ANSI и Юникод символьные типы без поддержки CRT.|  
  
 Следующая строка типов, доступных в проектах where **ATL_CSTRING_NO_CRT** не определен:  
  
|Тип CStringT|Объявление|  
|-------------------|-----------------|  
|**CAtlStringA**|Знак ANSI введите строку с поддержкой CRT.|  
|**CAtlStringW**|Знак Юникода типа string с поддержкой CRT.|  
|**CAtlString**|ANSI и Юникод символьные типы с поддержкой CRT.|  
  
 `CString` объекты также имеют следующие характеристики:  
  
- `CStringT` объекты могут увеличиваться в результате операции объединения.  
  
- `CStringT` объекты следуют «value семантики». Представьте `CStringT` объект как фактический строку, а не как указатель на строку.  
  
-   Можно свободно заменить `CStringT` объектов для `PCXSTR` аргументы функций.  
  
-   Управление пользовательской памяти буферы строк. Дополнительные сведения см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="cstringt-predefined-types"></a>CStringT предопределенные типы  
 Поскольку `CStringT` используется аргумент шаблона для определения типа символ (либо [wchar_t](../../c-runtime-library/standard-types.md) или [char](../../c-runtime-library/standard-types.md)) поддерживается, типы параметров метода, может быть затруднена время от времени. Чтобы упростить эту проблему, набор предопределенных типов определяется и используется во всей `CStringT` класса. В следующей таблице перечислены различные типы:  
  
|name|Описание|  
|----------|-----------------|  
|`XCHAR`|Отдельный символ (либо `wchar_t` или `char`) с тем же типом символ, `CStringT` объекта.|  
|**YCHAR**|Отдельный символ (либо `wchar_t` или `char`) с противоположной символьным типом как `CStringT` объект.|  
|`PXSTR`|Указатель на строку знаков (либо `wchar_t` или `char`) с тем же типом символ, `CStringT` объекта.|  
|**PYSTR**|Указатель на строку знаков (либо `wchar_t` или `char`) с противоположной символьным типом как `CStringT` объект.|  
|`PCXSTR`|Указатель на **const** строка символов (либо `wchar_t` или `char`) с тем же типом символ, `CStringT` объекта.|  
|**PCYSTR**|Указатель на **const** строка символов (либо `wchar_t` или `char`) с противоположной символьным типом как `CStringT` объект.|  
  
> [!NOTE]
>  Код, который ранее использовался недокументированные методы `CString` (такие как **AssignCopy**) должны быть заменены код, который использует следующие методы документированные `CStringT` (такие как `GetBuffer` или `ReleaseBuffer`). Эти методы наследуются от `CSimpleStringT`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## <a name="requirements"></a>Требования  
  
|Header|Используйте для|  
|------------|-------------|  
|CStringT.h|MFC-только для строковых объектов|  
|atlstr.h|Не-MFC строковых объектов|  
  
##  <a name="allocsysstring"></a>  CStringT::AllocSysString  
 Выделяет строку автоматизации совместимый тип `BSTR` и копирует содержимое `CStringT` объекта, включая завершающий символ null.  
  
```  
BSTR AllocSysString() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вновь выделенные строки.  
  
### <a name="remarks"></a>Примечания  
 В приложениях MFC [CMemoryException класса](../../mfc/reference/cmemoryexception-class.md) создается, если существует нехватка памяти. В программах ATL [CAtlException](../../atl/reference/catlexception-class.md) возникает исключение. Эта функция обычно используется для возврата строки для автоматизации.  
  

 Как правило Если эта строка передается в функцию COM в качестве] параметра, то это требует, чтобы освободить строку участник. Это можно сделать с помощью [SysFreeString](https://msdn.microsoft.com/library/windows/desktop/ms221481.aspx), как описано в Windows SDK. Дополнительные сведения см. в разделе [распределение и освобождение памяти для BSTR](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).  
  
 Дополнительные сведения о функции выделения OLE в Windows см. в разделе [SysAllocString](https://msdn.microsoft.com/library/windows/desktop/ms221458.aspx) в Windows SDK.  

  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CStringT::AllocSysString`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]  
  
##  <a name="ansitooem"></a>  CStringT::AnsiToOem  
 Преобразует все символы в этом `CStringT` объекта из кодировки ANSI в набор символов OEM.  
  
```  
void AnsiToOem();
```  
  
### <a name="remarks"></a>Примечания  
 Функция недоступна при `_UNICODE` определен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]  
  
##  <a name="appendformat"></a>  CStringT::AppendFormat  
 Добавляет форматированных данных в существующий `CStringT` объекта.  
  
```  
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```  
  
### <a name="parameters"></a>Параметры  
 `pszFormat`  
 Строка управления форматом.  
  
 `nFormatID`  
 Строковый идентификатор ресурса, содержащее строку управления форматом.  
  
 `argument`  
 Необязательные аргументы.  
  
### <a name="remarks"></a>Примечания  
 Эта функция форматирует и добавляет серию символов и значений в `CStringT`. Каждый необязательный аргумент (если есть) преобразуется и добавлены согласно соответствующей спецификацией формата в `pszFormat` или из строкового ресурса, обозначенную `nFormatID`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]  
  
##  <a name="collate"></a>  CStringT::Collate  
 Сравнивает две строки с помощью универсальная текстовая функция `_tcscoll`.  
  
```  
int Collate(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Другая строка, используемый для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны, < 0, если это `CStringT` объект меньше, чем `psz`, или > 0, если это `CStringT` объект больше, чем `psz`.  
  
### <a name="remarks"></a>Примечания  
 Универсальная текстовая функция `_tcscoll`, которая определена в TCHAR. Символ «H» сопоставляет либо `strcoll`, `wcscoll`, или `_mbscoll`, в зависимости от кодировки, определенные во время компиляции. Каждая функция выполняет сравнение с учетом регистра строк согласно кодовой странице в настоящее время используется. Дополнительные сведения см. в разделе [strcoll wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
##  <a name="collatenocase"></a>  CStringT::CollateNoCase  
 Сравнивает две строки с помощью универсальная текстовая функция `_tcscoll`.  
  
```  
int CollateNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Другая строка, используемый для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки являются идентичными (без учета регистра букв), < 0, если это `CStringT` объект меньше, чем `psz` (без учета регистра), или > 0, если это `CStringT` объект больше `psz` (без учета регистра).  
  
### <a name="remarks"></a>Примечания  
 Универсальная текстовая функция `_tcscoll`, которая определена в TCHAR. Символ «H» сопоставляет либо `stricoll`, `wcsicoll`, или `_mbsicoll`, в зависимости от кодировки, определенные во время компиляции. Каждая функция выполняет сравнение без учета регистра строк, согласно кодовой странице в настоящий момент. Дополнительные сведения см. в разделе [strcoll wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]  
  
##  <a name="compare"></a>  CStringT::Compare  
 Сравнивает две строки (с учетом регистра).  
  
```  
int Compare(PCXSTR psz) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Другая строка, используемый для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны, < 0, если это `CStringT` объект меньше, чем `psz`, или > 0, если это `CStringT` объект больше, чем `psz`.  
  
### <a name="remarks"></a>Примечания  
 Универсальная текстовая функция `_tcscmp`, которая определена в TCHAR. Символ «H» сопоставляет либо `strcmp`, `wcscmp`, или `_mbscmp`, в зависимости от кодировки, определенные во время компиляции. Каждая функция выполняет сравнение строк с учетом регистра и не зависит от языкового стандарта. Дополнительные сведения см. в разделе [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).  
  
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
 `psz`  
 Другая строка, используемый для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны (без учета регистра), < 0, если это `CStringT` объект меньше, чем `psz` (без учета регистра), или > 0, если это `CStringT` больше чем `psz` (без учета регистра).  
  
### <a name="remarks"></a>Примечания  
 Универсальная текстовая функция `_tcsicmp`, которая определена в TCHAR. Символ «H» сопоставляет либо `_stricmp`, `_wcsicmp` или `_mbsicmp`, в зависимости от кодировки, определенные во время компиляции. Каждая функция выполняет сравнение без учета регистра строк. Сравнение зависит от `LC_CTYPE` аспект языкового стандарта, но не `LC_COLLATE`. Дополнительные сведения см. в разделе [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).  
  
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
 `pch`  
 Указатель на массив символов длиной `nLength`не нулем.  
  
 `nLength`  
 Число символов в `pch`.  
  
 `ch`  
 Одиночный символ.  
  
 `pszSrc`  
 Идентифицирующий копируется это `CStringT` объекта.  
  
 `pStringMgr`  
 Указатель на диспетчер памяти для `CStringT` объекта. Дополнительные сведения о `IAtlStringMgr` и управление памятью для `CStringT`, в разделе [управление памятью с CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 `strSrc`  
 Существующий `CStringT` объект копируется это `CStringT` объекта. Дополнительные сведения о `CThisString` и `CThisSimpleString`, см. в разделе "Примечания".  
  
 `varSrc`  
 Variant-объект копируется это `CStringT` объекта.  
  
 `BaseType`  
 Тип символа класса string. Ниже указаны доступные значения.  
  
 `char` (для символьных строк ANSI).  
  
 `wchar_t` (для символьных строк Юникода).  
  
 `TCHAR` (для ANSI и Юникод символьных строк).  
  
 `bMFCDLL`  
 Логическое значение, указывающее, является ли проект библиотеки DLL MFC (TRUE) или нет (FALSE).  
  
 `SystemString`  
 Должен быть `System::String`, и проект должен быть скомпилирован с параметром/CLR.  
  
 `pString`  
 Дескриптор для `CStringT` объекта.  
  
### <a name="remarks"></a>Примечания  
 Поскольку конструкторы копирования входных данных в новое хранилище, выделенное, следует иметь в виду, что память может привести к исключения. Обратите внимание, что некоторые из этих конструкторов действуют как функции преобразования. Это позволяет заменить, например, `LPTSTR` где `CStringT` требуется объект.  
  
- `CStringT`( `LPCSTR` `lpsz` ): Создает строку в Юникоде `CStringT` строки ANSI. Также можно использовать этот конструктор для загрузки строкового ресурса, как показано в следующем примере.  
  
- `CStringT(` `LPCWSTR` `lpsz` ): Создает `CStringT` строки Юникода.  
  
- `CStringT`( `const unsigned char*` `psz` ): Позволяет создавать `CStringT` из указателя на `unsigned char`.  
  
> [!NOTE]
>  Определение **_CSTRING_DISABLE_NARROW_WIDE_CONVERSION** макрос, чтобы отключить неявные строк преобразование между [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] и [!INCLUDE[TLA#tla_unicode](../../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] строки. Макрос исключает из компиляции конструкторы для поддержки преобразования.  
  
 Обратите внимание, что `strSrc` параметр может быть либо `CStringT` или `CThisSimpleString` объекта. Для `CStringT`, используйте один из его экземпляров по умолчанию ( `CString`, `CStringA`, или `CStringW`); для `CThisSimpleString`, используйте `this` указателя. `CThisSimpleString` Объявляет экземпляр класса [класса CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), — это более мелкие класс строка с менее встроенных функциональных возможностей, чем `CStringT` класса.  
  
 Перегрузка оператора `CSimpleStringT<>&()` создает `CStringT` объекта из `CSimpleStringT` объявления.  
  
> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляры, которые содержат внедренные символы null, не рекомендуется его. Вызов методов и операторов для `CStringT` объектов, которые содержат внедренные символы null может привести к непредвиденным результатам.  
  
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
 Удаление символа или символов из строки, начиная с данного индекса.  
  
```  
int Delete(int iIndex, int nCount = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `iIndex`  
 Отсчитываемый от нуля индекс первого символа в `CStringT` удаляемого объекта.  
  
 `nCount`  
 Число символов для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина измененные строки.  
  
### <a name="remarks"></a>Примечания  
 Если `nCount` длиннее, чем строка, остальная часть строки будут удалены.  
  
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
 `pszSub`  
 Подстрока для поиска.  
  
 `iStart`  
 Индекс символа в строке, чтобы начать поиск с или 0, чтобы запустить с самого начала.  
  
 `ch`  
 Одиночный символ для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого символа в этом `CStringT` объект, который соответствует запрошенного substring или символы; -1, если подстрока или символ не найден.  
  
### <a name="remarks"></a>Примечания  
 Функция перегружен, чтобы принять оба одного символа (аналогично функции времени выполнения `strchr`) и строки (аналогично `strstr`).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]  
  
##  <a name="findoneof"></a>  CStringT::FindOneOf  
 Выполняет поиск первого символа, который соответствует любому символу, содержащихся в этой строке `pszCharSet`.  
  
```  
int FindOneOf(PCXSTR pszCharSet) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszCharSet`  
 Строка, содержащая символы для сопоставления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого символа в этой строке, в которой присутствует также в `pszCharSet`; -1, если совпадения нет.  
  
### <a name="remarks"></a>Примечания  
 Находит первое вхождение любого символа в `pszCharSet`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]  
  
##  <a name="format"></a>  CStringT::Format  
 Записывает форматированные данные `CStringT` так же, как [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) форматирует данные в стиле C массив символов.  
  
```  
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```  
  
### <a name="parameters"></a>Параметры  
 `nFormatID`  
 Строковый идентификатор ресурса, содержащее строку управления форматом.  
  
 `pszFormat`  
 Строка управления форматом.  
  
 `argument`  
 Необязательные аргументы.  
  
### <a name="remarks"></a>Примечания  
 Эта функция форматирует и сохраняет серию символов и значений в `CStringT`. Каждый необязательный аргумент (если есть) преобразуется и выводится согласно соответствующей спецификацией формата в `pszFormat` или из строкового ресурса, обозначенную `nFormatID`.  
  
 Вызов завершится ошибкой, если сам объект строки предлагается как параметр `Format`. Например следующий код приведет к непредсказуемым результатам:  
  
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
 `nFormatID`  
 Строковый идентификатор ресурса, содержащий текст неформатированный сообщения.  
  
 `pszFormat`  
 Указывает на строку управления форматом. Он будет сканирование для вставок и соответствующим образом в формате. Строка формата подобна функции времени выполнения `printf`-стиль строки формата, за исключением того, он допускает использование параметров должны быть вставлены в произвольном порядке.  
  
 `argument`  
 Необязательные аргументы.  
  
### <a name="remarks"></a>Примечания  
 Функция требует определения сообщения в качестве входного. Определение сообщения определяется `pszFormat` или из строкового ресурса, обозначенную `nFormatID`. Функция копирует текстовое сообщение, отформатированное для `CStringT` объекта, обработкой, внедренных вставки последовательности по запросу.  
  
> [!NOTE]
> `FormatMessage` пытается выделить системную память для вновь форматируемой строки. Если эта попытка завершается неудачей, исключение памяти автоматически создается исключение.  
  
 Каждой вставки должен иметь соответствующий следующий параметр `pszFormat` или `nFormatID` параметра. В тексте сообщения для динамического форматирования сообщения поддерживаются несколько escape-последовательности. Дополнительные сведения см. в разделе Windows [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) функции в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]  
  
##  <a name="formatmessagev"></a>  CStringT::FormatMessageV  
 Форматирование строки сообщения при помощи переменное число аргументов.  
  
```  
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```  
  
### <a name="parameters"></a>Параметры  
 `pszFormat`  
 Указывает на строку управления форматом. Он будет сканирование для вставок и соответствующим образом в формате. Строка формата подобна функции времени выполнения `printf`-стиль строки формата, за исключением того, он допускает использование параметров должны быть вставлены в произвольном порядке.  
  
 `pArgList`  
 Указатель на список аргументов.  
  
### <a name="remarks"></a>Примечания  
 Функция требует определения сообщения в качестве выходных данных определяется `pszFormat`. Функция копирует форматированный текст сообщения и переменный список аргументов для `CStringT` объекта, обработкой, внедренных вставки последовательности по запросу.  
  
> [!NOTE]
> `FormatMessageV` вызовы [CStringT::FormatMessage](#formatmessage), который пытается выделить системной памяти для вновь форматируемой строки. Если эта попытка завершается неудачей, исключение памяти автоматически создается исключение.  
  
 Дополнительные сведения см. в разделе Windows [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) функции в Windows SDK.  
  
##  <a name="formatv"></a>  CStringT::FormatV  
 Форматирование строки сообщения при помощи переменное число аргументов.  
  
```  
void FormatV(PCXSTR pszFormat, va_list args);
```  
  
### <a name="parameters"></a>Параметры  
 `pszFormat`  
 Указывает на строку управления форматом. Он будет сканирование для вставок и соответствующим образом в формате. Строка формата подобна функции времени выполнения `printf`-стиль строки формата, за исключением того, он допускает использование параметров должны быть вставлены в произвольном порядке.  
  
 `args`  
 Указатель на список аргументов.  
  
### <a name="remarks"></a>Примечания  
 Записывает форматированную строку и переменный список аргументов для `CStringT` строки в том же, как `vsprintf_s` форматирует данные в стиле C массив символов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]  
  
##  <a name="getenvironmentvariable"></a>  CStringT::GetEnvironmentVariable  
 Задает строковое значение указанной переменной среды.  
  
```  
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```  
  
### <a name="parameters"></a>Параметры  
 `pszVar`  
 Указатель null нулевым байтом строка, указывающая переменной среды.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Получает значение указанной переменной из блок среды вызывающего процесса. Значение в виде символом null строку символов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]  
  
##  <a name="insert"></a>  CStringT::Insert  
 Вставляет символ или подстроку с указанным индексом в строке.  
  
```  
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```  
  
### <a name="parameters"></a>Параметры  
 `iIndex`  
 Индекс символа, перед которым курсор будет иметь место.  
  
 `psz`  
 Указатель на подстроки для вставки.  
  
 `ch`  
 Вставляемый знак.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина измененные строки.  
  
### <a name="remarks"></a>Примечания  
 `iIndex` Идентифицирует первый символ, который будет перемещен, чтобы освободить место для символа или подстроки. Если `nIndex` равен нулю, курсор будет выполняться перед всю строку. Если `nIndex` больше, чем длина строки, функция будет объединения присутствует строки и новые материалы, предоставляемые либо `ch` или `psz`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]  
  
##  <a name="left"></a>  CStringT::Left  
 Извлекает `nCount` самых левых символов из этого объекта `CStringT` и возвращает копию извлеченной подстроки.  
  
```  
CStringT Left(int nCount) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `nCount`  
 Число символов, извлекаемых из данного объекта `CStringT`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CStringT`, содержащий копию указанного диапазона символов. Возвращенный объект `CStringT` может быть пустым.  
  
### <a name="remarks"></a>Примечания  
 Если значение `nCount` превышает длину строки, извлекается вся строка. Функция `Left` аналогична функции `Left` в языке Basic.  
  
 Для многобайтовых кодировок (MBCS) значение `nCount` обрабатывает каждую 8-разрядную последовательность как один символ, поэтому значение `nCount` возвращает количество многобайтовых символов, умноженное на 2.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]  
  
##  <a name="loadstring"></a>  CStringT::LoadString  
 Считывает строку ресурса Windows, определяется `nID`, в существующую коллекцию `CStringT` объекта.  
  
```  
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `hInstance`  
 Дескриптор экземпляра модуля.  
  
 `nID`  
 Идентификатор Windows строку ресурса.  
  
 `wLanguageID`  
 Язык строкового ресурса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если загрузка ресурсов выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Загрузка строковых ресурсов ( `nID`) из указанного модуля ( `hInstance`) с использованием указанного языка ( `wLanguage`).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]  
  
##  <a name="makelower"></a>  CStringT::MakeLower  
 Преобразует `CStringT` объекта в строку в нижний регистр.  
  
```  
CStringT& MakeLower();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результирующая строка нижнего регистра.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]  
  
##  <a name="makereverse"></a>  CStringT::MakeReverse  
 Меняет порядок символов в `CStringT` объекта.  
  
```  
CStringT& MakeReverse();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полученный в обратном направлении строки.  
  
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
 Извлекает подстроку длиной `nCount` символов из этого `CStringT` объект, начиная с позиции `iFirst` (от нуля).  
  
```  
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `iFirst`  
 Отсчитываемый от нуля индекс первого символа в этом `CStringT` объекта, которые будут включены в извлеченной подстроки.  
  
 `nCount`  
 Число символов, извлекаемых из данного объекта `CStringT`. Если этот параметр не задан, будет извлечен остаток строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CStringT`, содержащий копию указанного диапазона символов. Обратите внимание, что возвращаемый `CStringT` объекта может быть пустым.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает копию извлеченной подстроки. `Mid` аналогичен функция основные Mid (за исключением того, что индексы в Basic начинаются с 1).  
  
 Для многобайтовой кодировки (MBCS) `nCount` ссылается на каждый 8-разрядное символ, то есть руководитель и младший байт один Многобайтовый символ считаются за два символа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]  
  
##  <a name="oemtoansi"></a>  CStringT::OemToAnsi  
 Преобразует все символы в этом `CStringT` объекта из OEM кодировки набора знаков ANSI.  
  
```  
void OemToAnsi();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция недоступна при `_UNICODE` определен.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CStringT::AnsiToOem](#ansitooem).  
  
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
 `ch1`  
 ANSI или Юникод символ для добавления со строкой.  
  
 `ch2`  
 ANSI или Юникод символ для добавления со строкой.  
  
 `str1`  
 Объект `CStringT` для объединения с строку или символ.  
  
 `str2`  
 Объект `CStringT` для объединения с строку или символ.  
  
 `psz1`  
 Указатель на строку завершающим нулем для объединения с строку или символ.  
  
 `psz2`  
 Указатель на строку для объединения с строку или символ.  
  
### <a name="remarks"></a>Примечания  
 Существует семь формы перегрузки `CStringT::operator+` функции. Первая версия объединяет две существующие `CStringT` объектов. Объединение двух следующих `CStringT` объекта и строку, завершающуюся символом null. Объединение двух следующих `CStringT` объекта, а также символ ANSI. Последние две СЦЕПИТЬ `CStringT` объекта и символ Юникода.  
  
> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляры, которые содержат внедренные символы null, не рекомендуется его. Вызов методов и операторов для `CStringT` объектов, которые содержат внедренные символы null может привести к непредвиденным результатам.  
  
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
 str  
 Ссылка на объект `CThisSimpleString`.  
  
 `bMFCDLL`  
 Логическое значение, указывающее, является ли проект MFC библиотеки DLL.  
  
 `BaseType`  
 Базовый тип строки.  
  
 `var`  
 Variant-объект для объединения с данной строки.  
  
 `ch`  
 ANSI или Юникод символ для добавления со строкой.  
  
 `pszSrc`  
 Указатель, объединяемых исходной строки.  
  
 `strSrc`  
 Объект `CStringT` для объединения с данной строки.  
  
### <a name="remarks"></a>Примечания  
 Оператор принимает другой `CStringT` объект, указателем символа или один символ. Следует иметь в виду, памяти, исключения могут возникать при каждом использовании этот оператор объединения, так как новое хранилище может быть выделено для символов, добавленных к этому `CStringT` объекта.  
  
 Сведения о `CThisSimpleString`, в разделе «Примечания» [CStringT::CStringT](#cstringt).  
  
> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляры, которые содержат внедренные символы null, не рекомендуется его. Вызов методов и операторов для `CStringT` объектов, которые содержат внедренные символы null может привести к непредвиденным результатам.  
  
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
 `ch1`  
 ANSI или Юникод знака для сравнения.  
  
 `ch2`  
 ANSI или Юникод знака для сравнения.  
  
 `str1`  
 Объект `CStringT` для сравнения.  
  
 `str2`  
 Объект `CStringT` для сравнения.  
  
 `psz1`  
 Указатель на строку завершающим нулем для сравнения.  
  
 `psz2`  
 Указатель на строку завершающим нулем для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Проверяет, является ли строку или символ слева равен строку или символ, с правой стороны и возвращает значение TRUE или FALSE соответственно.  
  
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
 `ch1`  
 ANSI или Юникод символ для добавления со строкой.  
  
 `ch2`  
 ANSI или Юникод символ для добавления со строкой.  
  
 `str1`  
 Объект `CStringT` для сравнения.  
  
 `str2`  
 Объект `CStringT` для сравнения.  
  
 `psz1`  
 Указатель на строку завершающим нулем для сравнения.  
  
 `psz2`  
 Указатель на строку завершающим нулем для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Проверяет строку или символ слева не равно строку или символ справа от оператора.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]  
  
##  <a name="operator_lt"></a>  CStringT::operator &lt;  
 Определяет, является ли строка в левой части оператора меньше, чем строка справа от оператора.  
  
```  
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `str1`  
 Объект `CStringT` для сравнения.  
  
 `str2`  
 Объект `CStringT` для сравнения.  
  
 `psz1`  
 Указатель на строку завершающим нулем для сравнения.  
  
 `psz2`  
 Указатель на строку завершающим нулем для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Лексикографического сравнения строк, символ за символом до:  
  
-   Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.  
  
-   Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.  
  
-   Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, поэтому сроки равны.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]  
  
##  <a name="operator_gt"></a>  CStringT::operator &gt;  
 Определяет, является ли строка слева от оператора больше, чем строка справа от оператора.  
  
```  
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `str1`  
 Объект `CStringT` для сравнения.  
  
 `str2`  
 Объект `CStringT` для сравнения.  
  
 `psz1`  
 Указатель на строку завершающим нулем для сравнения.  
  
 `psz2`  
 Указатель на строку завершающим нулем для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Лексикографического сравнения строк, символ за символом до:  
  
-   Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.  
  
-   Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.  
  
-   Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]  
  
##  <a name="operator_lt_eq"></a>  CStringT::operator &lt;=  
 Определяет, является ли строка в левой части оператора меньше или равным строке справа от оператора.  
  
```  
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `str1`  
 Объект `CStringT` для сравнения.  
  
 `str2`  
 Объект `CStringT` для сравнения.  
  
 `psz1`  
 Указатель на строку завершающим нулем для сравнения.  
  
 `psz2`  
 Указатель на строку завершающим нулем для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Лексикографического сравнения строк, символ за символом до:  
  
-   Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.  
  
-   Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.  
  
-   Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]  
  
##  <a name="operator_gt_eq"></a>  CStringT::operator &gt;=  
 Определяет, является ли строка слева от оператора больше или равным строке справа от оператора.  
  
```  
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `str1`  
 Объект `CStringT` для сравнения.  
  
 `str2`  
 Объект `CStringT` для сравнения.  
  
 `psz1`  
 Указатель на строку для сравнения.  
  
 `psz2`  
 Указатель на строку для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Лексикографического сравнения строк, символ за символом до:  
  
-   Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.  
  
-   Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.  
  
-   Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]  
  
##  <a name="remove"></a>  CStringT::Remove  
 Удаляет все вхождения указанного символа в строке.  
  
```  
int Remove(XCHAR chRemove);
```  
  
### <a name="parameters"></a>Параметры  
 `chRemove`  
 Знак, который необходимо удалить из строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов, удалено из строки. Нуль, если строка не изменяется.  
  
### <a name="remarks"></a>Примечания  
 Сравнение символа чувствительны к регистру.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]  
  
##  <a name="replace"></a>  CStringT::Replace  
 Существуют две версии `Replace`. Первая версия заменяет одну или несколько копий подстроки, используя другой подстрокой. Обе подстроки, завершающуюся значением null. Вторая версия заменяет одну или несколько копий символа с помощью другого символа. Обе версии оперируют символьные данные, хранящиеся в `CStringT`.  
  
```  
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```  
  
### <a name="parameters"></a>Параметры  
 `pszOld`  
 Указатель на строку, завершающуюся значением null должен быть заменен `pszNew`.  
  
 `pszNew`  
 Указатель на строку, завершающуюся значением null, которая заменяет `pszOld`.  
  
 `chOld`  
 Символ должен быть заменен `chNew`.  
  
 `chNew`  
 Замена символов `chOld`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число экземпляров замененного символ или подстроку, или нуль, если строка не изменяется.  
  
### <a name="remarks"></a>Примечания  
 `Replace` можно изменить длину строки, так как `pszNew` и `pszOld` не нужно иметь одинаковую длину, и несколько копий старого подстроки может быть изменено в новую. Функция выполняется сопоставление с учетом регистра.  
  
 Примеры `CStringT` экземпляры `CString`, `CStringA`, и `CStringW`.  
  
 Для `CStringA`, `Replace` работает с ANSI или многобайтовая кодировка (MBCS). Для `CStringW`, `Replace` работает с расширенными символами.  
  
 Для `CString`, символьный тип данных выбран во время компиляции, в зависимости того определен ли константы в следующей таблице.  
  
|Константа|Символьный тип данных|  
|----------------------|-------------------------|  
|`_UNICODE`|Расширенные символы|  
|`_MBCS`|Многобайтовые символы|  
|Ни|Однобайтовые символы|  
|Оба значения|Не определено|  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]  
  
##  <a name="reversefind"></a>  CStringT::ReverseFind  
 Выполняет это `CStringT` объект для сопоставления последнего символа.  
  
```  
int ReverseFind(XCHAR ch) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ch`  
 Символ для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс последнего символа в данном `CStringT` объект, который соответствует запрошенного символ или значение -1, если символ не найден.  
  
### <a name="remarks"></a>Примечания  
 Функция аналогична функции времени выполнения `strrchr`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]  
  
##  <a name="right"></a>  CStringT::Right  
 Извлекает последний (то есть правых) `nCount` символов из этого `CStringT` объекта и возвращает копию извлеченной подстроки.  
  
```  
CStringT Right(int nCount) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `nCount`  
 Число символов, извлекаемых из данного объекта `CStringT`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CStringT`, содержащий копию указанного диапазона символов. Обратите внимание, что возвращаемый `CStringT` объекта может быть пустым.  
  
### <a name="remarks"></a>Примечания  
 Если значение `nCount` превышает длину строки, извлекается вся строка. `Right` Аналогично базовый `Right` функции (за исключением того, что индексы в Basic отсчитываются от нуля).  
  
 Для многобайтовой кодировки (MBCS) `nCount` ссылается на каждый 8-разрядное символ, то есть руководитель и младший байт один Многобайтовый символ считаются за два символа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]  
  
##  <a name="setsysstring"></a>  CStringT::SetSysString  
 Перераспределяет `BSTR` , на который указывает `pbstr` и копирует содержимое `CStringT` объекта, включая `NULL` символов.  
  
```  
BSTR SetSysString(BSTR* pbstr) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `pbstr`  
 Указатель на строку символов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая строка.  
  
### <a name="remarks"></a>Примечания  
 В зависимости от содержимого `CStringT` объект, значение `BSTR` ссылается `pbstr` можно изменить. Эта функция создает `CMemoryException` Если существует нехватка памяти.  
  
 Эта функция обычно используется для изменения значения строк, передаваемых по ссылке для автоматизации.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]  
  
##  <a name="spanexcluding"></a>  CStringT::SpanExcluding  
 Извлекает символы из строки, начиная с первого символа, не входящие в набор символов, которые идентифицируют `pszCharSet`.  
  
```  
CStringT SpanExcluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `pszCharSet`  
 Строка интерпретируется как набор символов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Подстроке, которая содержит символы в строке, которые не находятся в `pszCharSet`, начиная с первого символа в строке и заканчивая первого символа в строке, которая присутствует также в `pszCharSet` (то есть, начиная с первого символа в Строка и найти до, но не включая первого символа в строку, которая является `pszCharSet`). Возвращает всю строку, если ни один знак из `pszCharSet` найдено в строке.  
  
### <a name="remarks"></a>Примечания  
 `SpanExcluding` Извлекает и возвращает все символы, предшествующие первое вхождение символа из `pszCharSet` (другими словами, символ из `pszCharSet` и все символы в строке, не возвращаются). Если ни один знак из `pszCharSet` находится в строке, затем `SpanExcluding` возвращает всю строку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]  
  
##  <a name="spanincluding"></a>  CStringT::SpanIncluding  
 Извлекает символы из строки, начиная с первого символа, в набор символов, которые идентифицируют `pszCharSet`.  
  
```  
CStringT SpanIncluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `pszCharSet`  
 Строка интерпретируется как набор символов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Подстроке, которая содержит символы в строке, в которой находятся в `pszCharSet`, начиная с первого символа в строке и заканчивается, когда символ находится в строке, которая не находится в `pszCharSet`. `SpanIncluding` Возвращает пустой подстрокой, если первый символ в строке не находится в указанном наборе.  
  
### <a name="remarks"></a>Примечания  
 Если первый символ строки не в наборе символов, то `SpanIncluding` возвращает пустую строку. В противном случае он возвращает последовательность последовательных символов, которые входят в набор.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]  
  
##  <a name="tokenize"></a>  CStringT::Tokenize  
 Находит следующий токен в целевой строке  
  
```  
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `pszTokens`  
 Строка, содержащая разделители токенов. Порядок эти разделители не имеет значения.  
  
 `iStart`  
 Отсчитываемый от нуля индекс начала поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CStringT` объект, содержащий текущее значение маркера.  
  
### <a name="remarks"></a>Примечания  
 `Tokenize` Функция находит следующий токен в целевой строке. Набор символов в `pszTokens` указывает возможные разделители токенов, которые требуется найти. При каждом вызове `Tokenize` начинается функция `iStart`, пропускает ведущие разделители и возвращает `CStringT` объект, содержащий текущий маркер, который представляет собой строку символов до следующего символа-разделителя. Значение `iStart` обновляться до позиции, следующей конечный символ разделителя или -1, если достигнут конец строки. Можно выделить другие токены из оставшейся части целевой строки с помощью последовательных вызовов `Tokenize`, с использованием `iStart` для отслеживания где в строке следующий токен — для чтения. Если нет больше токенов функция возвращает пустую строку и `iStart` будет иметь значение -1.  
  
 В отличие от CRT маркировки функций, таких как [strtok_s _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), `Tokenize` не изменяет целевой строки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]  
  
### <a name="remarks"></a>Примечания  
 Выходные данные этого примера выглядит следующим образом:  
  
 `Resulting Token: First`  
  
 `Resulting Token: Second`  
  
 `Resulting Token: Third`  
  
##  <a name="trim"></a>  CStringT::Trim  
 Обрезка начальных и конечных символов из строки.  
  
```  
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```  
  
### <a name="parameters"></a>Параметры  
 `chTarget`  
 Целевой символ для усечения.  
  
 `pszTargets`  
 Указатель на строку, содержащую символы целевой для усечения. Все начальные и конечные вхождения символов в `pszTarget` будут удалены из `CStringT` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обрезанная строка.  
  
### <a name="remarks"></a>Примечания  
 Удаляет все начальные и конечные вхождения одно из следующих:  
  
-   Символ, указанный `chTarget.`  
  
-   Все символы, входящие в строки, заданной параметром `pszTargets.`  
  
-   Пробел.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]  
  
### <a name="remarks"></a>Примечания  
 Выходные данные этого примера выглядит следующим образом:  
  
 `Before: "******Soccer is best, but liquor is quicker!!!!!"`  
  
 `After : "Soccer is best, but liquor is quicker"`  
  
##  <a name="trimleft"></a>  CStringT::TrimLeft  
 Обрезка начальных символов из строки.  
  
```  
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```  
  
### <a name="parameters"></a>Параметры  
 `chTarget`  
 Целевой символ для усечения.  
  
 `pszTargets`  
 Указатель на строку, содержащую символы целевой для усечения. Все начальные вхождения символов в `pszTarget` будут удалены из `CStringT` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полученный обрезанная строка.  
  
### <a name="remarks"></a>Примечания  
 Удаляет все начальные и конечные вхождения одно из следующих:  
  
-   Символ, указанный `chTarget.`  
  
-   Все символы, входящие в строки, заданной параметром `pszTargets.`  
  
-   Пробел.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]  
  
##  <a name="trimright"></a>  CStringT::TrimRight  
 Обрезка конечных символов из строки.  
  
```  
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```  
  
### <a name="parameters"></a>Параметры  
 `chTarget`  
 Целевой символ для усечения.  
  
 `pszTargets`  
 Указатель на строку, содержащую символы целевой для усечения. Все конечные вхождения символов в `pszTarget` будут удалены из `CStringT` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CStringT` , содержащий обрезанная строка.  
  
### <a name="remarks"></a>Примечания  
 Удаляет конечные вхождения одно из следующих:  
  
-   Символ, указанный `chTarget.`  
  
-   Все символы, входящие в строки, заданной параметром `pszTargets.`  
  
-   Пробел.  
  
 `CStringT& TrimRight(XCHAR chTarget)` Версия принимает один параметр символов и удаляет все копии этого знака в конце `CStringT` строковые данные. Он начинается с конца строки и работает ближе к началу. Он останавливается при обнаружении другой символ или `CSTringT` символьных данных не хватает.  
  
 `CStringT& TrimRight(PCXSTR pszTargets)` Версия принимает нулем строка, содержащая различных символов для поиска. Удаляет все копии этих символов в `CStringT` объекта. Он начинается в конце строки и работает ближе к началу. Он останавливается при обнаружении символ, который не находится в целевой строке или `CStringT` символьных данных не хватает. Он не пытается сопоставить строку всей целевой подстрокой, расположенной в конце `CStringT`.  
  
 `CStringT& TrimRight()` Версии не требует параметров. Он урезает любые конечные символы пробела в конце `CStringT` строки. Разрывы строк, пробелы или вкладок, может быть пробельных символов.  
  
-  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [Класс CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)


