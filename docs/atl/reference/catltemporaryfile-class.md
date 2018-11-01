---
title: Класс CAtlTemporaryFile
ms.date: 11/04/2016
f1_keywords:
- CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::Close
- ATLFILE/ATL::CAtlTemporaryFile::Create
- ATLFILE/ATL::CAtlTemporaryFile::Flush
- ATLFILE/ATL::CAtlTemporaryFile::GetPosition
- ATLFILE/ATL::CAtlTemporaryFile::GetSize
- ATLFILE/ATL::CAtlTemporaryFile::HandsOff
- ATLFILE/ATL::CAtlTemporaryFile::HandsOn
- ATLFILE/ATL::CAtlTemporaryFile::LockRange
- ATLFILE/ATL::CAtlTemporaryFile::Read
- ATLFILE/ATL::CAtlTemporaryFile::Seek
- ATLFILE/ATL::CAtlTemporaryFile::SetSize
- ATLFILE/ATL::CAtlTemporaryFile::TempFileName
- ATLFILE/ATL::CAtlTemporaryFile::UnlockRange
- ATLFILE/ATL::CAtlTemporaryFile::Write
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
ms.openlocfilehash: f440476db3618c24f0fd1cfbfe028c959517a607
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642282"
---
# <a name="catltemporaryfile-class"></a>Класс CAtlTemporaryFile

