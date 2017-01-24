---
title: "CStringT Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CString"
  - "CStringT"
  - "ATL::CStringT"
  - "ATL.CStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringT class"
  - "shared classes, CStringT"
  - "строки [C++], в ATL"
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
caps.latest.revision: 33
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет объект `CStringT`.  
  
## Синтаксис  
  
```  
  
      template< typename   
      BaseType  
      , class   
      StringTraits  
       >  
class CStringT :   
public CSimpleStringT<   BaseType,   _CSTRING_IMPL_::_MFCDLLTraitsCheck<      BaseType,      StringTraits   >   ::c_bIsMFCDLLTraits>  
```  
  
#### Параметры  
 `BaseType`  
 Тип символа строкового класса.  Может принимать следующие значения:  
  
-   `char` \(для символьных строк ANSI\).  
  
-   `wchar_t` \(для символьных строк в юникоде\).  
  
-   **TCHAR** \(и для символьных строк ANSI и юникод\).  
  
 `StringTraits`  
 Определяет, является ли поддержка библиотеки времени выполнения c \(CRT\) необходимостей класса строки и, где строковые ресурсы найдены.  Может принимать следующие значения:  
  
-   **Wchar\_t strtraitatl\<** &#124; `char` &#124; **TCHAR, wchar\_t chtraitscrt\<** &#124; `char` &#124; **TCHAR \> \>**  
  
     Класс требует поддержки и поиска CRT для строк ресурса в указанном модуле `m_hInstResource` \(членом класса модуля приложения\).  
  
-   **Wchar\_t strtraitatl\<** &#124; `char` &#124; **TCHAR, wchar\_t chtraitsos\<** &#124; `char` &#124; **TCHAR \> \>**  
  
     Класс не требует поддержки и поиска CRT для строк ресурса в указанном модуле `m_hInstResource` \(членом класса модуля приложения\).  
  
-   **Wchar\_t strtraitmfc\<** &#124; `char` &#124; **TCHAR, wchar\_t chtraitscrt\<** &#124; `char` &#124; **TCHAR \> \>**  
  
     Класс требует поддержки и поиска CRT для строк ресурса с помощью стандартного алгоритма поиска MFC.  
  
-   **Wchar\_t strtraitmfc\<** &#124; `char` &#124; **TCHAR, wchar\_t chtraitsos\<** &#124; `char` &#124; **TCHAR \> \>**  
  
     Класс не требует поддержки и поиска CRT для строк ресурса с помощью стандартного алгоритма поиска MFC.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStringT::CStringT](../Topic/CStringT::CStringT.md)|Создает объект `CStringT` различными способами.|  
