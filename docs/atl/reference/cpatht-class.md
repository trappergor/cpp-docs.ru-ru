---
title: Класс CPathT
ms.date: 11/04/2016
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
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
ms.openlocfilehash: cf845d04c008e83d0e9851718c995036bc810b55
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449352"
---
# <a name="cpatht-class"></a>Класс CPathT

Этот класс представляет собой путь.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <typename StringType>
class CPathT
```

#### <a name="parameters"></a>Параметры

*StringType*<br/>
Класс string ATL и MFC для пути (см. в разделе [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)).

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CPathT::PCXSTR](#pcxstr)|Тип постоянной строки.|
|[CPathT::PXSTR](#pxstr)|Тип string.|
|[CPathT::XCHAR](#xchar)|Тип символа.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPathT::CPathT](#cpatht)|Конструктор для пути.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPathT::AddBackslash](#addbackslash)|Вызовите этот метод, чтобы добавить обратную косую черту в конец строки для создания правильного синтаксиса для пути.|
|[CPathT::AddExtension](#addextension)|Вызовите этот метод, чтобы добавить расширение файла в путь.|
|[CPathT::Append](#append)|Вызовите этот метод, чтобы добавить строку к текущему пути.|
|[CPathT::BuildRoot](#buildroot)|Вызовите этот метод, чтобы создать корневой путь из числа данного диска.|
|[CPathT::Canonicalize](#canonicalize)|Вызовите этот метод для преобразования пути в канонической форме.|
|[CPathT::Combine](#combine)|Этот метод используется для сцепления строка, представляющая имя каталога и строка, представляющая путь к файлу в один путь.|
|[CPathT::CommonPrefix](#commonprefix)|Вызовите этот метод, чтобы определить, использует ли указанный путь Общий префикс совместно с по текущему пути.|
|[CPathT::CompactPath](#compactpath)|Этот метод используется для усечения путь к файлу в соответствии с размерами ширину данного точек, заменив компоненты пути на кнопку с многоточием.|
|[CPathT::CompactPathEx](#compactpathex)|Этот метод используется для усечения путь к файлу в соответствии с размерами указанного числа символов, заменив компоненты пути на кнопку с многоточием.|
|[CPathT::FileExists](#fileexists)|Вызовите этот метод, чтобы проверить, существует ли файл в этот путь.|
|[CPathT::FindExtension](#findextension)|Вызовите этот метод, чтобы найти позицию расширение файла в пути.|
|[CPathT::FindFileName](#findfilename)|Вызовите этот метод, чтобы определить позицию имени файла в пути.|
|[CPathT::GetDriveNumber](#getdrivenumber)|Вызовите этот метод для поиска пути для букву диска в диапазоне от «A» до «Z» и возвращает соответствующий номер диска.|
|[CPathT::GetExtension](#getextension)|Этот метод используется для получения расширения файла из пути.|
|[CPathT::IsDirectory](#isdirectory)|Вызовите этот метод, чтобы проверить, является ли путь является допустимым каталогом.|
|[CPathT::IsFileSpec](#isfilespec)|Вызовите этот метод для поиска пути для любые символы, разделив их пути (например, ":" или "\\"). Если никакие символы разделителя пути присутствует, путь считается являться путем файловой спецификации.|
|[CPathT::IsPrefix](#isprefix)|Вызовите этот метод, чтобы определить, содержит ли путь допустимый префикс типа, передаваемый по *pszPrefix*.|
|[CPathT::IsRelative](#isrelative)|Этот метод используется для определения того, если путь является относительным.|
|[CPathT::IsRoot](#isroot)|Вызовите этот метод, чтобы определить, является ли путь корневом каталоге.|
|[CPathT::IsSameRoot](#issameroot)|Вызовите этот метод, чтобы определить, имеет ли другой путь общий корневой компонент с по текущему пути.|
|[CPathT::IsUNC](#isunc)|Вызовите этот метод, чтобы определить, является ли путь допустимым путем UNC (соглашения об универсальных именах) для сервера и совместного использования.|
|[CPathT::IsUNCServer](#isuncserver)|Вызовите этот метод, чтобы определить, является ли путь допустимым путем UNC (соглашения об универсальных именах) для сервера только.|
|[CPathT::IsUNCServerShare](#isuncservershare)|Вызовите этот метод, чтобы определить, является ли путь допустимым путем UNC (соглашения об универсальных именах) общий ресурс, \\ \  *server*\ *совместно использовать*.|
|[CPathT::MakePretty](#makepretty)|Этот метод используется для преобразования пути для всех символов нижнего регистра, чтобы предоставить путь согласованного внешнего вида.|
|[CPathT::MatchSpec](#matchspec)|Вызовите этот метод для поиска пути для строка, содержащая тип совпадения подстановочный знак.|
|[CPathT::QuoteSpaces](#quotespaces)|Вызовите этот метод, чтобы заключить путь в кавычки, если он содержит пробелы.|
|[CPathT::RelativePathTo](#relativepathto)|Этот метод используется для создания относительный путь из одного файла или папки в другую.|
|[CPathT::RemoveArgs](#removeargs)|Вызовите этот метод, чтобы удалить любые аргументы командной строки из пути.|
|[CPathT::RemoveBackslash](#removebackslash)|Этот метод используется для удаления из пути обратную косую черту.|
|[CPathT::RemoveBlanks](#removeblanks)|Вызовите этот метод, чтобы удалить все начальные и конечные пробелы из пути.|
|[CPathT::RemoveExtension](#removeextension)|Вызовите этот метод, чтобы удалить расширение файла из пути, если таковой имеется.|
|[CPathT::RemoveFileSpec](#removefilespec)|Этот метод для удаления из пути, в конце имени файла и обратной косой черты при их наличии.|
|[CPathT::RenameExtension](#renameextension)|Этот метод используется для замены нового расширения расширение имени файла в пути. Если имя файла не содержит расширения, расширение будет вложен в конец строки.|
|[CPathT::SkipRoot](#skiproot)|Вызовите этот метод для синтаксического анализа пути, игнорируя букву диска или части пути UNC сервера или общей папки.|
|[CPathT::StripPath](#strippath)|Вызовите этот метод, чтобы удалить часть пути полный путь и имя файла.|
|[CPathT::StripToRoot](#striptoroot)|Вызовите этот метод, чтобы удалить все части пути, за исключением сведений о корневом.|
|[CPathT::UnquoteSpaces](#unquotespaces)|Этот метод используется для удаления кавычек в начале и конце пути.|

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

Вызовите этот метод, чтобы добавить обратную косую черту в конец строки для создания правильного синтаксиса для пути. Если путь уже содержит обратную косую черту, будут добавляться не обратной косой черты.

```
void AddBackslash();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathAddBackSlash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha).

