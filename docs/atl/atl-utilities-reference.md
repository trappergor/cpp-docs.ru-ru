---
title: Справочник по служебным программам ATL
ms.date: 11/04/2016
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
ms.openlocfilehash: 6c1481929f832e6f810ce46773f328f278b503fa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491699"
---
# <a name="atl-utilities-reference"></a>Справочник по служебным программам ATL

ATL предоставляет код для управления путями и URL-адресами в виде [кпаст](../atl/reference/cpatht-class.md) и [фигурных](../atl/reference/curl-class.md). Пул потоков [ксреадпул](../atl/reference/cthreadpool-class.md)можно использовать в приложениях. Этот код можно найти в файлах atlpath.h и atlutil.h.

### <a name="classes"></a>Классы

|||
|-|-|
|[Класс CPathT](../atl/reference/cpatht-class.md)|Этот класс представляет путь.|
|[Класс CDebugReportHook](../atl/reference/cdebugreporthook-class.md)|Этот класс используется для отправки отладочных отчетов в именованный канал.|
|[Класс CNonStatelessWorker](../atl/reference/cnonstatelessworker-class.md)|Получает запросы из пула потоков и передает их в рабочий объект, который создается и уничтожается при каждом запросе.|
|[Класс CNoWorkerThread](../atl/reference/cnoworkerthread-class.md)|Используйте этот класс в качестве аргумента для `MonitorClass` параметра шаблона для кэширования классов, если требуется отключить динамическое обслуживание кэша.|
|[Класс CThreadPool](../atl/reference/cthreadpool-class.md)|Этот класс предоставляет пул рабочих потоков, которые обрабатывают очередь рабочих элементов.|
|[Класс CUrl](../atl/reference/curl-class.md)|Этот класс представляет URL-адрес. Он позволяет управлять каждым элементом URL-адреса независимо от того, выполняется ли синтаксический анализ существующей строки URL-адреса или создание строки с нуля.|
|[Класс CWorkerThread](../atl/reference/cworkerthread-class.md)|Этот класс создает рабочий поток или использует существующий, ожидает один или несколько дескрипторов объектов ядра и выполняет указанную клиентскую функцию, когда один из дескрипторов получает сигнал.|

### <a name="typedefs"></a>Определения типов

|||
|-|-|
|[кпас](../atl/reference/atl-typedefs.md#cpath)|Специализация [кпаст](../atl/reference/cpatht-class.md) с помощью `CString`.|
|[кпаса](../atl/reference/atl-typedefs.md#cpatha)|Специализация [кпаст](../atl/reference/cpatht-class.md) с помощью `CStringA`.|
|[кпасв](../atl/reference/atl-typedefs.md#cpathw)|Специализация [кпаст](../atl/reference/cpatht-class.md) с помощью `CStringW`.|
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|Тип, используемый для указания номера порта в [фигурных скобках](../atl/reference/curl-class.md) .|

### <a name="enums"></a>перечислениям;

|||
|-|-|
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|Члены этого перечисления предоставляют константы для схем, распознаваемых [фигурой](../atl/reference/curl-class.md).|

### <a name="functions"></a>Функции

|||
|-|-|
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|Вызывайте эту функцию для приведения URL-адреса к каноническому виду, что включает преобразование небезопасных символов и пробелов в escape-последовательности.|
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|Вызывайте эту функцию для объединения базового и относительного URL-адресов в один канонический URL-адрес.|
|[атлескапеурл](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|Вызывайте эту функцию для преобразования всех небезопасных символов в escape-последовательности.|
|[атлжетдефаултурлпорт](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|Вызовите эту функцию, чтобы получить номер порта по умолчанию, связанный с определенным протоколом или схемой Интернета.|
|[атлхексвалуе](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.|
|[атлисунсафеурлчар](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|Вызывайте эту функцию, чтобы определить, безопасно ли использовать символ в URL-адресе.|
|[атлунескапеурл](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|Вызывайте эту функцию для обратного преобразования escape-символов в первоначальные значения.|
|[системтиметохттпдате](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP.|

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)| Эта функция представляет собой перегруженную оболочку для [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha
). | |[ ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)| Эта функция представляет собой перегруженную оболочку для [PathAddExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw). | |[ ATLPath::Append](../atl/reference/atl-path-functions.md#append)| Эта функция представляет собой перегруженную оболочку для [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw). | |[ ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)| Эта функция представляет собой перегруженную оболочку для [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw). | |[ ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)| Эта функция представляет собой перегруженную оболочку для [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew). | |[ ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)| Эта функция представляет собой перегруженную оболочку для [PathCombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew). | |[ ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)| Эта функция представляет собой перегруженную оболочку для [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw). | |[ ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)| Эта функция представляет собой перегруженную оболочку для [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw). | |[ ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)| Эта функция представляет собой перегруженную оболочку для [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw). | |[ ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)| Эта функция представляет собой перегруженную оболочку для [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw). | |[ ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)| Эта функция представляет собой перегруженную оболочку для [PathFindExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw). | |[ ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)| Эта функция представляет собой перегруженную оболочку для [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew). | |[ ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)| Эта функция представляет собой перегруженную оболочку для [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw). | |[ ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)| Эта функция представляет собой перегруженную оболочку для [PathIsDirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw). | |[ ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)| Эта функция представляет собой перегруженную оболочку для [PathIsFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw). | |[ ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)| Эта функция представляет собой перегруженную оболочку для [PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw). | |[ ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)| Эта функция представляет собой перегруженную оболочку для [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew). | |[ ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)| Эта функция представляет собой перегруженную оболочку для [PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw). | |[ ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)| Эта функция представляет собой перегруженную оболочку для [PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw). | |[ ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)| Эта функция представляет собой перегруженную оболочку для [PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw). | |[ ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)| Эта функция представляет собой перегруженную оболочку для [PathIsUNCServer](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw). | |[ ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)| Эта функция представляет собой перегруженную оболочку для [PathIsUNCServerShare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew).| |[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)|This function is an overloaded wrapper for [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw).| |[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)|This function is an overloaded wrapper for [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw).| |[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)|This function is an overloaded wrapper for [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw).| |[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)|This function is an overloaded wrapper for [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow).| |[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)|This function is an overloaded wrapper for [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw).| |[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)|This function is an overloaded wrapper for [PathRemoveBackslash](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw).| |[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)|This function is an overloaded wrapper for [PathRemoveBlanks](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw).| |[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)|This function is an overloaded wrapper for [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw).| |[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)|This function is an overloaded wrapper for [PathRemoveFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw).| |[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)|This function is an overloaded wrapper for [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw).| |[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)|This function is an overloaded wrapper for [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw).| |[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)|This function is an overloaded wrapper for [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw).| |[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)|This function is an overloaded wrapper for [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw).| |[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)|This function is an overloaded wrapper for [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw).|

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)<br/>
[Компоненты ATL COM Desktop](../atl/atl-com-desktop-components.md)
