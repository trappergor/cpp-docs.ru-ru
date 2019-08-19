---
title: Класс Кфилефинд
ms.date: 11/04/2016
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
ms.openlocfilehash: f2dfd3421d2154b4894b62b71d7993c483a77c53
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916124"
---
# <a name="cfilefind-class"></a>Класс Кфилефинд

Выполняет поиск по локальному файлу и является базовым классом для [кгоферфилефинд](../../mfc/reference/cgopherfilefind-class.md) и [кфтпфилефинд](../../mfc/reference/cftpfilefind-class.md), которые выполняют поиск файлов в Интернете.

## <a name="syntax"></a>Синтаксис

```
class CFileFind : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CFileFind::CFileFind](#cfilefind)|Создает объект `CFileFind`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кфилефинд:: Close](#close)|Закрывает поисковый запрос.|
|[CFileFind::FindFile](#findfile)|Выполняет поиск указанного имени файла в каталоге.|
|[CFileFind::FindNextFile](#findnextfile)|Возобновляет Поиск файла из предыдущего вызова [финдфиле](#findfile).|
|[CFileFind::GetCreationTime](#getcreationtime)|Возвращает время создания файла.|
|[CFileFind::GetFileName](#getfilename)|Возвращает имя найденного файла, включая расширение.|
|[CFileFind::GetFilePath](#getfilepath)|Возвращает полный путь к найденному файлу.|
|[CFileFind::GetFileTitle](#getfiletitle)|Возвращает заголовок найденного файла. Заголовок не включает расширение.|
|[CFileFind::GetFileURL](#getfileurl)|Возвращает URL-адрес найденного файла, включая путь к файлу.|
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Возвращает время последнего обращения к файлу.|
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Возвращает время последнего изменения и сохранения файла.|
|[CFileFind::GetLength](#getlength)|Возвращает длину найденного файла в байтах.|
|[CFileFind::GetRoot](#getroot)|Возвращает корневой каталог найденного файла.|
|[CFileFind::IsArchived](#isarchived)|Определяет, архивируется ли найденный файл.|
|[CFileFind::IsCompressed](#iscompressed)|Определяет, сжат ли найденный файл.|
|[Кфилефинд:: подкаталог](#isdirectory)|Определяет, является ли найденный файл каталогом.|
|[Кфилефинд:: наТочки](#isdots)|Определяет, имеет ли имя найденного файла имя "." или "..", указывая, что фактически является каталогом.|
|[Кфилефинд:: Hidden](#ishidden)|Определяет, скрыт ли найденный файл.|
|[Кфилефинд:: onобычная](#isnormal)|Определяет, является ли найденный файл нормальным (иными словами, не имеет других атрибутов).|
|[Кфилефинд:: IsReadOnly](#isreadonly)|Определяет, доступен ли найденный файл только для чтения.|
|[Кфилефинд:: a System](#issystem)|Определяет, является ли найденный файл системным.|
|[Кфилефинд::](#istemporary)|Определяет, является ли найденный файл временным.|
|[Кфилефинд:: Матчесмаск](#matchesmask)|Указывает необходимые атрибуты файла для поиска.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CFileFind::CloseContext](#closecontext)|Закрывает файл, указанный текущим поисковым маркером.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CFileFind::m_pTM](#m_ptm)|Указатель на `CAtlTransactionManager` объект.|

## <a name="remarks"></a>Примечания

`CFileFind`включает функции-члены, которые начинают поиск, находят файл и возвращают заголовок, имя или путь к файлу. При поиске в Интернете функция-член [жетфилеурл](#getfileurl) возвращает URL файла.

`CFileFind`является базовым классом для двух других классов MFC, предназначенных для поиска конкретных `CGopherFileFind` типов серверов: работает специально с серверами `CFtpFileFind` Gopher и работает специально с FTP-серверами. Вместе эти три класса предоставляют клиенту простой механизм поиска файлов независимо от протокола сервера, типа файла или расположения на локальном или удаленном сервере.

Следующий код выполнит перечисление всех файлов в текущем каталоге, выполнив печать имени каждого файла:

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

Чтобы не усложнять пример, этот код использует класс C++ стандартной библиотеки. `cout` Строку можно заменить на `CListBox::AddString`вызов, например, в программе с графическим пользовательским интерфейсом. `cout`

Дополнительные сведения об использовании `CFileFind` и других классах WinInet см. в статье Интернет – [программирование с помощью WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="cfilefind"></a>  CFileFind::CFileFind

Эта функция-член вызывается при `CFileFind` создании объекта.

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Параметры

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: filename](#getfilename).

##  <a name="close"></a>Кфилефинд:: Close

Вызовите эту функцию члена, чтобы завершить поиск, сбросить контекст и освободить все ресурсы.

```
void Close();
```

### <a name="remarks"></a>Примечания

После вызова `Close`не нужно создавать новый `CFileFind` экземпляр перед вызовом [финдфиле](#findfile) , чтобы начать новый поиск.

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: filename](#getfilename).

##  <a name="closecontext"></a>  CFileFind::CloseContext

Закрывает файл, указанный текущим поисковым маркером.

```
virtual void CloseContext();
```

### <a name="remarks"></a>Примечания

Закрывает файл, заданный текущим значением маркера поиска. Переопределите эту функцию, чтобы изменить поведение по умолчанию.

Чтобы получить допустимый маркер поиска, необходимо вызвать функции [финдфиле](#findfile) или [FindNextFile](#findnextfile) по крайней мере один раз. Функции `FindFile` и`FindNextFile` используют описатель поиска для поиска файлов с именами, соответствующими заданному имени.

##  <a name="findfile"></a>  CFileFind::FindFile

Вызовите эту функцию-член, чтобы открыть Поиск файла.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>Параметры

*пстрнаме*<br/>
Указатель на строку, содержащую имя искомого файла. Если передать значение NULL для *пстрнаме*, `FindFile` выполняет поиск по подстановочному знаку (*.\*).

*двунусед*<br/>
Зарезервировано `FindFile` для выполнения полиморфизма с производными классами. Должен быть равен 0.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Примечания

После вызова `FindFile` для начала поиска файла вызовите [FindNextFile](#findnextfile) для получения последующих файлов. Необходимо вызвать `FindNextFile` хотя бы один раз перед вызовом любой из следующих функций члена атрибута:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [жетфилетитле](#getfiletitle)

- [GetFilePath](#getfilepath)

- [жетфилеурл](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [С заархивированным](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory) (является каталогом);

- [Точки](#isdots)

- [IsHidden](#ishidden)

- [Обычная](#isnormal)

- [IsReadOnly](#isreadonly)

- [Указанным параметром IsSystem](#issystem)

- [IsTemporary задано](#istemporary)

- [матчесмаск](#matchesmask)

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DataDirectory](#isdirectory).

##  <a name="findnextfile"></a>  CFileFind::FindNextFile

Вызовите эту функцию-член, чтобы продолжить поиск файла из предыдущего вызова [финдфиле](#findfile).

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если есть больше файлов; нуль, если найденный файл является последним в каталоге или если произошла ошибка. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror). Если найденный файл является последним файлом в каталоге или не удается найти соответствующие файлы, `GetLastError` функция возвращает ERROR_NO_MORE_FILES.

### <a name="remarks"></a>Примечания

Необходимо вызвать `FindNextFile` хотя бы один раз перед вызовом любой из следующих функций члена атрибута:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [жетфилетитле](#getfiletitle)

- [GetFilePath](#getfilepath)

- [жетфилеурл](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [С заархивированным](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory) (является каталогом);

- [Точки](#isdots)

- [IsHidden](#ishidden)

- [Обычная](#isnormal)

- [IsReadOnly](#isreadonly)

- [Указанным параметром IsSystem](#issystem)

- [IsTemporary задано](#istemporary)

- [матчесмаск](#matchesmask)

`FindNextFile`заключает в оболочку функцию Win32 [FindNextFile](/windows/desktop/api/fileapi/nf-fileapi-findnextfilea).

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DataDirectory](#isdirectory).

##  <a name="getcreationtime"></a>  CFileFind::GetCreationTime

Вызовите эту функцию члена, чтобы получить время создания указанного файла.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>Параметры

*птиместамп*<br/>
Указатель на структуру [fileTime](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) , содержащую время создания файла.

*рефтиме*<br/>
Ссылка на объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения; 0 в случае неудачи. `GetCreationTime` возвращает 0, только если [FindNextFile](#findnextfile) никогда не вызывался для этого `CFileFind` объекта.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `GetCreationTime`перед вызовом.

> [!NOTE]
>  Не все файловые системы используют одну и ту же семантику для реализации отметки времени, возвращаемой этой функцией. Эта функция может возвращать то же значение, что и другие функции отметки времени, если базовая файловая система или сервер не поддерживает поддержание атрибута времени. Сведения о форматах времени см. в разделе Структура [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) . В некоторых операционных системах возвращенное время находится на локальном часовом поясе компьютера, где находится файл. Дополнительные сведения см. в разделе API Win32 [филетиметолокалфилетиме](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) .

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DATALENGTH](#getlength).

##  <a name="getfilename"></a>  CFileFind::GetFileName

Вызовите эту функцию члена, чтобы получить имя найденного файла.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя самого последнего найденного файла.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода filename.

`GetFileName`является одной из трех `CFileFind` функций-членов, возвращающих некоторую форму имени файла. В следующем списке описаны три и их отличия.

- `GetFileName`Возвращает имя файла, включая расширение. Например, вызов `GetFileName` для создания сообщения пользователя о файле *к:\михтмл\мифиле.ткст* возвращает имя файла *MyFile. txt*.

- Функция [FilePath](#getfilepath) возвращает полный путь к файлу. Например, вызов `GetFilePath` для создания сообщения пользователя о файле *к:\михтмл\мифиле.ткст* Возвращает путь к файлу *к:\михтмл\мифиле.ткст*.

- [Жетфилетитле](#getfiletitle) возвращает имя файла, исключая расширение файла. Например, вызов `GetFileTitle` для создания сообщения пользователя о файле *к:\михтмл\мифиле.ткст* возвращает имя файла *MyFile*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

##  <a name="getfilepath"></a>  CFileFind::GetFilePath

Вызовите эту функцию члена, чтобы получить полный путь к указанному файлу.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Путь к указанному файлу.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `GetFilePath`перед вызовом.

`GetFilePath`является одной из трех `CFileFind` функций-членов, возвращающих некоторую форму имени файла. В следующем списке описаны три и их отличия.

- Параметр [filename](#getfilename) возвращает имя файла, включая расширение. Например, вызов `GetFileName` для создания сообщения пользователя о файле *к:\михтмл\мифиле.ткст* возвращает имя файла *MyFile. txt*.

- `GetFilePath`Возвращает полный путь к файлу. Например, вызов `GetFilePath` для создания сообщения пользователя о файле `c:\myhtml\myfile.txt` Возвращает путь к `c:\myhtml\myfile.txt`файлу.

- [Жетфилетитле](#getfiletitle) возвращает имя файла, исключая расширение файла. Например, вызов `GetFileTitle` для создания сообщения пользователя о файле *к:\михтмл\мифиле.ткст* возвращает имя файла *MyFile*.

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: filename](#getfilename).

##  <a name="getfiletitle"></a>  CFileFind::GetFileTitle

Вызовите эту функцию члена, чтобы получить заголовок найденного файла.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Заголовок файла.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `GetFileTitle`перед вызовом.

`GetFileTitle`является одной из трех `CFileFind` функций-членов, возвращающих некоторую форму имени файла. В следующем списке описаны три и их отличия.

- Параметр [filename](#getfilename) возвращает имя файла, включая расширение. Например, вызов `GetFileName` для создания сообщения пользователя о файле *к:\михтмл\мифиле.ткст* возвращает имя файла *MyFile. txt*.

- Функция [FilePath](#getfilepath) возвращает полный путь к файлу. Например, вызов `GetFilePath` для создания сообщения пользователя о файле *к:\михтмл\мифиле.ткст* Возвращает путь к файлу *к:\михтмл\мифиле.ткст*.

- `GetFileTitle`Возвращает имя файла, исключая расширение файла. Например, вызов `GetFileTitle` для создания сообщения пользователя о файле *к:\михтмл\мифиле.ткст* возвращает имя файла *MyFile*.

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: filename](#getfilename).

##  <a name="getfileurl"></a>  CFileFind::GetFileURL

Вызовите эту функцию-член для получения указанного URL.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Возвращаемое значение

Полный URL-адрес.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `GetFileURL`перед вызовом.

Функция `GetFileURL` аналогична функции-члену [GetFilePath](#getfilepath), за исключением того, что она возвращает URL в форме `file://path`. Например, вызов `GetFileURL` для получения полного URL-адреса для *MyFile. txt* возвращает URL- `file://c:\myhtml\myfile.txt`адрес.

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: filename](#getfilename).

##  <a name="getlastaccesstime"></a>  CFileFind::GetLastAccessTime

Вызовите эту функцию члена, чтобы получить время последнего доступа к заданному файлу.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>Параметры

*рефтиме*<br/>
Ссылка на объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) .

