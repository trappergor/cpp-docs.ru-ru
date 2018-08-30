---
title: Функции пути ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42995e4040c6f73614659eede61f1560e1f31aed
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214409"
---
# <a name="atl-path-functions"></a>Функции пути ATL

Библиотека ATL предоставляет класс ATLPath для управления путями в виде [CPathT](cpatht-class.md). Этот код можно найти в atlpath.h.  
  
### <a name="related-classes"></a>Связанные классы  
  
|||  
|-|-|  
|[Класс CPathT](cpatht-class.md)|Этот класс представляет собой путь.|  

### <a name="related-typedefs"></a>Связанные определения типов  
  
|||  
|-|-|  
|`CPath`|Специализация [CPathT](cpatht-class.md) с помощью `CString`.|  
|`CPathA`|Специализация [CPathT](cpatht-class.md) с помощью `CStringA`.|  
|`CPathW`|Специализация [CPathT](cpatht-class.md) с помощью `CStringW`.|  
  
### <a name="functions"></a>Функции  
  
|||  
|-|-|  
|[ATLPath::AddBackslash](#addbackslash)|Эта функция представляет собой перегруженную оболочку для [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha).|  
|[ATLPath::AddExtension](#addextension)|Эта функция представляет собой перегруженную оболочку для [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona).|  
|[ATLPath::Append](#append)|Эта функция представляет собой перегруженную оболочку для [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda).|  
|[ATLPath::BuildRoot](#buildroot)|Эта функция представляет собой перегруженную оболочку для [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota).|  
|[ATLPath::Canonicalize](#canonicalize)|Эта функция представляет собой перегруженную оболочку для [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea).|  
|[ATLPath::Combine](#combine)|Эта функция представляет собой перегруженную оболочку для [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea).|  
|[ATLPath::CommonPrefix](#commonprefix)|Эта функция представляет собой перегруженную оболочку для [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa).|  
|[ATLPath::CompactPath](#compactpath)|Эта функция представляет собой перегруженную оболочку для [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha).|  
|[ATLPath::CompactPathEx](#compactpathex)|Эта функция представляет собой перегруженную оболочку для [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa).|  
|[ATLPath::FileExists](#fileexists)|Эта функция представляет собой перегруженную оболочку для [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa).|  
|[ATLPath::FindExtension](#findextension)|Эта функция представляет собой перегруженную оболочку для [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona).|  
|[ATLPath::FindFileName](#findfilename)|Эта функция представляет собой перегруженную оболочку для [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea).|  
|[ATLPath::GetDriveNumber](#getdrivenumber)|Эта функция представляет собой перегруженную оболочку для [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera).|  
|[ATLPath::IsDirectory](#isdirectory)|Эта функция представляет собой перегруженную оболочку для [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya).|  
|[ATLPath::IsFileSpec](#isfilespec)|Эта функция представляет собой перегруженную оболочку для [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca).|  
|[ATLPath::IsPrefix](#isprefix)|Эта функция представляет собой перегруженную оболочку для [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa).|  
|[ATLPath::IsRelative](#isrelative)|Эта функция представляет собой перегруженную оболочку для [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea).|  
|[ATLPath::IsRoot](#isroot)|Эта функция представляет собой перегруженную оболочку для [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota).|  
|[ATLPath::IsSameRoot](#issameroot)|Эта функция представляет собой перегруженную оболочку для [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota).|  
|[ATLPath::IsUNC](#isunc)|Эта функция представляет собой перегруженную оболочку для [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca).|  
|[ATLPath::IsUNCServer](#isuncserver)|Эта функция представляет собой перегруженную оболочку для [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera).|  
|[ATLPath::IsUNCServerShare](#isuncservershare)|Эта функция представляет собой перегруженную оболочку для [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).|  
|[ATLPath::MakePretty](#makepretty)|Эта функция представляет собой перегруженную оболочку для [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).|  
|[ATLPath::MatchSpec](#matchspec)|Эта функция представляет собой перегруженную оболочку для [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).|  
|[ATLPath::QuoteSpaces](#quotespaces)|Эта функция представляет собой перегруженную оболочку для [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).|  
|[ATLPath::RelativePathTo](#relativepathto)|Эта функция представляет собой перегруженную оболочку для [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).|  
|[ATLPath::RemoveArgs](#removeargs)|Эта функция представляет собой перегруженную оболочку для [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).|  
|[ATLPath::RemoveBackslash](#removebackslash)|Эта функция представляет собой перегруженную оболочку для [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).|  
|[ATLPath::RemoveBlanks](#removeblanks)|Эта функция представляет собой перегруженную оболочку для [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).|  
|[ATLPath::RemoveExtension](#removeextension)|Эта функция представляет собой перегруженную оболочку для [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).|  
|[ATLPath::RemoveFileSpec](#removefilespec)|Эта функция представляет собой перегруженную оболочку для [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).|  
|[ATLPath::RenameExtension](#renameextension)|Эта функция представляет собой перегруженную оболочку для [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).|  
|[ATLPath::SkipRoot](#skiproot)|Эта функция представляет собой перегруженную оболочку для [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).|  
|[ATLPath::StripPath](#strippath)|Эта функция представляет собой перегруженную оболочку для [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).|  
|[ATLPath::StripToRoot](#striptoroot)|Эта функция представляет собой перегруженную оболочку для [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).|  
|[ATLPath::UnquoteSpaces](#unquotespaces)|Эта функция представляет собой перегруженную оболочку для [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlpath.h  

## <a name="addbackslash"></a> ATLPath::AddBackSlash

Эта функция представляет собой перегруженную оболочку для [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* AddBackslash(char* pszPath);  
inline wchar_t* AddBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha) сведения.  
  
 
  

## <a name="addextension"></a> ATLPath::AddExtension
 Эта функция представляет собой перегруженную оболочку для [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL AddExtension(char* pszPath, const char* pszExtension);  
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona) сведения. 
  
## <a name="append"></a> ATLPath::Append
 Эта функция представляет собой перегруженную оболочку для [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL Append(char* pszPath, const char* pszMore);  
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda) сведения.  
  
 
  

## <a name="buildroot"></a> ATLPath::BuildRoot
 Эта функция представляет собой перегруженную оболочку для [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* BuildRoot(char* pszPath, int iDrive);  
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota) сведения.  
  
 
  

## <a name="canonicalize"></a> ATLPath::Canonicalize
 Эта функция представляет собой перегруженную оболочку для [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);  
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea) сведения.  
  
 
  

## <a name="combine"></a> ATLPath::Combine 
Эта функция представляет собой перегруженную оболочку для [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea).  

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
Дополнительные сведения см. PathCombine.


## <a name="commonprefix"></a> ATLPath::CommonPrefix
 Эта функция представляет собой перегруженную оболочку для [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa).  
  
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
 См. в разделе [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa) сведения.  
  
 
  

## <a name="compactpath"></a> ATLPath::CompactPath
 Эта функция представляет собой перегруженную оболочку для [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha).  
  
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
 См. в разделе [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha) сведения.  
  
 
  

## <a name="compactpathex"></a> ATLPath::CompactPathEx
 Эта функция представляет собой перегруженную оболочку для [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa).  
  
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
 См. в разделе [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa) сведения.  
  
 
  

## <a name="fileexists"></a> ATLPath::FileExists
 Эта функция представляет собой перегруженную оболочку для [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL FileExists(const char* pszPath);  
inline BOOL FileExists(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa) сведения.  
  
 
  

## <a name="findextension"></a> ATLPath::FindExtension
 Эта функция представляет собой перегруженную оболочку для [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* FindExtension(const char* pszPath);  
inline wchar_t* FindExtension(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona) сведения.  
  
 
  

## <a name="findfilename"></a> ATLPath::FindFileName
 Эта функция представляет собой перегруженную оболочку для [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* FindFileName(const char* pszPath);  
inline wchar_t* FindFileName(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) сведения.  
  
 
  

## <a name="getdrivenumber"></a> ATLPath::GetDriveNumber  
 Эта функция представляет собой перегруженную оболочку для [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline int GetDriveNumber(const char* pszPath);  
inline int GetDriveNumber(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera) сведения.  
  
 


## <a name="isdirectory"></a>  ATLPath::IsDirectory 
Эта функция представляет собой перегруженную оболочку для [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya).

```  
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```  
### <a name="remarks"></a>Примечания
Дополнительные сведения см. PathIsDirectory.  

## <a name="isfilespec"></a> ATLPath::IsFileSpec
 Эта функция представляет собой перегруженную оболочку для [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsFileSpec(const char* pszPath);  
inline BOOL IsFileSpec(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca) сведения.  
  
 
  

## <a name="isprefix"></a> ATLPath::IsPrefix
 Эта функция представляет собой перегруженную оболочку для [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);  
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa) сведения.  
  
 
  

## <a name="isrelative"></a> ATLPath::IsRelative
 Эта функция представляет собой перегруженную оболочку для [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsRelative(const char* pszPath);  
inline BOOL IsRelative(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea) сведения.  
  
 
  

## <a name="isroot"></a> ATLPath::IsRoot
 Эта функция представляет собой перегруженную оболочку для [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsRoot(const char* pszPath);  
inline BOOL IsRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota) сведения.  
  
 
  

## <a name="issameroot"></a> ATLPath::IsSameRoot
 Эта функция представляет собой перегруженную оболочку для [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);  
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota) сведения.  
  
 
  

## <a name="isunc"></a> ATLPath::IsUNC
 Эта функция представляет собой перегруженную оболочку для [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsUNC(const char* pszPath);  
inline BOOL IsUNC(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca) сведения.  
  
 
  

## <a name="isuncserver"></a> ATLPath::IsUNCServer
 Эта функция представляет собой перегруженную оболочку для [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsUNCServer(const char* pszPath);  
inline BOOL IsUNCServer(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera) сведения.  
  
 
  

## <a name="isuncservershare"></a> ATLPath::IsUNCServerShare
 Эта функция представляет собой перегруженную оболочку для [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsUNCServerShare(const char* pszPath);  
inline BOOL IsUNCServerShare(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea) сведения.  
  
 
  

## <a name="makepretty"></a> ATLPath::MakePretty
 Эта функция представляет собой перегруженную оболочку для [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL MakePretty(char* pszPath);  
inline BOOL MakePretty(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya) сведения.  
  
 
  

## <a name="matchspec"></a> ATLPath::MatchSpec  
 Эта функция представляет собой перегруженную оболочку для [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);  
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca) сведения.  
  
 
  

## <a name="quotespaces"></a> ATLPath::QuoteSpaces  
 Эта функция представляет собой перегруженную оболочку для [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void QuoteSpaces(char* pszPath);  
inline void QuoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa) сведения.  
  
 
  

## <a name="relativepathto"></a> ATLPath::RelativePathTo
 Эта функция представляет собой перегруженную оболочку для [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).  
  
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
 См. в разделе [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa) сведения.  
  
 
  

## <a name="removeargs"></a> ATLPath::RemoveArgs  
 Эта функция представляет собой перегруженную оболочку для [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void RemoveArgs(char* pszPath);  
inline void RemoveArgs(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa) сведения.  
  
 
  

## <a name="removebackslash"></a> ATLPath::RemoveBackslash
 Эта функция представляет собой перегруженную оболочку для [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* RemoveBackslash(char* pszPath);  
inline wchar_t* RemoveBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha) сведения.  
  
 
  

## <a name="removeblanks"></a> ATLPath::RemoveBlanks
 Эта функция представляет собой перегруженную оболочку для [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void RemoveBlanks(char* pszPath);  
inline void RemoveBlanks(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa) сведения.  
  
 
  

## <a name="removeextension"></a> ATLPath::RemoveExtension
 Эта функция представляет собой перегруженную оболочку для [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void RemoveExtension(char* pszPath);  
inline void RemoveExtension(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona) сведения.  
  
 
  

## <a name="removefilespec"></a> ATLPath::RemoveFileSpec
 Эта функция представляет собой перегруженную оболочку для [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL RemoveFileSpec(char* pszPath);  
inline BOOL RemoveFileSpec(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca) сведения.  
  
 
  

## <a name="renameextension"></a> ATLPath::RenameExtension
 Эта функция представляет собой перегруженную оболочку для [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL RenameExtension(char* pszPath, const char* pszExt);  
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona) сведения.  
  
 
  

## <a name="skiproot"></a> ATLPath::SkipRoot
 Эта функция представляет собой перегруженную оболочку для [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* SkipRoot(const char* pszPath);  
inline wchar_t* SkipRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota) сведения.  
  
 
  

## <a name="strippath"></a> ATLPath::StripPath
 Эта функция представляет собой перегруженную оболочку для [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void StripPath(char* pszPath);  
inline void StripPath(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha) сведения.  
  
 
  


## <a name="striptoroot"></a> ATLPath::StripToRoot
 Эта функция представляет собой перегруженную оболочку для [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL StripToRoot(char* pszPath);  
inline BOOL StripToRoot(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota) сведения.  
  
 
  

## <a name="unquotespaces"></a> ATLPath::UnquoteSpaces
 Эта функция представляет собой перегруженную оболочку для [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void UnquoteSpaces(char* pszPath);  
inline void UnquoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa) сведения.  
  
 
  
 
