---
title: "Класс CStringT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CString
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
caps.latest.revision: 33
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9660db5ff0d41a31f7d2a4e824df4e4bdf6a00e6
ms.lasthandoff: 02/24/2017

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
  
- `char`(для символьных строк ANSI).  
  
- `wchar_t`(для символьных строк в Юникоде).  
  
- **TCHAR** (для символьных строк ANSI или Юникод).  
  
 `StringTraits`  
 Определяет, должен ли класс string поддержка библиотеки времени выполнения C (CRT) и где расположены строковые ресурсы. Ниже указаны доступные значения.  
  
- **StrTraitATL<> </> ** | `char` | **TCHAR, ChTraitsCRT<> </> ** | `char` | **TCHAR > >**  
  
     Класс требует поддержки CRT и поиск строк ресурса в модуль, указанный параметром `m_hInstResource` (член класса модуля приложения).  
  
- **StrTraitATL<> </> ** | `char` | **TCHAR, ChTraitsOS<> </> ** | `char` | **TCHAR > >**  
  
     Класс не требуется поддержка CRT и поиск строк ресурса в модуль, указанный параметром `m_hInstResource` (член класса модуля приложения).  
  
- **StrTraitMFC<> </> ** | `char` | **TCHAR, ChTraitsCRT<> </> ** | `char` | **TCHAR > >**  
  
     Классу требуется поддержка CRT и выполняет поиск строки ресурсов, с помощью стандартного алгоритма поиска MFC.  
  
