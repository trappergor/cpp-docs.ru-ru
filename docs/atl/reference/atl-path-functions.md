---
title: Функции пути ATL
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, path
f1_keywords:
- ATLPATH/ATL::ATLPath::AddBackslash
- ATLPATH/ATL::ATLPath::AddExtension
- ATLPATH/ATL::ATLPath::Append
- ATLPATH/ATL::ATLPath::BuildRoot
- ATLPATH/ATL::ATLPath::Canonicalize
- ATLPATH/ATL::ATLPath::Combine
- ATLPATH/ATL::ATLPath::CommonPrefix
- ATLPATH/ATL::ATLPath::CompactPath
- ATLPATH/ATL::ATLPath::CompactPathEx
- ATLPATH/ATL::ATLPath::FileExists
- ATLPATH/ATL::ATLPath::FindExtension
- ATLPATH/ATL::ATLPath::FindFileName
- ATLPATH/ATL::ATLPath::GetDriveNumber
- ATLPATH/ATL::ATLPath::IsDirectory
- ATLPATH/ATL::ATLPath::IsFileSpec
- ATLPATH/ATL::ATLPath::IsPrefix
- ATLPATH/ATL::ATLPath::IsRelative
- ATLPATH/ATL::ATLPath::IsRoot
- ATLPATH/ATL::ATLPath::IsSameRoot
- ATLPATH/ATL::ATLPath::IsUNC
- ATLPATH/ATL::ATLPath::IsUNCServer
- ATLPATH/ATL::ATLPath::IsUNCServerShare
- ATLPATH/ATL::ATLPath::MakePretty
- ATLPATH/ATL::ATLPath::MatchSpec
- ATLPATH/ATL::ATLPath::QuoteSpaces
- ATLPATH/ATL::ATLPath::RelativePathTo
- ATLPATH/ATL::ATLPath::RemoveArgs
- ATLPATH/ATL::ATLPath::RemoveBackslash
- ATLPATH/ATL::ATLPath::RemoveBlanks
- ATLPATH/ATL::ATLPath::RemoveExtension
- ATLPATH/ATL::ATLPath::RemoveFileSpec
- ATLPATH/ATL::ATLPath::RenameExtension
- ATLPATH/ATL::ATLPath::SkipRoot
- ATLPATH/ATL::ATLPath::StripPath
- ATLPATH/ATL::ATLPath::StripToRoot
- ATLPATH/ATL::ATLPath::UnquoteSpaces
ms.assetid: d1ec2b8d-7ec7-43ea-90dd-0a740d2a742b
ms.openlocfilehash: 76efbb0bd43b800f186eac1afa168fc2a0c939f6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497985"
---
# <a name="atl-path-functions"></a>Функции пути ATL

ATL предоставляет класс ATLPath для манипуляции путями в форме [кпаст](cpatht-class.md). Этот код можно найти в atlpath. h.

### <a name="related-classes"></a>Связанные классы

|||
|-|-|
|[Класс CPathT](cpatht-class.md)|Этот класс представляет путь.|

### <a name="related-typedefs"></a>Связанные определения типов

|||
|-|-|
|`CPath`|Специализация [кпаст](cpatht-class.md) с помощью `CString`.|
|`CPathA`|Специализация [кпаст](cpatht-class.md) с помощью `CStringA`.|
|`CPathW`|Специализация [кпаст](cpatht-class.md) с помощью `CStringW`.|

### <a name="functions"></a>Функции

