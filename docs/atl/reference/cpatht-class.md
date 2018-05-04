---
title: Класс CPathT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CPathT
- ATLPATH/ATL::CPathT
- ATLPATH/ATL::CPathT::PCXSTR
- ATLPATH/ATL::CPathT::PXSTR
- ATLPATH/ATL::CPathT::XCHAR
- ATLPATH/ATL::CPathT::CPathT
- ATLPATH/ATL::CPathT::AddBackslash
- ATLPATH/ATL::CPathT::AddExtension
- ATLPATH/ATL::CPathT::Append
- ATLPATH/ATL::CPathT::BuildRoot
- ATLPATH/ATL::CPathT::Canonicalize
- ATLPATH/ATL::CPathT::Combine
- ATLPATH/ATL::CPathT::CommonPrefix
- ATLPATH/ATL::CPathT::CompactPath
- ATLPATH/ATL::CPathT::CompactPathEx
- ATLPATH/ATL::CPathT::FileExists
- ATLPATH/ATL::CPathT::FindExtension
- ATLPATH/ATL::CPathT::FindFileName
- ATLPATH/ATL::CPathT::GetDriveNumber
- ATLPATH/ATL::CPathT::GetExtension
- ATLPATH/ATL::CPathT::IsDirectory
- ATLPATH/ATL::CPathT::IsFileSpec
- ATLPATH/ATL::CPathT::IsPrefix
- ATLPATH/ATL::CPathT::IsRelative
- ATLPATH/ATL::CPathT::IsRoot
- ATLPATH/ATL::CPathT::IsSameRoot
- ATLPATH/ATL::CPathT::IsUNC
- ATLPATH/ATL::CPathT::IsUNCServer
- ATLPATH/ATL::CPathT::IsUNCServerShare
- ATLPATH/ATL::CPathT::MakePretty
- ATLPATH/ATL::CPathT::MatchSpec
- ATLPATH/ATL::CPathT::QuoteSpaces
- ATLPATH/ATL::CPathT::RelativePathTo
- ATLPATH/ATL::CPathT::RemoveArgs
- ATLPATH/ATL::CPathT::RemoveBackslash
- ATLPATH/ATL::CPathT::RemoveBlanks
- ATLPATH/ATL::CPathT::RemoveExtension
- ATLPATH/ATL::CPathT::RemoveFileSpec
- ATLPATH/ATL::CPathT::RenameExtension
- ATLPATH/ATL::CPathT::SkipRoot
- ATLPATH/ATL::CPathT::StripPath
- ATLPATH/ATL::CPathT::StripToRoot
- ATLPATH/ATL::CPathT::UnquoteSpaces
- ATLPATH/ATL::CPathT::m_strPath
dev_langs:
- C++
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37f669ddc7912f45222d52f10311ff70110e170f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cpatht-class"></a>Класс CPathT
Этот класс представляет путь.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename StringType>
class CPathT
```  
  
#### <a name="parameters"></a>Параметры  
 `StringType`  
 Класс string ATL и MFC для пути (в разделе [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)).  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPathT::PCXSTR](#pcxstr)|Тип постоянной строки.|  
|[CPathT::PXSTR](#pxstr)|Тип строки.|  
|[CPathT::XCHAR](#xchar)|Тип символа.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPathT::CPathT](#cpatht)|Конструктор для пути.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPathT::AddBackslash](#addbackslash)|Этот метод служит для добавления обратной косой черты до конца строки для создания правильного синтаксиса для пути.|  
|[CPathT::AddExtension](#addextension)|Вызовите этот метод, чтобы добавить расширение файла с путем.|  
|[CPathT::Append](#append)|Вызовите этот метод, чтобы добавить строку к текущему пути.|  
|[CPathT::BuildRoot](#buildroot)|Этот метод используется для создания корневого пути из нескольких заданного диска.|  
|[CPathT::Canonicalize](#canonicalize)|Этот метод вызывается для преобразования пути в каноническую форму.|  
|[CPathT::Combine](#combine)|Этот метод используется для сцепления строку, представляющую имя каталога и строка, представляющая путь файла в один путь.|  
|[CPathT::CommonPrefix](#commonprefix)|Этот метод используется для определения, имеет ли указанный путь общего префикса с текущего пути.|  
|[CPathT::CompactPath](#compactpath)|Этот метод используется для усечения путь к файлу в соответствии с размерами ширину данного точек, заменив компоненты пути с многоточием.|  
|[CPathT::CompactPathEx](#compactpathex)|Этот метод используется для усечения путь к файлу в соответствии с размерами заданного числа знаков, заменив компоненты пути с многоточием.|  
|[CPathT::FileExists](#fileexists)|Вызовите этот метод, чтобы проверить, существует ли файл в этот путь.|  
|[CPathT::FindExtension](#findextension)|Вызовите этот метод, чтобы определить позицию расширение файла в пути.|  
|[CPathT::FindFileName](#findfilename)|Вызовите этот метод, чтобы определить позицию имени файла в пути.|  
|[CPathT::GetDriveNumber](#getdrivenumber)|Вызовите этот метод для поиска по пути для букву диска в диапазоне от «A» до «Z» и возвращает соответствующий номер диска.|  
|[CPathT::GetExtension](#getextension)|Этот метод используется для получения расширения файла из пути.|  
|[CPathT::IsDirectory](#isdirectory)|Этот метод вызывается для проверки, является ли путь является допустимым каталогом.|  
|[CPathT::IsFileSpec](#isfilespec)|Вызовите этот метод для поиска по пути для символы разделителя пути (например, ":" или "\\"). Если не используются никакие символы разделителя пути отсутствует, путь считается путь спецификация файла.|  
|[CPathT::IsPrefix](#isprefix)|Вызовите этот метод, чтобы определить, содержит ли путь допустимый префикс типа, передаваемый по `pszPrefix`.|  
|[CPathT::IsRelative](#isrelative)|Этот метод используется для определения, если путь является относительным.|  
|[CPathT::IsRoot](#isroot)|Вызовите этот метод, чтобы определить, является ли путь корневого каталога.|  
|[CPathT::IsSameRoot](#issameroot)|Вызовите этот метод, чтобы определить, имеет ли другой путь общий корневой компонент с текущего пути.|  
|[CPathT::IsUNC](#isunc)|Вызовите этот метод, чтобы определить, является ли путь допустимый путь UNC (соглашения об универсальных именах) для сервера и совместно использовать.|  
|[CPathT::IsUNCServer](#isuncserver)|Вызовите этот метод, чтобы определить, является ли путь для сервера только допустимый путь UNC (соглашения об универсальных именах).|  
|[CPathT::IsUNCServerShare](#isuncservershare)|Вызовите этот метод, чтобы определить, является ли путь допустимый путь общего ресурса UNC (соглашения об универсальных именах), \\ \  *сервера*\ *совместное использование*.|  
|[CPathT::MakePretty](#makepretty)|Этот метод используется для преобразования всех символов нижнего регистра, чтобы предоставить путь согласованного внешнего вида пути.|  
|[CPathT::MatchSpec](#matchspec)|Вызовите этот метод для поиска по пути для строка, содержащая тип совпадения подстановочный знак.|  
|[CPathT::QuoteSpaces](#quotespaces)|Вызовите этот метод, чтобы заключить путь в кавычки, если он содержит пробелы.|  
|[CPathT::RelativePathTo](#relativepathto)|Этот метод используется для создания относительный путь из одного файла или папки в другую.|  
|[CPathT::RemoveArgs](#removeargs)|Вызовите этот метод, чтобы удалить все аргументы командной строки из пути.|  
|[CPathT::RemoveBackslash](#removebackslash)|Этот метод используется для удаления из пути обратную косую черту.|  
|[CPathT::RemoveBlanks](#removeblanks)|Вызовите этот метод, чтобы удалить все начальные и конечные пробелы из пути.|  
|[CPathT::RemoveExtension](#removeextension)|Вызовите этот метод, чтобы удалить расширение файла из пути, если таковой имеется.|  
|[CPathT::RemoveFileSpec](#removefilespec)|Этот метод для удаления конечные имя файла и обратную косую черту из пути, если они указаны.|  
|[CPathT::RenameExtension](#renameextension)|Этот метод используется для замены нового расширения расширение имени файла в пути. Если имя файла не содержит расширения, расширения будут присоединены до конца строки.|  
|[CPathT::SkipRoot](#skiproot)|Вызовите этот метод для синтаксического анализа пути, игнорирование букву диска или части пути UNC общий ресурс сервера.|  
|[CPathT::StripPath](#strippath)|Вызовите этот метод, чтобы удалить часть пути полный путь и имя файла.|  
|[CPathT::StripToRoot](#striptoroot)|Этот метод используется для удаления всех составляющих Кроме сведений о корневой путь.|  
|[CPathT::UnquoteSpaces](#unquotespaces)|Этот метод используется для удаления кавычки в начале и конце пути.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPathT::operator const StringType &](#operator_const_stringtype_amp)|Этот оператор позволяет объекту рассматриваться как строка.|  
|[CPathT::operator CPathT::PCXSTR](#operator_cpatht__pcxstr)|Этот оператор позволяет объекту рассматриваться как строка.|  
|[CPathT::operator StringType &](#operator_stringtype)|Этот оператор позволяет объекту рассматриваться как строка.|  
|[CPathT::operator +=](#operator_add_eq)|Этот оператор добавляет строку к пути.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPathT::m_strPath](#m_strpath)|Путь.|  
  
## <a name="remarks"></a>Примечания  
 `CPath`, `CPathA`, и `CPathW` являются экземпляров `CPathT` определяются следующим образом:  
  
 `typedef CPathT< CString > CPath;`  
  
 `typedef CPathT< CStringA > CPathA;`  
  
 `typedef CPathT< CStringW > CPathW;`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlpath.h  
  
##  <a name="addbackslash"></a>  CPathT::AddBackslash  
 Этот метод служит для добавления обратной косой черты до конца строки для создания правильного синтаксиса для пути. Если путь уже содержит обратную косую черту, будет добавлен без обратной косой черты.  
  
```
void AddBackslash();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathAddBackSlash](http://msdn.microsoft.com/library/windows/desktop/bb773561).  
  
##  <a name="addextension"></a>  CPathT::AddExtension  
 Вызовите этот метод, чтобы добавить расширение файла с путем.  
  
```
BOOL AddExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>Параметры  
 `pszExtension`  
 Чтобы добавить расширение файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).  
  
##  <a name="append"></a>  CPathT::Append  
 Вызовите этот метод, чтобы добавить строку к текущему пути.  
  
```
BOOL Append(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>Параметры  
 `pszMore`  
 Добавляемая строка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).  
  
##  <a name="buildroot"></a>  CPathT::BuildRoot  
 Этот метод используется для создания корневого пути из нескольких заданного диска.  
  
```
void BuildRoot(int iDrive);
```  
  
### <a name="parameters"></a>Параметры  
 *iDrive*  
 Номер диска (0 — ответ, 1 — б. и т. д.).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).  
  
