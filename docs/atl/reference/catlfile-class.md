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
ms.openlocfilehash: 39f323874ccde5178722235b9beb34c2572407a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318965"
---
# <a name="catlfile-class"></a>Класс CAtlFile

Этот класс обеспечивает тонкую обертку вокруг API обработки файлов Windows.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

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

|Имя|Описание|
|----------|-----------------|
|[CAtlFile::Создание](#create)|Вызовите этот метод, чтобы создать или открыть файл.|
|[CAtlFile::Флеш](#flush)|Вызов иметод, чтобы очистить буферы для файла и привести к тому, что все буферизированные данные будут записаны в файл.|
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|Вызовите этот метод, чтобы получить результаты перекрываемых операций в файле.|
|[CAtlFile::GetPosition](#getposition)|Вызовите этот метод, чтобы получить текущее положение указателя файла из файла.|
|[CAtlFile::GetSize](#getsize)|Вызовите этот метод, чтобы получить размер байтов файла.|
|[CAtlFile::LockRange](#lockrange)|Вызовите этот метод, чтобы заблокировать область в файле, чтобы предотвратить доступ к нему в других процессах.|
|[CAtlFile::Читать](#read)|Вызовите этот метод для чтения данных из файла, начиная с позиции, указанной указателем файла.|
|[CAtlFile::Ищите](#seek)|Вызовите этот метод для перемещения указателя файла файла.|
|[CAtlFile::SetSize](#setsize)|Вызовите этот метод, чтобы установить размер файла.|
|[CAtlFile::UnlockRange](#unlockrange)|Вызовите этот метод, чтобы разблокировать область файла.|
|[CAtlFile::Написать](#write)|Вызовите этот метод, чтобы записать данные в файл, начиная с позиции, указанной указателем файла.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAtlFile::m_pTM](#m_ptm)|Указатель `CAtlTransactionManager` на объект|

## <a name="remarks"></a>Remarks

Используйте этот класс, когда потребности в обработке файлов относительно просты, но требуется больше абстракции, чем предоставляет API Windows, без включения зависимостей MFC.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Chandle](../../atl/reference/chandle-class.md)

`CAtlFile`

## <a name="requirements"></a>Требования

**Заголовок:** atlfile.h

## <a name="catlfilecatlfile"></a><a name="catlfile"></a>CAtlFile::CAtlFile

Конструктор.

```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```

### <a name="parameters"></a>Параметры

*Файл*<br/>
Объект файла.

*hFile*<br/>
Ручка файла.

*Ptm*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Remarks

Конструктор копирования передает право собственности на `CAtlFile` рукоятку файла с исходного объекта на вновь построенный объект.

## <a name="catlfilecreate"></a><a name="create"></a>CAtlFile::Создание

Вызовите этот метод, чтобы создать или открыть файл.

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
Необходимый доступ. Смотрите *dwDesiredAccess* в [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilew) в Windows SDK.

*dwShareMode*<br/>
Режим обмена. Смотрите *dwShareMode* в `CreateFile`.

*dwCreationDisposition*<br/>
Расположение создания. Смотрите *dwCreationDisposition* в `CreateFile`.

*dwFlagsAndАтрибуты*<br/>
Флаги и атрибуты. Смотрите *dwFlagsAndАтрибуты* в `CreateFile`.

*лза*<br/>
Атрибуты безопасности. Смотрите *lpSecurityАтрибуты* в `CreateFile`.

*hTemplateFile*<br/>
Файл шаблона. Смотрите *hTemplateFile* в `CreateFile`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызовы [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilew) для создания или открытия файла.

## <a name="catlfileflush"></a><a name="flush"></a>CAtlFile::Флеш

Вызов иметод, чтобы очистить буферы для файла и привести к тому, что все буферизированные данные будут записаны в файл.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызывает [FlushFileBuffers,](/windows/win32/api/fileapi/nf-fileapi-flushfilebuffers) чтобы смыть буферизированные данные в файл.

## <a name="catlfilegetoverlappedresult"></a><a name="getoverlappedresult"></a>CAtlFile::GetOverlappedResult

Вызовите этот метод, чтобы получить результаты перекрываемых операций в файле.

```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```

### <a name="parameters"></a>Параметры

*pOverlapped*<br/>
Перекрытая структура. Смотрите *lpOverlapped* в [GetOverlappedResult](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) в Windows SDK.

*dwBytesПеренесено*<br/>
Байты перенесены. Смотрите *lpNumberOfBytesПеренесено* в `GetOverlappedResult`.

*bПодождите*<br/>
Опция ожидания. Смотрите *bWait* в `GetOverlappedResult`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызовы [GetOverlappedResult,](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) чтобы получить результаты перекрываемых операций в файле.

## <a name="catlfilegetposition"></a><a name="getposition"></a>CAtlFile::GetPosition

Вызовите этот метод, чтобы получить текущее положение указателя файла.

```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Положение в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызывает [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) для того чтобы получить в настоящее время положение указателя архива.

## <a name="catlfilegetsize"></a><a name="getsize"></a>CAtlFile::GetSize

Вызовите этот метод, чтобы получить размер байтов файла.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Параметры

*nЛен*<br/>
Количество байтов в файле.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызывает [GetFileSize](/windows/win32/api/fileapi/nf-fileapi-getfilesize) для того чтобы получить размер в байтах архива.

## <a name="catlfilelockrange"></a><a name="lockrange"></a>CAtlFile::LockRange

Вызовите этот метод, чтобы заблокировать область в файле, чтобы предотвратить доступ к нему в других процессах.

```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Положение в файле, где должен начаться блокировка.

*Ncount*<br/>
Длина диапазона байт, который будет заблокирован.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызывает [LockFile](/windows/win32/api/fileapi/nf-fileapi-lockfile) для блокировки области в файле. Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Можно заблокировать несколько областей файла, но перекрывающиеся области не допускаются. При разблокировке региона с помощью [CAtlFile::UnlockRange](#unlockrange)диапазон байт должен точно соответствовать региону, который ранее был заблокирован. `LockRange`не объединяет прилегающие регионы; если два заблокированных региона смываются, необходимо разблокировать каждый отдельно.

## <a name="catlfilem_ptm"></a><a name="m_ptm"></a>CAtlFile::m_pTM

Указатель на `CAtlTransactionManager` объект.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Remarks

## <a name="catlfileread"></a><a name="read"></a>CAtlFile::Читать

Вызовите этот метод для чтения данных из файла, начиная с позиции, указанной указателем файла.

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
Указатель на буфер, который будет получать данные, считываемые из файла.

*nBufSize*<br/>
Размер буфера в байтах.

*nBytesЧитаться*<br/>
Число переданных байтов.

*pOverlapped*<br/>
Перекрытая структура. Смотрите *lpOverlapped* в [ReadFile](/windows/win32/api/fileapi/nf-fileapi-readfile) в Windows SDK.

*pfnCompletionRoutine*<br/>
Процедура завершения. Смотрите *lpCompletionRoutine* в [ReadFileEx](/windows/win32/api/fileapi/nf-fileapi-readfileex) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Первые три формы вызова [ReadFile](/windows/win32/api/fileapi/nf-fileapi-readfile), последний [ReadFileEx](/windows/win32/api/fileapi/nf-fileapi-readfileex) читать данные из файла. Используйте [CAtlFile::Ищите,](#seek) чтобы переместить указатель файла.

## <a name="catlfileseek"></a><a name="seek"></a>CAtlFile::Ищите

Вызовите этот метод для перемещения указателя файла файла.

```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Параметры

*nOffset*<br/>
Смещение от отправной точки предоставлено *dwFrom*.

*dwFrom*<br/>
Отправная точка (FILE_BEGIN, FILE_CURRENT или FILE_END).

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызывает [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) для перемещения указателя файла.

## <a name="catlfilesetsize"></a><a name="setsize"></a>CAtlFile::SetSize

Вызовите этот метод, чтобы установить размер файла.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Параметры

*nNewLen*<br/>
Новая длина файла в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызывает [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) и [SetEndOfFile,](/windows/win32/api/fileapi/nf-fileapi-setendoffile) чтобы установить размер файла. В обратном порядке указатель файла позиционируется в конце файла.

## <a name="catlfileunlockrange"></a><a name="unlockrange"></a>CAtlFile::UnlockRange

Вызовите этот метод, чтобы разблокировать область файла.

```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Положение в файле, где должна начаться разблокировка.

*Ncount*<br/>
Длина диапазона байт, который будет разблокирован.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызовы [UnlockFile,](/windows/win32/api/fileapi/nf-fileapi-unlockfile) чтобы разблокировать область файла.

## <a name="catlfilewrite"></a><a name="write"></a>CAtlFile::Написать

Вызовите этот метод, чтобы записать данные в файл, начиная с позиции, указанной указателем файла.

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
Буфер, содержащий данные, которые будут записаны в файл.

*nBufSize*<br/>
Количество байтов, которые будут перенесены из буфера.

*pOverlapped*<br/>
Перекрытая структура. Смотрите *lpOverlapped* в [WriteFile](/windows/win32/api/fileapi/nf-fileapi-writefile) в Windows SDK.

*pfnCompletionRoutine*<br/>
Процедура завершения. Смотрите *lpCompletionRoutine* в [WriteFileEx](/windows/win32/api/fileapi/nf-fileapi-writefileex) в Windows SDK.

*pnBytesНаписано*<br/>
Байты написаны.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Первые три формы называют [WriteFile](/windows/win32/api/fileapi/nf-fileapi-writefile), последние звонки [WriteFileEx,](/windows/win32/api/fileapi/nf-fileapi-writefileex) чтобы написать данные в файл. Используйте [CAtlFile::Ищите,](#seek) чтобы переместить указатель файла.

## <a name="see-also"></a>См. также раздел

[Маркес](../../overview/visual-cpp-samples.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CHandle](../../atl/reference/chandle-class.md)