|[CStringT::~CStringT](../Topic/CStringT::~CStringT.md)|Удаляет объект `CStringT`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md)|Выбирает `BSTR` из данных `CStringT`.|  
|[CStringT::AnsiToOem](../Topic/CStringT::AnsiToOem.md)|Выполняет преобразование из в\- размещения кодировка ANSI в символ OEM \- набор.|  
|[CStringT::AppendFormat](../Topic/CStringT::AppendFormat.md)|Форматированные данные добавитями к существующему `CStringT` объект.|  
|[CStringT::Collate](../Topic/CStringT::Collate.md)|Сравнивает 2 строк \(регистр, сведения о языковой стандарт\- определенной польз\).|  
|[CStringT::CollateNoCase](../Topic/CStringT::CollateNoCase.md)|Сравнивает 2 строк \(с учетом регистра, сведения о языковой стандарт\- определенной польз\).|  
|[CStringT::Compare](../Topic/CStringT::Compare.md)|Сравнивает 2 строк \(с учетом регистра\).|  
|[CStringT::CompareNoCase](../Topic/CStringT::CompareNoCase.md)|Сравнивает 2 строк \(регистр символов не учитывается\).|  
|[CStringT::Delete](../Topic/CStringT::Delete.md)|Удаляет знак или знаки из строки.|  
|[CStringT::Find](../Topic/CStringT::Find.md)|Находит символ или подстрока в рамках более крупной строки.|  
|[CStringT::FindOneOf](../Topic/CStringT::FindOneOf.md)|Находит первый соответствующий символ из набора.|  
|[CStringT::Format](../Topic/CStringT::Format.md)|Форматирует строки по мере `sprintf`.|  
|[CStringT::FormatMessage](../Topic/CStringT::FormatMessage.md)|Форматирует строки сообщения.|  
|[CStringT::FormatMessageV](../Topic/CStringT::FormatMessageV.md)|Форматирует строка сообщения, используя список аргументов переменной.|  
|[CStringT::FormatV](../Topic/CStringT::FormatV.md)|Форматирует строки, используя список аргументов переменной.|  
|[CStringT::GetEnvironmentVariable](../Topic/CStringT::GetEnvironmentVariable.md)|Задает строку в значение указанной переменной среды.|  
|[CStringT::Insert](../Topic/CStringT::Insert.md)|Вставляет один знак или подстроку на заданный индекс в строке.|  
|[CStringT::Left](../Topic/CStringT::Left.md)|Извлекает левая часть строки.|  
|[CStringT::LoadString](../Topic/CStringT::LoadString.md)|Загружает существующий объект `CStringT` из ресурса Windows.|  
|[CStringT::MakeLower](../Topic/CStringT::MakeLower.md)|Преобразование всех символов в данной строке в нижний регистр символов.|  
|[CStringT::MakeReverse](../Topic/CStringT::MakeReverse.md)|Изменяет строку.|  
|[CStringT::MakeUpper](../Topic/CStringT::MakeUpper.md)|Преобразование всех символов в данной строке в символы верхнего регистра.|  
|[CStringT::Mid](../Topic/CStringT::Mid.md)|Извлекает средняя часть строки.|  
|[CStringT::OemToAnsi](../Topic/CStringT::OemToAnsi.md)|Выполняет преобразование в\- размещения из символов OEM \- установка в набор символов ANSI.|  
|[CStringT::Remove](../Topic/CStringT::Remove.md)|Удаляет отображаемый символов из строки.|  
|[CStringT::Replace](../Topic/CStringT::Replace.md)|Указывает replaces символы с другими символами.|  
|[CStringT::ReverseFind](../Topic/CStringT::ReverseFind.md)|Находит символ в более крупной строки; начинается с конца.|  
|[CStringT::Right](../Topic/CStringT::Right.md)|Извлекает правая часть строки.|  
|[CStringT::SetSysString](../Topic/CStringT::SetSysString.md)|Задает существующий объект `BSTR` данными из объекта `CStringT`.|  
|[CStringT::SpanExcluding](../Topic/CStringT::SpanExcluding.md)|Извлекает символов из строки, начиная с первого символа, в наборе символов, определенных `pszCharSet`.|  
|[CStringT::SpanIncluding](../Topic/CStringT::SpanIncluding.md)|Извлекает подстроку, которая содержит только символы в наборе.|  
|[CStringT::Tokenize](../Topic/CStringT::Tokenize.md)|Токены извлечь указанные в строке целевого объекта.|  
|[CStringT::Trim](../Topic/CStringT::Trim.md)|Усекает все начальные и конечные символы пробела из строки.|  
|[CStringT::TrimLeft](../Topic/CStringT::TrimLeft.md)|Trim, который привел знаками пробела из строки.|  
|[CStringT::TrimRight](../Topic/CStringT::TrimRight.md)|Усекаются замыкающие знаки пробела из строки.|  
  
### Операторы  
  
|||  
|-|-|  
|[CStringT::operator \=](../Topic/CStringT::operator%20=.md)|Присвоить новое значение объекта `CStringT`.|  
|[CStringT::operator \+](../Topic/CStringT::operator%20+.md)|Сцепляет 2 строк или знаков и строк.|  
|[CStringT::operator \+\=](../Topic/CStringT::operator%20+=.md)|Сцепляет новую строку в конец существующей строки.|  
|[CStringT::operator \=\=](../Topic/CStringT::operator%20==.md)|Определяет, логически равны 2 строк.|  
|[CStringT::operator \!\=](../Topic/CStringT::operator%20!=.md)|Определяет, 2 строк логическое не равны.|  
|[CStringT::operator \<](../Topic/CStringT::operator%20%3C.md)|Определяет, является ли строка в левой части оператора, чем в строке справа.|  
|[CStringT::operator \>](../Topic/CStringT::operator%20%3E.md)|Определяет, является ли строка в левой части оператора больше строки справа.|  
|[CStringT::operator \<\=](../Topic/CStringT::operator%20%3C=.md)|Определяет, является ли строка в левой части оператора, меньше или равно строке справа.|  
|[CStringT::operator \>\=](../Topic/CStringT::operator%20%3E=.md)|Определяет, является ли строка в левой части оператора больше или равно строке справа.|  
  
## Заметки  
 `CStringT` наследуется от [класс CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md).  Расширенные функции, например упорядочения и манипуляция знака, поиск, реализованы `CStringT`.  
  
> [!NOTE]
>  Объекты `CStringT` обеспечивают возможность возникновения исключения.  Это происходит, когда не хватает памяти для выполнения объекта `CStringT` какой\-либо причине.  
  
 Объект `CStringT` состоит из последовательности знаков переменной длины.  `CStringT` предоставляет функции и операторы, используя синтаксис, подобный этому из основного.  Соединение и операторы сравнения вместе с упрощенным элемента управления памятью, что объекты `CStringT` более удобным использовать чем массивы обычного символа.  
  