Этот класс предоставляет методы для создания и использования временных файлов.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAtlTemporaryFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|Конструктор.|
|[CAtlTemporaryFile:: ~ CAtlTemporaryFile](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlTemporaryFile::Close](#close)|Вызовите этот метод, чтобы закрыть во временный файл и удалить его содержимое или сохранять их под именем указанного файла.|
|[CAtlTemporaryFile::Create](#create)|Вызовите этот метод, чтобы создать временный файл.|
|[CAtlTemporaryFile::Flush](#flush)|Этот метод используется для принудительного любые данные, остающихся в буфере файл для записи во временный файл.|
|[CAtlTemporaryFile::GetPosition](#getposition)|Этот метод используется для получения текущего положения указателя файла.|
|[CAtlTemporaryFile::GetSize](#getsize)|Вызовите этот метод, чтобы получить размер в байтах временного файла.|
|[CAtlTemporaryFile::HandsOff](#handsoff)|Вызовите этот метод, чтобы файл отделяется от `CAtlTemporaryFile` объекта.|
|[CAtlTemporaryFile::HandsOn](#handson)|Вызовите этот метод, чтобы открыть существующий временный файл и поместите указатель в конец файла.|
|[CAtlTemporaryFile::LockRange](#lockrange)|Вызовите этот метод, чтобы заблокировать регион, в файле, чтобы запретить доступ к нему другими процессами.|
|[CAtlTemporaryFile::Read](#read)|Этот метод используется для чтения данных из временного файла, начиная с позиции, указанной проверкой указатель файла.|
|[CAtlTemporaryFile::Seek](#seek)|Этот метод используется для перемещения указателя файла временный файл.|
|[CAtlTemporaryFile::SetSize](#setsize)|Вызовите этот метод, чтобы задать размер временного файла.|
|[CAtlTemporaryFile::TempFileName](#tempfilename)|Этот метод используется для возврата имени временного файла.|
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|Вызовите этот метод, чтобы разблокировать область временного файла.|
|[CAtlTemporaryFile::Write](#write)|Этот метод используется для записи данных во временный файл, начиная с позиции, указанной проверкой указатель файла.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAtlTemporaryFile::operator ДЕСКРИПТОР](#operator_handle)|Возвращает дескриптор во временный файл.|

## <a name="remarks"></a>Примечания

`CAtlTemporaryFile` позволяет легко создавать и использовать временный файл. Файл является автоматически с именем, открытия, закрытия и удален. Если содержимое файла требуется после закрытия файла, они могут сохраняться в новый файл с указанным именем.

## <a name="requirements"></a>Требования

**Заголовок:** atlfile.h

## <a name="example"></a>Пример

См. в примере [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="catltemporaryfile"></a>  CAtlTemporaryFile::CAtlTemporaryFile

Конструктор.

```
CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Примечания

Файл не открыт в действительности, пока выполняется вызов для [CAtlTemporaryFile::Create](#create).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]

##  <a name="dtor"></a>  CAtlTemporaryFile:: ~ CAtlTemporaryFile

Деструктор

```
~CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Примечания

Деструктор вызывает [CAtlTemporaryFile::Close](#close).

##  <a name="close"></a>  CAtlTemporaryFile::Close

Вызовите этот метод, чтобы закрыть во временный файл и удалить его содержимое или сохранять их под именем указанного файла.

```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```

### <a name="parameters"></a>Параметры

*szNewName*<br/>
Имя для нового файла для хранения временных файлов в содержимое. Если этот аргумент равен NULL, содержимое временный файл удаляется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="example"></a>Пример

См. в примере [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="create"></a>  CAtlTemporaryFile::Create

Вызовите этот метод, чтобы создать временный файл.

```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```

### <a name="parameters"></a>Параметры

*pszDir*<br/>
Путь для временного файла. Если имеет значение NULL, [GetTempPath](/windows/desktop/api/fileapi/nf-fileapi-gettemppatha) будет вызываться для присвоения пути.

*dwDesiredAccess*<br/>
Необходимый доступ. См. в разделе *dwDesiredAccess* в [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="example"></a>Пример

См. в примере [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="flush"></a>  CAtlTemporaryFile::Flush

Этот метод используется для принудительного любые данные, остающихся в буфере файл для записи во временный файл.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Аналогичную [CAtlTemporaryFile::HandsOff](#handsoff), за исключением того, что файл не закрыт.

### <a name="example"></a>Пример

См. в примере [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="getposition"></a>  CAtlTemporaryFile::GetPosition

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

Для изменения положения указателя файла, используйте [CAtlTemporaryFile::Seek](#seek).

##  <a name="getsize"></a>  CAtlTemporaryFile::GetSize

Вызовите этот метод, чтобы получить размер в байтах временного файла.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Параметры

*nLen*<br/>
Число байтов в файле.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="handsoff"></a>  CAtlTemporaryFile::HandsOff

Вызовите этот метод, чтобы файл отделяется от `CAtlTemporaryFile` объекта.

```
HRESULT HandsOff() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

`HandsOff` и [CAtlTemporaryFile::HandsOn](#handson) используются для файл отделяется от объекта и подсоедините ее при необходимости. `HandsOff` будет принудительно любые данные, остающихся в буфере файл для записи во временный файл и закройте файл. Если вы хотите закрыть и окончательно удалить файл, или если вы хотите закрыть и сохранить содержимое файла с заданным именем, используйте [CAtlTemporaryFile::Close](#close).

##  <a name="handson"></a>  CAtlTemporaryFile::HandsOn

Вызовите этот метод, чтобы открыть существующий временный файл и поместите указатель в конец файла.

```
HRESULT HandsOn() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

[CAtlTemporaryFile::HandsOff](#handsoff) и `HandsOn` используются для файл отделяется от объекта и подсоедините ее при необходимости.

##  <a name="lockrange"></a>  CAtlTemporaryFile::LockRange

Вызовите этот метод, чтобы заблокировать регион, в временный файл, чтобы запретить доступ к нему другими процессами.

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

Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Вы можете заблокировать более одной области файла, но разрешены не перекрывающихся областей. Чтобы успешно разблокировать региона, используйте [CAtlTemporaryFile::UnlockRange](#unlockrange), обеспечивая диапазон байтов в точности соответствует области, который ранее был заблокирован. `LockRange` не объединяет смежные разделы; Если два заблокированных раздела являются смежными, чтобы разблокировать каждого отдельно.

##  <a name="operator_handle"></a>  CAtlTemporaryFile::operator ДЕСКРИПТОР

Возвращает дескриптор во временный файл.

```
operator HANDLE() throw();
```

##  <a name="read"></a>  CAtlTemporaryFile::Read

Этот метод используется для чтения данных из временного файла, начиная с позиции, указанной проверкой указатель файла.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```

### <a name="parameters"></a>Параметры

*pBuffer*<br/>
Указатель на буфер, который будет получать данные, считанные из файла.

*nBufSize*<br/>
Размер буфера в байтах.

*nBytesRead*<br/>
Количество прочитанных байтов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [CAtlFile::Read](../../atl/reference/catlfile-class.md#read). Чтобы изменить положение указателя файла, вызовите [CAtlTemporaryFile::Seek](#seek).

### <a name="example"></a>Пример

См. в примере [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="seek"></a>  CAtlTemporaryFile::Seek

Этот метод используется для перемещения указателя файла временный файл.

```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Параметры

*nOffset*<br/>
Смещение в байтах от начала точки, заданной параметром *dwFrom.*

*dwFrom*<br/>
Начальная точка (FILE_BEGIN, FILE_CURRENT или FILE_END).

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek). Для получения текущего положения указателя файла, вызовите [CAtlTemporaryFile::GetPosition](#getposition).

### <a name="example"></a>Пример

См. в примере [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="setsize"></a>  CAtlTemporaryFile::SetSize

Вызовите этот метод, чтобы задать размер временного файла.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Параметры

*nNewLen*<br/>
Новая длина файла в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize). При возвращении указатель файла находится в конце файла.

##  <a name="tempfilename"></a>  CAtlTemporaryFile::TempFileName

Вызовите этот метод для возврата имени временного файла.

```
LPCTSTR TempFileName() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает LPCTSTR, указывающий на имя файла.

### <a name="remarks"></a>Примечания

Имя файла создается в [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile) вызовом [GetTempFile](/windows/desktop/api/fileapi/nf-fileapi-gettempfilenamea)функции пакета SDK для Windows. Расширение файла всегда будет «TFR» для временного файла.

##  <a name="unlockrange"></a>  CAtlTemporaryFile::UnlockRange

Вызовите этот метод, чтобы разблокировать область временного файла.

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

Вызовы [CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange).

##  <a name="write"></a>  CAtlTemporaryFile::Write

Этот метод используется для записи данных во временный файл, начиная с позиции, указанной проверкой указатель файла.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```

### <a name="parameters"></a>Параметры

*pBuffer*<br/>
Буфер, содержащий данные для записи в файл.

*nBufSize*<br/>
Число байтов, передаваемых из буфера.

*pnBytesWritten*<br/>
Число записанных байтов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [CAtlFile::Write](../../atl/reference/catlfile-class.md#write).

### <a name="example"></a>Пример

См. в примере [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс CAtlFile](../../atl/reference/catlfile-class.md)