##  <a name="canonicalize"></a>  CPathT::Canonicalize  
 Этот метод вызывается для преобразования пути в каноническую форму.  
  
```
void Canonicalize();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).  
  
##  <a name="combine"></a>  CPathT::Combine  
 Этот метод используется для сцепления строку, представляющую имя каталога и строка, представляющая путь файла в один путь.  
  
```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```  
  
### <a name="parameters"></a>Параметры  
 `pszDir`  
 Путь к каталогу.  
  
 *pszFile*  
 Путь к файлу.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571).  
  
##  <a name="commonprefix"></a>  CPathT::CommonPrefix  
 Этот метод используется для определения, имеет ли указанный путь общего префикса с текущего пути.  
  
```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```  
  
### <a name="parameters"></a>Параметры  
 `pszOther`  
 Путь для сравнения с текущей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает общий префикс.  
  
### <a name="remarks"></a>Примечания  
 Префикс — один из этих типов: «C:\\\\«,». «,».. «,».. \\\\". Дополнительные сведения см. в разделе [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).  
  
##  <a name="compactpath"></a>  CPathT::CompactPath  
 Этот метод используется для усечения путь к файлу в соответствии с размерами ширину данного точек, заменив компоненты пути с многоточием.  
  
```
BOOL CompactPath(HDC hDC, UINT nWidth);
```  
  
### <a name="parameters"></a>Параметры  
 `hDC`  
 Контекст устройства, используемый для метрики шрифтов.  
  
 `nWidth`  
 Ширина в пикселях, будут вынуждены помещается в строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).  
  
##  <a name="compactpathex"></a>  CPathT::CompactPathEx  
 Этот метод используется для усечения путь к файлу в соответствии с размерами заданного числа знаков, заменив компоненты пути с многоточием.  
  
```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nMaxChars`  
 Максимальное число символов, которые должны содержаться в новую строку, включая завершающий символ NULL.  
  
 `dwFlags`  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).  
  
##  <a name="cpatht"></a>  CPathT::CPathT  
 Конструктор.  
  
```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pszPath*  
 Указатель на строку пути.  
  
 *path*  
 Строка пути.  
  