##  <a name="addextension"></a>  CPathT::AddExtension

Вызовите этот метод, чтобы добавить расширение файла в путь.

```
BOOL AddExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Параметры

*pszExtension*<br/>
Чтобы добавить расширение файла.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona).

##  <a name="append"></a>  CPathT::Append

Вызовите этот метод, чтобы добавить строку к текущему пути.

```
BOOL Append(PCXSTR pszMore);
```

### <a name="parameters"></a>Параметры

*pszMore*<br/>
Добавляемая строка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda).

##  <a name="buildroot"></a>  CPathT::BuildRoot

Вызовите этот метод, чтобы создать корневой путь из числа данного диска.

```
void BuildRoot(int iDrive);
```

### <a name="parameters"></a>Параметры

*iDrive*<br/>
Номер (0 — ответ, 1 — б и т. д.).

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota).

##  <a name="canonicalize"></a>  CPathT::Canonicalize

Вызовите этот метод для преобразования пути в канонической форме.

```
void Canonicalize();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea).

##  <a name="combine"></a>  CPathT::Combine

Этот метод используется для сцепления строка, представляющая имя каталога и строка, представляющая путь к файлу в один путь.

```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```

### <a name="parameters"></a>Параметры

*pszDir*<br/>
Путь к каталогу.

*pszFile*<br/>
Путь к файлу.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea).

##  <a name="commonprefix"></a>  CPathT::CommonPrefix

Вызовите этот метод, чтобы определить, использует ли указанный путь Общий префикс совместно с по текущему пути.

```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```

### <a name="parameters"></a>Параметры

*pszOther*<br/>
Путь для сравнения с текущей.

### <a name="return-value"></a>Возвращаемое значение

Возвращает общий префикс.

### <a name="remarks"></a>Примечания

Префикс является одним из этих типов: «C:\\\\«,». «,».. «,».. \\\\". Дополнительные сведения см. в разделе [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa).

##  <a name="compactpath"></a>  CPathT::CompactPath

Этот метод используется для усечения путь к файлу в соответствии с размерами ширину данного точек, заменив компоненты пути на кнопку с многоточием.

```
BOOL CompactPath(HDC hDC, UINT nWidth);
```

### <a name="parameters"></a>Параметры

*hDC*<br/>
Контекст устройства, используемые для метрик шрифтов.

*nWidth*<br/>
Ширина в пикселях, будут вынуждены помещаются в строку.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha).

##  <a name="compactpathex"></a>  CPathT::CompactPathEx

Этот метод используется для усечения путь к файлу в соответствии с размерами указанного числа символов, заменив компоненты пути на кнопку с многоточием.

```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```

### <a name="parameters"></a>Параметры

*nMaxChars*<br/>
Максимальное число символов, которые должны содержаться в новую строку, включая завершающий нуль-символ.