- **StrTraitMFC<> </> ** | `char` | **TCHAR, ChTraitsOS<> </> ** | `char` | **TCHAR > >**  
  
     Класс не требуется поддержка CRT и выполняет поиск строки ресурсов, с помощью стандартного алгоритма поиска MFC.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringT::CStringT](#cstringt)|Создает `CStringT` объект различными способами.|  
|[CStringT:: ~ CStringT](#_dtorcstringt)|Уничтожает объект `CStringT`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringT::AllocSysString](#allocsysstring)|Выделяет `BSTR` из `CStringT` данных.|  
|[CStringT::AnsiToOem](#ansitooem)|Такое преобразование на месте кодировки ANSI, в набор символов OEM.|  
|[CStringT::AppendFormat](#appendformat)|Добавляет форматированных данных в существующий `CStringT` объекта.|  
|[CStringT::Collate](#collate)|Сравнивает две строки (регистр, использует языкового стандарта).|  
|[CStringT::CollateNoCase](#collatenocase)|Сравнивает две строки (без учета регистра, использует языкового стандарта).|  
|[CStringT::Compare](#compare)|Сравнивает две строки (с учетом регистра).|  
|[CStringT::CompareNoCase](#comparenocase)|Сравнивает две строки (без учета регистра).|  
|[CStringT::Delete](#delete)|Удаление символа или символов из строки.|  
|[CStringT::Find](#find)|Поиск символа или подстроки в состав более крупной строки.|  
|[CStringT::FindOneOf](#findoneof)|Находит первый соответствующий символ из набора.|  
|[CStringT::Format](#format)|Форматирует строку как `sprintf` does.|  
|[CStringT::FormatMessage](#formatmessage)|Форматирует строку сообщения.|  
|[CStringT::FormatMessageV](#formatmessagev)|Форматирование строки сообщения при помощи переменное число аргументов.|  
|[CStringT::FormatV](#formatv)|Определяет строку, с помощью переменной список аргументов.|  
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Задает строковое значение указанной переменной среды.|  
|[CStringT::Insert](#insert)|Вставляет один символ или подстроку с указанным индексом в строке.|  
|[CStringT::Left](#left)|Извлекает в левой части строки.|  
|[CStringT::LoadString](#loadstring)|Загружает существующий `CStringT` из ресурса Windows.|  
|[CStringT::MakeLower](#makelower)|Преобразует все знаки в данной строке в нижний регистр.|  
|[CStringT::MakeReverse](#makereverse)|Изменяет строку.|  
|[CStringT::MakeUpper](#makeupper)|Преобразует все знаки в данной строке в верхний регистр.|  
|[CStringT::Mid](#mid)|Извлекает средней части строки.|  
|[CStringT::OemToAnsi](#oemtoansi)|Такое преобразование на месте OEM кодировки набора знаков ANSI.|  
|[CStringT::Remove](#remove)|Удаляет указанных символов из строки.|  
|[CStringT::Replace](#replace)|Заменяет указанный символов с другими символами.|  
|[CStringT::ReverseFind](#reversefind)|Поиск символов в длинной строке; начиная с конца.|  
|[CStringT::Right](#right)|Извлекает правую часть строки.|  
|[CStringT::SetSysString](#setsysstring)|Задает существующий `BSTR` объекта данными из `CStringT` объекта.|  
|[CStringT::SpanExcluding](#spanexcluding)|Извлекает символы из строки, начиная с первого символа, не отображаемые в набор символов, идентифицируемый `pszCharSet`.|  
|[CStringT::SpanIncluding](#spanincluding)|Извлекает подстроку, содержащая только символы в наборе.|  
|[CStringT::Tokenize](#tokenize)|Извлекает указанный маркеры в целевой строке.|  
|[CStringT::Trim](#trim)|Удаляет все начальные и конечные пробелы из строки.|  
|[CStringT::TrimLeft](#trimleft)|Обрезка начальных пробелов в строке.|  
|[CStringT::TrimRight](#trimright)|Обрезка конечные символы пробела в строке.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#operator_eq)|Присваивает новое значение для `CStringT` объекта.|  
|[CStringT::operator +](#operator_add)|Сцепляет две строки или символ и строку.|  
|[CStringT::operator +=](#operator_add_eq)|Сцепляет новую строку в конец существующей строки.|  
|[CStringT::operator ==](#operator_eq_eq)|Определяет, логически равны ли две строки.|  
|[CStringT::operator! =](#operator_neq)|Определяет, если две строки логически не равны.|  
|[CStringT::operator&lt;](#operator_lt)|Определяет, является ли строка в левой части оператора меньше строка с правой стороны.|  
|[CStringT::operator&gt;](#operator_gt)|Определяет, является ли строка слева от оператора больше, чем строка в правой части.|  
|[CStringT::operator&lt;=](#operator_lt_eq)|Определяет, является ли строка в левой части оператора меньше или равным строке справа от оператора.|  
|[CStringT::operator&gt;=](#operator_gt_eq)|Определяет, является ли строка слева от оператора больше или равным строке справа от оператора.|  
  
## <a name="remarks"></a>Примечания  
 `CStringT`наследует от [CSimpleStringT класса](../../atl-mfc-shared/reference/csimplestringt-class.md). Дополнительные функции, такие как символ манипуляций, упорядочение и поиск, реализуются `CStringT`.  
  
> [!NOTE]
> `CStringT`объекты способны исключения. Это происходит, когда `CStringT` объекта недостаточно памяти для какой-либо причине.  
  
 Объект `CStringT` объект состоит из последовательности символов переменной длины. `CStringT`предоставляет функции и операторы, используя синтаксис, аналогичный Basic. Объединение и операторы сравнения, вместе с упрощенной памятью `CStringT` проще в использовании, чем обычный символ массивы объектов.  
  
> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляры, которые содержат внедренные символы null, мы не рекомендуем его. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы null может привести к непредвиденным результатам.  
  
 С помощью различных сочетаний `BaseType` и `StringTraits` параметров, `CStringT` объекты можно поставляются в следующих типов, которые были заранее библиотеки ATL.  
  
 При использовании в приложении ATL:  
  
 `CString`, `CStringA`, и `CStringW` экспортируются из библиотеки DLL MFC (MFC90. Библиотека DLL), никогда не от пользователя библиотеки DLL. Это позволяет предотвратить `CStringT` из определяемой multiply.  
  
> [!NOTE]
>  Если обнаружены ошибки компоновщика при экспорте `CString`-класс, производный от расширения MFC DLL в Visual C++ .NET 2002, а также обойти эту проблему как описано в статье базы знаний «Связывание ошибки при вы импорта создания классы» (номер Q309801), следует удалить этот код, так как эта ошибка исправлена в Visual C++ .NET 2003. Статьи базы знаний можно найти на компакт-диске библиотеки MSDN или в [http://support.microsoft.com/support](http://support.microsoft.com/support).  
  
 В приложениях MFC доступны следующие строки:  
  
|Тип CStringT|Объявление|  
|-------------------|-----------------|  
|`CStringA`|Знак ANSI введите строку с поддержкой CRT.|  
|`CStringW`|Знак Юникода типа string с поддержкой CRT.|  
|`CString`|ANSI и Юникод символьные типы с поддержкой CRT.|  
  
 Следующая строка типов, доступных в проектах where **ATL_CSTRING_NO_CRT** определяется:  
  
|Тип CStringT|Объявление|  
|-------------------|-----------------|  
|**CAtlStringA**|Знак ANSI введите строку без поддержки CRT.|  
|**CAtlStringW**|Знак Юникода типа string, не поддерживающих CRT.|  
|**CAtlString**|ANSI и Юникод символьные типы без поддержки CRT.|  
  
 Следующая строка типов, доступных в проектах where **ATL_CSTRING_NO_CRT** не определен:  
  
|Тип CStringT|Объявление|  
|-------------------|-----------------|  
|**CAtlStringA**|Знак ANSI введите строку с поддержкой CRT.|  
|**CAtlStringW**|Знак Юникода типа string с поддержкой CRT.|  
|**CAtlString**|ANSI и Юникод символьные типы с поддержкой CRT.|  
  
 `CString`объекты также имеют следующие характеристики:  
  
- `CStringT`объекты могут увеличиваться в результате операции объединения.  
  
- `CStringT`объекты следуют «value семантику». Представьте `CStringT` объект как фактической строки, а не как указатель на строку.  
  
-   Вы можете свободно заменить `CStringT` объектов для `PCXSTR` аргументы функций.  
  
-   Управление памятью, настраиваемого для буферы строк. Дополнительные сведения см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="cstringt-predefined-types"></a>CStringT предопределенные типы  
 Поскольку `CStringT` использует аргумент шаблона, чтобы определить тип символа (либо [wchar_t](../../c-runtime-library/standard-types.md) или [char](../../c-runtime-library/standard-types.md)) поддерживается, типы параметров метода, может быть затруднена время от времени. Чтобы упростить эту проблему, набор предопределенных типов определяется и используется во всей `CStringT` класса. В следующей таблице перечислены различные типы:  
  
|Имя|Описание|  
|----------|-----------------|  
|`XCHAR`|Один символ (либо `wchar_t` или `char`) с тем же типом символов, `CStringT` объект.|  
|**YCHAR**|Один символ (либо `wchar_t` или `char`) с противоположной символьный тип как `CStringT` объект.|  
|`PXSTR`|Указатель на строку знаков (либо `wchar_t` или `char`) с тем же типом символов, `CStringT` объект.|  
|**PYSTR**|Указатель на строку знаков (либо `wchar_t` или `char`) с противоположной символьный тип как `CStringT` объект.|  
|`PCXSTR`|Указатель на **const** строку символов (либо `wchar_t` или `char`) с тем же типом символов, `CStringT` объект.|  
|**PCYSTR**|Указатель на **const** строку символов (либо `wchar_t` или `char`) с противоположной символьный тип как `CStringT` объект.|  
  
> [!NOTE]
>  Код, который ранее используются недокументированные методы `CString` (таких как **AssignCopy**) необходимо заменить код, который использует следующие методы документированные `CStringT` (таких как `GetBuffer` или `ReleaseBuffer`). Эти методы наследуются от `CSimpleStringT`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## <a name="requirements"></a>Требования  
  
|Header|Использовать для|  
|------------|-------------|  
|CStringT.h|MFC-только для строковых объектов|  
|atlstr.h|MFC не строковых объектов|  
  
##  <a name="a-nameallocsysstringa--cstringtallocsysstring"></a><a name="allocsysstring"></a>CStringT::AllocSysString  
 Выделяет строку автоматизации совместимый тип `BSTR` и копирует содержимое `CStringT` объекта, включая завершающий символ null.  
  
```  
BSTR AllocSysString() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вновь выделенные строки.  
  
### <a name="remarks"></a>Примечания  
 В приложениях MFC [CMemoryException класса](../../mfc/reference/cmemoryexception-class.md) создается, если существует нехватка памяти. В программах ATL [CAtlException](../../atl/reference/catlexception-class.md) возникает исключение. Эта функция обычно используется для возврата строки для автоматизации.  
  
 Как правило Если эта строка передается в функцию COM в качестве] параметра, то это требует, чтобы освободить строку участник. Это можно сделать с помощью [SysFreeString](http://msdn.microsoft.com/en-us/8f230ee3-5f6e-4cb9-a910-9c90b754dcd3), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Дополнительные сведения см. в разделе [распределение и освобождение памяти для BSTR](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).  
  
 Дополнительные сведения о функции выделения OLE в Windows см. в разделе [SysAllocString](http://msdn.microsoft.com/en-us/9e0437a2-9b4a-4576-88b0-5cb9d08ca29b) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CStringT::AllocSysString`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#105;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]  
  
##  <a name="a-nameansitooema--cstringtansitooem"></a><a name="ansitooem"></a>CStringT::AnsiToOem  
 Преобразует все символы в этом `CStringT` объекта кодировки ANSI, в набор символов OEM.  
  
```  
void AnsiToOem();
```  
  
### <a name="remarks"></a>Примечания  
 Функция недоступна при `_UNICODE` определен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#106;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]  
  
##  <a name="a-nameappendformata--cstringtappendformat"></a><a name="appendformat"></a>CStringT::AppendFormat  
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
 Эта функция форматирует и добавляет серию символов и значений в `CStringT`. Каждый необязательный аргумент (при наличии) преобразуется и добавлением согласно соответствующей спецификацией формата в `pszFormat` или из строкового ресурса, идентифицируемый `nFormatID`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#107;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]  
  
##  <a name="a-namecollatea--cstringtcollate"></a><a name="collate"></a>CStringT::Collate  
 Сравнивает две строки с помощью универсальная текстовая функция `_tcscoll`.  
  
```  
int Collate(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Другие строки, используемый для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны, < 0="" if="" this=""> `CStringT` объект меньше, чем `psz`, или настроек 0, если это `CStringT` объект больше, чем `psz`.  
  
### <a name="remarks"></a>Примечания  
 Универсальная текстовая функция `_tcscoll`, которая определена в TCHAR. Сопоставляет H, либо `strcoll`, `wcscoll`, или `_mbscoll`, в зависимости от кодировки, определенные во время компиляции. Каждая функция выполняет сравнение с учетом регистра строки в соответствии с кодовой страницей, в настоящее время используется. Дополнительные сведения см. в разделе [strcoll wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
##  <a name="a-namecollatenocasea--cstringtcollatenocase"></a><a name="collatenocase"></a>CStringT::CollateNoCase  
 Сравнивает две строки с помощью универсальная текстовая функция `_tcscoll`.  
  
```  
int CollateNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Другие строки, используемый для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны (без учета регистра), < 0="" if="" this=""> `CStringT` объект меньше, чем `psz` (без учета регистра), или настроек 0, если это `CStringT` объект больше, чем `psz` (без учета регистра).  
  
### <a name="remarks"></a>Примечания  
 Универсальная текстовая функция `_tcscoll`, которая определена в TCHAR. Сопоставляет H, либо `stricoll`, `wcsicoll`, или `_mbsicoll`, в зависимости от кодировки, определенные во время компиляции. Каждая функция выполняет сравнение без учета регистра строк, согласно кодовой странице в настоящий момент. Дополнительные сведения см. в разделе [strcoll wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#109;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]  
  
##  <a name="a-namecomparea--cstringtcompare"></a><a name="compare"></a>CStringT::Compare  
 Сравнивает две строки (с учетом регистра).  
  
```  
int Compare(PCXSTR psz) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Другие строки, используемый для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны, < 0="" if="" this=""> `CStringT` объект меньше, чем `psz`, или настроек 0, если это `CStringT` объект больше, чем `psz`.  
  
### <a name="remarks"></a>Примечания  
 Универсальная текстовая функция `_tcscmp`, которая определена в TCHAR. Сопоставляет H, либо `strcmp`, `wcscmp`, или `_mbscmp`, в зависимости от кодировки, определенные во время компиляции. Каждая функция выполняет сравнение строк с учетом регистра и не зависит от языкового стандарта. Дополнительные сведения см. в разделе [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).  
  
 Если строка содержит внедренные значения NULL, для сравнения строки считается усечено до первого внедренный символ null.  
  
### <a name="example"></a>Пример  
 В следующем примере показано использование функции `CStringT::Compare`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#110;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]  
  
##  <a name="a-namecomparenocasea--cstringtcomparenocase"></a><a name="comparenocase"></a>CStringT::CompareNoCase  
 Сравнивает две строки (без учета регистра).  
  
```  
int CompareNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Другие строки, используемый для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны (без учета регистра), <0 if="" this=""></0> `CStringT` объект меньше, чем `psz` (без учета регистра), или настроек&0;, если это `CStringT` объект больше, чем `psz` (без учета регистра).  
  
### <a name="remarks"></a>Примечания  
 Универсальная текстовая функция `_tcsicmp`, которая определена в TCHAR. Сопоставляет H, либо `_stricmp`, `_wcsicmp` или `_mbsicmp`, в зависимости от кодировки, определенные во время компиляции. Каждая функция выполняет сравнение строк без учета регистра. Сравнение зависит от `LC_CTYPE` аспект языкового стандарта, но не `LC_COLLATE`. Дополнительные сведения см. в разделе [_stricmp _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#111;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]  
  
##  <a name="a-namecstringta--cstringtcstringt"></a><a name="cstringt"></a>CStringT::CStringT  
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
 Указатель на массив символов длиной `nLength`, символом null.  
  
 `nLength`  
 Число символов в `pch`.  
  
 `ch`  
 Один символ.  
  
 `pszSrc`  
 Завершающим нулем строку необходимо скопировать в это `CStringT` объекта.  
  
 `pStringMgr`  
 Указатель на диспетчер памяти для `CStringT` объекта. Дополнительные сведения о `IAtlStringMgr` и управление памятью для `CStringT`, в разделе [управление памятью с помощью CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 `strSrc`  
 Существующий `CStringT` объекта должно быть скопировано в это `CStringT` объекта. Дополнительные сведения о `CThisString` и `CThisSimpleString`, см. раздел «Примечания».  
  
 `varSrc`  
 Variant-объект копируется это `CStringT` объекта.  
  
 `BaseType`  
 Тип символа класса string. Ниже указаны доступные значения.  
  
 `char`(для символьных строк ANSI).  
  
 `wchar_t`(для символьных строк в Юникоде).  
  
 `TCHAR`(для ANSI и Юникод символьных строк).  
  
 `bMFCDLL`  
 Логическое значение, указывающее, является ли проект библиотеки DLL MFC (TRUE) или нет (FALSE).  
  
 `SystemString`  
 Должен быть `System::String`, и проект должен быть скомпилирован с параметром/CLR.  
  
 `pString`  
 Дескриптор для `CStringT` объекта.  
  
### <a name="remarks"></a>Примечания  
 Поскольку конструкторы скопировать входных данных в новое хранилище, выделенное, следует иметь в виду памяти может привести к исключения. Обратите внимание, что некоторые из этих конструкторов выступать в качестве функции преобразования. Это позволяет заменить, например, `LPTSTR` где `CStringT` ожидается объект.  
  
- `CStringT`( `LPCSTR` `lpsz` ): Создает Юникода `CStringT` строки ANSI. Этот конструктор также позволяет загрузить строку ресурса, как показано в следующем примере.  
  
- `CStringT(``LPCWSTR` `lpsz` ): Создает `CStringT` из строки Юникода.  
  
- `CStringT`( `const unsigned char*` `psz` ): Позволяет создавать `CStringT` из указателя на `unsigned char`.  
  
> [!NOTE]
>  Определение **_CSTRING_DISABLE_NARROW_WIDE_CONVERSION** макрос, чтобы отключить строку неявное преобразование между [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] и [!INCLUDE[TLA#tla_unicode](../../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] строки. Макрос исключает из компиляции конструкторы, которые поддерживают преобразование.  
  
 Обратите внимание, что `strSrc` параметр может быть либо `CStringT` или `CThisSimpleString` объекта. Для `CStringT`, используйте один из его экземпляров по умолчанию ( `CString`, `CStringA`, или `CStringW`), `CThisSimpleString`, используйте `this` указателя. `CThisSimpleString`Объявляет экземпляр [класса CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), меньшего размера класса string с менее встроенных функциональных возможностей, чем `CStringT` класса.  
  
 Перегрузка оператора `CSimpleStringT<>&()` создает `CStringT` объекта из `CSimpleStringT` объявления.  
  
> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляры, которые содержат внедренные символы null, мы не рекомендуем его. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы null может привести к непредвиденным результатам.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#112;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]  
  
##  <a name="a-namedtorcstringta--cstringtcstringt"></a><a name="_dtorcstringt"></a>CStringT:: ~ CStringT  
 Уничтожает `CStringT` объекта.  
  
```  
~CStringT() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Уничтожает `CStringT` объекта.  
  
##  <a name="a-namedeletea--cstringtdelete"></a><a name="delete"></a>CStringT::Delete  
 Удаляет символ или символы из строки, начиная с данного индекса.  
  
```  
int Delete(int iIndex, int nCount = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `iIndex`  
 Отсчитываемый от нуля индекс первого символа в `CStringT` удаляемый объект.  
  
 `nCount`  
 Число удаляемых знаков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина измененные строки.  
  
### <a name="remarks"></a>Примечания  
 Если `nCount` длиннее, чем строка, оставшаяся часть строки будут удалены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#113;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]  
  
```Output  
Before: Soccer is best,
    but hockey is quicker!  
After: Soccer best,
    but hockey is quicker!  
```  
  
##  <a name="a-namefinda--cstringtfind"></a><a name="find"></a>CStringT::Find  
 Ищет первое совпадение для символа или подстроки данной строки.  
  
```  
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszSub`  
 Подстрока для поиска.  
  
 `iStart`  
 Индекс символа в строке, чтобы начать поиск с или 0, чтобы начать с самого начала.  
  
 `ch`  
 Символ для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого символа в этом `CStringT` объект, который соответствует запрошенного substring или символы; -1, если подстрока или символ не найден.  
  
### <a name="remarks"></a>Примечания  
 Функция перегружен, чтобы принять оба одного символа (аналогично функции времени выполнения `strchr`) и строки (аналогично `strstr`).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#114;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]  
  
##  <a name="a-namefindoneofa--cstringtfindoneof"></a><a name="findoneof"></a>CStringT::FindOneOf  
 Выполняет поиск первого символа, который соответствует любому символу, содержащихся в этой строке `pszCharSet`.  
  
```  
int FindOneOf(PCXSTR pszCharSet) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszCharSet`  
 Строка, содержащая символы для сопоставления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого символа в данной строке, которая также находится в `pszCharSet`; -1, если нет соответствия.  
  
### <a name="remarks"></a>Примечания  
 Находит первое вхождение символы в `pszCharSet`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#115;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]  
  
##  <a name="a-nameformata--cstringtformat"></a><a name="format"></a>CStringT::Format  
 Записывает форматированные данные `CStringT` в том же, как [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) форматы данных в стиле C массив символов.  
  
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
 Эта функция форматирует и сохраняет серию символов и значений в `CStringT`. Каждый необязательный аргумент (при наличии) преобразуется и выводится согласно соответствующей спецификацией формата в `pszFormat` или из строкового ресурса, идентифицируемый `nFormatID`.  
  
 Вызов завершится ошибкой, если сам объект string предлагается в качестве параметра `Format`. Например следующий код приведет к непредсказуемым результатам:  
  
 [!code-cpp[NVC_ATLMFC_Utilities&116;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]  
  
 Дополнительные сведения см. в разделе [Синтаксис описания формата: функции printf и wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#117;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]  
  
##  <a name="a-nameformatmessagea--cstringtformatmessage"></a><a name="formatmessage"></a>CStringT::FormatMessage  
 Форматирует строку сообщения.  
  
```  
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```  
  
### <a name="parameters"></a>Параметры  
 `nFormatID`  
 Идентификатор ресурса строка, содержащая текст без форматирования сообщений.  
  
 `pszFormat`  
 Указывает на строку управления форматом. Будет проверен на наличие операций вставки и соответствующим образом в формате. Строка формата аналогична функции времени выполнения `printf`-стиль строки формата, за исключением того, он допускает использование параметров должны быть вставлены в произвольном порядке.  
  
 `argument`  
 Необязательные аргументы.  
  
### <a name="remarks"></a>Примечания  
 Функция требует определения сообщения как входные данные. Определение сообщения определяется `pszFormat` или из строкового ресурса, идентифицируемый `nFormatID`. Функция копирует форматированный текст сообщения для `CStringT` объекта, обработкой, внедренные вставки последовательности по запросу.  
  
> [!NOTE]
> `FormatMessage`пытается выделить системную память для вновь форматируемой строки. Если эта попытка завершается неудачей, исключение памяти автоматически вызывается исключение.  
  
 Каждой операции вставки должен иметь соответствующий параметр ниже `pszFormat` или `nFormatID` параметра. В тексте сообщения для динамического форматирования сообщения поддерживаются несколько escape-последовательности. Дополнительные сведения см. в разделе Windows [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#118;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]  
  
##  <a name="a-nameformatmessageva--cstringtformatmessagev"></a><a name="formatmessagev"></a>CStringT::FormatMessageV  
 Форматирование строки сообщения при помощи переменное число аргументов.  
  
```  
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```  
  
### <a name="parameters"></a>Параметры  
 `pszFormat`  
 Указывает на строку управления форматом. Будет проверен на наличие операций вставки и соответствующим образом в формате. Строка формата аналогична функции времени выполнения `printf`-стиль строки формата, за исключением того, он допускает использование параметров должны быть вставлены в произвольном порядке.  
  
 `pArgList`  
 Указатель на список аргументов.  
  
### <a name="remarks"></a>Примечания  
 Функция требует определения сообщения в качестве выходных данных определяется `pszFormat`. Функция копирует форматированный текст сообщения и списка переменных аргументов `CStringT` объекта, обработкой, внедренные вставки последовательности по запросу.  
  
> [!NOTE]
> `FormatMessageV`вызовы [CStringT::FormatMessage](#formatmessage), который пытается выделить системную память для вновь форматируемой строки. Если эта попытка завершается неудачей, исключение памяти автоматически вызывается исключение.  
  
 Дополнительные сведения см. в разделе Windows [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameformatva--cstringtformatv"></a><a name="formatv"></a>CStringT::FormatV  
 Форматирование строки сообщения при помощи переменное число аргументов.  
  
```  
void FormatV(PCXSTR pszFormat, va_list args);
```  
  
### <a name="parameters"></a>Параметры  
 `pszFormat`  
 Указывает на строку управления форматом. Будет проверен на наличие операций вставки и соответствующим образом в формате. Строка формата аналогична функции времени выполнения `printf`-стиль строки формата, за исключением того, он допускает использование параметров должны быть вставлены в произвольном порядке.  
  
 `args`  
 Указатель на список аргументов.  
  
### <a name="remarks"></a>Примечания  
 Записывает отформатированную строку и переменной список аргументов для `CStringT` строки в том же способом, что `vsprintf_s` форматы данных в стиле C массив символов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#119;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#120;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]  
  
##  <a name="a-namegetenvironmentvariablea--cstringtgetenvironmentvariable"></a><a name="getenvironmentvariable"></a>CStringT::GetEnvironmentVariable  
 Задает строковое значение указанной переменной среды.  
  
```  
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```  
  
### <a name="parameters"></a>Параметры  
 `pszVar`  
 Указатель нулем строку, которая определяет переменную среды.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Получает значение указанной переменной из блок среды вызывающего процесса. Значение в форме нулем строку символов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#121;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]  
  
##  <a name="a-nameinserta--cstringtinsert"></a><a name="insert"></a>CStringT::Insert  
 Вставляет один символ или подстроку с указанным индексом в строке.  
  
```  
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```  
  
### <a name="parameters"></a>Параметры  
 `iIndex`  
 Индекс символа, перед которым вставки будет выполняться.  
  
 `psz`  
 Указатель подстрока, которую необходимо вставить.  
  
 `ch`  
 Вставляемый знак.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина измененные строки.  
  
### <a name="remarks"></a>Примечания  
 `iIndex` Параметр определяет первый символ, который будет перемещена, чтобы освободить место для символа или подстроки. Если `nIndex` равен нулю, курсор будет находиться до всю строку. Если `nIndex` больше, чем длина строки, функция будет объединения присутствует строки и либо обеспечивается новый материал `ch` или `psz`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#122;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]  
  
##  <a name="a-namelefta--cstringtleft"></a><a name="left"></a>CStringT::Left  
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
 [!code-cpp[NVC_ATLMFC_Utilities&#123;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]  
  
##  <a name="a-nameloadstringa--cstringtloadstring"></a><a name="loadstring"></a>CStringT::LoadString  
 Считывает строку ресурса Windows, идентифицируемый `nID`, в существующий `CStringT` объекта.  
  
```  
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `hInstance`  
 Дескриптор экземпляра модуля.  
  
 `nID`  
 Идентификатор строки ресурсов Windows.  
  
 `wLanguageID`  
 Язык строкового ресурса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если загрузка ресурсов выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Загрузка строковых ресурсов ( `nID`) из указанного модуля ( `hInstance`) с использованием указанного языка ( `wLanguage`).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#124;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]  
  
##  <a name="a-namemakelowera--cstringtmakelower"></a><a name="makelower"></a>CStringT::MakeLower  
 Преобразует `CStringT` объекта в строку в нижний регистр.  
  
```  
CStringT& MakeLower();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результирующая строка нижнего регистра.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#125;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]  
  
##  <a name="a-namemakereversea--cstringtmakereverse"></a><a name="makereverse"></a>CStringT::MakeReverse  
 Меняет порядок символов в `CStringT` объекта.  
  
```  
CStringT& MakeReverse();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полученный в обратном порядке строки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#126;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]  
  
##  <a name="a-namemakeuppera--cstringtmakeupper"></a><a name="makeupper"></a>CStringT::MakeUpper  
 Преобразует `CStringT` объекта в строку в верхнем регистре.  
  
```  
CStringT& MakeUpper();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результирующая строка верхнего регистра.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#127;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]  
  
##  <a name="a-namemida--cstringtmid"></a><a name="mid"></a>CStringT::Mid  
 Извлекает подстроку длины `nCount` символов из этого `CStringT` объекта, начиная с позиции `iFirst` (от нуля).  
  
```  
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `iFirst`  
 Отсчитываемый от нуля индекс первого символа в этом `CStringT` объекта, которые будут включены в извлеченной подстроки.  
  
 `nCount`  
 Число символов, извлекаемых из данного объекта `CStringT`. Если этот параметр не задан, будет извлечен оставшейся части строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CStringT`, содержащий копию указанного диапазона символов. Обратите внимание, что возвращаемый `CStringT` объекта может быть пустым.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает копию извлеченной подстроки. `Mid`Аналогично Mid основные функции (за исключением того, что индексы в Basic начинается с&1;).  
  
 Для многобайтовых кодировок (MBCS), `nCount` ссылается на каждый байт символа; то есть, интерес и следа 8-разрядных одним многобайтовых символов считаются за два символа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#128;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]  
  
##  <a name="a-nameoemtoansia--cstringtoemtoansi"></a><a name="oemtoansi"></a>CStringT::OemToAnsi  
 Преобразует все символы в этом `CStringT` объекта OEM кодировки набора знаков ANSI.  
  
```  
void OemToAnsi();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция недоступна при `_UNICODE` определен.  
  
### <a name="example"></a>Пример  
 В примере показано [CStringT::AnsiToOem](#ansitooem).  
  
##  <a name="a-nameoperatoradda--cstringtoperator-"></a><a name="operator_add"></a>CStringT::operator +  
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
 Символ ANSI или Юникод для объединения со строкой.  
  
 `ch2`  
 Символ ANSI или Юникод для объединения со строкой.  
  
 `str1`  
 Объект `CStringT` для объединения с строку или символ.  
  
 `str2`  
 Объект `CStringT` для объединения с строку или символ.  
  
 `psz1`  
 Указатель нулем строка для сцепления с строку или символ.  
  
 `psz2`  
 Указатель на строку для объединения с строку или символ.  
  
### <a name="remarks"></a>Примечания  
 Существует семь формы перегрузки `CStringT::operator+` функции. Первая версия объединяет две существующие `CStringT` объектов. Объединение двух следующих `CStringT` объекта и строку, завершающуюся значением null. Объединение двух следующих `CStringT` объекта, а также символ ANSI. Объединение двух последних `CStringT` объекта и символ Юникода.  
  
> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляры, которые содержат внедренные символы null, мы не рекомендуем его. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы null может привести к непредвиденным результатам.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#140;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]  
  
##  <a name="a-nameoperatoraddeqa--cstringtoperator-"></a><a name="operator_add_eq"></a>CStringT::operator +=  
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
 Логическое значение, указывающее, является ли проект библиотеки DLL MFC.  
  
 `BaseType`  
 Базовый тип string.  
  
 `var`  
 Объект variant для сцепления для этой строки.  
  
 `ch`  
 Символ ANSI или Юникод для объединения со строкой.  
  
 `pszSrc`  
 Указатель, объединяемых исходной строки.  
  
 `strSrc`  
 Объект `CStringT` для сцепления для этой строки.  
  
### <a name="remarks"></a>Примечания  
 Оператор принимает другой `CStringT` объект, указатель символа или один символ. Следует иметь в виду, памяти, исключения могут возникать при использовании этот оператор объединения, так как новое хранилище может быть выделено для символов, которые добавляются в этот `CStringT` объекта.  
  
 Сведения о `CThisSimpleString`, в разделе «Примечания» [CStringT::CStringT](#cstringt).  
  
> [!NOTE]
>  Несмотря на то, что можно создать `CStringT` экземпляры, которые содержат внедренные символы null, мы не рекомендуем его. Вызов методов и операторов для `CStringT` объектов, содержащих внедренные символы null может привести к непредвиденным результатам.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#141;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]  
  
##  <a name="a-nameoperatoreqeqa--cstringtoperator-"></a><a name="operator_eq_eq"></a>CStringT::operator ==  
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
 Указатель на строку нулем для сравнения.  
  
 `psz2`  
 Указатель на строку нулем для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Проверяет, является ли строку или символ с левой стороны равно строку или символ в правой части и возвращает значение TRUE или FALSE соответственно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#142;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]  
  
##  <a name="a-nameoperatorneqa--cstringtoperator-"></a><a name="operator_neq"></a>CStringT::operator! =  
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
 Символ ANSI или Юникод для объединения со строкой.  
  
 `ch2`  
 Символ ANSI или Юникод для объединения со строкой.  
  
 `str1`  
 Объект `CStringT` для сравнения.  
  
 `str2`  
 Объект `CStringT` для сравнения.  
  
 `psz1`  
 Указатель на строку нулем для сравнения.  
  
 `psz2`  
 Указатель на строку нулем для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Проверяет строку или символ слева не равно строку или символ с правой стороны.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#143;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]  
  
##  <a name="a-nameoperatorlta--cstringtoperator-lt"></a><a name="operator_lt"></a>CStringT::operator&lt;  
 Определяет, является ли строка в левой части оператора меньше, чем строка в правой части.  
  
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
 Указатель на строку нулем для сравнения.  
  
 `psz2`  
 Указатель на строку нулем для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Лексикографических сравнения строк, символ до:  
  
-   Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.  
  
-   Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.  
  
-   Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, поэтому сроки равны.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#144;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]  
  
##  <a name="a-nameoperatorgta--cstringtoperator-gt"></a><a name="operator_gt"></a>CStringT::operator&gt;  
 Определяет, является ли строка слева от оператора больше, чем строка в правой части.  
  
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
 Указатель на строку нулем для сравнения.  
  
 `psz2`  
 Указатель на строку нулем для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Лексикографических сравнения строк, символ до:  
  
-   Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.  
  
-   Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.  
  
-   Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#145;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]  
  
##  <a name="a-nameoperatorlteqa--cstringtoperator-lt"></a><a name="operator_lt_eq"></a>CStringT::operator&lt;=  
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
 Указатель на строку нулем для сравнения.  
  
 `psz2`  
 Указатель на строку нулем для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Лексикографических сравнения строк, символ до:  
  
-   Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.  
  
-   Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.  
  
-   Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#146;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]  
  
##  <a name="a-nameoperatorgteqa--cstringtoperator-gt"></a><a name="operator_gt_eq"></a>CStringT::operator&gt;=  
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
 Лексикографических сравнения строк, символ до:  
  
-   Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.  
  
-   Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.  
  
-   Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&147;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]  
  
##  <a name="a-nameremovea--cstringtremove"></a><a name="remove"></a>CStringT::Remove  
 Удаляет все вхождения указанного символа в строке.  
  
```  
int Remove(XCHAR chRemove);
```  
  
### <a name="parameters"></a>Параметры  
 `chRemove`  
 Символ будет удалена из строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов, удалена из строки. Нуль, если строка не изменяется.  
  
### <a name="remarks"></a>Примечания  
 Сравнение символа чувствительны к регистру.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#129;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]  
  
##  <a name="a-namereplacea--cstringtreplace"></a><a name="replace"></a>CStringT::Replace  
 Существует две версии `Replace`. Первая версия заменяет одну или несколько копий подстроки, используя другой подстрокой. Обе подстроки, заканчивающаяся нулем. Вторая версия заменяет одну или несколько копий символ с помощью другой символ. Обе версии работают с символьные данные, хранящиеся в `CStringT`.  
  
```  
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```  
  
### <a name="parameters"></a>Параметры  
 `pszOld`  
 Указатель на строку, завершающуюся значением null заменяется `pszNew`.  
  
 `pszNew`  
 Указатель нулем строку, которая заменяет `pszOld`.  
  
 `chOld`  
 Символ заменяется `chNew`.  
  
 `chNew`  
 Замена символов `chOld`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число экземпляров замененного символ или подстроку, или нуль, если строка не изменяется.  
  
### <a name="remarks"></a>Примечания  
 `Replace`можно изменить длину строки, так как `pszNew` и `pszOld` не нужно иметь одинаковую длину, и несколько копий старый подстроки может быть изменено в новую. Функция выполняет совпадение с учетом регистра.  
  
 Примеры `CStringT` экземпляры `CString`, `CStringA`, и `CStringW`.  
  
 Для `CStringA`, `Replace` работает с ANSI или многобайтовая кодировка (MBCS). Для `CStringW`, `Replace` работает с расширенными символами.  
  
 Для `CString`, символьный тип данных выбирается во время компиляции по ли определенные константы в следующей таблице.  
  
|Константа|Символьный тип данных|  
|----------------------|-------------------------|  
|`_UNICODE`|Расширенные символы|  
|`_MBCS`|Многобайтовые символы|  
|Никакой|Однобайтовые символы|  
|Оба значения|Не определено|  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#200;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]  
  
##  <a name="a-namereversefinda--cstringtreversefind"></a><a name="reversefind"></a>CStringT::ReverseFind  
 Выполняет поиск этого `CStringT` объекта для сопоставления последнего символа.  
  
```  
int ReverseFind(XCHAR ch) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ch`  
 Символ для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс последнего символа в этом `CStringT` объект, который соответствует запрошенного символов или –&1;, если символ не найден.  
  
### <a name="remarks"></a>Примечания  
 Функция аналогична функции времени выполнения `strrchr`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#130;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]  
  
##  <a name="a-namerighta--cstringtright"></a><a name="right"></a>CStringT::Right  
 Извлекает последний (то есть, справа) `nCount` символов из этого `CStringT` объекта и возвращает копию извлеченной подстроки.  
  
```  
CStringT Right(int nCount) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `nCount`  
 Число символов, извлекаемых из данного объекта `CStringT`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CStringT`, содержащий копию указанного диапазона символов. Обратите внимание, что возвращаемый `CStringT` объекта может быть пустым.  
  
### <a name="remarks"></a>Примечания  
 Если значение `nCount` превышает длину строки, извлекается вся строка. `Right`подобна основной `Right` функции (за исключением того, что индексы в Basic отсчитываются от нуля).  
  
 Для многобайтовых кодировок (MBCS), `nCount` ссылается на каждый байт символа; то есть, интерес и следа 8-разрядных одним многобайтовых символов считаются за два символа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#131;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]  
  
##  <a name="a-namesetsysstringa--cstringtsetsysstring"></a><a name="setsysstring"></a>CStringT::SetSysString  
 Перераспределяет `BSTR` указывает `pbstr` и копирует содержимое `CStringT` объекта, включая `NULL` символов.  
  
```  
BSTR SetSysString(BSTR* pbstr) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `pbstr`  
 Указатель на строку знаков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая строка.  
  
### <a name="remarks"></a>Примечания  
 В зависимости от содержимого `CStringT` объект, значение `BSTR` ссылается `pbstr` можно изменить. Эта функция создает исключение `CMemoryException` , если существует нехватка памяти.  
  
 Эта функция обычно используется для изменения значения строк, передаваемых по ссылке для автоматизации.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#132;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]  
  
##  <a name="a-namespanexcludinga--cstringtspanexcluding"></a><a name="spanexcluding"></a>CStringT::SpanExcluding  
 Извлекает символы из строки, начиная с первого символа, не отображаемые в набор символов, идентифицируемый `pszCharSet`.  
  
```  
CStringT SpanExcluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `pszCharSet`  
 Строка интерпретируется как набор символов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Подстроки, содержит символы в строке, не входящие в `pszCharSet`, начиная с первого символа в строке и заканчивая первого символа в строке, которая также находится в `pszCharSet` (то есть, начиная с первого символа в строке и до, но не включая первого символа в строке, в которой находится `pszCharSet`). Возвращает всю строку, если ни один знак из `pszCharSet` найдено в строке.  
  
### <a name="remarks"></a>Примечания  
 `SpanExcluding`Извлекает и возвращает все символы, предшествующие первое вхождение символа из `pszCharSet` (другими словами, символ из `pszCharSet` и все символы в строке, не возвращаются). Если ни один знак из `pszCharSet` находится в строке, а затем `SpanExcluding` возвращает всю строку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#133;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]  
  
##  <a name="a-namespanincludinga--cstringtspanincluding"></a><a name="spanincluding"></a>CStringT::SpanIncluding  
 Извлекает символы из строки, начиная с первого символа, в набор символов, идентифицируемый `pszCharSet`.  
  
```  
CStringT SpanIncluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `pszCharSet`  
 Строка интерпретируется как набор символов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Подстроки, содержит символы в строке, в `pszCharSet`, начиная с первого символа в строке и заканчивается, когда символ находится в строке, которая не находится в `pszCharSet.``SpanIncluding` возвращает пустой подстрокой, если первый символ в строке не существует в указанном наборе.  
  
### <a name="remarks"></a>Примечания  
 Если первый символ строки не в набор символов, то `SpanIncluding` возвращает пустую строку. В противном случае — возвращает последовательность последовательных символов, которые находятся в наборе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#134;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]  
  
##  <a name="a-nametokenizea--cstringttokenize"></a><a name="tokenize"></a>CStringT::Tokenize  
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
 Объект `CStringT` объект, содержащий значение текущего маркера.  
  
### <a name="remarks"></a>Примечания  
 `Tokenize` Функция находит следующий токен в целевой строке. Набор символов в `pszTokens` указывает возможные разделители токенов, которые удалось найти. При каждом вызове `Tokenize` функции начинается с `iStart`, пропускает ведущие разделители и возвращает `CStringT` объект, содержащий текущий маркер, который представляет собой строку символов до следующего символа разделителя. Значение `iStart` обновляется положение, следующее конечный символ разделителя или -1, если достигнут конец строки. Можно выделить другие токены из оставшейся части целевая строка с помощью последовательных вызовов `Tokenize`, с использованием `iStart` для отслеживания того, где в строке, с которого следует считать следующий токен. Если нет больше токенов функция возвратит пустую строку и `iStart` будет задано значение -1.  
  
 В отличие от CRT маркировки функции, такие как [strtok_s _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), `Tokenize` не изменяет целевой строки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#135;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]  
  
### <a name="remarks"></a>Примечания  
 Выходные данные для этого примера выглядит следующим образом:  
  
 `Resulting Token: First`  
  
 `Resulting Token: Second`  
  
 `Resulting Token: Third`  
  
##  <a name="a-nametrima--cstringttrim"></a><a name="trim"></a>CStringT::Trim  
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
  
-   Символ`chTarget.`  
  
-   Все символы, найденные в строки, заданной параметром`pszTargets.`  
  
-   Пробел.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#136;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]  
  
### <a name="remarks"></a>Примечания  
 Выходные данные для этого примера выглядит следующим образом:  
  
 `Before: "******Soccer is best, but liquor is quicker!!!!!"`  
  
 `After : "Soccer is best, but liquor is quicker"`  
  
##  <a name="a-nametrimlefta--cstringttrimleft"></a><a name="trimleft"></a>CStringT::TrimLeft  
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
  
-   Символ`chTarget.`  
  
-   Все символы, найденные в строки, заданной параметром`pszTargets.`  
  
-   Пробел.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#137;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]  
  
##  <a name="a-nametrimrighta--cstringttrimright"></a><a name="trimright"></a>CStringT::TrimRight  
 Удаляет конечные знаки из строки.  
  
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
 Удаляет конечные вхождения одно из следующих действий:  
  
-   Символ`chTarget.`  
  
-   Все символы, найденные в строки, заданной параметром`pszTargets.`  
  
-   Пробел.  
  
 `CStringT& TrimRight(XCHAR chTarget)` Версия принимает один параметр символов и удаляет все копии этого символа из конца `CStringT` строковые данные. Он начинается с конца строки и работает ближе к началу. Он останавливается при обнаружении другого символа или `CSTringT` хватает символьных данных.  
  
 `CStringT& TrimRight(PCXSTR pszTargets)` Версия принимает нулем строка, содержащая различных символов для поиска. Она удаляет все копии этих символов в `CStringT` объекта. Он начинается в конце строки и работает ближе к началу. Он останавливается при обнаружении символ, который не находится в целевой строке или `CStringT` хватает символьных данных. Он не пытается сопоставить строку всей целевой подстрокой в конце `CStringT`.  
  
 `CStringT& TrimRight()` Версии не требует параметров. Он урезает любые конечные символы пробела в конце `CStringT` строку. Разрывы строк, пробелы или вкладок, может быть пробельных символов.  
  
-  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#138;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [Класс CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)



