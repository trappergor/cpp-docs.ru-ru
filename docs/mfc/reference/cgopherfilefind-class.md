---
title: Класс CGopherFileFind
ms.date: 11/04/2016
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
helpviewer_keywords:
- CGopherFileFind [MFC], CGopherFileFind
- CGopherFileFind [MFC], FindFile
- CGopherFileFind [MFC], FindNextFile
- CGopherFileFind [MFC], GetCreationTime
- CGopherFileFind [MFC], GetLastAccessTime
- CGopherFileFind [MFC], GetLastWriteTime
- CGopherFileFind [MFC], GetLength
- CGopherFileFind [MFC], GetLocator
- CGopherFileFind [MFC], GetScreenName
- CGopherFileFind [MFC], IsDots
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
ms.openlocfilehash: c1157b3583e266a09840f710b46766ffc4f31b5e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269699"
---
# <a name="cgopherfilefind-class"></a>Класс CGopherFileFind

Помогает в поиске файлов Интернета на серверах gopher.

> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены являются устаревшими, так как они не работают на платформе Windows XP, но они будут продолжать работать на более ранние платформы.

## <a name="syntax"></a>Синтаксис

```
class CGopherFileFind : public CFileFind
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|Создает объект `CGopherFileFind`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CGopherFileFind::FindFile](#findfile)|Находит файл на сервере gopher.|
|[CGopherFileFind::FindNextFile](#findnextfile)|Продолжает поиск файла из предыдущего вызова [FindFile](#findfile).|
|[CGopherFileFind::GetCreationTime](#getcreationtime)|Получает время создания указанного файла.|
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|Получает время последнего обращения к указанному файлу.|
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|Получает время последней операции записи указанного файла.|
|[CGopherFileFind::GetLength](#getlength)|Получает длину файла, в байтах.|
|[CGopherFileFind::GetLocator](#getlocator)|Получение `CGopherLocator` объекта.|
|[CGopherFileFind::GetScreenName](#getscreenname)|Получает имя экрана gopher.|
|[CGopherFileFind::IsDots](#isdots)|Тесты для текущего каталога и родительский каталог маркеров при переборе файлы.|

## <a name="remarks"></a>Примечания

`CGopherFileFind` включает в себя функции-члены, начать поиск, укажите расположение файла и файла URL-адрес возврата.

Другие классы MFC, предназначенные для Интернета и локальный файл, в котором выполняется поиск включают в себя [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) и [CFileFind](../../mfc/reference/cfilefind-class.md). Вместе с `CGopherFileFind`, эти классы предоставляют простой механизм для пользователя для поиска конкретных файлов, независимо от протокола сервера, тип файла или расположение (локальном компьютере или удаленном сервере.) Обратите внимание на то, что отсутствует класс MFC для поиска по HTTP-серверами, так как HTTP не поддерживает прямое файлами, необходимые при поиске.

> [!NOTE]
> `CGopherFileFind` не поддерживает следующие функции-члены базового класса [CFileFind](../../mfc/reference/cfilefind-class.md):

- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)

- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)

- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)

- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)

- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)

Кроме того, при использовании с `CGopherFileFind`, `CFileFind` функция-член [IsDots](../../mfc/reference/cfilefind-class.md#isdots) всегда имеет значение FALSE.

Дополнительные сведения об использовании `CGopherFileFind` и другие классы WinInet, см. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CGopherFileFind`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

##  <a name="cgopherfilefind"></a>  CGopherFileFind::CGopherFileFind

Эта функция-член вызывается для создания `CGopherFileFind` объекта.

