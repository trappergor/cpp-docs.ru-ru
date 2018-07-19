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
ms.openlocfilehash: ad0db4641731f4c92550fad075b759957383c52a
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027581"
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
|[ATLPath::AddBackslash](#addbackslash)|Эта функция представляет собой перегруженную оболочку для [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561).|  
|[ATLPath::AddExtension](#addextension)|Эта функция представляет собой перегруженную оболочку для [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).|  
|[ATLPath::Append](#append)|Эта функция представляет собой перегруженную оболочку для [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).|  
|[ATLPath::BuildRoot](#buildroot)|Эта функция представляет собой перегруженную оболочку для [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).|  
|[ATLPath::Canonicalize](#canonicalize)|Эта функция представляет собой перегруженную оболочку для [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).|  
|[ATLPath::Combine](#combine)|Эта функция представляет собой перегруженную оболочку для [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571).|  
|[ATLPath::CommonPrefix](#commonprefix)|Эта функция представляет собой перегруженную оболочку для [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).|  
|[ATLPath::CompactPath](#compactpath)|Эта функция представляет собой перегруженную оболочку для [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).|  
|[ATLPath::CompactPathEx](#compactpathex)|Эта функция представляет собой перегруженную оболочку для [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).|  
|[ATLPath::FileExists](#fileexists)|Эта функция представляет собой перегруженную оболочку для [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).|  
|[ATLPath::FindExtension](#findextension)|Эта функция представляет собой перегруженную оболочку для [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).|  
|[ATLPath::FindFileName](#findfilename)|Эта функция представляет собой перегруженную оболочку для [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).|  
|[ATLPath::GetDriveNumber](#getdrivenumber)|Эта функция представляет собой перегруженную оболочку для [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).|  
|[ATLPath::IsDirectory](#isdirectory)|Эта функция представляет собой перегруженную оболочку для [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621).|  
|[ATLPath::IsFileSpec](#isfilespec)|Эта функция представляет собой перегруженную оболочку для [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).|  
|[ATLPath::IsPrefix](#isprefix)|Эта функция представляет собой перегруженную оболочку для [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).|  
|[ATLPath::IsRelative](#isrelative)|Эта функция представляет собой перегруженную оболочку для [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).|  
|[ATLPath::IsRoot](#isroot)|Эта функция представляет собой перегруженную оболочку для [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).|  
|[ATLPath::IsSameRoot](#issameroot)|Эта функция представляет собой перегруженную оболочку для [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).|  
|[ATLPath::IsUNC](#isunc)|Эта функция представляет собой перегруженную оболочку для [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712).|  
|[ATLPath::IsUNCServer](#isuncserver)|Эта функция представляет собой перегруженную оболочку для [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).|  
|[ATLPath::IsUNCServerShare](#isuncservershare)|Эта функция представляет собой перегруженную оболочку для [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).|  
|[ATLPath::MakePretty](#makepretty)|Эта функция представляет собой перегруженную оболочку для [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).|  
|[ATLPath::MatchSpec](#matchspec)|Эта функция представляет собой перегруженную оболочку для [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).|  
|[ATLPath::QuoteSpaces](#quotespaces)|Эта функция представляет собой перегруженную оболочку для [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).|  
|[ATLPath::RelativePathTo](#relativepathto)|Эта функция представляет собой перегруженную оболочку для [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).|  
|[ATLPath::RemoveArgs](#removeargs)|Эта функция представляет собой перегруженную оболочку для [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).|  
|[ATLPath::RemoveBackslash](#removebackslash)|Эта функция представляет собой перегруженную оболочку для [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).|  
|[ATLPath::RemoveBlanks](#removeblanks)|Эта функция представляет собой перегруженную оболочку для [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).|  
|[ATLPath::RemoveExtension](#removeextension)|Эта функция представляет собой перегруженную оболочку для [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).|  
|[ATLPath::RemoveFileSpec](#removefilespec)|Эта функция представляет собой перегруженную оболочку для [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).|  
|[ATLPath::RenameExtension](#renameextension)|Эта функция представляет собой перегруженную оболочку для [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).|  
|[ATLPath::SkipRoot](#skiproot)|Эта функция представляет собой перегруженную оболочку для [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).|  
|[ATLPath::StripPath](#strippath)|Эта функция представляет собой перегруженную оболочку для [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).|  
|[ATLPath::StripToRoot](#striptoroot)|Эта функция представляет собой перегруженную оболочку для [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).|  
|[ATLPath::UnquoteSpaces](#unquotespaces)|Эта функция представляет собой перегруженную оболочку для [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlpath.h  

## <a name="addbackslash"></a> ATLPath::AddBackSlash

Эта функция представляет собой перегруженную оболочку для [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* AddBackslash(char* pszPath);  
inline wchar_t* AddBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561) сведения.  
  
 
  

## <a name="addextension"></a> ATLPath::AddExtension
 Эта функция представляет собой перегруженную оболочку для [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL AddExtension(char* pszPath, const char* pszExtension);  
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563) сведения. 
  
## <a name="append"></a> ATLPath::Append
 Эта функция представляет собой перегруженную оболочку для [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL Append(char* pszPath, const char* pszMore);  
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565) сведения.  
  
 
  

## <a name="buildroot"></a> ATLPath::BuildRoot
 Эта функция представляет собой перегруженную оболочку для [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* BuildRoot(char* pszPath, int iDrive);  
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567) сведения.  
  
 
  

## <a name="canonicalize"></a> ATLPath::Canonicalize
 Эта функция представляет собой перегруженную оболочку для [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);  
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569) сведения.  
  
 
  

## <a name="combine"></a> ATLPath::Combine 
Эта функция представляет собой перегруженную оболочку для [PathCombine](https://msdn.microsoft.com/library/windows/desktop/bb773571).  

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
 Эта функция представляет собой перегруженную оболочку для [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).  
  
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
 См. в разделе [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574) сведения.  
  
 
  

## <a name="compactpath"></a> ATLPath::CompactPath
 Эта функция представляет собой перегруженную оболочку для [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).  
  
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
 См. в разделе [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575) сведения.  
  
 
  

## <a name="compactpathex"></a> ATLPath::CompactPathEx
 Эта функция представляет собой перегруженную оболочку для [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).  
  
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
 См. в разделе [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578) сведения.  
  
 
  

## <a name="fileexists"></a> ATLPath::FileExists
 Эта функция представляет собой перегруженную оболочку для [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL FileExists(const char* pszPath);  
inline BOOL FileExists(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584) сведения.  
  
 
  

## <a name="findextension"></a> ATLPath::FindExtension
 Эта функция представляет собой перегруженную оболочку для [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* FindExtension(const char* pszPath);  
inline wchar_t* FindExtension(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587) сведения.  
  
 
  

## <a name="findfilename"></a> ATLPath::FindFileName
 Эта функция представляет собой перегруженную оболочку для [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* FindFileName(const char* pszPath);  
inline wchar_t* FindFileName(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) сведения.  
  
 
  

## <a name="getdrivenumber"></a> ATLPath::GetDriveNumber  
 Эта функция представляет собой перегруженную оболочку для [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline int GetDriveNumber(const char* pszPath);  
inline int GetDriveNumber(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612) сведения.  
  
 


## <a name="isdirectory"></a>  ATLPath::IsDirectory 
Эта функция представляет собой перегруженную оболочку для [PathIsDirectory](https://msdn.microsoft.com/library/windows/desktop/bb773621).

```  
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```  
### <a name="remarks"></a>Примечания
Дополнительные сведения см. PathIsDirectory.  

## <a name="isfilespec"></a> ATLPath::IsFileSpec
 Эта функция представляет собой перегруженную оболочку для [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsFileSpec(const char* pszPath);  
inline BOOL IsFileSpec(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627) сведения.  
  
 
  

## <a name="isprefix"></a> ATLPath::IsPrefix
 Эта функция представляет собой перегруженную оболочку для [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);  
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650) сведения.  
  
 
  

## <a name="isrelative"></a> ATLPath::IsRelative
 Эта функция представляет собой перегруженную оболочку для [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsRelative(const char* pszPath);  
inline BOOL IsRelative(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660) сведения.  
  
 
  

## <a name="isroot"></a> ATLPath::IsRoot
 Эта функция представляет собой перегруженную оболочку для [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsRoot(const char* pszPath);  
inline BOOL IsRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674) сведения.  
  
 
  

## <a name="issameroot"></a> ATLPath::IsSameRoot
 Эта функция представляет собой перегруженную оболочку для [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);  
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687) сведения.  
  
 
  

## <a name="isunc"></a> ATLPath::IsUNC
 Эта функция представляет собой перегруженную оболочку для [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsUNC(const char* pszPath);  
inline BOOL IsUNC(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712) сведения.  
  
 
  

## <a name="isuncserver"></a> ATLPath::IsUNCServer
 Эта функция представляет собой перегруженную оболочку для [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsUNCServer(const char* pszPath);  
inline BOOL IsUNCServer(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722) сведения.  
  
 
  

## <a name="isuncservershare"></a> ATLPath::IsUNCServerShare
 Эта функция представляет собой перегруженную оболочку для [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL IsUNCServerShare(const char* pszPath);  
inline BOOL IsUNCServerShare(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723) сведения.  
  
 
  

## <a name="makepretty"></a> ATLPath::MakePretty
 Эта функция представляет собой перегруженную оболочку для [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL MakePretty(char* pszPath);  
inline BOOL MakePretty(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725) сведения.  
  
 
  

## <a name="matchspec"></a> ATLPath::MatchSpec  
 Эта функция представляет собой перегруженную оболочку для [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);  
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727) сведения.  
  
 
  

## <a name="quotespaces"></a> ATLPath::QuoteSpaces  
 Эта функция представляет собой перегруженную оболочку для [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void QuoteSpaces(char* pszPath);  
inline void QuoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739) сведения.  
  
 
  

## <a name="relativepathto"></a> ATLPath::RelativePathTo
 Эта функция представляет собой перегруженную оболочку для [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).  
  
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
 См. в разделе [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740) сведения.  
  
 
  

## <a name="removeargs"></a> ATLPath::RemoveArgs  
 Эта функция представляет собой перегруженную оболочку для [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void RemoveArgs(char* pszPath);  
inline void RemoveArgs(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742) сведения.  
  
 
  

## <a name="removebackslash"></a> ATLPath::RemoveBackslash
 Эта функция представляет собой перегруженную оболочку для [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* RemoveBackslash(char* pszPath);  
inline wchar_t* RemoveBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743) сведения.  
  
 
  

## <a name="removeblanks"></a> ATLPath::RemoveBlanks
 Эта функция представляет собой перегруженную оболочку для [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void RemoveBlanks(char* pszPath);  
inline void RemoveBlanks(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745) сведения.  
  
 
  

## <a name="removeextension"></a> ATLPath::RemoveExtension
 Эта функция представляет собой перегруженную оболочку для [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void RemoveExtension(char* pszPath);  
inline void RemoveExtension(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746) сведения.  
  
 
  

## <a name="removefilespec"></a> ATLPath::RemoveFileSpec
 Эта функция представляет собой перегруженную оболочку для [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL RemoveFileSpec(char* pszPath);  
inline BOOL RemoveFileSpec(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748) сведения.  
  
 
  

## <a name="renameextension"></a> ATLPath::RenameExtension
 Эта функция представляет собой перегруженную оболочку для [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL RenameExtension(char* pszPath, const char* pszExt);  
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749) сведения.  
  
 
  

## <a name="skiproot"></a> ATLPath::SkipRoot
 Эта функция представляет собой перегруженную оболочку для [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline char* SkipRoot(const char* pszPath);  
inline wchar_t* SkipRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754) сведения.  
  
 
  

## <a name="strippath"></a> ATLPath::StripPath
 Эта функция представляет собой перегруженную оболочку для [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void StripPath(char* pszPath);  
inline void StripPath(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756) сведения.  
  
 
  


## <a name="striptoroot"></a> ATLPath::StripToRoot
 Эта функция представляет собой перегруженную оболочку для [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline BOOL StripToRoot(char* pszPath);  
inline BOOL StripToRoot(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757) сведения.  
  
 
  

## <a name="unquotespaces"></a> ATLPath::UnquoteSpaces
 Эта функция представляет собой перегруженную оболочку для [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
inline void UnquoteSpaces(char* pszPath);  
inline void UnquoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763) сведения.  
  
 
  
 
