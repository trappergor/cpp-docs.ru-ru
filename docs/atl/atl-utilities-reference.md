---
title: Справочник по служебным программам ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b802d8764dda321e2e313f793f4f2e4745dbcc7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="atl-utilities-reference"></a>Справочник по служебным программам ATL
Библиотека ATL предоставляет код для обработки URL-адреса и пути в виде [CPathT](../atl/reference/cpatht-class.md) и [CUrl](../atl/reference/curl-class.md). Пул потоков [CThreadPool](../atl/reference/cthreadpool-class.md), можно использовать в приложениях. Этот код можно найти в atlpath.h и файлов atlutil.h.  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс CPathT](../atl/reference/cpatht-class.md)|Этот класс представляет путь.|  
|[Класс CDebugReportHook](../atl/reference/cdebugreporthook-class.md)|Этот класс можно используйте для отправки отчетов отладки именованного канала.|  
|[Класс CNonStatelessWorker](../atl/reference/cnonstatelessworker-class.md)|Получает запросы из пула потоков и передает их рабочий объект, который создается и уничтожается при каждом запросе.|  
|[Класс CNoWorkerThread](../atl/reference/cnoworkerthread-class.md)|Этот класс используется в качестве аргумента для `MonitorClass` параметр шаблона классы кэша, если вы хотите отключить обслуживания динамического кэша.|  
|[Класс CThreadPool](../atl/reference/cthreadpool-class.md)|Этот класс предоставляет пул рабочих потоков, обрабатывающих очередь рабочих элементов.|  
|[Класс CUrl](../atl/reference/curl-class.md)|Этот класс представляет URL-адрес. Он позволяет управлять каждый элемент URL-адреса независимо от других ли синтаксический анализ URL-адрес существующей строки или создании строки с нуля.|  
|[Класс CWorkerThread](../atl/reference/cworkerthread-class.md)|Этот класс создает рабочий поток или использует уже существующий, ожидает один или несколько маркеров объектов ядра и выполняет функцию указанного клиента, когда один из маркеров, получает сигнал.|  
  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[CPath](../atl/reference/atl-typedefs.md#cpath)|Специализация [CPathT](../atl/reference/cpatht-class.md) с помощью `CString`.|  
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|Специализация [CPathT](../atl/reference/cpatht-class.md) с помощью `CStringA`.|  
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|Специализация [CPathT](../atl/reference/cpatht-class.md) с помощью `CStringW`.|  
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|Тип используемого [CUrl](../atl/reference/curl-class.md) для указания номера порта.|  
  
### <a name="enums"></a>перечислениям;  
  
|||  
|-|-|  
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|Члены этого перечисления предоставляют константы для схем, поддерживаемая [CUrl](../atl/reference/curl-class.md).|  
  
### <a name="functions"></a>Функции  
  
|||  
|-|-|  
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|Вызывайте эту функцию для приведения URL-адреса к каноническому виду, что включает преобразование небезопасных символов и пробелов в escape-последовательности.|  
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|Вызывайте эту функцию для объединения базового и относительного URL-адресов в один канонический URL-адрес.|  
|[AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|Вызывайте эту функцию для преобразования всех небезопасных символов в escape-последовательности.|  
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|Эта функция вызывается для получения номера порта по умолчанию, связанного с определенным Интернет-протоколом или схемой.|  
|[AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.|  
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|Вызывайте эту функцию, чтобы определить, безопасно ли использовать символ в URL-адресе.|  
|[AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|Вызывайте эту функцию для обратного преобразования escape-символов в первоначальные значения.|  
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP.|  

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)| Эта функция представляет собой перегруженную оболочку для [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561). |  
|[ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)| Эта функция представляет собой перегруженную оболочку для [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563). |  
|[ATLPath::Append](../atl/reference/atl-path-functions.md#append)| Эта функция представляет собой перегруженную оболочку для [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565). |  
|[ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)| Эта функция представляет собой перегруженную оболочку для [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567). |  
|[ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)| Эта функция представляет собой перегруженную оболочку для [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569). |  
|[ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)| Эта функция представляет собой перегруженную оболочку для [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571). |  
|[ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)| Эта функция представляет собой перегруженную оболочку для [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574). |  
|[ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)| Эта функция представляет собой перегруженную оболочку для [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575). |  
|[ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)| Эта функция представляет собой перегруженную оболочку для [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578). |  
|[ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)| Эта функция представляет собой перегруженную оболочку для [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584). |  
|[ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)| Эта функция представляет собой перегруженную оболочку для [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587). |  
|[ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)| Эта функция представляет собой перегруженную оболочку для [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589). |  
|[ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)| Эта функция представляет собой перегруженную оболочку для [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612). |  
|[ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)| Эта функция представляет собой перегруженную оболочку для [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621). |  
|[ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)| Эта функция представляет собой перегруженную оболочку для [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627). |  
|[ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)| Эта функция представляет собой перегруженную оболочку для [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650). |  
|[ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)| Эта функция представляет собой перегруженную оболочку для [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660). |  
|[ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)| Эта функция представляет собой перегруженную оболочку для [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674). |  
|[ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)| Эта функция представляет собой перегруженную оболочку для [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687). |  
|[ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)| Эта функция представляет собой перегруженную оболочку для [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712). |  
|[ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)| Эта функция представляет собой перегруженную оболочку для [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722). |  
|[ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)| Эта функция представляет собой перегруженную оболочку для [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723). |  
|[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)| Эта функция представляет собой перегруженную оболочку для [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725). |  
|[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)| Эта функция представляет собой перегруженную оболочку для [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727). |  
|[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)| Эта функция представляет собой перегруженную оболочку для [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739). |  
|[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)| Эта функция представляет собой перегруженную оболочку для [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740). |  
|[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)| Эта функция представляет собой перегруженную оболочку для [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742). |  
|[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)| Эта функция представляет собой перегруженную оболочку для [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743). |  
|[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)| Эта функция представляет собой перегруженную оболочку для [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745). |  
|[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)| Эта функция представляет собой перегруженную оболочку для [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746). |  
|[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)| Эта функция представляет собой перегруженную оболочку для [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748). |  
|[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)| Эта функция представляет собой перегруженную оболочку для [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749). |  
|[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)| Эта функция представляет собой перегруженную оболочку для [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754). |  
|[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)| Эта функция представляет собой перегруженную оболочку для [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756). |  
|[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)| Эта функция представляет собой перегруженную оболочку для [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757). |  
|[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)| Эта функция представляет собой перегруженную оболочку для [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763). |  
  

## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)   
 [Компоненты ATL COM Desktop](../atl/atl-com-desktop-components.md)