*птиместамп*<br/>
Указатель на структуру [fileTime](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) , содержащую время последнего обращения к файлу.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения; 0 в случае неудачи. `GetLastAccessTime` возвращает 0, только если [FindNextFile](#findnextfile) никогда не вызывался для этого объекта `CFileFind`.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `GetLastAccessTime`перед вызовом.

> [!NOTE]
>  Не все файловые системы используют одну и ту же семантику для реализации отметки времени, возвращаемой этой функцией. Эта функция может возвращать то же значение, что и другие функции отметки времени, если базовая файловая система или сервер не поддерживает поддержание атрибута времени. Сведения о форматах времени см. в разделе Структура [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) . В некоторых операционных системах возвращенное время находится на локальном часовом поясе компьютера, где находится файл. Дополнительные сведения см. в разделе API Win32 [филетиметолокалфилетиме](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) .

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DATALENGTH](#getlength).

##  <a name="getlastwritetime"></a>  CFileFind::GetLastWriteTime

Вызовите эту функцию члена, чтобы получить время последнего изменения файла.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>Параметры

*птиместамп*<br/>
Указатель на структуру [fileTime](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) , содержащую время последней запись в файл.

*рефтиме*<br/>
Ссылка на объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения; 0 в случае неудачи. `GetLastWriteTime` возвращает 0, только если [FindNextFile](#findnextfile) никогда не вызывался для этого объекта `CFileFind`.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `GetLastWriteTime`перед вызовом.

> [!NOTE]
>  Не все файловые системы используют одну и ту же семантику для реализации отметки времени, возвращаемой этой функцией. Эта функция может возвращать то же значение, что и другие функции отметки времени, если базовая файловая система или сервер не поддерживает поддержание атрибута времени. Сведения о форматах времени см. в разделе Структура [Win32_Find_Data](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) . В некоторых операционных системах возвращенное время находится на локальном часовом поясе компьютера, где находится файл. Дополнительные сведения см. в разделе API Win32 [филетиметолокалфилетиме](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) .

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DATALENGTH](#getlength).

##  <a name="getlength"></a>  CFileFind::GetLength

Вызовите эту функцию члена, чтобы получить длину найденного файла в байтах.

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина найденного файла в байтах.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `GetLength`перед вызовом.

`GetLength`использует структуру Win32 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) для получения и возврата значения размера файла в байтах.

> [!NOTE]
>  Начиная с MFC 7,0 `GetLength` поддерживает 64-разрядные целочисленные типы. Ранее существующий код, созданный с помощью этой более новой версии библиотеки, может привести к предупреждениям усечения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

##  <a name="getroot"></a>  CFileFind::GetRoot

Вызовите эту функцию члена, чтобы получить корень найденного файла.

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>Возвращаемое значение

Корень активного поиска.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `GetRoot`перед вызовом.

Эта функция-член возвращает описатель диска и имя пути, используемые для запуска поиска. Например, вызов [финдфиле](#findfile) с `*.dat` результатом `GetRoot` возврата пустой строки. Передача `c:\windows\system\*.dll`пути, например, в `FindFile` возвращаемые `c:\windows\system\`результаты `GetRoot` .

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: filename](#getfilename).

##  <a name="isarchived"></a>  CFileFind::IsArchived

Вызовите эту функцию-член, чтобы определить, архивируется ли найденный файл.

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Приложения помечают файл архива, для которого создается резервная копия или удаление, с помощью FILE_ATTRIBUTE_ARCHIVE атрибут файла, определенный в структуре [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) .

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `IsArchived`перед вызовом.

Полный список атрибутов файла см. в функции-члене [матчесмаск](#matchesmask) .

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DATALENGTH](#getlength).

##  <a name="iscompressed"></a>  CFileFind::IsCompressed

Вызовите эту функцию-член, чтобы определить, сжат ли найденный файл.

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Сжатый файл помечается как FILE_ATTRIBUTE_COMPRESSED, атрибут файла, определенный в структуре [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) . Для файла этот атрибут указывает, что все данные в файле сжимаются. Для каталога этот атрибут указывает на то, что для вновь создаваемых файлов и подкаталогов используется сжатие по умолчанию.

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `IsCompressed`перед вызовом.

Полный список атрибутов файла см. в функции-члене [матчесмаск](#matchesmask) .

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DATALENGTH](#getlength).

##  <a name="isdirectory"></a>Кфилефинд:: подкаталог

Вызовите эту функцию-член, чтобы определить, является ли найденный файл каталогом.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Файл, являющийся каталогом, помечается атрибутом FILE_ATTRIBUTE_DIRECTORY, определенным в структуре [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) .

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `IsDirectory`перед вызовом.

Полный список атрибутов файла см. в функции-члене [матчесмаск](#matchesmask) .

### <a name="example"></a>Пример

Эта небольшая программа выполняет рекурсивный рекурсию для каждого каталога C:\. диск и выводит имя каталога.

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

##  <a name="isdots"></a>Кфилефинд:: наТочки

Вызывайте эту функцию-член для проверки текущего каталога и маркеров родительского каталога при переборе файлов.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если найденный файл имеет имя "." или "..", что означает, что найденный файл действительно является каталогом. В противном случае — 0.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `IsDots`перед вызовом.

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DataDirectory](#isdirectory).

##  <a name="ishidden"></a>  CFileFind::IsHidden

Вызовите эту функцию-член, чтобы определить, скрыт ли найденный файл.

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Скрытые файлы, помеченные FILE_ATTRIBUTE_HIDDEN, атрибут файла, определенный в структуре [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) . Скрытый файл не включается в обычный список каталогов.

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `IsHidden`перед вызовом.

Полный список атрибутов файла см. в функции-члене [матчесмаск](#matchesmask) .

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DATALENGTH](#getlength).

##  <a name="isnormal"></a>Кфилефинд:: onобычная

Вызовите эту функцию-член, чтобы определить, является ли найденный файл обычным.

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Файлы, помеченные с помощью FILE_ATTRIBUTE_NORMAL, атрибут файла, определенный в структуре [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) . Для обычного файла не заданы другие атрибуты. Все остальные атрибуты файла переопределяют этот атрибут.

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `IsNormal`перед вызовом.

Полный список атрибутов файла см. в функции-члене [матчесмаск](#matchesmask) .

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DATALENGTH](#getlength).

##  <a name="isreadonly"></a>Кфилефинд:: IsReadOnly

Вызовите эту функцию-член, чтобы определить, доступен ли найденный файл только для чтения.

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Файл, предназначенный только для чтения, помечен как FILE_ATTRIBUTE_READONLY, атрибут файла, определенный в структуре [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) . Приложения могут читать такой файл, но не могут выполнять запись в него или удалять его.

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `IsReadOnly`перед вызовом.

Полный список атрибутов файла см. в функции-члене [матчесмаск](#matchesmask) .

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DATALENGTH](#getlength).

##  <a name="issystem"></a>  CFileFind::IsSystem

Вызовите эту функцию-член, чтобы определить, является ли найденный файл системным.

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Системный файл помечается как FILE_ATTRIBUTE_SYSTEM, — атрибутом файла, определенным в структуре [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) . Системный файл является частью или используется исключительно операционной системой.

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `IsSystem`перед вызовом.

Полный список атрибутов файла см. в функции-члене [матчесмаск](#matchesmask) .

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DATALENGTH](#getlength).

##  <a name="istemporary"></a>Кфилефинд::

Вызовите эту функцию-член, чтобы определить, является ли найденный файл временным.

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Временный файл помечается как FILE_ATTRIBUTE_TEMPORARY, атрибут файла, определенный в структуре [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) . Временный файл используется для временного хранения. Приложения должны выполнять запись в файл только в случае крайней необходимости. Большая часть данных файла остается в памяти без записи на носитель, так как файл скоро будет удален.

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `IsTemporary`перед вызовом.

Полный список атрибутов файла см. в функции-члене [матчесмаск](#matchesmask) .

### <a name="example"></a>Пример

  См. пример для [кфилефинд:: DATALENGTH](#getlength).

##  <a name="m_ptm"></a>  CFileFind::m_pTM

Указатель на `CAtlTransactionManager` объект.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Примечания

##  <a name="matchesmask"></a>Кфилефинд:: Матчесмаск

Вызовите эту функцию-член для проверки атрибутов файла в найденном файле.

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>Параметры

*двмаск*<br/>
Задает один или несколько атрибутов файла, определенных в структуре [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) , для найденного файла. Для поиска нескольких атрибутов используйте оператор побитового или (&#124;). Допустимо любое сочетание следующих атрибутов:

- FILE_ATTRIBUTE_ARCHIVE файл является архивным файлом. Приложения используют этот атрибут для пометки файлов для резервного копирования или удаления.

- FILE_ATTRIBUTE_COMPRESSED файл или каталог сжат. Для файла это означает, что все данные в файле сжимаются. Для каталога это означает, что для вновь создаваемых файлов и подкаталогов используется сжатие по умолчанию.

- FILE_ATTRIBUTE_DIRECTORY файл является каталогом.

- FILE_ATTRIBUTE_NORMAL. для файла не заданы другие атрибуты. Этот атрибут допустим только в том случае, если он используется отдельно. Все остальные атрибуты файла переопределяют этот атрибут.

- FILE_ATTRIBUTE_HIDDEN. файл скрыт. Он не должен включаться в обычный список каталогов.

- FILE_ATTRIBUTE_READONLY файл доступен только для чтения. Приложения могут считывать файл, но не могут выполнять запись в него или удалять его.

- FILE_ATTRIBUTE_SYSTEM. файл является частью или используется исключительно операционной системой.

- FILE_ATTRIBUTE_TEMPORARY. файл используется для временного хранения. Приложения должны выполнять запись в файл только в случае крайней необходимости. Большая часть данных файла остается в памяти без записи на носитель, так как файл скоро будет удален.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз `MatchesMask`перед вызовом.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)<br/>
[Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)<br/>
[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс CHttpFile](../../mfc/reference/chttpfile-class.md)