*dwFlags*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa).

##  <a name="cpatht"></a>  CPathT::CPathT

Конструктор.

```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```

### <a name="parameters"></a>Параметры

*pszPath*<br/>
Указатель на строку пути.

*path*<br/>
Строка пути.

##  <a name="fileexists"></a>  CPathT::FileExists

Вызовите этот метод, чтобы проверить, существует ли файл в этот путь.

```
BOOL FileExists() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если файл существует, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa).

##  <a name="findextension"></a>  CPathT::FindExtension

Вызовите этот метод, чтобы найти позицию расширение файла в пути.

```
int FindExtension() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает позицию «.» перед расширением. Не найдено, возвращается значение -1.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona).

##  <a name="findfilename"></a>  CPathT::FindFileName

Вызовите этот метод, чтобы определить позицию имени файла в пути.

```
int FindFileName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает позицию имени файла. Имя файла не найден, возвращается значение -1.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea).

##  <a name="getdrivenumber"></a>  CPathT::GetDriveNumber

Вызовите этот метод для поиска пути для букву диска в диапазоне от «A» до «Z» и возвращает соответствующий номер диска.

```
int GetDriveNumber() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает номер диска как целое число от 0 до 25 (соответствующие на «A» до «Z»), если путь содержит букву диска или -1, в противном случае.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera).

##  <a name="getextension"></a>  CPathT::GetExtension

Этот метод используется для получения расширения файла из пути.

```
StringType GetExtension() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает расширение файла.

##  <a name="isdirectory"></a>  CPathT::IsDirectory

Вызовите этот метод, чтобы проверить, является ли путь является допустимым каталогом.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение (16), если путь является каталогом, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya).

##  <a name="isfilespec"></a>  CPathT::IsFileSpec

Вызовите этот метод для поиска пути для любые символы, разделив их пути (например, ":" или "\\"). Если никакие символы разделителя пути присутствует, путь считается являться путем файловой спецификации.

```
BOOL IsFileSpec() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если нет символов, разделив их пути в пути, или значение FALSE, если присутствуют символы разделителя пути.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca).

##  <a name="isprefix"></a>  CPathT::IsPrefix

Вызовите этот метод, чтобы определить, содержит ли путь допустимый префикс типа, передаваемый по *pszPrefix*.

```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```

### <a name="parameters"></a>Параметры

*pszPrefix*<br/>
Префикс, который требуется найти. Префикс является одним из этих типов: «C:\\\\«,». «,».. «,».. \\\\".

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если путь содержит префикс, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa).

##  <a name="isrelative"></a>  CPathT::IsRelative

Этот метод используется для определения того, если путь является относительным.

```
BOOL IsRelative() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если путь является относительным, или значение FALSE, если он является абсолютным.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea).

##  <a name="isroot"></a>  CPathT::IsRoot

Вызовите этот метод, чтобы определить, является ли путь корневом каталоге.

```
BOOL IsRoot() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если путь является корнем, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota).

##  <a name="issameroot"></a>  CPathT::IsSameRoot

Вызовите этот метод, чтобы определить, имеет ли другой путь общий корневой компонент с по текущему пути.

```
BOOL IsSameRoot(PCXSTR pszOther) const;
```

### <a name="parameters"></a>Параметры

*pszOther*<br/>
По другому пути.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если обе строки имеют одного корневого компонента, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota).

##  <a name="isunc"></a>  CPathT::IsUNC

Вызовите этот метод, чтобы определить, является ли путь допустимым путем UNC (соглашения об универсальных именах) для сервера и совместного использования.

```
BOOL IsUNC() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если путь допустимый UNC-путь, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca).

##  <a name="isuncserver"></a>  CPathT::IsUNCServer

Вызовите этот метод, чтобы определить, является ли путь допустимым путем UNC (соглашения об универсальных именах) для сервера только.

```
BOOL IsUNCServer() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, является ли строка допустимый UNC-путь к серверу только (отсутствует имя общего ресурса), или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera).

##  <a name="isuncservershare"></a>  CPathT::IsUNCServerShare

Вызовите этот метод, чтобы определить, является ли путь допустимым путем UNC (соглашения об универсальных именах) общий ресурс, \\ \  *server*\ *совместно использовать*.

