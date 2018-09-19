---
title: Справочник по служебным программам ATL | Документация Майкрософт
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
ms.openlocfilehash: eadb1edc174d07fbc6e9ef1bfb24b436bd76033d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056154"
---
# <a name="atl-utilities-reference"></a>Справочник по служебным программам ATL

Библиотека ATL предоставляет код для манипулирования пути и URL-адреса в виде [CPathT](../atl/reference/cpatht-class.md) и [CUrl](../atl/reference/curl-class.md). Пул потоков [CThreadPool](../atl/reference/cthreadpool-class.md), можно использовать в приложениях. Этот код можно найти в atlpath.h и файлов atlutil.h.

### <a name="classes"></a>Классы

|||
|-|-|
|[Класс CPathT](../atl/reference/cpatht-class.md)|Этот класс представляет собой путь.|
|[Класс CDebugReportHook](../atl/reference/cdebugreporthook-class.md)|Этот класс используется для отправки отчетов отладки именованного канала.|
|[Класс CNonStatelessWorker](../atl/reference/cnonstatelessworker-class.md)|Получает запросы из пула потоков и передают их в рабочий объект, который создается и уничтожается при каждом запросе.|
|[Класс CNoWorkerThread](../atl/reference/cnoworkerthread-class.md)|Этот класс используется в качестве аргумента для `MonitorClass` параметр шаблона классов кэша, если вы хотите отключить обслуживания динамического кэша.|
|[Класс CThreadPool](../atl/reference/cthreadpool-class.md)|Этот класс предоставляет пул рабочих потоков, обрабатывающих очередь рабочих элементов.|
|[Класс CUrl](../atl/reference/curl-class.md)|Этот класс представляет URL-адрес. Он позволяет управлять каждый элемент URL-адреса независимо от других ли синтаксический анализ URL-адрес существующей строки или создании строки с нуля.|
|[Класс CWorkerThread](../atl/reference/cworkerthread-class.md)|Этот класс создает рабочий поток или используется существующая рабочая область, ожидает один или несколько дескрипторов объектов ядра и выполняет функцию указанного клиента, когда один из маркеров, получает сигнал.|

### <a name="typedefs"></a>Определения типов

|||
|-|-|
|[CPath](../atl/reference/atl-typedefs.md#cpath)|Специализация [CPathT](../atl/reference/cpatht-class.md) с помощью `CString`.|
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|Специализация [CPathT](../atl/reference/cpatht-class.md) с помощью `CStringA`.|
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|Специализация [CPathT](../atl/reference/cpatht-class.md) с помощью `CStringW`.|
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|Тип, используемый [CUrl](../atl/reference/curl-class.md) для указания номера порта.|

### <a name="enums"></a>перечислениям;

|||
|-|-|
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|Элементы этого перечисления предоставляют константы для схем, поддерживаемая [CUrl](../atl/reference/curl-class.md).|

### <a name="functions"></a>Функции

|||
|-|-|
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|Вызывайте эту функцию для приведения URL-адреса к каноническому виду, что включает преобразование небезопасных символов и пробелов в escape-последовательности.|
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|Вызывайте эту функцию для объединения базового и относительного URL-адресов в один канонический URL-адрес.|
|[AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|Вызывайте эту функцию для преобразования всех небезопасных символов в escape-последовательности.|
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|Вызывайте эту функцию, чтобы получить номер порта по умолчанию, связанные с определенным Интернет-протоколом или схемой.|
|[AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.|
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|Вызывайте эту функцию, чтобы определить, безопасно ли использовать символ в URL-адресе.|
|[AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|Вызывайте эту функцию для обратного преобразования escape-символов в первоначальные значения.|
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP.|  

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)| Эта функция представляет собой перегруженную оболочку для [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha
). | |[ ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)| Эта функция представляет собой перегруженную оболочку для [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona). | |[ ATLPath::Append](../atl/reference/atl-path-functions.md#append)| Эта функция представляет собой перегруженную оболочку для [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda). | |[ ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)| Эта функция представляет собой перегруженную оболочку для [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota). | |[ ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)| Эта функция представляет собой перегруженную оболочку для [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea). | |[ ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)| Эта функция представляет собой перегруженную оболочку для [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea). | |[ ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)| Эта функция представляет собой перегруженную оболочку для [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa). | |[ ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)| Эта функция представляет собой перегруженную оболочку для [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha). | |[ ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)| Эта функция представляет собой перегруженную оболочку для [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa). | |[ ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)| Эта функция представляет собой перегруженную оболочку для [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa). | |[ ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)| Эта функция представляет собой перегруженную оболочку для [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona). | |[ ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)| Эта функция представляет собой перегруженную оболочку для [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea). | |[ ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)| Эта функция представляет собой перегруженную оболочку для [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera). | |[ ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)| Эта функция представляет собой перегруженную оболочку для [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya). | |[ ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)| Эта функция представляет собой перегруженную оболочку для [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca). | |[ ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)| Эта функция представляет собой перегруженную оболочку для [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa). | |[ ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)| Эта функция представляет собой перегруженную оболочку для [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea). | |[ ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)| Эта функция представляет собой перегруженную оболочку для [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota). | |[ ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)| Эта функция представляет собой перегруженную оболочку для [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota). | |[ ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)| Эта функция представляет собой перегруженную оболочку для [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca). | |[ ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)| Эта функция представляет собой перегруженную оболочку для [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera). | |[ ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)| Эта функция представляет собой перегруженную оболочку для [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).| |[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)|This function is an overloaded wrapper for [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).| |[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)|This function is an overloaded wrapper for [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).| |[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)|This function is an overloaded wrapper for [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).| |[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)|This function is an overloaded wrapper for [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).| |[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)|This function is an overloaded wrapper for [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).| |[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)|This function is an overloaded wrapper for [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).| |[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)|This function is an overloaded wrapper for [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).| |[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)|This function is an overloaded wrapper for [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).| |[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)|This function is an overloaded wrapper for [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).| |[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)|This function is an overloaded wrapper for [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).| |[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)|This function is an overloaded wrapper for [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).| |[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)|This function is an overloaded wrapper for [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).| |[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)|This function is an overloaded wrapper for [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).| |[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)|This function is an overloaded wrapper for [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).|

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)<br/>
[Компоненты ATL COM Desktop](../atl/atl-com-desktop-components.md)
