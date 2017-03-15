---
title: "Класс CPathT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CPathT
- CPathT
- ATL::CPathT<StringType>
- ATL::CPathT
- ATL.CPathT<StringType>
dev_langs:
- C++
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8cbd91ae1c4318788b38b2daaa7721d1a29fca98
ms.lasthandoff: 02/24/2017

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
 Класс string ATL и MFC для пути (см. [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)).  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPathT::PCXSTR](#pcxstr)|Константа строковый тип.|  
|[CPathT::PXSTR](#pxstr)|Тип string.|  
|[CPathT::XCHAR](#xchar)|Тип символа.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPathT::CPathT](#cpatht)|Конструктор для пути.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPathT::AddBackslash](#addbackslash)|Этот метод используется для добавления в конец строки для создания правильного синтаксиса пути обратную косую черту.|  
|[CPathT::AddExtension](#addextension)|Этот метод можно добавить расширение файла в пути.|  
|[CPathT::Append](#append)|Вызовите этот метод, чтобы добавить строку к текущему пути.|  
|[CPathT::BuildRoot](#buildroot)|Этот метод используется для создания корневой путь из числа заданного диска.|  
|[CPathT::Canonicalize](#canonicalize)|Вызовите этот метод, чтобы преобразовать путь в канонической форме.|  
|[CPathT::Combine](#combine)|Этот метод используется для сцепления строка, представляющая имя каталога и строка, представляющая путь к файлу в один путь.|  
|[CPathT::CommonPrefix](#commonprefix)|Вызовите этот метод, чтобы определить, использует ли указанный путь общего префикса с текущего пути.|  
|[CPathT::CompactPath](#compactpath)|Этот метод используется для усечения путь к файлу в соответствии с размерами заданного пикселов, заменив компоненты контура эллипса.|  
|[CPathT::CompactPathEx](#compactpathex)|Этот метод используется для усечения путь к файлу в соответствии с размерами указанного числа символов, заменив компоненты контура эллипса.|  
|[CPathT::FileExists](#fileexists)|Вызовите этот метод, чтобы проверить, существует ли файл в этот путь.|  
|[CPathT::FindExtension](#findextension)|Этот метод используется для определения положения расширение файла в пути.|  
|[CPathT::FindFileName](#findfilename)|Вызовите этот метод, чтобы определить позицию имени файла в пути.|  
|[CPathT::GetDriveNumber](#getdrivenumber)|Этот метод вызывается для поиска пути для букву диска в диапазоне от «A» до «Z» и возвращают соответствующий номер диска.|  
|[CPathT::GetExtension](#getextension)|Этот метод используется для получения расширения файла из пути.|  
|[CPathT::IsDirectory](#isdirectory)|Этот метод вызывается для проверки, является ли путь является допустимым каталогом.|  
|[CPathT::IsFileSpec](#isfilespec)|Этот метод вызывается для поиска пути для любой путь разграничение символов (например, ":" или "\\"). Если не используются никакие символы выделение путь существует, путь считается путь файловой спецификации.|  
|[CPathT::IsPrefix](#isprefix)|Вызовите этот метод, чтобы определить, содержит ли путь допустимый префикс типа, переданного `pszPrefix`.|  
|[CPathT::IsRelative](#isrelative)|Этот метод вызывается для определения, если путь является относительным.|  
|[CPathT::IsRoot](#isroot)|Вызовите этот метод, чтобы определить, является ли путь корневого каталога.|  
|[CPathT::IsSameRoot](#issameroot)|Вызовите этот метод, чтобы определить, имеет ли другой путь общий корневой компонент с текущего пути.|  
|[CPathT::IsUNC](#isunc)|Вызовите этот метод, чтобы определить, является ли путь допустимый путь UNC (соглашения об универсальных именах) для сервера и совместно использовать.|  
|[CPathT::IsUNCServer](#isuncserver)|Вызовите этот метод, чтобы определить, является ли путь для сервера только допустимый путь UNC (универсальное правило именования).|  
|[CPathT::IsUNCServerShare](#isuncservershare)|Вызовите этот метод, чтобы определить, является ли путь допустимый путь общего ресурса UNC (соглашения об универсальных именах), \\ \  *сервера*\ *совместное использование*.|  
|[CPathT::MakePretty](#makepretty)|Этот метод используется для преобразования всех символов нижнего регистра, чтобы предоставить путь согласованного внешнего вида контура.|  
|[CPathT::MatchSpec](#matchspec)|Этот метод вызывается для поиска пути для строка, содержащая тип соответствия подстановочный знак.|  
|[CPathT::QuoteSpaces](#quotespaces)|Вызовите этот метод, чтобы заключить путь в кавычки, если он содержит пробелы.|  
|[CPathT::RelativePathTo](#relativepathto)|Этот метод используется для создания относительный путь из одного файла или папки в другую.|  
|[CPathT::RemoveArgs](#removeargs)|Вызовите этот метод, чтобы удалить все аргументы командной строки из пути.|  
|[CPathT::RemoveBackslash](#removebackslash)|Этот метод используется для удаления обратную косую черту в пути.|  
|[CPathT::RemoveBlanks](#removeblanks)|Вызовите этот метод, чтобы удалить все начальные и конечные пробелы из пути.|  
|[CPathT::RemoveExtension](#removeextension)|Вызовите этот метод, чтобы удалить расширение файла из пути, если он существует.|  
|[CPathT::RemoveFileSpec](#removefilespec)|Вызовите этот метод, чтобы удалить конечные имя файла и обратную косую черту из пути, при их наличии.|  
|[CPathT::RenameExtension](#renameextension)|Этот метод используется для замены нового расширения расширение имени файла в пути. Если имя файла не содержит расширения, расширение будет подключен к конца строки.|  
|[CPathT::SkipRoot](#skiproot)|Этот метод вызывается для синтаксического анализа пути, игнорируя букву диска или части пути UNC общий ресурс сервера.|  
|[CPathT::StripPath](#strippath)|Вызовите этот метод, чтобы удалить часть пути полный путь и имя файла.|  
|[CPathT::StripToRoot](#striptoroot)|Этот метод используется для удаления всех частей, за исключением сведений о корневом пути.|  
|[CPathT::UnquoteSpaces](#unquotespaces)|Этот метод вызывается для удаления кавычек в начале и конце пути.|  
  
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
  
##  <a name="a-nameaddbackslasha--cpathtaddbackslash"></a><a name="addbackslash"></a>CPathT::AddBackslash  
 Этот метод используется для добавления в конец строки для создания правильного синтаксиса пути обратную косую черту. Если путь уже содержит обратную косую черту, будут добавляться без обратной косой черты.  
  
```
void AddBackslash();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathAddBackSlash](http://msdn.microsoft.com/library/windows/desktop/bb773561).  
  
##  <a name="a-nameaddextensiona--cpathtaddextension"></a><a name="addextension"></a>CPathT::AddExtension  
 Этот метод можно добавить расширение файла в пути.  
  
```
BOOL AddExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>Параметры  
 `pszExtension`  
 Чтобы добавить расширение файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).  
  
##  <a name="a-nameappenda--cpathtappend"></a><a name="append"></a>CPathT::Append  
 Вызовите этот метод, чтобы добавить строку к текущему пути.  
  
```
BOOL Append(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>Параметры  
 `pszMore`  
 Добавляемая строка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).  
  
##  <a name="a-namebuildroota--cpathtbuildroot"></a><a name="buildroot"></a>CPathT::BuildRoot  
 Этот метод используется для создания корневой путь из числа заданного диска.  
  
```
void BuildRoot(int iDrive);
```  
  
### <a name="parameters"></a>Параметры  
 *iDrive*  
 Номер диска (0 — ответ, 1-б. и т. д.).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).  
  
##  <a name="a-namecanonicalizea--cpathtcanonicalize"></a><a name="canonicalize"></a>CPathT::Canonicalize  
 Вызовите этот метод, чтобы преобразовать путь в канонической форме.  
  
```
void Canonicalize();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).  
  
##  <a name="a-namecombinea--cpathtcombine"></a><a name="combine"></a>CPathT::Combine  
 Этот метод используется для сцепления строка, представляющая имя каталога и строка, представляющая путь к файлу в один путь.  
  
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
  
##  <a name="a-namecommonprefixa--cpathtcommonprefix"></a><a name="commonprefix"></a>CPathT::CommonPrefix  
 Вызовите этот метод, чтобы определить, использует ли указанный путь общего префикса с текущего пути.  
  
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
  
##  <a name="a-namecompactpatha--cpathtcompactpath"></a><a name="compactpath"></a>CPathT::CompactPath  
 Этот метод используется для усечения путь к файлу в соответствии с размерами заданного пикселов, заменив компоненты контура эллипса.  
  
```
BOOL CompactPath(HDC hDC, UINT nWidth);
```  
  
### <a name="parameters"></a>Параметры  
 `hDC`  
 Контекст устройства, используемый для метрики шрифтов.  
  
 `nWidth`  
 Ширина в пикселях, будут вынуждены помещается в строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).  
  
##  <a name="a-namecompactpathexa--cpathtcompactpathex"></a><a name="compactpathex"></a>CPathT::CompactPathEx  
 Этот метод используется для усечения путь к файлу в соответствии с размерами указанного числа символов, заменив компоненты контура эллипса.  
  
```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nMaxChars`  
 Максимальное число символов, содержащихся в новой строке, включая завершающий символ NULL.  
  
 `dwFlags`  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).  
  
##  <a name="a-namecpathta--cpathtcpatht"></a><a name="cpatht"></a>CPathT::CPathT  
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
  
##  <a name="a-namefileexistsa--cpathtfileexists"></a><a name="fileexists"></a>CPathT::FileExists  
 Вызовите этот метод, чтобы проверить, существует ли файл в этот путь.  
  
```
BOOL FileExists() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если файл существует, или FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).  
  
##  <a name="a-namefindextensiona--cpathtfindextension"></a><a name="findextension"></a>CPathT::FindExtension  
 Этот метод используется для определения положения расширение файла в пути.  
  
```
int FindExtension() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию «.» выше расширения. Если не найдено, возвращает значение -1.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).  
  
##  <a name="a-namefindfilenamea--cpathtfindfilename"></a><a name="findfilename"></a>CPathT::FindFileName  
 Вызовите этот метод, чтобы определить позицию имени файла в пути.  
  
```
int FindFileName() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию имени файла. Если имя файла не найдено, возвращает значение -1.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).  
  
##  <a name="a-namegetdrivenumbera--cpathtgetdrivenumber"></a><a name="getdrivenumber"></a>CPathT::GetDriveNumber  
 Этот метод вызывается для поиска пути для букву диска в диапазоне от «A» до «Z» и возвращают соответствующий номер диска.  
  
```
int GetDriveNumber() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает номер диска как целое число от 0 до 25 (соответствующий на «A» до «Z»), если путь содержит букву диска или -1, в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).  
  
##  <a name="a-namegetextensiona--cpathtgetextension"></a><a name="getextension"></a>CPathT::GetExtension  
 Этот метод используется для получения расширения файла из пути.  
  
```
StringType GetExtension() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает расширение файла.  
  
##  <a name="a-nameisdirectorya--cpathtisdirectory"></a><a name="isdirectory"></a>CPathT::IsDirectory  
 Этот метод вызывается для проверки, является ли путь является допустимым каталогом.  
  
```
BOOL IsDirectory() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение (16), если путь является каталогом, `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621).  
  
##  <a name="a-nameisfilespeca--cpathtisfilespec"></a><a name="isfilespec"></a>CPathT::IsFileSpec  
 Этот метод вызывается для поиска пути для любой путь разграничение символов (например, ":" или "\\"). Если не используются никакие символы выделение путь существует, путь считается путь файловой спецификации.  
  
```
BOOL IsFileSpec() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если нет символов, разделяющий путь в пути, и FALSE, если путь разграничение символов.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).  
  
##  <a name="a-nameisprefixa--cpathtisprefix"></a><a name="isprefix"></a>CPathT::IsPrefix  
 Вызовите этот метод, чтобы определить, содержит ли путь допустимый префикс типа, переданного `pszPrefix`.  
  
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
  
##  <a name="a-nameisrelativea--cpathtisrelative"></a><a name="isrelative"></a>CPathT::IsRelative  
 Этот метод вызывается для определения, если путь является относительным.  
  
```
BOOL IsRelative() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если путь является относительным, или значение FALSE, если это абсолютный.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).  
  
##  <a name="a-nameisroota--cpathtisroot"></a><a name="isroot"></a>CPathT::IsRoot  
 Вызовите этот метод, чтобы определить, является ли путь корневого каталога.  
  
```
BOOL IsRoot() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если путь корня или FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).  
  
##  <a name="a-nameissameroota--cpathtissameroot"></a><a name="issameroot"></a>CPathT::IsSameRoot  
 Вызовите этот метод, чтобы определить, имеет ли другой путь общий корневой компонент с текущего пути.  
  
```
BOOL IsSameRoot(PCXSTR pszOther) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pszOther`  
 Путь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если обе строки имеют одинаковые корневой компонент, или FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).  
  
##  <a name="a-nameisunca--cpathtisunc"></a><a name="isunc"></a>CPathT::IsUNC  
 Вызовите этот метод, чтобы определить, является ли путь допустимый путь UNC (соглашения об универсальных именах) для сервера и совместно использовать.  
  
```
BOOL IsUNC() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если путь является допустимым UNC-путем, или значение FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712).  
  
##  <a name="a-nameisuncservera--cpathtisuncserver"></a><a name="isuncserver"></a>CPathT::IsUNCServer  
 Вызовите этот метод, чтобы определить, является ли путь для сервера только допустимый путь UNC (универсальное правило именования).  
  
```
BOOL IsUNCServer() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если строка имеет допустимый UNC-путь для сервера только (нет имени общего ресурса), или FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).  
  
##  <a name="a-nameisuncserversharea--cpathtisuncservershare"></a><a name="isuncservershare"></a>CPathT::IsUNCServerShare  
 Вызовите этот метод, чтобы определить, является ли путь допустимый путь общего ресурса UNC (соглашения об универсальных именах), \\ \  *сервера*\ *совместное использование*.  
  
```
BOOL IsUNCServerShare() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если путь в форме \\ \  *сервера*\ *совместное использование*, или FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).  
  
##  <a name="a-namemstrpatha--cpathtmstrpath"></a><a name="m_strpath"></a>CPathT::m_strPath  
 Путь.  
  
```
StringType m_strPath;
```  
  
### <a name="remarks"></a>Примечания  
 `StringType`параметр шаблона является `CPathT`.  
  
##  <a name="a-namemakeprettya--cpathtmakepretty"></a><a name="makepretty"></a>CPathT::MakePretty  
 Этот метод используется для преобразования всех символов нижнего регистра, чтобы предоставить путь согласованного внешнего вида контура.  
  
```
BOOL MakePretty();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В противном случае возвращает значение TRUE, если путь был преобразован, или FALSE.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).  
  
##  <a name="a-namematchspeca--cpathtmatchspec"></a><a name="matchspec"></a>CPathT::MatchSpec  
 Этот метод вызывается для поиска пути для строка, содержащая тип соответствия подстановочный знак.  
  
```
BOOL MatchSpec(PCXSTR pszSpec) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pszSpec`  
 Указатель на строку, завершающуюся значением null с типом файла, который требуется найти. Например, чтобы проверить, является ли файл в текущем пути DOC-файл `pszSpec` должно быть присвоено значение «* .doc».  
  
### <a name="return-value"></a>Возвращаемое значение  
 В противном случае возвращает значение TRUE, если строка соответствует или FALSE.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).  
  
##  <a name="a-nameoperatoraddeqa--cpathtoperator-"></a><a name="operator_add_eq"></a>CPathT::operator +=  
 Этот оператор добавляет строку к пути.  
  
```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>Параметры  
 `pszMore`  
 Добавляемая строка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный путь.  
  
##  <a name="a-nameoperatorconststringtypeampa--cpathtoperator-const-stringtype-amp"></a><a name="operator_const_stringtype_amp"></a>CPathT::operator const StringType&amp;  
 Этот оператор позволяет объекту рассматриваться как строка.  
  
```
 operatorconst StringType&() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает строку, представляющую текущий путь, управляемых этим объектом.  
  
##  <a name="a-nameoperatorcpathtpcxstra--cpathtoperator-cpathtpcxstr"></a><a name="operator_cpatht__pcxstr"></a>CPathT::operator CPathT::PCXSTR  
 Этот оператор позволяет объекту рассматриваться как строка.  
  
```
 operatorPCXSTR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает строку, представляющую текущий путь, управляемых этим объектом.  
  
##  <a name="a-nameoperatorstringtypeampa--cpathtoperator-stringtype-amp"></a><a name="operator_stringtype__amp"></a>CPathT::operator StringType&amp;  
 Этот оператор позволяет объекту рассматриваться как строка.  
  
```
 operatorStringType&() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает строку, представляющую текущий путь, управляемых этим объектом.  
  
##  <a name="a-namepcxstra--cpathtpcxstr"></a><a name="pcxstr"></a>CPathT::PCXSTR  
 Константа строковый тип.  
  
```
typedef StringType::PCXSTR PCXSTR;
```  
  
### <a name="remarks"></a>Примечания  
 `StringType`параметр шаблона является `CPathT`.  
  
##  <a name="a-namepxstra--cpathtpxstr"></a><a name="pxstr"></a>CPathT::PXSTR  
 Тип string.  
  
```
typedef StringType::PXSTR PXSTR;
```  
  
### <a name="remarks"></a>Примечания  
 `StringType`параметр шаблона является `CPathT`.  
  
##  <a name="a-namequotespacesa--cpathtquotespaces"></a><a name="quotespaces"></a>CPathT::QuoteSpaces  
 Вызовите этот метод, чтобы заключить путь в кавычки, если он содержит пробелы.  
  
```
void QuoteSpaces();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).  
  
##  <a name="a-namerelativepathtoa--cpathtrelativepathto"></a><a name="relativepathto"></a>CPathT::RelativePathTo  
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
 Атрибуты файла `pszFrom`. Если это значение содержит FILE_ATTRIBUTE_DIRECTORY, `pszFrom` предполагается, что он является каталогом, в противном случае, `pszFrom` считается в файл.  
  
 `pszTo`  
 Конечная точка относительный путь.  
  
 *dwAttrTo*  
 Атрибуты файла `pszTo`. Если это значение содержит FILE_ATTRIBUTE_DIRECTORY, `pszTo` предполагается, что он является каталогом, в противном случае, `pszTo` считается в файл.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).  
  
##  <a name="a-nameremoveargsa--cpathtremoveargs"></a><a name="removeargs"></a>CPathT::RemoveArgs  
 Вызовите этот метод, чтобы удалить все аргументы командной строки из пути.  
  
```
void RemoveArgs();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).  
  
##  <a name="a-nameremovebackslasha--cpathtremovebackslash"></a><a name="removebackslash"></a>CPathT::RemoveBackslash  
 Этот метод используется для удаления обратную косую черту в пути.  
  
```
void RemoveBackslash();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).  
  
##  <a name="a-nameremoveblanksa--cpathtremoveblanks"></a><a name="removeblanks"></a>CPathT::RemoveBlanks  
 Вызовите этот метод, чтобы удалить все начальные и конечные пробелы из пути.  
  
```
void RemoveBlanks();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).  
  
##  <a name="a-nameremoveextensiona--cpathtremoveextension"></a><a name="removeextension"></a>CPathT::RemoveExtension  
 Вызовите этот метод, чтобы удалить расширение файла из пути, если он существует.  
  
```
void RemoveExtension();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).  
  
##  <a name="a-nameremovefilespeca--cpathtremovefilespec"></a><a name="removefilespec"></a>CPathT::RemoveFileSpec  
 Вызовите этот метод, чтобы удалить конечные имя файла и обратную косую черту из пути, при их наличии.  
  
```
BOOL RemoveFileSpec();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).  
  
##  <a name="a-namerenameextensiona--cpathtrenameextension"></a><a name="renameextension"></a>CPathT::RenameExtension  
 Этот метод используется для замены нового расширения расширение имени файла в пути. Если имя файла не содержит расширения, расширение будет подключен к пути.  
  
```
BOOL RenameExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>Параметры  
 `pszExtension`  
 Новое расширение имени файла, перед которым стоит «.» символов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).  
  
##  <a name="a-nameskiproota--cpathtskiproot"></a><a name="skiproot"></a>CPathT::SkipRoot  
 Этот метод вызывается для синтаксического анализа пути, игнорируя букву диска или части пути UNC (соглашения об универсальных именах) общий ресурс сервера.  
  
```
int SkipRoot() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию в начале вложенного пути, соответствует корню (букву диска или UNC-общий ресурс сервера).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).  
  
##  <a name="a-namestrippatha--cpathtstrippath"></a><a name="strippath"></a>CPathT::StripPath  
 Вызовите этот метод, чтобы удалить часть пути полный путь и имя файла.  
  
```
void StripPath();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).  
  
##  <a name="a-namestriptoroota--cpathtstriptoroot"></a><a name="striptoroot"></a>CPathT::StripToRoot  
 Этот метод используется для удаления всех частей, за исключением сведений о корневом пути.  
  
```
BOOL StripToRoot();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает TRUE, если буква диска был найден в пути, и FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).  
  
##  <a name="a-nameunquotespacesa--cpathtunquotespaces"></a><a name="unquotespaces"></a>CPathT::UnquoteSpaces  
 Этот метод вызывается для удаления кавычек в начале и конце пути.  
  
```
void UnquoteSpaces();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).  
  
##  <a name="a-namexchara--cpathtxchar"></a><a name="xchar"></a>CPathT::XCHAR  
 Тип символа.  
  
```
typedef StringType::XCHAR XCHAR;
```  
  
### <a name="remarks"></a>Примечания  
 `StringType`параметр шаблона является `CPathT`.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../atl/reference/atl-classes.md)   
 [Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)
