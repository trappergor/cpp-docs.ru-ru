---
title: Функции ATL Path
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
ms.openlocfilehash: f3d8fa63e7fd20f8a0d6759fee8417b3fbc29486
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319224"
---
# <a name="atl-path-functions"></a>Функции ATL Path

ATL предоставляет класс ATLPath для манипулирования путями в виде [CPathT.](cpatht-class.md) Этот код можно найти в atlpath.h.

### <a name="related-classes"></a>Похожие классы

|||
|-|-|
|[Класс CPathT](cpatht-class.md)|Этот класс представляет собой путь.|

### <a name="related-typedefs"></a>Связанные Typedefs

|||
|-|-|
|`CPath`|Специализация [CPathT](cpatht-class.md) `CString`с использованием .|
|`CPathA`|Специализация [CPathT](cpatht-class.md) `CStringA`с использованием .|
|`CPathW`|Специализация [CPathT](cpatht-class.md) `CStringW`с использованием .|

### <a name="functions"></a>Функции

|||
|-|-|
|[ATLPath::AddBackslash](#addbackslash)|Эта функция представляет собой перегруженную обертку для [PathAddBackslash.](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)|
|[ATLPath::AddExtension](#addextension)|Эта функция представляет собой перегруженную обертку для [PathAddExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)|
|[ATLPath::Append](#append)|Эта функция представляет собой перегруженную обертку для [PathAppend.](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)|
|[ATLPath::BuildRoot](#buildroot)|Эта функция представляет собой перегруженную обертку для [PathBuildRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)|
|[ATLPath::Canonicalize](#canonicalize)|Эта функция представляет собой перегруженную обертку для [PathCanonicalize.](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)|
|[ATLPath::Combine](#combine)|Эта функция представляет собой перегруженную обертку для [PathCombine.](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)|
|[ATLPath::CommonPrefix](#commonprefix)|Эта функция представляет собой перегруженную обертку для [PathCommonPrefix.](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)|
|[ATLPath::CompactPath](#compactpath)|Эта функция представляет собой перегруженную обертку для [PathCompactPath.](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)|
|[ATLPath::CompactPathEx](#compactpathex)|Эта функция представляет собой перегруженную обертку для [PathCompactPathEx.](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)|
|[ATLPath::FileExists](#fileexists)|Эта функция представляет собой перегруженную обертку для [PathFileExists.](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)|
|[ATLPath::FindExtension](#findextension)|Эта функция представляет собой перегруженную обертку для [PathFindExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)|
|[ATLPath::FindFileName](#findfilename)|Эта функция представляет собой перегруженную обертку для [PathFindFileName.](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)|
|[ATLPath::GetDriveNumber](#getdrivenumber)|Эта функция представляет собой перегруженную обертку для [PathGetDriveNumber.](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)|
|[ATLPath::IsDirectory](#isdirectory)|Эта функция представляет собой перегруженную обертку для [PathIsDirectory.](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)|
|[ATLPath::IsFileSpec](#isfilespec)|Эта функция представляет собой перегруженную обертку для [PathIsFileSpec.](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)|
|[ATLPath::IsPrefix](#isprefix)|Эта функция представляет собой перегруженную обертку для [PathIsPrefix.](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)|
|[ATLPath::IsRelative](#isrelative)|Эта функция представляет собой перегруженную обертку для [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew).|
|[ATLPath::IsRoot](#isroot)|Эта функция представляет собой перегруженную обертку для [PathIsRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)|
|[ATLPath::IsSameRoot](#issameroot)|Эта функция представляет собой перегруженную обертку для [PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw).|
|[ATLPath::IsUNC](#isunc)|Эта функция представляет собой перегруженную обертку для [PathIsUNC.](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)|
|[ATLPath::IsUNCServer](#isuncserver)|Эта функция представляет собой перегруженную обертку для [PathIsUNCServer](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw).|
|[ATLPath::IsUNCServerShare](#isuncservershare)|Эта функция представляет собой перегруженную обертку для [PathIsUNCServerShare.](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)|
|[ATLPath::MakePretty](#makepretty)|Эта функция представляет собой перегруженную обертку для [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw).|
|[ATLPath::MatchSpec](#matchspec)|Эта функция представляет собой перегруженную обертку для [PathMatchSpec.](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)|
|[ATLPath::QuoteSpaces](#quotespaces)|Эта функция представляет собой перегруженную обертку для [Pathuu'uispaces.](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)|
|[ATLPath::RelativePathTo](#relativepathto)|Эта функция представляет собой перегруженную обертку для [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow).|
|[ATLPath::RemoveArgs](#removeargs)|Эта функция представляет собой перегруженную обертку для [PathRemoveArgs.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)|
|[ATLPath::RemoveBackslash](#removebackslash)|Эта функция представляет собой перегруженную обертку для [PathRemoveBackslash.](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)|
|[ATLPath::RemoveBlanks](#removeblanks)|Эта функция представляет собой перегруженную обертку для [PathRemoveBlanks.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)|
|[ATLPath::RemoveExtension](#removeextension)|Эта функция представляет собой перегруженную обертку для [PathRemoveExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)|
|[ATLPath::RemoveFileSpec](#removefilespec)|Эта функция представляет собой перегруженную обертку для [PathRemoveFileSpec.](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)|
|[ATLPath::RenameExtension](#renameextension)|Эта функция представляет собой перегруженную обертку для [PathRenameExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)|
|[ATLPath::SkipRoot](#skiproot)|Эта функция представляет собой перегруженную обертку для [PathSkipRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)|
|[ATLPath::StripPath](#strippath)|Эта функция представляет собой перегруженную обертку для [PathStripPath.](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)|
|[ATLPath::StripToRoot](#striptoroot)|Эта функция представляет собой перегруженную обертку для [PathStripToRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)|
|[ATLPath::UnquoteSpaces](#unquotespaces)|Эта функция представляет собой перегруженную обертку для [PathUnquoteSpaces.](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)|

## <a name="requirements"></a>Требования

**Заголовок:** atlpath.h

## <a name="atlpathaddbackslash"></a><a name="addbackslash"></a>ATLPath::AddBackSlash

Эта функция представляет собой перегруженную обертку для [PathAddBackslash.](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)

### <a name="syntax"></a>Синтаксис

```
inline char* AddBackslash(char* pszPath);
inline wchar_t* AddBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathAddBackslash.](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)

## <a name="atlpathaddextension"></a><a name="addextension"></a>ATLPath::AddExtension

Эта функция представляет собой перегруженную обертку для [PathAddExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)

### <a name="syntax"></a>Синтаксис

```
inline BOOL AddExtension(char* pszPath, const char* pszExtension);
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathAddExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)

## <a name="atlpathappend"></a><a name="append"></a>ATLPath::Приложение

Эта функция представляет собой перегруженную обертку для [PathAppend.](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)

### <a name="syntax"></a>Синтаксис

```
inline BOOL Append(char* pszPath, const char* pszMore);
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);
```

### <a name="remarks"></a>Remarks

Подробности смотрите в [PathAppend.](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)

## <a name="atlpathbuildroot"></a><a name="buildroot"></a>ATLPath::BuildRoot

Эта функция представляет собой перегруженную обертку для [PathBuildRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)

### <a name="syntax"></a>Синтаксис

```
inline char* BuildRoot(char* pszPath, int iDrive);
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathBuildRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)

## <a name="atlpathcanonicalize"></a><a name="canonicalize"></a>ATLPath::Каноникализация

Эта функция представляет собой перегруженную обертку для [PathCanonicalize.](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)

### <a name="syntax"></a>Синтаксис

```
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathCanonicalize.](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)

## <a name="atlpathcombine"></a><a name="combine"></a>ATLPath::Комбинат

Эта функция представляет собой перегруженную обертку для [PathCombine.](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)

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

### <a name="remarks"></a>Remarks

Подробности смотрите в PathCombine.

## <a name="atlpathcommonprefix"></a><a name="commonprefix"></a>ATLPath::CommonPrefix

Эта функция представляет собой перегруженную обертку для [PathCommonPrefix.](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)

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

### <a name="remarks"></a>Remarks

Подробности смотрите в материале [PathCommonPrefix.](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)

## <a name="atlpathcompactpath"></a><a name="compactpath"></a>ATLPath::CompactPath

Эта функция представляет собой перегруженную обертку для [PathCompactPath.](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)

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

### <a name="remarks"></a>Remarks

Подробности смотрите в [PathCompactPath.](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)

## <a name="atlpathcompactpathex"></a><a name="compactpathex"></a>ATLPath::CompactPathEx

Эта функция представляет собой перегруженную обертку для [PathCompactPathEx.](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)

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

### <a name="remarks"></a>Remarks

Подробности смотрите в [PathCompactPathEx.](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)

## <a name="atlpathfileexists"></a><a name="fileexists"></a>ATLPath::FileExists

Эта функция представляет собой перегруженную обертку для [PathFileExists.](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)

### <a name="syntax"></a>Синтаксис

```
inline BOOL FileExists(const char* pszPath);
inline BOOL FileExists(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Смотрите [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw) для получения подробной информации.

## <a name="atlpathfindextension"></a><a name="findextension"></a>ATLPath::FindExtension

Эта функция представляет собой перегруженную обертку для [PathFindExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)

### <a name="syntax"></a>Синтаксис

```
inline char* FindExtension(const char* pszPath);
inline wchar_t* FindExtension(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathFindExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)

## <a name="atlpathfindfilename"></a><a name="findfilename"></a>ATLPath::FindFileName

Эта функция представляет собой перегруженную обертку для [PathFindFileName.](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)

### <a name="syntax"></a>Синтаксис

```
inline char* FindFileName(const char* pszPath);
inline wchar_t* FindFileName(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о [компании PathFindFileName.](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)

## <a name="atlpathgetdrivenumber"></a><a name="getdrivenumber"></a>ATLPath::GetDriveНомер

Эта функция представляет собой перегруженную обертку для [PathGetDriveNumber.](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)

### <a name="syntax"></a>Синтаксис

```
inline int GetDriveNumber(const char* pszPath);
inline int GetDriveNumber(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathGetDriveNumber.](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)

## <a name="atlpathisdirectory"></a><a name="isdirectory"></a>ATLPath::IsDirectory

Эта функция представляет собой перегруженную обертку для [PathIsDirectory.](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)

```
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробности смотрите в справочной информации PathIsDirectory.

## <a name="atlpathisfilespec"></a><a name="isfilespec"></a>ATLPath::IsFileSpec

Эта функция представляет собой перегруженную обертку для [PathIsFileSpec.](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsFileSpec(const char* pszPath);
inline BOOL IsFileSpec(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробности смотрите в [материале PathIsFileSpec.](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)

## <a name="atlpathisprefix"></a><a name="isprefix"></a>ATLPath::IsPrefix

Эта функция представляет собой перегруженную обертку для [PathIsPrefix.](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробности смотрите в материале [PathIsPrefix.](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)

## <a name="atlpathisrelative"></a><a name="isrelative"></a>ATLPath::Относительно

Эта функция представляет собой перегруженную обертку для [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew).

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsRelative(const char* pszPath);
inline BOOL IsRelative(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathIsRelative.](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)

## <a name="atlpathisroot"></a><a name="isroot"></a>ATLPath::IsRoot

Эта функция представляет собой перегруженную обертку для [PathIsRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsRoot(const char* pszPath);
inline BOOL IsRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробности смотрите в [материале PathIsRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)

## <a name="atlpathissameroot"></a><a name="issameroot"></a>ATLPath::IsSameRoot

Эта функция представляет собой перегруженную обертку для [PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathIsSameRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)

## <a name="atlpathisunc"></a><a name="isunc"></a>ATLPath::ISUNC

Эта функция представляет собой перегруженную обертку для [PathIsUNC.](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsUNC(const char* pszPath);
inline BOOL IsUNC(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробности смотрите в [PathIsUNC.](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)

## <a name="atlpathisuncserver"></a><a name="isuncserver"></a>ATLPath:ISUNCServer

Эта функция представляет собой перегруженную обертку для [PathIsUNCServer](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsUNCServer(const char* pszPath);
inline BOOL IsUNCServer(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробности смотрите в [материале PathIsUNCServer.](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)

## <a name="atlpathisuncservershare"></a><a name="isuncservershare"></a>ATLPath::IsUNCServerShare

Эта функция представляет собой перегруженную обертку для [PathIsUNCServerShare.](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)

### <a name="syntax"></a>Синтаксис

```
inline BOOL IsUNCServerShare(const char* pszPath);
inline BOOL IsUNCServerShare(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathIsUNCServerShare.](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)

## <a name="atlpathmakepretty"></a><a name="makepretty"></a>ATLPath::MakePretty

Эта функция представляет собой перегруженную обертку для [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw).

### <a name="syntax"></a>Синтаксис

```
inline BOOL MakePretty(char* pszPath);
inline BOOL MakePretty(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathMakePretty.](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)

## <a name="atlpathmatchspec"></a><a name="matchspec"></a>ATLPath:MatchSpec

Эта функция представляет собой перегруженную обертку для [PathMatchSpec.](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)

### <a name="syntax"></a>Синтаксис

```
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);
```

### <a name="remarks"></a>Remarks

Подробности в [PathMatchSpec.](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)

## <a name="atlpathquotespaces"></a><a name="quotespaces"></a>ATLPath::КвотаПространства

Эта функция представляет собой перегруженную обертку для [Pathuu'uispaces.](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)

### <a name="syntax"></a>Синтаксис

```
inline void QuoteSpaces(char* pszPath);
inline void QuoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале Path'uotе:s.](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)

## <a name="atlpathrelativepathto"></a><a name="relativepathto"></a>ATLPath::RelativePathTo

Эта функция представляет собой перегруженную обертку для [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow).

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

### <a name="remarks"></a>Remarks

Подробности смотрите в [PathRelativePathTo.](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)

## <a name="atlpathremoveargs"></a><a name="removeargs"></a>ATLPath::RemoveArgs

Эта функция представляет собой перегруженную обертку для [PathRemoveArgs.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)

### <a name="syntax"></a>Синтаксис

```
inline void RemoveArgs(char* pszPath);
inline void RemoveArgs(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробности смотрите в [маршруте PathRemoveArgs.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)

## <a name="atlpathremovebackslash"></a><a name="removebackslash"></a>ATLPath::RemoveBackslash

Эта функция представляет собой перегруженную обертку для [PathRemoveBackslash.](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)

### <a name="syntax"></a>Синтаксис

```
inline char* RemoveBackslash(char* pszPath);
inline wchar_t* RemoveBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathRemoveBackslash.](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)

## <a name="atlpathremoveblanks"></a><a name="removeblanks"></a>ATLPath::RemoveBlanks

Эта функция представляет собой перегруженную обертку для [PathRemoveBlanks.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)

### <a name="syntax"></a>Синтаксис

```
inline void RemoveBlanks(char* pszPath);
inline void RemoveBlanks(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathRemoveBlanks.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)

## <a name="atlpathremoveextension"></a><a name="removeextension"></a>ATLPath::RemoveExtension

Эта функция представляет собой перегруженную обертку для [PathRemoveExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)

### <a name="syntax"></a>Синтаксис

```
inline void RemoveExtension(char* pszPath);
inline void RemoveExtension(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathRemoveExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)

## <a name="atlpathremovefilespec"></a><a name="removefilespec"></a>ATLPath::RemoveFileSpec

Эта функция представляет собой перегруженную обертку для [PathRemoveFileSpec.](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)

### <a name="syntax"></a>Синтаксис

```
inline BOOL RemoveFileSpec(char* pszPath);
inline BOOL RemoveFileSpec(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробности смотрите в [pathRemoveFileSpec.](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)

## <a name="atlpathrenameextension"></a><a name="renameextension"></a>ATLPath::Переименование

Эта функция представляет собой перегруженную обертку для [PathRenameExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)

### <a name="syntax"></a>Синтаксис

```
inline BOOL RenameExtension(char* pszPath, const char* pszExt);
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);
```

### <a name="remarks"></a>Remarks

Подробнее о [компании PathRenameExtension.](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)

## <a name="atlpathskiproot"></a><a name="skiproot"></a>ATLPath::Skip

Эта функция представляет собой перегруженную обертку для [PathSkipRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)

### <a name="syntax"></a>Синтаксис

```
inline char* SkipRoot(const char* pszPath);
inline wchar_t* SkipRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в [материале PathSkipRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)

## <a name="atlpathstrippath"></a><a name="strippath"></a>ATLPath::StripPath

Эта функция представляет собой перегруженную обертку для [PathStripPath.](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)

### <a name="syntax"></a>Синтаксис

```
inline void StripPath(char* pszPath);
inline void StripPath(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробности смотрите в [PathStripPath.](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)

## <a name="atlpathstriptoroot"></a><a name="striptoroot"></a>ATLPath::StripToroot

Эта функция представляет собой перегруженную обертку для [PathStripToRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)

### <a name="syntax"></a>Синтаксис

```
inline BOOL StripToRoot(char* pszPath);
inline BOOL StripToRoot(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробности смотрите в [материале PathStripToRoot.](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)

## <a name="atlpathunquotespaces"></a><a name="unquotespaces"></a>ATLPath::UnquoteSpaces

Эта функция представляет собой перегруженную обертку для [PathUnquoteSpaces.](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)

### <a name="syntax"></a>Синтаксис

```
inline void UnquoteSpaces(char* pszPath);
inline void UnquoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

Подробнее о [настройках PathUnquoteSpaces.](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)