```
explicit CGopherFileFind(
    CGopherConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pConnection*<br/>
Указатель на [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) объекта.

*dwContext*<br/>
Идентификатор контекста для операции. См. в разделе **"Примечания"** Дополнительные сведения о *dwContext*.

### <a name="remarks"></a>Примечания

Значение по умолчанию для *dwContext* отправленные MFC для `CGopherFileFind` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, который создан `CGopherFileFind` объекта. При построении `CGopherFileFind` объекта, можно переопределить значение по умолчанию присвоено значение по своему выбору, идентификатор контекста. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния в объекте, с которой он определен. См. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.

##  <a name="findfile"></a>  CGopherFileFind::FindFile

Вызов этой функции-члена для поиска файла gopher.

```
virtual BOOL FindFile(
    CGopherLocator& refLocator,
    LPCTSTR pstrString,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

virtual BOOL FindFile(
    LPCTSTR pstrString,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>Параметры

*refLocator*<br/>
Ссылку на [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.

*pstrString*<br/>
Указатель на строку, содержащую имя файла.

*dwFlags*<br/>
Флаги, описывающие способ обработки этого сеанса. Ниже приведены допустимые флаги.

- INTERNET_FLAG_RELOAD получить данные от удаленного сервера, даже если он кэшируется локально.

- INTERNET_FLAG_DONT_CACHE не кэшировать данные, локально или в всех шлюзов.

- Запросить INTERNET_FLAG_SECURE безопасные транзакции по сети с помощью Secure Sockets Layer или использованию PCT. Этот флаг применим только для HTTP-запросов.

- INTERNET_FLAG_USE_EXISTING Если это возможно, повторно использовать существующие подключения к серверу для новых `FindFile` запросы, а не создавать новый сеанс для каждого запроса.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

### <a name="remarks"></a>Примечания

После вызова метода `FindFile` для получения первого объекта gopher, можно вызвать [FindNextFile](#findnextfile) для получения файлов последующих gopher.

##  <a name="findnextfile"></a>  CGopherFileFind::FindNextFile

Вызовите эту функцию-член для продолжения поиска файла начался вызовом [CGopherFileFind::FindFile](#findfile).

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, при наличии нескольких файлов; нуль, если найден файл является последним в каталоге или если возникает ошибка. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360). Если файл найден последнего файла в каталоге, или если соответствующие файлы можно найти, `GetLastError` функция возвращает ERROR_NO_MORE_FILES.

##  <a name="getcreationtime"></a>  CGopherFileFind::GetCreationTime

Получает время создания текущего файла.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>Параметры

*pTimeStamp*<br/>
Указатель на [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) структуру, содержащую время создания файла.

*refTime*<br/>
Ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; 0, если операция завершилась неудачей. `GetCreationTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван на это `CGopherFileFind` объекта.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetCreationTime`.

> [!NOTE]
>  Не все файловые системы используйте ту же семантику, чтобы реализовать отметку времени, возвращаемое этой функцией. Эта функция может возвращать же значение, возвращенное другие функции отметку времени, если базовой файловой системы или сервер не поддерживает сохранение атрибут времени. См. в разделе [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были зоны локальной машине, что он находится. См. в разделе Win32 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API Дополнительные сведения.

##  <a name="getlastaccesstime"></a>  CGopherFileFind::GetLastAccessTime

Получает время последнего обращения к указанному файлу.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>Параметры

*refTime*<br/>
Ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта.

*pTimeStamp*<br/>
Указатель на [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) структуру, содержащую время последнего доступа к файлу.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; 0, если операция завершилась неудачей. `GetLastAccessTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван на это `CGopherFileFind` объекта.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetLastAccessTime`.

> [!NOTE]
>  Не все файловые системы используйте ту же семантику, чтобы реализовать отметку времени, возвращаемое этой функцией. Эта функция может возвращать же значение, возвращенное другие функции отметку времени, если базовой файловой системы или сервер не поддерживает сохранение атрибут времени. См. в разделе [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были зоны локальной машине, что он находится. См. в разделе Win32 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API Дополнительные сведения.

##  <a name="getlastwritetime"></a>  CGopherFileFind::GetLastWriteTime

Получает время последнего изменения файла.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>Параметры

*pTimeStamp*<br/>
Указатель на [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) структуру, содержащую время последней операции записи файла.

*refTime*<br/>
Ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; 0, если операция завершилась неудачей. `GetLastWriteTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван на это `CGopherFileFind` объекта.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetLastWriteTime`.

> [!NOTE]
>  Не все файловые системы используйте ту же семантику, чтобы реализовать отметку времени, возвращаемое этой функцией. Эта функция может возвращать же значение, возвращенное другие функции отметку времени, если базовой файловой системы или сервер не поддерживает сохранение атрибут времени. См. в разделе [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были зоны локальной машине, что он находится. См. в разделе Win32 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API Дополнительные сведения.

##  <a name="getlength"></a>  CGopherFileFind::GetLength

Эта функция члена получить длину в байтах, найденного файла.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина найденного файла в байтах.

### <a name="remarks"></a>Примечания

`GetLength` используется структура Win32 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) для получения значения от размера файла в байтах.

> [!NOTE]
>  Начиная с MFC 7.0 `GetLength` поддерживает 64-разрядными целочисленными типами. Ранее существовавшие кода, созданного с помощью этой новой версии библиотеки может привести предупреждения об усечении.

### <a name="example"></a>Пример

  См. в примере [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (реализацию базового класса).

##  <a name="getlocator"></a>  CGopherFileFind::GetLocator

Вызывайте эту функцию члена, чтобы получить [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта, [FindFile](#findfile) использует, чтобы найти файл gopher.

```
CGopherLocator GetLocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CGopherLocator`.

##  <a name="getscreenname"></a>  CGopherFileFind::GetScreenName

Вызывайте эту функцию член, чтобы получить имя экрана gopher.

```
CString GetScreenName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя экрана gopher.

##  <a name="isdots"></a>  CGopherFileFind::IsDots

Тесты для текущего каталога и родительский каталог маркеров при переборе файлы.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если найден файл имеет имя «. «или»..», который указывает, что найденный файл является папкой. В противном случае 0.

### <a name="remarks"></a>Примечания

Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsDots`.

## <a name="see-also"></a>См. также

[Класс CFileFind](../../mfc/reference/cfilefind-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)<br/>
[Класс CFileFind](../../mfc/reference/cfilefind-class.md)<br/>
[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс CHttpFile](../../mfc/reference/chttpfile-class.md)
