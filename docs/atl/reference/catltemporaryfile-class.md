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
ms.openlocfilehash: 605e4bcbe7208b18d8d1a50507e8e142a93bde5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321312"
---
# <a name="catltemporaryfile-class"></a>Класс CAtlTemporaryFile

Этот класс предоставляет методы создания и использования временного файла.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CAtlTemporaryFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlВременнофайл::CAtlВременноЕФайл](#catltemporaryfile)|Конструктор.|
|[CAtlВременноеФайл:::::::CAtlTemporaryFile](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlВременноЕФайл::Закрыть](#close)|Вызовите этот метод, чтобы закрыть временный файл и либо удалить его содержимое или хранить его под указанным именем файла.|
|[CAtlВременноФайл::Создание](#create)|Вызовите этот метод, чтобы создать временный файл.|
|[CAtlВременноЕФайл::Флеш](#flush)|Вызовите этот метод, чтобы заставить любые данные, оставшиеся в буфере файла, быть записаны во временный файл.|
|[CAtlВременноеФайл::GetPosition](#getposition)|Вызовите этот метод, чтобы получить текущее положение указателя файла.|
|[CAtlВременноеФайл::GetSize](#getsize)|Вызовите этот метод, чтобы получить размер байтов временного файла.|
|[CAtlВременноеФайл::HandsOff](#handsoff)|Вызовите этот метод, чтобы `CAtlTemporaryFile` отмежевать файл от объекта.|
|[CAtlВременноеФайл::HandsOn](#handson)|Вызовите этот метод, чтобы открыть существующий временный файл и расположить указатель в конце файла.|
|[CAtlВременноеФайл::LockRange](#lockrange)|Вызовите этот метод, чтобы заблокировать область в файле, чтобы предотвратить доступ к нему в других процессах.|
|[CAtlВременноЕФайл::Читать](#read)|Вызовите этот метод для чтения данных из временного файла, начиная с позиции, указанной указателем файла.|
|[CAtlВременноЕФайл::Ищите](#seek)|Вызовите этот метод, чтобы переместить указатель файла временного файла.|
|[CAtlВременноеФайл::SetSize](#setsize)|Вызовите этот метод, чтобы установить размер временного файла.|
|[CAtlВременноеФайл::TempFileName](#tempfilename)|Вызовите этот метод, чтобы вернуть имя временного файла.|
|[CAtlВременноеФайл::UnlockRange](#unlockrange)|Вызовите этот метод, чтобы разблокировать область временного файла.|
|[CAtlВременноФайл::Написать](#write)|Вызовите этот метод, чтобы записать данные во временный файл, начиная с позиции, указанной указателем файла.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAtlВременноЕФайл::оператор HANDLE](#operator_handle)|Возвращает ручку во временный файл.|

## <a name="remarks"></a>Remarks

`CAtlTemporaryFile`упрощает создание и использование временного файла. Файл автоматически называется, открывается, закрывается и удаляется. Если содержимое файла требуется после закрытия файла, они могут быть сохранены в новом файле с указанным именем.

## <a name="requirements"></a>Требования

**Заголовок:** atlfile.h

## <a name="example"></a>Пример

Смотрите пример [для CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="catltemporaryfile"></a>CAtlВременнофайл::CAtlВременноЕФайл

Конструктор.

```
CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Remarks

Файл фактически не открывается до тех пор, пока не будет сделан вызов [cAtlTemporaryFile::Create](#create).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="dtor"></a>CAtlВременноеФайл:::::::CAtlTemporaryFile

Деструктор

```
~CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Remarks

Деструктор вызывает [CAtlTemporaryFile::Закрыть](#close).

## <a name="catltemporaryfileclose"></a><a name="close"></a>CAtlВременноЕФайл::Закрыть

Вызовите этот метод, чтобы закрыть временный файл и либо удалить его содержимое или хранить его под указанным именем файла.

```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```

### <a name="parameters"></a>Параметры

*szNewName*<br/>
Имя нового файла для хранения содержимого временного файла. Если этот аргумент NULL, содержимое временного файла удаляется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="example"></a>Пример

Смотрите пример [для CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfilecreate"></a><a name="create"></a>CAtlВременноФайл::Создание

Вызовите этот метод, чтобы создать временный файл.

```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```

### <a name="parameters"></a>Параметры

*pszDir*<br/>
Путь для временного файла. Если это NULL, [GetTempPath](/windows/win32/api/fileapi/nf-fileapi-gettemppathw) будет вызван для присвоения пути.

*dwDesiredAccess*<br/>
Необходимый доступ. Смотрите *dwDesiredAccess* в [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilew) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="example"></a>Пример

Смотрите пример [для CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfileflush"></a><a name="flush"></a>CAtlВременноЕФайл::Флеш

Вызовите этот метод, чтобы заставить любые данные, оставшиеся в буфере файла, быть записаны во временный файл.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Похож на [CAtlTemporaryFile::HandsOff](#handsoff), за исключением того, что файл не закрыт.

### <a name="example"></a>Пример

Смотрите пример [для CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfilegetposition"></a><a name="getposition"></a>CAtlВременноеФайл::GetPosition

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

Чтобы изменить положение указателя файла, используйте [CAtlTemporaryFile::Seek](#seek).

## <a name="catltemporaryfilegetsize"></a><a name="getsize"></a>CAtlВременноеФайл::GetSize

Вызовите этот метод, чтобы получить размер байтов временного файла.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Параметры

*nЛен*<br/>
Количество байтов в файле.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catltemporaryfilehandsoff"></a><a name="handsoff"></a>CAtlВременноеФайл::HandsOff

Вызовите этот метод, чтобы `CAtlTemporaryFile` отмежевать файл от объекта.

```
HRESULT HandsOff() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

`HandsOff`и [CAtlTemporaryFile::HandsOn](#handson) используются для отсоединения файла от объекта и при необходимости прикреплять его. `HandsOff`заставит заставить любые данные, оставшиеся в буфере файла, быть записаны на временный файл, а затем закрыть файл. Если вы хотите закрыть и удалить файл на постоянной основе, или если вы хотите закрыть и сохранить содержимое файла с данным именем, используйте [CAtlTemporaryFile::Закрыть](#close).

## <a name="catltemporaryfilehandson"></a><a name="handson"></a>CAtlВременноеФайл::HandsOn

Вызовите этот метод, чтобы открыть существующий временный файл и расположить указатель в конце файла.

```
HRESULT HandsOn() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

[CAtlTemporaryFile::HandsOff](#handsoff) `HandsOn` и используются для отсоединения файла от объекта и при необходимости прикреплять его.

## <a name="catltemporaryfilelockrange"></a><a name="lockrange"></a>CAtlВременноеФайл::LockRange

Вызовите этот метод, чтобы заблокировать область во временном файле, чтобы предотвратить доступ к нему в других процессах.

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

Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Можно заблокировать несколько областей файла, но перекрывающиеся области не допускаются. Чтобы успешно разблокировать область, используйте [CAtlTemporaryFile::UnlockRange,](#unlockrange)гарантируя, что диапазон байт точно соответствует региону, который ранее был заблокирован. `LockRange`не объединяет прилегающие регионы; если два заблокированных региона смываются, необходимо разблокировать каждый отдельно.

## <a name="catltemporaryfileoperator-handle"></a><a name="operator_handle"></a>CAtlВременноЕФайл::оператор HANDLE

Возвращает ручку во временный файл.

```
operator HANDLE() throw();
```

## <a name="catltemporaryfileread"></a><a name="read"></a>CAtlВременноЕФайл::Читать

Вызовите этот метод для чтения данных из временного файла, начиная с позиции, указанной указателем файла.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```

### <a name="parameters"></a>Параметры

*pBuffer*<br/>
Указатель на буфер, который будет получать данные, считываемые из файла.

*nBufSize*<br/>
Размер буфера в байтах.

*nBytesЧитаться*<br/>
Число переданных байтов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызовы [CAtlFile::Читать](../../atl/reference/catlfile-class.md#read). Чтобы изменить положение указателя файла, позвоните [cAtlTemporaryFile::Seek](#seek).

### <a name="example"></a>Пример

Смотрите пример [для CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfileseek"></a><a name="seek"></a>CAtlВременноЕФайл::Ищите

Вызовите этот метод, чтобы переместить указатель файла временного файла.

```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Параметры

*nOffset*<br/>
Смещение, в байтах, от отправной точки, данной *dwFrom.*

*dwFrom*<br/>
Отправная точка (FILE_BEGIN, FILE_CURRENT или FILE_END).

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызовы [CAtlFile::Ищите](../../atl/reference/catlfile-class.md#seek). Чтобы получить текущую позицию указателя файла, позвоните [CAtlTemporaryFile::GetPosition](#getposition).

### <a name="example"></a>Пример

Смотрите пример [для CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfilesetsize"></a><a name="setsize"></a>CAtlВременноеФайл::SetSize

Вызовите этот метод, чтобы установить размер временного файла.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Параметры

*nNewLen*<br/>
Новая длина файла в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызовы [CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize). В обратном порядке указатель файла позиционируется в конце файла.

## <a name="catltemporaryfiletempfilename"></a><a name="tempfilename"></a>CAtlВременноеФайл::TempFileName

Вызовите этот метод, чтобы вернуть имя временного файла.

```
LPCTSTR TempFileName() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает LPCTSTR, указывающий на имя файла.

### <a name="remarks"></a>Remarks

Имя файла генерируется в [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile) с вызовом функции [GetTempFile](/windows/win32/api/fileapi/nf-fileapi-gettempfilenamew)Windows SDK. Расширение файла всегда будет "TFR" для временного файла.

## <a name="catltemporaryfileunlockrange"></a><a name="unlockrange"></a>CAtlВременноеФайл::UnlockRange

Вызовите этот метод, чтобы разблокировать область временного файла.

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

Вызовы [CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange).

## <a name="catltemporaryfilewrite"></a><a name="write"></a>CAtlВременноФайл::Написать

Вызовите этот метод, чтобы записать данные во временный файл, начиная с позиции, указанной указателем файла.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```

### <a name="parameters"></a>Параметры

*pBuffer*<br/>
Буфер, содержащий данные, которые будут записаны в файл.

*nBufSize*<br/>
Количество байтов, которые будут перенесены из буфера.

*pnBytesНаписано*<br/>
Количество записанных байт.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызовы [CAtlFile::Запись](../../atl/reference/catlfile-class.md#write).

### <a name="example"></a>Пример

Смотрите пример [для CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CAtlFile](../../atl/reference/catlfile-class.md)