##  <a name="fileexists"></a>  CPathT::FileExists  
 Вызовите этот метод, чтобы проверить, существует ли файл в этот путь.  
  
```
BOOL FileExists() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если файл существует, или FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).  
  
##  <a name="findextension"></a>  CPathT::FindExtension  
 Вызовите этот метод, чтобы определить позицию расширение файла в пути.  
  
```
int FindExtension() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию «.» перед расширением. Не найдено, возвращается значение -1.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).  
  
##  <a name="findfilename"></a>  CPathT::FindFileName  
 Вызовите этот метод, чтобы определить позицию имени файла в пути.  
  
```
int FindFileName() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию имени файла. Имя файла не найден, возвращается значение -1.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).  
  
##  <a name="getdrivenumber"></a>  CPathT::GetDriveNumber  
 Вызовите этот метод для поиска по пути для букву диска в диапазоне от «A» до «Z» и возвращает соответствующий номер диска.  
  
```
int GetDriveNumber() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает номер диска как целое число от 0 до 25 (соответствующий на «A» до «Z»), если путь содержит букву диска или -1, в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).  
  
##  <a name="getextension"></a>  CPathT::GetExtension  
 Этот метод используется для получения расширения файла из пути.  
  
```
StringType GetExtension() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает расширение файла.  
  
##  <a name="isdirectory"></a>  CPathT::IsDirectory  
 Этот метод вызывается для проверки, является ли путь является допустимым каталогом.  
  
```
BOOL IsDirectory() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение (16), если путь является каталогом, `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621).  
  
##  <a name="isfilespec"></a>  CPathT::IsFileSpec  
 Вызовите этот метод для поиска по пути для символы разделителя пути (например, ":" или "\\"). Если не используются никакие символы разделителя пути отсутствует, путь считается путь спецификация файла.  
  
```
BOOL IsFileSpec() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если доступных символов нет разделителя пути в пути, и значение FALSE, если символы разделителя пути.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).  
  
