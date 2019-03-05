---
title: Класс CAtlFile
ms.date: 11/04/2016
f1_keywords:
- CAtlFile
- ATLFILE/ATL::CAtlFile
- ATLFILE/ATL::CAtlFile::CAtlFile
- ATLFILE/ATL::CAtlFile::Create
- ATLFILE/ATL::CAtlFile::Flush
- ATLFILE/ATL::CAtlFile::GetOverlappedResult
- ATLFILE/ATL::CAtlFile::GetPosition
- ATLFILE/ATL::CAtlFile::GetSize
- ATLFILE/ATL::CAtlFile::LockRange
- ATLFILE/ATL::CAtlFile::Read
- ATLFILE/ATL::CAtlFile::Seek
- ATLFILE/ATL::CAtlFile::SetSize
- ATLFILE/ATL::CAtlFile::UnlockRange
- ATLFILE/ATL::CAtlFile::Write
- ATLFILE/ATL::CAtlFile::m_pTM
helpviewer_keywords:
- CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
ms.openlocfilehash: 19e230f150803019d47e1ea710e7d713d1822a53
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270100"
---
# <a name="catlfile-class"></a>Класс CAtlFile

Этот класс предоставляет тонкую оболочку Windows API обработки файлов.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAtlFile : public CHandle
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlFile::CAtlFile](#catlfile)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CAtlFile::Create](#create)|Этот метод используется для создания или открытия файла.|
|[CAtlFile::Flush](#flush)|Этот метод используется для очистки буферов для файла и потере всех буферизованных данных для записи в файл.|
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|Этот метод используется для получения результатов операции перекрывающегося на файле.|
|[CAtlFile::GetPosition](#getposition)|Вызовите этот метод для получения текущего положения указателя файла из файла.|
|[CAtlFile::GetSize](#getsize)|Вызовите этот метод, чтобы получить размер файла в байтах.|
|[CAtlFile::LockRange](#lockrange)|Вызовите этот метод, чтобы заблокировать регион, в файле, чтобы запретить доступ к нему другими процессами.|
|[CAtlFile::Read](#read)|Этот метод используется для чтения данных из файла, начиная с позиции, указанной проверкой указатель файла.|
|[CAtlFile::Seek](#seek)|Этот метод используется для перемещения файла указателя файла.|
|[CAtlFile::SetSize](#setsize)|Вызовите этот метод, чтобы задать размер файла.|
|[CAtlFile::UnlockRange](#unlockrange)|Вызовите этот метод, чтобы разблокировать область файла.|
|[CAtlFile::Write](#write)|Этот метод используется для записи данных в файл, начиная с позиции, указанной проверкой указатель файла.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание:|
|----------|-----------------|
|[CAtlFile::m_pTM](#m_ptm)|Указатель на `CAtlTransactionManager` объект|

## <a name="remarks"></a>Примечания

Этот класс используется в том случае, когда потребности обработки файлов относительно просты, но дополнительные абстракции, чем предоставляет Windows API является обязательным, не включая зависимости MFC.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CHandle](../../atl/reference/chandle-class.md)

`CAtlFile`

## <a name="requirements"></a>Требования

**Заголовок:** atlfile.h

##  <a name="catlfile"></a>  CAtlFile::CAtlFile

Конструктор.

```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```

### <a name="parameters"></a>Параметры

*file*<br/>
Объект файла.

*hFile*<br/>
Дескриптор файла.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Примечания

Конструктор копии передает право владения дескриптор файла из исходного `CAtlFile` объект для вновь созданного объекта.

##  <a name="create"></a>  CAtlFile::Create

Этот метод используется для создания или открытия файла.

```
HRESULT Create(
    LPCTSTR szFilename,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes = FILE_ATTRIBUTE_NORMAL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    HANDLE hTemplateFile = NULL) throw();
```

### <a name="parameters"></a>Параметры

*szFilename*<br/>
Имя файла.

*dwDesiredAccess*<br/>
Необходимый доступ. См. в разделе *dwDesiredAccess* в [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) в пакете Windows SDK.

*dwShareMode*<br/>
Режим общего доступа. См. в разделе *dwShareMode* в `CreateFile`.

*dwCreationDisposition*<br/>
Расположение для создания. См. в разделе *dwCreationDisposition* в `CreateFile`.

*dwFlagsAndAttributes*<br/>
Флаги и атрибуты. См. в разделе *dwFlagsAndAttributes* в `CreateFile`.

*lpsa*<br/>
Атрибуты безопасности. См. в разделе *lpSecurityAttributes* в `CreateFile`.

*hTemplateFile*<br/>
Файл шаблона. См. в разделе *hTemplateFile* в `CreateFile`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) для создания или открытия файла.

##  <a name="flush"></a>  CAtlFile::Flush

Этот метод используется для очистки буферов для файла и потере всех буферизованных данных для записи в файл.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [FlushFileBuffers](/windows/desktop/api/fileapi/nf-fileapi-flushfilebuffers) сквозной буферизированные данные в файл.

##  <a name="getoverlappedresult"></a>  CAtlFile::GetOverlappedResult

Этот метод используется для получения результатов операции перекрывающегося на файле.

```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```

### <a name="parameters"></a>Параметры

*pOverlapped*<br/>
Перекрывающуюся структуру. См. в разделе *lpOverlapped* в [GetOverlappedResult](/windows/desktop/api/ioapiset/nf-ioapiset-getoverlappedresult) в пакете Windows SDK.

*dwBytesTransferred*<br/>
Число переданных байтов. См. в разделе *lpNumberOfBytesTransferred* в `GetOverlappedResult`.

*bWait*<br/>
Параметр ожидания. См. в разделе *bWait* в `GetOverlappedResult`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [GetOverlappedResult](/windows/desktop/api/ioapiset/nf-ioapiset-getoverlappedresult) для получения результатов операции перекрывающегося на файле.

##  <a name="getposition"></a>  CAtlFile::GetPosition

Этот метод используется для получения текущего положения указателя файла.

```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Позиция, в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer) для получения текущего положения указателя файла.

##  <a name="getsize"></a>  CAtlFile::GetSize

Вызовите этот метод, чтобы получить размер файла в байтах.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Параметры

*nLen*<br/>
Число байтов в файле.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [GetFileSize](/windows/desktop/api/fileapi/nf-fileapi-getfilesize) для получения размера файла в байтах.

##  <a name="lockrange"></a>  CAtlFile::LockRange

Вызовите этот метод, чтобы заблокировать регион, в файле, чтобы запретить доступ к нему другими процессами.

```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Позиция в файле, где должна начинаться блокировки.

*nCount*<br/>
Длина диапазона байтов, который будет заблокирован.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [LockFile](/windows/desktop/api/fileapi/nf-fileapi-lockfile) снять блокировку с области в файле. Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Вы можете заблокировать более одной области файла, но разрешены не перекрывающихся областей. При снятии блокировки области, с помощью [CAtlFile::UnlockRange](#unlockrange), диапазон байтов должен точно соответствовать регион, который ранее был заблокирован. `LockRange` не объединяет смежные разделы; Если два заблокированных раздела являются смежными, чтобы разблокировать каждого отдельно.

##  <a name="m_ptm"></a>  CAtlFile::m_pTM

Указатель на `CAtlTransactionManager` объект.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Примечания

##  <a name="read"></a>  CAtlFile::Read

Этот метод используется для чтения данных из файла, начиная с позиции, указанной проверкой указатель файла.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();
```

### <a name="parameters"></a>Параметры

*pBuffer*<br/>
Указатель на буфер, который будет получать данные, считанные из файла.

*nBufSize*<br/>
Размер буфера в байтах.

*nBytesRead*<br/>
Количество прочитанных байтов.

*pOverlapped*<br/>
Перекрывающуюся структуру. См. в разделе *lpOverlapped* в [ReadFile](/windows/desktop/api/fileapi/nf-fileapi-readfile) в пакете Windows SDK.

*pfnCompletionRoutine*<br/>
Подпрограммы завершения. См. в разделе *lpCompletionRoutine* в [ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Первые три формы вызвать [ReadFile](/windows/desktop/api/fileapi/nf-fileapi-readfile), последний [ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex) для чтения данных из файла. Используйте [CAtlFile::Seek](#seek) для перемещения указателя файла.

##  <a name="seek"></a>  CAtlFile::Seek

Этот метод используется для перемещения файла указателя файла.

```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Параметры

*nOffset*<br/>
Смещение от начальной точки, заданной параметром *dwFrom*.

*dwFrom*<br/>
Начальная точка (FILE_BEGIN, FILE_CURRENT или FILE_END).

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer) для перемещения указателя файла.

##  <a name="setsize"></a>  CAtlFile::SetSize

Вызовите этот метод, чтобы задать размер файла.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Параметры

*nNewLen*<br/>
Новая длина файла в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer) и [SetEndOfFile](/windows/desktop/api/fileapi/nf-fileapi-setendoffile) для установки размера файла. При возвращении указатель файла находится в конце файла.

##  <a name="unlockrange"></a>  CAtlFile::UnlockRange

Вызовите этот метод, чтобы разблокировать область файла.

```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Позиция в файле, где должна начинаться снятие блокировки.

*nCount*<br/>
Длина диапазона байтов должен быть разблокирован.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [UnlockFile](/windows/desktop/api/fileapi/nf-fileapi-unlockfile) для разблокировки область файла.

##  <a name="write"></a>  CAtlFile::Write

Этот метод используется для записи данных в файл, начиная с позиции, указанной проверкой указатель файла.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();
```

### <a name="parameters"></a>Параметры

*pBuffer*<br/>
Буфер, содержащий данные для записи в файл.

*nBufSize*<br/>
Число байтов, передаваемых из буфера.

*pOverlapped*<br/>
Перекрывающуюся структуру. См. в разделе *lpOverlapped* в [WriteFile](/windows/desktop/api/fileapi/nf-fileapi-writefile) в пакете Windows SDK.

*pfnCompletionRoutine*<br/>
Подпрограммы завершения. См. в разделе *lpCompletionRoutine* в [WriteFileEx](/windows/desktop/api/fileapi/nf-fileapi-writefileex) в пакете Windows SDK.

*pnBytesWritten*<br/>
Байты для записи.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Первые три формы вызвать [WriteFile](/windows/desktop/api/fileapi/nf-fileapi-writefile), последний вызовы [WriteFileEx](/windows/desktop/api/fileapi/nf-fileapi-writefileex) для записи данных в файл. Используйте [CAtlFile::Seek](#seek) для перемещения указателя файла.

## <a name="see-also"></a>См. также

[Пример бегущей строки](../../visual-cpp-samples.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс CHandle](../../atl/reference/chandle-class.md)
