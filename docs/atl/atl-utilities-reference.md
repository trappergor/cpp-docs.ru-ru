---
title: Справочник по служебным программам ATL
ms.date: 11/04/2016
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
ms.openlocfilehash: f9e59a2c67d391995d94d77f526613534acb48de
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831879"
---
# <a name="atl-utilities-reference"></a>Справочник по служебным программам ATL

ATL предоставляет код для управления путями и URL-адресами в виде [кпаст](../atl/reference/cpatht-class.md) и [фигурных](../atl/reference/curl-class.md). Пул потоков [ксреадпул](../atl/reference/cthreadpool-class.md)можно использовать в приложениях. Этот код можно найти в файлах atlpath.h и atlutil.h.

## <a name="classes"></a>Классы

| &nbsp; | &nbsp; |
|--|--|
| [Класс CPathT](../atl/reference/cpatht-class.md) | Этот класс представляет путь. |
| [Класс CDebugReportHook](../atl/reference/cdebugreporthook-class.md) | Этот класс используется для отправки отладочных отчетов в именованный канал. |
| [Класс CNonStatelessWorker](../atl/reference/cnonstatelessworker-class.md) | Получает запросы из пула потоков и передает их в рабочий объект, который создается и уничтожается при каждом запросе. |
| [Класс CNoWorkerThread](../atl/reference/cnoworkerthread-class.md) | Используйте этот класс в качестве аргумента для `MonitorClass` параметра шаблона для кэширования классов, если требуется отключить динамическое обслуживание кэша. |
| [Класс CThreadPool](../atl/reference/cthreadpool-class.md) | Этот класс предоставляет пул рабочих потоков, которые обрабатывают очередь рабочих элементов. |
| [Класс CUrl](../atl/reference/curl-class.md) | Этот класс представляет URL-адрес. Он позволяет управлять каждым элементом URL-адреса независимо от того, выполняется ли синтаксический анализ существующей строки URL-адреса или создание строки с нуля. |
| [Класс CWorkerThread](../atl/reference/cworkerthread-class.md) | Этот класс создает рабочий поток или использует существующий, ожидает один или несколько дескрипторов объектов ядра и выполняет указанную клиентскую функцию, когда один из дескрипторов получает сигнал. |

## <a name="typedefs"></a>Определения типов