```
BOOL IsUNCServerShare() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если путь в форме \\ \  *server*\ *совместно использовать*, или FALSE в противном случае.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).

##  <a name="m_strpath"></a>  CPathT::m_strPath

Путь.

```
StringType m_strPath;
```

### <a name="remarks"></a>Примечания

`StringType` параметр шаблона `CPathT`.

##  <a name="makepretty"></a>  CPathT::MakePretty

Этот метод используется для преобразования пути для всех символов нижнего регистра, чтобы предоставить путь согласованного внешнего вида.

```
BOOL MakePretty();
```

### <a name="return-value"></a>Возвращаемое значение

В противном случае возвращает значение TRUE, если путь был преобразован, или значение FALSE.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).

##  <a name="matchspec"></a>  CPathT::MatchSpec

Вызовите этот метод для поиска пути для строка, содержащая тип совпадения подстановочный знак.

```
BOOL MatchSpec(PCXSTR pszSpec) const;
```

### <a name="parameters"></a>Параметры

*pszSpec*<br/>
Указатель на заканчивающуюся нулем строку, с типом файла, который требуется найти. Например, чтобы проверить, является ли файл в текущем пути DOC-файл *pszSpec* следует установить значение «* .doc».

### <a name="return-value"></a>Возвращаемое значение

В противном случае возвращает значение TRUE, если строка соответствует, или значение FALSE.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).

##  <a name="operator_add_eq"></a>  CPathT::operator +=

Этот оператор добавляет строку к пути.

```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```

### <a name="parameters"></a>Параметры

*pszMore*<br/>
Добавляемая строка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленные путь.

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

`StringType` параметр шаблона `CPathT`.

##  <a name="pxstr"></a>  CPathT::PXSTR

Тип string.

```
typedef StringType::PXSTR PXSTR;
```

### <a name="remarks"></a>Примечания

`StringType` параметр шаблона `CPathT`.

##  <a name="quotespaces"></a>  CPathT::QuoteSpaces

Вызовите этот метод, чтобы заключить путь в кавычки, если он содержит пробелы.

```
void QuoteSpaces();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).

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

*pszFrom*<br/>
Начало относительного пути.

*dwAttrFrom*<br/>
Атрибуты файла *pszFrom*. Если это значение содержит FILE_ATTRIBUTE_DIRECTORY, *pszFrom* принятой является каталогом; в противном случае, *pszFrom* предполагается, что в файл.

*pszTo*<br/>
Конечная точка относительного пути.

*dwAttrTo*<br/>
Атрибуты файла *pszTo*. Если это значение содержит FILE_ATTRIBUTE_DIRECTORY, *pszTo* принятой является каталогом; в противном случае, *pszTo* предполагается, что в файл.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).

##  <a name="removeargs"></a>  CPathT::RemoveArgs

Вызовите этот метод, чтобы удалить любые аргументы командной строки из пути.

```
void RemoveArgs();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).

##  <a name="removebackslash"></a>  CPathT::RemoveBackslash

Этот метод используется для удаления из пути обратную косую черту.

```
void RemoveBackslash();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).

##  <a name="removeblanks"></a>  CPathT::RemoveBlanks

Вызовите этот метод, чтобы удалить все начальные и конечные пробелы из пути.

```
void RemoveBlanks();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).

##  <a name="removeextension"></a>  CPathT::RemoveExtension

Вызовите этот метод, чтобы удалить расширение файла из пути, если таковой имеется.

```
void RemoveExtension();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).

##  <a name="removefilespec"></a>  CPathT::RemoveFileSpec

Этот метод для удаления из пути, в конце имени файла и обратной косой черты при их наличии.

```
BOOL RemoveFileSpec();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).

##  <a name="renameextension"></a>  CPathT::RenameExtension

Этот метод используется для замены нового расширения расширение имени файла в пути. Если имя файла не содержит расширения, расширение будет вложен в конец пути.

```
BOOL RenameExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Параметры

*pszExtension*<br/>
Новое расширение имени файла, предшествует «.» символов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).

##  <a name="skiproot"></a>  CPathT::SkipRoot

Вызовите этот метод для синтаксического анализа пути, игнорируя букву диска или части пути UNC (соглашения об универсальных именах) сервера или общей папки.

```
int SkipRoot() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает позицию начала субконтура, соответствует корню (букву диска или UNC сервера или общей папки).

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).

##  <a name="strippath"></a>  CPathT::StripPath

Вызовите этот метод, чтобы удалить часть пути полный путь и имя файла.

```
void StripPath();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).

##  <a name="striptoroot"></a>  CPathT::StripToRoot

Вызовите этот метод, чтобы удалить все части пути, за исключением сведений о корневом.

```
BOOL StripToRoot();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если буква диска был найден в пути, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).

##  <a name="unquotespaces"></a>  CPathT::UnquoteSpaces

Этот метод используется для удаления кавычек в начале и конце пути.

```
void UnquoteSpaces();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).

##  <a name="xchar"></a>  CPathT::XCHAR

Тип символа.

```
typedef StringType::XCHAR XCHAR;
```

### <a name="remarks"></a>Примечания

`StringType` параметр шаблона `CPathT`.

## <a name="see-also"></a>См. также

[Классы](../../atl/reference/atl-classes.md)<br/>
[Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)