##  <a name="isprefix"></a>  CPathT::IsPrefix  
 Вызовите этот метод, чтобы определить, содержит ли путь допустимый префикс типа, передаваемый по `pszPrefix`.  
  
```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pszPrefix`  
 Префикс, который требуется найти. Префикс — один из этих типов: «C:\\\\«,». «,».. «,».. \\\\".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если путь содержит префикс, или значение FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).  
  
##  <a name="isrelative"></a>  CPathT::IsRelative  
 Этот метод используется для определения, если путь является относительным.  
  
```
BOOL IsRelative() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если путь является относительным, или FALSE, если он является абсолютным.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).  
  
##  <a name="isroot"></a>  CPathT::IsRoot  
 Вызовите этот метод, чтобы определить, является ли путь корневого каталога.  
  
```
BOOL IsRoot() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если путь является корневой, или значение FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).  
  
##  <a name="issameroot"></a>  CPathT::IsSameRoot  
 Вызовите этот метод, чтобы определить, имеет ли другой путь общий корневой компонент с текущего пути.  
  
```
BOOL IsSameRoot(PCXSTR pszOther) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pszOther`  
 Путь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если обе строки имеют одинаковые корневой компонент, или значение FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).  
  
##  <a name="isunc"></a>  CPathT::IsUNC  
 Вызовите этот метод, чтобы определить, является ли путь допустимый путь UNC (соглашения об универсальных именах) для сервера и совместно использовать.  
  