| &emsp; | &emsp; |
|--|--|
| [кпас](../atl/reference/atl-typedefs.md#cpath) | Специализация [кпаст](../atl/reference/cpatht-class.md) с помощью `CString` . |
| [кпаса](../atl/reference/atl-typedefs.md#cpatha) | Специализация [кпаст](../atl/reference/cpatht-class.md) с помощью `CStringA` . |
| [кпасв](../atl/reference/atl-typedefs.md#cpathw) | Специализация [кпаст](../atl/reference/cpatht-class.md) с помощью `CStringW` . |
| [ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port) | Тип, используемый для указания номера порта в [фигурных скобках](../atl/reference/curl-class.md) . |

## <a name="enums"></a>Перечисления

| &emsp; | &emsp; |
|--|--|
| [ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md) | Члены этого перечисления предоставляют константы для схем, распознаваемых [фигурой](../atl/reference/curl-class.md). |

## <a name="functions"></a>Функции

| &emsp; | &emsp; |
|--|--|
| [AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl) | Вызывайте эту функцию для приведения URL-адреса к каноническому виду, что включает преобразование небезопасных символов и пробелов в escape-последовательности. |
| [AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl) | Вызывайте эту функцию для объединения базового и относительного URL-адресов в один канонический URL-адрес. |
| [AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl) | Вызывайте эту функцию для преобразования всех небезопасных символов в escape-последовательности. |
| [AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport) | Вызовите эту функцию, чтобы получить номер порта по умолчанию, связанный с определенным протоколом или схемой Интернета. |
| [AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue) | Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры. |
| [AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar) | Вызывайте эту функцию, чтобы определить, безопасно ли использовать символ в URL-адресе. |
| [AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl) | Вызывайте эту функцию для обратного преобразования escape-символов в первоначальные значения. |
| [SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate) | Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP. |
| [ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash) | Эта функция является перегруженной оболочкой для [Пасаддбаккслаш] (/Виндовс/десктоп/АПИ/шлвапи/НФ-шлвапи-пасаддбаккслаша |
| ). |
| [ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension) | Эта функция является перегруженной оболочкой для [пасаддекстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw). |
| [ATLPath::Append](../atl/reference/atl-path-functions.md#append) | Эта функция является перегруженной оболочкой для [пасаппенд](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw). |
| [ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot) | Эта функция является перегруженной оболочкой для [пасбуилдрут](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw). |
| [ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize) | Эта функция является перегруженной оболочкой для [пасканоникализе](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew). |
| [ATLPath::Combine](../atl/reference/atl-path-functions.md#combine) | Эта функция является перегруженной оболочкой для [паскомбине](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew). |
| [ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix) | Эта функция является перегруженной оболочкой для [паскоммонпрефикс](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw). |
| [ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath) | Эта функция является перегруженной оболочкой для [паскомпактпас](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw). |
| [ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex) | Эта функция является перегруженной оболочкой для [паскомпактпасекс](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw). |
| [ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists) | Эта функция является перегруженной оболочкой для [пасфиликсистс](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw). |
| [ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension) | Эта функция является перегруженной оболочкой для [пасфиндекстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw). |
| [ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename) | Эта функция является перегруженной оболочкой для [пасфиндфиленаме](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew). |
| [ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber) | Эта функция является перегруженной оболочкой для [пасжетдривенумбер](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw). |
| [ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory) | Эта функция является перегруженной оболочкой для [пасисдиректори](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw). |
| [ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec) | Эта функция является перегруженной оболочкой для [пасисфилеспек](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw). |
| [ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix) | Эта функция является перегруженной оболочкой для [пасиспрефикс](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw). |
| [ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative) | Эта функция является перегруженной оболочкой для [пасисрелативе](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew). |
| [ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot) | Эта функция является перегруженной оболочкой для [пасисрут](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw). |
| [ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot) | Эта функция является перегруженной оболочкой для [пасиссамерут](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw). |
| [ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc) | Эта функция является перегруженной оболочкой для [пасисунк](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw). |
| [ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver) | Эта функция является перегруженной оболочкой для [пасисунксервер](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw). |
| [ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare) | Эта функция является перегруженной оболочкой для [пасисунксервершаре](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew). |
| [ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty) | Эта функция является перегруженной оболочкой для [пасмакепретти](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw). |
| [ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec) | Эта функция является перегруженной оболочкой для [пасматчспек](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw). |
| [ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces) | Эта функция является перегруженной оболочкой для [паскуотеспацес](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw). |
| [ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto) | Эта функция является перегруженной оболочкой для [пасрелативепасто](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow). |
| [ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs) | Эта функция является перегруженной оболочкой для [пасремовеаргс](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw). |
| [ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash) | Эта функция является перегруженной оболочкой для [пасремовебаккслаш](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw). |
| [ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks) | Эта функция является перегруженной оболочкой для [пасремовебланкс](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw). |
| [ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension) | Эта функция является перегруженной оболочкой для [пасремовикстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw). |
| [ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec) | Эта функция является перегруженной оболочкой для [пасремовефилеспек](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw). |
| [ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension) | Эта функция является перегруженной оболочкой для [пасренамикстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw). |
| [ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot) | Эта функция является перегруженной оболочкой для [пасскипрут](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw). |
| [ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath) | Эта функция является перегруженной оболочкой для [пасстриппас](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw). |
| [ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot) | Эта функция является перегруженной оболочкой для [пасстрипторут](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw). |
| [ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces) | Эта функция является перегруженной оболочкой для [пасункуотеспацес](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw). |

## <a name="see-also"></a>См. также раздел

[Концепции](../atl/active-template-library-atl-concepts.md)<br/>
[Компоненты ATL COM Desktop](../atl/atl-com-desktop-components.md)
