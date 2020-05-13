---
title: Класс CFtpFileFind
ms.date: 11/04/2016
f1_keywords:
- CFtpFileFind
- AFXINET/CFtpFileFind
- AFXINET/CFtpFileFind::CFtpFileFind
- AFXINET/CFtpFileFind::FindFile
- AFXINET/CFtpFileFind::FindNextFile
- AFXINET/CFtpFileFind::GetFileURL
helpviewer_keywords:
- CFtpFileFind [MFC], CFtpFileFind
- CFtpFileFind [MFC], FindFile
- CFtpFileFind [MFC], FindNextFile
- CFtpFileFind [MFC], GetFileURL
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
ms.openlocfilehash: cf4afb4a683c2d0cf5f2977107d02ee300a53cb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373743"
---
# <a name="cftpfilefind-class"></a>Класс CFtpFileFind

Помогает в поиске файлов Интернета на FTP-серверах.

## <a name="syntax"></a>Синтаксис

```
class CFtpFileFind : public CFileFind
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFtpFileFind::CFtpFileFind](#cftpfilefind)|Формирует объект `CFtpFileFind`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFtpFileFind::FindFile](#findfile)|Находит файл на сервере FTP.|
|[CFtpFileFind::FindNextFile](#findnextfile)|Продолжает поиск файлов от предыдущего вызова [FindFile](#findfile).|
|[CFtpFileFind::GetFileURL](#getfileurl)|Получает URL-адрес, включая путь, найденного файла.|

## <a name="remarks"></a>Remarks

`CFtpFileFind`включает функции участника, которые начинают поиск, находят файл и возвращают URL или другую описательную информацию о файле.

Другие классы MFC, предназначенные для поиска в Интернете и локальном файле, включают [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) и [CFileFind.](../../mfc/reference/cfilefind-class.md) Вместе `CFtpFileFind`с этими классами клиент узелко в ней может находить определенные файлы, независимо от протокола сервера или типа файла (локальную машину или удаленный сервер). Обратите внимание, что нет класса MFC для поиска на серверах HTTP, потому что HTTP не поддерживает прямые манипуляции файлами, необходимые для поиска.

Для получения дополнительной информации о том, как использовать `CFtpFileFind` и другие классы WinInet, см. [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md)

## <a name="example"></a>Пример

Следующий код демонстрирует, как перечислить все файлы в текущем каталоге сервера FTP.

[!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CFtpFileFind`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cftpfilefindcftpfilefind"></a><a name="cftpfilefind"></a>CFtpFileFind::CFtpFileFind

Эта функция члена называется `CFtpFileFind` для построения объекта.

```
explicit CFtpFileFind(
    CFtpConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pConnection*<br/>
Указатель на объект `CFtpConnection`. Вы можете получить подключение FTP, позвонив [в CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection).

*Dwcontext*<br/>
Идентификатор `CFtpFileFind` контекста для объекта. Более подробную информацию об этом параметре можно увидеть в **комментариях.**

### <a name="remarks"></a>Remarks

Значение по умолчанию для *dwContext* отправляется MFC `CFtpFileFind` объекту с объекта [CInternetSession,](../../mfc/reference/cinternetsession-class.md) создавого `CFtpFileFind` объект. Можно переопределить значение по умолчанию, чтобы установить идентификатор контекста на значение по вашему выбору. Идентификатор контекста возвращается [в CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления статуса объекта, с помощью которого он идентифицируется. Для получения дополнительной информации об идентификаторе контекста смотрите статью [Internet First Steps: WinInet.](../../mfc/wininet-basics.md)

### <a name="example"></a>Пример

  Смотрите пример в обзоре занятий ранее в этой теме.

## <a name="cftpfilefindfindfile"></a><a name="findfile"></a>CFtpFileFind::FindFile

Вызовите эту функцию участника, чтобы найти файл FTP.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>Параметры

*pstrName*<br/>
Указатель на строку, содержащую имя файла, чтобы найти. Если NULL, вызов выполняет поиск подстановочных знаков (кв).

*dwFlags*<br/>
Флаги, описывающие, как обрабатывать этот сеанс. Эти флаги могут быть объединены с bitwise или оператора (&#124;) и являются следующими:

- INTERNET_FLAG_RELOAD получить данные из провода, даже если он локально кэшируется. Это флаг по умолчанию.

- INTERNET_FLAG_DONT_CACHE не кэшировать данные, либо локально, ни в каких-либо шлюзов.

- INTERNET_FLAG_RAW_DATA переопределить значение по умолчанию, чтобы вернуть исходные данные [(WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) структуры для FTP).

- INTERNET_FLAG_SECURE обеспечивает транзакции на проводе с помощью безопасных разъемов слоя или РСТ. Этот флаг применим только к запросам HTTP.

- INTERNET_FLAG_EXISTING_CONNECT Если это возможно, повторно использовать существующие соединения на сервере для новых `FindFile` запросов вместо создания нового сеанса для каждого запроса.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенную информацию об ошибке, позвоните в функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Remarks

После `FindFile` вызова для получения первого файла FTP, вы можете вызвать [FindNextFile](#findnextfile) для получения последующих файлов FTP.

### <a name="example"></a>Пример

  Смотрите более ранний пример в этой теме.

## <a name="cftpfilefindfindnextfile"></a><a name="findnextfile"></a>CFtpFileFind::FindNextFile

Вызовите эту функцию участника для продолжения поиска файлов, начатого с вызова к функции участника [FindFile.](#findfile)

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если есть больше файлов; ноль, если найденный файл является последним в каталоге или если произошла ошибка. Чтобы получить расширенную информацию об ошибке, позвоните в функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). Если найденный файл является последним файлом в каталоге, или если `GetLastError` не может быть найдено соответствие файлов, функция возвращается ERROR_NO_MORE_FILES.

### <a name="remarks"></a>Remarks

Вы должны позвонить по этой функции по крайней мере один раз, прежде чем позвонить любой функции атрибута (см. [CFileFind::FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).

`FindNextFile`обертывает функцию Win32 [FindNextFile](/windows/win32/api/fileapi/nf-fileapi-findnextfilew).

### <a name="example"></a>Пример

  Смотрите пример, который был ранее в этой теме.

## <a name="cftpfilefindgetfileurl"></a><a name="getfileurl"></a>CFtpFileFind::GetFileURL

Вызовите эту функцию участника, чтобы получить URL указанного файла.

```
CString GetFileURL() const;
```

### <a name="return-value"></a>Возвращаемое значение

Файл и путь универсального локатора ресурсов (URL).

### <a name="remarks"></a>Remarks

`GetFileURL`похож на функцию члена [CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath), за исключением `ftp://moose/dir/file.txt`того, что он возвращает URL в форме .

## <a name="see-also"></a>См. также раздел

[Класс CFileFind](../../mfc/reference/cfilefind-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)<br/>
[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс CHttpfile](../../mfc/reference/chttpfile-class.md)