```
BOOL IsUNC() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если путь является допустимым UNC-путь, или значение FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712).  
  
##  <a name="isuncserver"></a>  CPathT::IsUNCServer  
 Вызовите этот метод, чтобы определить, является ли путь для сервера только допустимый путь UNC (соглашения об универсальных именах).  
  
```
BOOL IsUNCServer() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если строка является допустимый UNC-путь к серверу только (нет имени общего ресурса), или FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).  
  
##  <a name="isuncservershare"></a>  CPathT::IsUNCServerShare  
 Вызовите этот метод, чтобы определить, является ли путь допустимый путь общего ресурса UNC (соглашения об универсальных именах), \\ \  *сервера*\ *совместное использование*.  
  
```
BOOL IsUNCServerShare() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если путь в виде \\ \  *сервера*\ *совместное использование*, или FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).  
  
##  <a name="m_strpath"></a>  CPathT::m_strPath  
 Путь.  
  
```
StringType m_strPath;
```  
  
### <a name="remarks"></a>Примечания  
 `StringType` — параметр шаблона для `CPathT`.  
  
##  <a name="makepretty"></a>  CPathT::MakePretty  
 Этот метод используется для преобразования всех символов нижнего регистра, чтобы предоставить путь согласованного внешнего вида пути.  
  
```
BOOL MakePretty();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В противном случае возвращает значение TRUE, если путь был преобразован, или значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).  
  
##  <a name="matchspec"></a>  CPathT::MatchSpec  
 Вызовите этот метод для поиска по пути для строка, содержащая тип совпадения подстановочный знак.  
  
```
BOOL MatchSpec(PCXSTR pszSpec) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pszSpec`  
 Указатель на строку, завершающуюся значением null с типом файла, который требуется найти. Например, чтобы проверить, является ли файл по пути текущего DOC-файл `pszSpec` должен иметь значение «* .doc».  
  
### <a name="return-value"></a>Возвращаемое значение  
 В противном случае возвращает значение TRUE, если строка соответствует или FALSE.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).  
  
##  <a name="operator_add_eq"></a>  CPathT::operator +=  
 Этот оператор добавляет строку к пути.  
  
```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>Параметры  
 `pszMore`  
 Добавляемая строка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный путь.  
  
##  <a name="operator_const_stringtype_amp"></a>  CPathT::operator const StringType &amp;  
 Этот оператор позволяет объекту рассматриваться как строка.  
  
```
 operatorconst StringType&() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает строку, представляющую текущий путь, управляемых этим объектом.  
  
##  <a name="operator_cpatht__pcxstr"></a>  CPathT::operator CPathT::PCXSTR  
 Этот оператор позволяет объекту рассматриваться как строка.  
  
```
 operatorPCXSTR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает строку, представляющую текущий путь, управляемых этим объектом.  
  
##  <a name="operator_stringtype__amp"></a>  CPathT::operator StringType &amp;  
 Этот оператор позволяет объекту рассматриваться как строка.  
  
```
 operatorStringType&() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает строку, представляющую текущий путь, управляемых этим объектом.  
  
##  <a name="pcxstr"></a>  CPathT::PCXSTR  
 Тип постоянной строки.  
  
```
typedef StringType::PCXSTR PCXSTR;
```  
  
### <a name="remarks"></a>Примечания  
 `StringType` — параметр шаблона для `CPathT`.  
  