|||
|-|-|
|[ATLPath:: Аддбаккслаш](#addbackslash)|Эта функция является перегруженной оболочкой для [пасаддбаккслаш](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw).|
|[ATLPath:: Аддекстенсион](#addextension)|Эта функция является перегруженной оболочкой для [пасаддекстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw).|
|[ATLPath:: Append](#append)|Эта функция является перегруженной оболочкой для [пасаппенд](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw).|
|[ATLPath:: BuildRoot](#buildroot)|Эта функция является перегруженной оболочкой для [пасбуилдрут](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw).|
|[ATLPath:: канонизировать](#canonicalize)|Эта функция является перегруженной оболочкой для [пасканоникализе](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew).|
|[ATLPath:: Combine](#combine)|Эта функция является перегруженной оболочкой для [паскомбине](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew).|
|[ATLPath:: Коммонпрефикс](#commonprefix)|Эта функция является перегруженной оболочкой для [паскоммонпрефикс](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw).|
|[ATLPath:: Компактпас](#compactpath)|Эта функция является перегруженной оболочкой для [паскомпактпас](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw).|
|[ATLPath:: Компактпасекс](#compactpathex)|Эта функция является перегруженной оболочкой для [паскомпактпасекс](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw).|
|[ATLPath:: FileExists](#fileexists)|Эта функция является перегруженной оболочкой для [пасфиликсистс](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw).|
|[ATLPath:: Финдекстенсион](#findextension)|Эта функция является перегруженной оболочкой для [пасфиндекстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw).|
|[ATLPath:: Финдфиленаме](#findfilename)|Эта функция является перегруженной оболочкой для [пасфиндфиленаме](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew).|
|[ATLPath::GetDriveNumber](#getdrivenumber)|Эта функция является перегруженной оболочкой для [пасжетдривенумбер](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw).|
|[ATLPath:: подкаталог](#isdirectory)|Эта функция является перегруженной оболочкой для [пасисдиректори](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw).|
|[ATLPath::IsFileSpec](#isfilespec)|Эта функция является перегруженной оболочкой для [пасисфилеспек](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw).|
|[ATLPath:: "префикс"](#isprefix)|Эта функция является перегруженной оболочкой для [пасиспрефикс](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw).|
|[ATLPath:: a](#isrelative)|Эта функция является перегруженной оболочкой для [пасисрелативе](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew).|
|[ATLPath:: \ root](#isroot)|Эта функция является перегруженной оболочкой для [пасисрут](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw).|
|[ATLPath::IsSameRoot](#issameroot)|Эта функция является перегруженной оболочкой для [пасиссамерут](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw).|
|[ATLPath:: Исунк](#isunc)|Эта функция является перегруженной оболочкой для [пасисунк](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw).|
|[ATLPath::IsUNCServer](#isuncserver)|Эта функция является перегруженной оболочкой для [пасисунксервер](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw).|
|[ATLPath:: Исунксервершаре](#isuncservershare)|Эта функция является перегруженной оболочкой для [пасисунксервершаре](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew).|
|[ATLPath:: Макепретти](#makepretty)|Эта функция является перегруженной оболочкой для [пасмакепретти](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw).|
|[ATLPath:: Матчспек](#matchspec)|Эта функция является перегруженной оболочкой для [пасматчспек](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw).|
|[ATLPath:: Куотеспацес](#quotespaces)|Эта функция является перегруженной оболочкой для [паскуотеспацес](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw).|
|[ATLPath:: Релативепасто](#relativepathto)|Эта функция является перегруженной оболочкой для [пасрелативепасто](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow).|
|[ATLPath:: Ремовеаргс](#removeargs)|Эта функция является перегруженной оболочкой для [пасремовеаргс](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw).|
|[ATLPath:: Ремовебаккслаш](#removebackslash)|Эта функция является перегруженной оболочкой для [пасремовебаккслаш](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw).|
|[ATLPath:: Ремовебланкс](#removeblanks)|Эта функция является перегруженной оболочкой для [пасремовебланкс](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw).|
|[ATLPath:: Ремовикстенсион](#removeextension)|Эта функция является перегруженной оболочкой для [пасремовикстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw).|
|[ATLPath:: Ремовефилеспек](#removefilespec)|Эта функция является перегруженной оболочкой для [пасремовефилеспек](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw).|
|[ATLPath:: Ренамикстенсион](#renameextension)|Эта функция является перегруженной оболочкой для [пасренамикстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw).|
|[ATLPath:: Скипрут](#skiproot)|Эта функция является перегруженной оболочкой для [пасскипрут](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw).|
|[ATLPath:: Стриппас](#strippath)|Эта функция является перегруженной оболочкой для [пасстриппас](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw).|
|[ATLPath::StripToRoot](#striptoroot)|Эта функция является перегруженной оболочкой для [пасстрипторут](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw).|
|[ATLPath:: Ункуотеспацес](#unquotespaces)|Эта функция является перегруженной оболочкой для [пасункуотеспацес](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw).|

## <a name="requirements"></a>Требования

**Заголовок:** atlpath. h

## <a name="addbackslash"></a>ATLPath:: Аддбаккслаш

Эта функция является перегруженной оболочкой для [пасаддбаккслаш](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw).

### <a name="syntax"></a>Синтаксис

```
inline char* AddBackslash(char* pszPath);
inline wchar_t* AddBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасаддбаккслаш](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw) .

## <a name="addextension"></a>ATLPath:: Аддекстенсион

Эта функция является перегруженной оболочкой для [пасаддекстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL AddExtension(char* pszPath, const char* pszExtension);
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасаддекстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw) .

## <a name="append"></a>ATLPath:: Append

Эта функция является перегруженной оболочкой для [пасаппенд](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL Append(char* pszPath, const char* pszMore);
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасаппенд](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw) .

## <a name="buildroot"></a>ATLPath:: BuildRoot

Эта функция является перегруженной оболочкой для [пасбуилдрут](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw).

### <a name="syntax"></a>Синтаксис

```
inline char* BuildRoot(char* pszPath, int iDrive);
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасбуилдрут](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw) .

## <a name="canonicalize"></a>ATLPath:: канонизировать

Эта функция является перегруженной оболочкой для [пасканоникализе](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew).

### <a name="syntax"></a>Синтаксис

```
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасканоникализе](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew) .

## <a name="combine"></a>ATLPath:: Combine

Эта функция является перегруженной оболочкой для [паскомбине](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew).

### <a name="syntax"></a>Синтаксис

```
inline char* Combine(
   char* pszDest,
   const char* pszDir,
   const char* pszFile
);

inline wchar_t* Combine(
   wchar_t* pszDest,
   const wchar_t* pszDir,
   const wchar_t* pszFile);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе Паскомбине.

## <a name="commonprefix"></a>ATLPath:: Коммонпрефикс

Эта функция является перегруженной оболочкой для [паскоммонпрефикс](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw).

### <a name="syntax"></a>Синтаксис

```
inline int CommonPrefix(
   const char* pszFile1,
   const char* pszFile2,
   char* pszDest);

inline int CommonPrefix(
   const wchar_t* pszFile1,
   const wchar_t* pszFile2,
   wchar_t* pszDest);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [паскоммонпрефикс](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw) .

## <a name="compactpath"></a>ATLPath:: Компактпас

Эта функция является перегруженной оболочкой для [паскомпактпас](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL CompactPath(
   HDC hDC,
   char* pszPath,
   UINT dx);

inline BOOL CompactPath(
   HDC hDC,
   wchar_t* pszPath,
   UINT dx);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [паскомпактпас](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw) .

## <a name="compactpathex"></a>ATLPath:: Компактпасекс

Эта функция является перегруженной оболочкой для [паскомпактпасекс](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL CompactPathEx(
   char* pszDest,
   const char* pszSrc,
   UINT nMaxChars,
   DWORD dwFlags);

inline BOOL CompactPathEx(
   wchar_t* pszDest,
   const wchar_t* pszSrc,
   UINT nMaxChars,
   DWORD dwFlags);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [паскомпактпасекс](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw) .

## <a name="fileexists"></a>ATLPath:: FileExists

Эта функция является перегруженной оболочкой для [пасфиликсистс](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL FileExists(const char* pszPath);
inline BOOL FileExists(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасфиликсистс](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw) .

## <a name="findextension"></a>ATLPath:: Финдекстенсион

Эта функция является перегруженной оболочкой для [пасфиндекстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw).

### <a name="syntax"></a>Синтаксис

```
inline char* FindExtension(const char* pszPath);
inline wchar_t* FindExtension(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасфиндекстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw) .

## <a name="findfilename"></a>ATLPath:: Финдфиленаме

Эта функция является перегруженной оболочкой для [пасфиндфиленаме](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew).

### <a name="syntax"></a>Синтаксис

```
inline char* FindFileName(const char* pszPath);
inline wchar_t* FindFileName(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасфиндфиленаме](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) .

## <a name="getdrivenumber"></a>ATLPath:: Жетдривенумбер

Эта функция является перегруженной оболочкой для [пасжетдривенумбер](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw).

### <a name="syntax"></a>Синтаксис

```
inline int GetDriveNumber(const char* pszPath);
inline int GetDriveNumber(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасжетдривенумбер](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw) .

## <a name="isdirectory"></a>ATLPath:: подкаталог

Эта функция является перегруженной оболочкой для [пасисдиректори](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw).

```
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе Пасисдиректори.

## <a name="isfilespec"></a>ATLPath:: Исфилеспек

Эта функция является перегруженной оболочкой для [пасисфилеспек](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsFileSpec(const char* pszPath);
inline BOOL IsFileSpec(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасисфилеспек](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw) .

## <a name="isprefix"></a>ATLPath:: "префикс"

Эта функция является перегруженной оболочкой для [пасиспрефикс](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасиспрефикс](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw) .

## <a name="isrelative"></a>ATLPath:: a

Эта функция является перегруженной оболочкой для [пасисрелативе](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew).

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsRelative(const char* pszPath);
inline BOOL IsRelative(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасисрелативе](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew) .

## <a name="isroot"></a>ATLPath:: \ root

Эта функция является перегруженной оболочкой для [пасисрут](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsRoot(const char* pszPath);
inline BOOL IsRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасисрут](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw) .

## <a name="issameroot"></a>ATLPath:: Иссамерут

Эта функция является перегруженной оболочкой для [пасиссамерут](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасиссамерут](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw) .

## <a name="isunc"></a>ATLPath:: Исунк

Эта функция является перегруженной оболочкой для [пасисунк](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsUNC(const char* pszPath);
inline BOOL IsUNC(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасисунк](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw) .

## <a name="isuncserver"></a>ATLPath:: Исунксервер

Эта функция является перегруженной оболочкой для [пасисунксервер](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsUNCServer(const char* pszPath);
inline BOOL IsUNCServer(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасисунксервер](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw) .

## <a name="isuncservershare"></a>ATLPath:: Исунксервершаре

Эта функция является перегруженной оболочкой для [пасисунксервершаре](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew).

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsUNCServerShare(const char* pszPath);
inline BOOL IsUNCServerShare(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасисунксервершаре](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew) .

## <a name="makepretty"></a>ATLPath:: Макепретти

Эта функция является перегруженной оболочкой для [пасмакепретти](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL MakePretty(char* pszPath);
inline BOOL MakePretty(wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасмакепретти](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw) .

## <a name="matchspec"></a>ATLPath:: Матчспек

Эта функция является перегруженной оболочкой для [пасматчспек](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасматчспек](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw) .

## <a name="quotespaces"></a>ATLPath:: Куотеспацес

Эта функция является перегруженной оболочкой для [паскуотеспацес](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw).

### <a name="syntax"></a>Синтаксис

```
inline void QuoteSpaces(char* pszPath);
inline void QuoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [паскуотеспацес](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw) .

## <a name="relativepathto"></a>ATLPath:: Релативепасто

Эта функция является перегруженной оболочкой для [пасрелативепасто](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow).

### <a name="syntax"></a>Синтаксис

```
inline BOOL RelativePathTo(
   char* pszPath,
   const char* pszFrom,
   DWORD dwAttrFrom,
   const char* pszTo,
   DWORD dwAttrTo);

inline BOOL RelativePathTo(
   wchar_t* pszPath,
   const wchar_t* pszFrom,
   DWORD dwAttrFrom,
   const wchar_t* pszTo,
   DWORD dwAttrTo);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасрелативепасто](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow) .

## <a name="removeargs"></a>ATLPath:: Ремовеаргс

Эта функция является перегруженной оболочкой для [пасремовеаргс](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw).

### <a name="syntax"></a>Синтаксис

```
inline void RemoveArgs(char* pszPath);
inline void RemoveArgs(wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасремовеаргс](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw) .

## <a name="removebackslash"></a>ATLPath:: Ремовебаккслаш

Эта функция является перегруженной оболочкой для [пасремовебаккслаш](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw).

### <a name="syntax"></a>Синтаксис

```
inline char* RemoveBackslash(char* pszPath);
inline wchar_t* RemoveBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасремовебаккслаш](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw) .

## <a name="removeblanks"></a>ATLPath:: Ремовебланкс

Эта функция является перегруженной оболочкой для [пасремовебланкс](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw).

### <a name="syntax"></a>Синтаксис

```
inline void RemoveBlanks(char* pszPath);
inline void RemoveBlanks(wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасремовебланкс](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw) .

## <a name="removeextension"></a>ATLPath:: Ремовикстенсион

Эта функция является перегруженной оболочкой для [пасремовикстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw).

### <a name="syntax"></a>Синтаксис

```
inline void RemoveExtension(char* pszPath);
inline void RemoveExtension(wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасремовикстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw) .

## <a name="removefilespec"></a>ATLPath:: Ремовефилеспек

Эта функция является перегруженной оболочкой для [пасремовефилеспек](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL RemoveFileSpec(char* pszPath);
inline BOOL RemoveFileSpec(wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасремовефилеспек](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw) .

## <a name="renameextension"></a>ATLPath:: Ренамикстенсион

Эта функция является перегруженной оболочкой для [пасренамикстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL RenameExtension(char* pszPath, const char* pszExt);
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасренамикстенсион](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw) .

## <a name="skiproot"></a>ATLPath:: Скипрут

Эта функция является перегруженной оболочкой для [пасскипрут](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw).

### <a name="syntax"></a>Синтаксис

```
inline char* SkipRoot(const char* pszPath);
inline wchar_t* SkipRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасскипрут](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw) .

## <a name="strippath"></a>ATLPath:: Стриппас

Эта функция является перегруженной оболочкой для [пасстриппас](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw).

### <a name="syntax"></a>Синтаксис

```
inline void StripPath(char* pszPath);
inline void StripPath(wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасстриппас](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw) .

## <a name="striptoroot"></a>ATLPath:: Стрипторут

Эта функция является перегруженной оболочкой для [пасстрипторут](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL StripToRoot(char* pszPath);
inline BOOL StripToRoot(wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасстрипторут](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw) .

## <a name="unquotespaces"></a>ATLPath:: Ункуотеспацес

Эта функция является перегруженной оболочкой для [пасункуотеспацес](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw).

### <a name="syntax"></a>Синтаксис

```
inline void UnquoteSpaces(char* pszPath);
inline void UnquoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [пасункуотеспацес](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw) .