> [!NOTE]
>  Хотя можно создать экземпляры `CStringT`, которые содержат внедренные нуль\-символы рекомендуется к ней.  Вызов методов и операторов, основанных на объектах `CStringT`, которые содержат внедренные нуль\-символы может дать непредусмотренных инструкций.  
  
 С использованием различных сочетаний параметров `BaseType` и `StringTraits` объекты `CStringT` могут поступать на следующие типы, которые являются стандартными библиотеками библиотеки ATL.  
  
 При использовании в приложении библиотеки ATL:  
  
 `CString`, `CStringA` и `CStringW` экспортироватьы из библиотеки DLL MFC \(MFC90.DLL\) никогда из библиотеки DLL пользователя.  Это делается для предотвращения `CStringT` от умножает заданный.  
  
> [!NOTE]
>  Если обнаружил ошибки компоновщика экспортирования `CString`\- производный класс из библиотеки DLL расширения MFC в Visual C\+\+ .NET 2002 и примененные решение, как описано в статье базы знаний "связывание ошибки при импорте CString\- Производные классы" \(Q309801\), необходимо удалить код временного решения, так как это было зафиксировано в Visual C\+\+ .NET 2003.  Статьи базы знаний можно найти на компакт\-диске библиотеки MSDN или по ссылке [http:\/\/support.microsoft.com\/](http://support.microsoft.com/).  
  
 Следующие строковые типы доступны в пределах MFC\-, работающих приложений:  
  
|Тип CStringT|Объявление|  
|------------------|----------------|  
|`CStringA`|Строка типа символов ANSI с поддержкой CRT.|  
|`CStringW`|Строка типа в юникоде с поддержкой CRT.|  
|`CString`|Типы и ANSI и в юникоде с поддержкой CRT.|  
  
 Следующие строковые типы доступных в проектах, в которых указан **ATL\_CSTRING\_NO\_CRT**:  
  
|Тип CStringT|Объявление|  
|------------------|----------------|  
|**CAtlStringA**|Строка типа символов ANSI без поддержки CRT.|  
|**CAtlStringW**|Строка символов юникода типа без поддержки CRT.|  
|**CAtlString**|Типы и ANSI и символ юникода без поддержки CRT.|  
  
 Следующие строковые типы доступных в проектах, в которых **ATL\_CSTRING\_NO\_CRT** не указано.  
  
|Тип CStringT|Объявление|  
|------------------|----------------|  
|**CAtlStringA**|Строка типа символов ANSI с поддержкой CRT.|  
|**CAtlStringW**|Строка типа в юникоде с поддержкой CRT.|  
|**CAtlString**|Типы и ANSI и в юникоде с поддержкой CRT.|  
  
 Объекты `CString` также имеют следующие характеристики:  
  
-   Объекты `CStringT` могут увеличиваться в результате операций соединения.  
  
-   Объекты `CStringT` следовать семантике "значения". Подумайте объекта `CStringT` как фактическая строка, а не как указатель на строку.  
  
-   Можно свободно заменить объекты `CStringT` для аргументов функции `PCXSTR`.  
  
-   Пользовательское управление памятью для буферов строки.  Дополнительные сведения см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## CStringT предопределило типы  
 Поскольку `CStringT` использует аргумент шаблона, чтобы указать поддерживаемый тип символов \(или [wchar\_t](../../c-runtime-library/standard-types.md) или [char](../../c-runtime-library/standard-types.md)\), типы параметров метода может осложнить временем.  Для упрощения этой проблемы набор стандартных типов определяется и используется в класс `CStringT`.  В следующей таблице перечислены различные типы:  
  
|Имя|Описание|  
|---------|--------------|  
|`XCHAR`|Один знак \(или `wchar_t` или `char`\) с тем же типом символов в виде объекта `CStringT`.|  
|**YCHAR**|Один знак \(или `wchar_t` или `char`\) с противоположным типом символов в виде объекта `CStringT`.|  
|`PXSTR`|Является указателем на символьную строку \(или `wchar_t` или `char`\) с тем же типом символов в виде объекта `CStringT`.|  
|**PYSTR**|Является указателем на символьную строку \(или `wchar_t` или `char`\) с противоположным типом символов в виде объекта `CStringT`.|  
|`PCXSTR`|Является указателем на символьную строку **const** \(или `wchar_t` или `char`\) с тем же типом символов в виде объекта `CStringT`.|  
|**PCYSTR**|Является указателем на символьную строку **const** \(или `wchar_t` или `char`\) с противоположным типом символов в виде объекта `CStringT`.|  
  
> [!NOTE]
>  Закодируйте, что ранее, используемые недокументированные методы `CString` \(например, **AssignCopy**\) должны быть заменены с кодом, используются следующие методы `CStringT` документированные \(например, `GetBuffer` или `ReleaseBuffer`\).  Эти методы наследуются от `CSimpleStringT`.  
  
## Иерархия наследования  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## Требования  
  
|Header|Использование|  
|------------|-------------------|  
|cstringt.h|Объект строки \- только MFC|  
|atlstr.h|Строковый объект, не относящихся к MFC|  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [CSimpleStringT Class](../../atl-mfc-shared/reference/csimplestringt-class.md)