##  <a name="pxstr"></a>  CPathT::PXSTR  
 Тип строки.  
  
```
typedef StringType::PXSTR PXSTR;
```  
  
### <a name="remarks"></a>Примечания  
 `StringType` — параметр шаблона для `CPathT`.  
  
##  <a name="quotespaces"></a>  CPathT::QuoteSpaces  
 Вызовите этот метод, чтобы заключить путь в кавычки, если он содержит пробелы.  
  
```
void QuoteSpaces();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).  
  
##  <a name="relativepathto"></a>  CPathT::RelativePathTo  
 Этот метод используется для создания относительный путь из одного файла или папки в другую.  
  
```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```  
  
### <a name="parameters"></a>Параметры  
 `pszFrom`  
 Начало относительного пути.  
  
 *dwAttrFrom*  
 Атрибуты файла `pszFrom`. Если это значение содержит FILE_ATTRIBUTE_DIRECTORY, `pszFrom` принятой является каталогом; в противном случае — `pszFrom` считается файла.  
  
 `pszTo`  
 Конечная точка относительного пути.  
  
 *dwAttrTo*  
 Атрибуты файла `pszTo`. Если это значение содержит FILE_ATTRIBUTE_DIRECTORY, `pszTo` принятой является каталогом; в противном случае — `pszTo` считается файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).  
  
##  <a name="removeargs"></a>  CPathT::RemoveArgs  
 Вызовите этот метод, чтобы удалить все аргументы командной строки из пути.  
  
```
void RemoveArgs();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).  
  
##  <a name="removebackslash"></a>  CPathT::RemoveBackslash  
 Этот метод используется для удаления из пути обратную косую черту.  
  
```
void RemoveBackslash();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).  
  
##  <a name="removeblanks"></a>  CPathT::RemoveBlanks  
 Вызовите этот метод, чтобы удалить все начальные и конечные пробелы из пути.  
  
```
void RemoveBlanks();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).  
  
##  <a name="removeextension"></a>  CPathT::RemoveExtension  
 Вызовите этот метод, чтобы удалить расширение файла из пути, если таковой имеется.  
  
```
void RemoveExtension();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).  
  
##  <a name="removefilespec"></a>  CPathT::RemoveFileSpec  
 Этот метод для удаления конечные имя файла и обратную косую черту из пути, если они указаны.  
  
```
BOOL RemoveFileSpec();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).  
  
##  <a name="renameextension"></a>  CPathT::RenameExtension  
 Этот метод используется для замены нового расширения расширение имени файла в пути. Если имя файла не содержит расширения, расширения будут присоединены в конце пути.  
  
```
BOOL RenameExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>Параметры  
 `pszExtension`  
 Предшествует новое расширение имени файла «.» символов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).  
  
##  <a name="skiproot"></a>  CPathT::SkipRoot  
 Вызовите этот метод для синтаксического анализа пути, игнорирование букву диска или части пути UNC (соглашения об универсальных именах) общий ресурс сервера.  
  
```
int SkipRoot() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию начала вложенного пути после корневого (буква диска или папка сервера UNC).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).  
  
##  <a name="strippath"></a>  CPathT::StripPath  
 Вызовите этот метод, чтобы удалить часть пути полный путь и имя файла.  
  
```
void StripPath();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).  
  
##  <a name="striptoroot"></a>  CPathT::StripToRoot  
 Этот метод используется для удаления всех составляющих Кроме сведений о корневой путь.  
  
```
BOOL StripToRoot();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает TRUE, если буква диска был найден в пути, и FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).  
  
##  <a name="unquotespaces"></a>  CPathT::UnquoteSpaces  
 Этот метод используется для удаления кавычки в начале и конце пути.  
  
```
void UnquoteSpaces();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).  
  
##  <a name="xchar"></a>  CPathT::XCHAR  
 Тип символа.  
  
```
typedef StringType::XCHAR XCHAR;
```  
  
### <a name="remarks"></a>Примечания  
 `StringType` — параметр шаблона для `CPathT`.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../atl/reference/atl-classes.md)   
 [Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)