---
title: Класс CInternetFile
ms.date: 11/04/2016
f1_keywords:
- CInternetFile
- AFXINET/CInternetFile
- AFXINET/CInternetFile::CInternetFile
- AFXINET/CInternetFile::Abort
- AFXINET/CInternetFile::Close
- AFXINET/CInternetFile::Flush
- AFXINET/CInternetFile::GetLength
- AFXINET/CInternetFile::Read
- AFXINET/CInternetFile::ReadString
- AFXINET/CInternetFile::Seek
- AFXINET/CInternetFile::SetReadBufferSize
- AFXINET/CInternetFile::SetWriteBufferSize
- AFXINET/CInternetFile::Write
- AFXINET/CInternetFile::WriteString
- AFXINET/CInternetFile::m_hFile
helpviewer_keywords:
- CInternetFile [MFC], CInternetFile
- CInternetFile [MFC], Abort
- CInternetFile [MFC], Close
- CInternetFile [MFC], Flush
- CInternetFile [MFC], GetLength
- CInternetFile [MFC], Read
- CInternetFile [MFC], ReadString
- CInternetFile [MFC], Seek
- CInternetFile [MFC], SetReadBufferSize
- CInternetFile [MFC], SetWriteBufferSize
- CInternetFile [MFC], Write
- CInternetFile [MFC], WriteString
- CInternetFile [MFC], m_hFile
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
ms.openlocfilehash: e3f1a7167f5464423754951764c4441513197841
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372391"
---
# <a name="cinternetfile-class"></a>Класс CInternetFile

Позволяет получить доступ к файлам в удаленных системах, которые используют интернет-протоколы.

## <a name="syntax"></a>Синтаксис

```
class CInternetFile : public CStdioFile
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInternetFile::: ИнтернетFile](#cinternetfile)|Формирует объект `CInternetFile`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CInternetFile::Аборт](#abort)|Закрывает файл, игнорируя все предупреждения и ошибки.|
|[CInternetFile::Закрыть](#close)|Закрывает `CInternetFile` и освобождает свои ресурсы.|
|[CInternetFile::Флеш](#flush)|Сбрасывает содержимое буфера записи и гарантирует, что данные в памяти записаны на целевую машину.|
|[CInternetFile::GetLength](#getlength)|Возвращает размер файла.|
|[CInternetFile::Читать](#read)|Читает количество указанных байтов.|
|[CInternetFile::ReadString](#readstring)|Читает поток символов.|
|[CInternetFile::Ищите](#seek)|Перемещает указатель в открытый файл.|
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|Устанавливает размер буфера, в котором будут читаться данные.|
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|Устанавливает размер буфера, в котором будут писаться данные.|
|[CInternetFile::Write](#write)|Записывает количество указанных байтов.|
|[CInternetFile::WriteString](#writestring)|Записывает строку с нулевым завершением в файл.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CInternetFile::оператор HINTERNET](#operator_hinternet)|Оператор литья для интернет-ручки.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CInternetFile:::m_hFile](#m_hfile)|Ручка к файлу.|

## <a name="remarks"></a>Remarks

Обеспечивает базовый класс для классов файлов [CHttpFile](../../mfc/reference/chttpfile-class.md) и [CGopherFile.](../../mfc/reference/cgopherfile-class.md) Вы никогда `CInternetFile` не создаете объект напрямую. Вместо этого создайте объект одного из его производных классов, позвонив [в CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Вы также можете `CInternetFile` создать объект, позвонив [по CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).

Функциями `CInternetFile` `Open` `LockRange`участника, `UnlockRange`и `Duplicate` не реализованы для `CInternetFile`. Если вы называете `CInternetFile` эти функции на объекте, вы получите [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Чтобы узнать `CInternetFile` больше о том, как работает с другими классами МФЦ Интернет, см. [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

`CInternetFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cinternetfileabort"></a><a name="abort"></a>CInternetFile::Аборт

Закрывает файл, связанный с этим объектом, и делает файл недоступным для чтения или записи.

```
virtual void Abort();
```

### <a name="remarks"></a>Remarks

Если вы не закрыли файл перед уничтожением объекта, деструктор закрывает его для вас.

При обработке `Abort` исключений, отличается от [закрыть](#close) двумя важными способами. Во-первых, `Abort` функция не выбрасывает исключение на сбои, поскольку она игнорирует сбои. Во-вторых, `Abort` не **assert,** если файл не был открыт или был закрыт ранее.

## <a name="cinternetfilecinternetfile"></a><a name="cinternetfile"></a>CInternetFile::: ИнтернетFile

Эта функция члена вызывается при создании `CInternetFile` объекта.

```
CInternetFile(
    HINTERNET hFile,
    LPCTSTR pstrFileName,
    CInternetConnection* pConnection,
    BOOL bReadMode);

CInternetFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrFileName,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext,
    BOOL bReadMode);
```

### <a name="parameters"></a>Параметры

*hFile*<br/>
Ручка к интернет-файлу.

*pstrFileName*<br/>
Указатель на строку, содержащую имя файла.

*pConnection*<br/>
Указатель на объект [CInternetConnection.](../../mfc/reference/cinternetconnection-class.md)

*bReadMode*<br/>
Указывает, является ли файл только для чтения.

*hСессия*<br/>
Ручка для сеанса Интернета.

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера.

*Dwcontext*<br/>
Идентификатор `CInternetFile` контекста для объекта. Дополнительную информацию об идентификаторе контекста можно получить в [рамках WinInet Basics.](../../mfc/wininet-basics.md)

### <a name="remarks"></a>Remarks

Вы никогда `CInternetFile` не создаете объект напрямую. Вместо этого создайте объект одного из его производных классов, позвонив [в CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Вы также можете `CInternetFile` создать объект, позвонив [по CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).

## <a name="cinternetfileclose"></a><a name="close"></a>CInternetFile::Закрыть

Закрывает `CInternetFile` и освобождает любой из своих ресурсов.

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

Если файл был открыт для записи, есть неявный вызов [Flush,](#flush) чтобы гарантировать, что все буферизированные данные записаны на унитаз. Вы должны `Close` позвонить, когда вы закончите с помощью файла.

## <a name="cinternetfileflush"></a><a name="flush"></a>CInternetFile::Флеш

Вызов исчерг эту функцию участника, чтобы смыть содержимое буфера записи.

```
virtual void Flush();
```

### <a name="remarks"></a>Remarks

Используйте `Flush` для обеспечения того, чтобы все данные в памяти были фактически записаны на целевую машину и чтобы гарантировать, что ваша транзакция с хост-машиной завершена. `Flush`эффективен `CInternetFile` только на объектах, открытых для написания.

## <a name="cinternetfilegetlength"></a><a name="getlength"></a>CInternetFile::GetLength

Возвращает размер файла.

```
virtual ULONGLONG GetLength() const;
```

## <a name="cinternetfilem_hfile"></a><a name="m_hfile"></a>CInternetFile:::m_hFile

Ручка файла, связанная с этим объектом.

```
HINTERNET m_hFile;
```

## <a name="cinternetfileoperator-hinternet"></a><a name="operator_hinternet"></a>CInternetFile::оператор HINTERNET

Используйте этот оператор, чтобы получить ручку Windows для текущей сессии Интернета.

```
operator HINTERNET() const;
```

## <a name="cinternetfileread"></a><a name="read"></a>CInternetFile::Читать

Вызов эту функцию участника для чтения в заданную память, начиная с *lpvBuf*, указанное количество байтов, *nCount*.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Параметры

*lpBuf*<br/>
Указатель на адрес в памяти, по которому считываются данные из файла.

*Ncount*<br/>
Число записываемых байтов.

### <a name="return-value"></a>Возвращаемое значение

Количество байтов, переданных в буфер. Значение возврата может быть меньше *nCount,* если конец файла был достигнут.

### <a name="remarks"></a>Remarks

Функция возвращает количество байтов на самом деле читать - число, которое может быть меньше, чем *nCount,* если файл заканчивается. Если ошибка возникает при чтении файла, функция бросает объект [CInternetException,](../../mfc/reference/cinternetexception-class.md) который описывает ошибку. Обратите внимание, что чтение после завершения файла не является ошибкой и не может быть причиной выдачи исключения.

Чтобы обеспечить получение всех данных, приложение `CInternetFile::Read` должно продолжать вызывать метод до тех пор, пока метод не вернется к нулю.

## <a name="cinternetfilereadstring"></a><a name="readstring"></a>CInternetFile::ReadString

Вызовите эту функцию участника, чтобы прочитать поток символов, пока он не найдет новый символ строки.

```
virtual BOOL ReadString(CString& rString);

virtual LPTSTR ReadString(
    LPTSTR pstr,
    UINT nMax);
```

### <a name="parameters"></a>Параметры

*pstr*<br/>
Указатель на строку, которая будет получать строку читается.

*nMax*<br/>
Максимальное количество символов, которые будут прочитаны.

*rString*<br/>
Ссылка на объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) который получает строку чтения.

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер, содержащий простые данные, извлеченные из объекта [CInternetFile.](../../mfc/reference/cinternetfile-class.md) Независимо от типа данных буфера, передаваемого этому методу, он не выполняет никаких манипуляций с данными (например, преобразование в Unicode), поэтому необходимо сопоставить возвращенные данные в ожидаемую структуру, как если бы тип **пустоты** <strong>\*</strong> был возвращен.

NULL, если конец файла был достигнут без считывания каких-либо данных; или, если boolean, FALSE, если конец файла был достигнут без чтения каких-либо данных.

### <a name="remarks"></a>Remarks

Функция помещает полученную линию в память, на которую ссылается параметр *pstr.* Он перестает читать символы, когда он достигает максимального количества символов, указанных *nMax*. Буфер всегда получает прекращающийся нулевой характер.

Если вы `ReadString` звоните без первого вызова [SetReadBufferSize,](#setreadbuffersize)вы получите буфер 4096 байтов.

## <a name="cinternetfileseek"></a><a name="seek"></a>CInternetFile::Ищите

Вызовите эту функцию участника, чтобы переместить указатель в ранее открытый файл.

```
virtual ULONGLONG Seek(
    LONGLONG lOffset,
    UINT nFrom);
```

### <a name="parameters"></a>Параметры

*lOffset*<br/>
Смещение байтов для перемещения указателя чтения/записи в файле.

*nОт*<br/>
Относительная ссылка на смещение. Необходимо установить одно из следующих значений.

- `CFile::begin`Перемещение указателя файла *lOff* байты вперед с начала файла.

- `CFile::current`Переместите байты по файлу *lOff* из текущего положения в файле.

- `CFile::end`Переместите указатель файла *lOff* байтов из конца файла. *lOff* должен быть отрицательным, чтобы искать в существующий файл; положительные значения будут искать мимо конца файла.

### <a name="return-value"></a>Возвращаемое значение

Новый байт компенсируется с начала файла, если запрашиваемый вопрос является законным; в противном случае значение не определено и объект [CInternetException](../../mfc/reference/cinternetexception-class.md) брошен.

### <a name="remarks"></a>Remarks

Функция `Seek` позволяет случайный доступ к содержимому файла, перемещая указатель указанную сумму, абсолютно или относительно. Никакие данные фактически не читаются во время поиска.

В настоящее время вызов этой функции участника поддерживается только для данных, связанных с `CHttpFile` объектами. Он не поддерживается для FTP или суслик запросы. Если вы `Seek` вызовете одну из этих неподдерживаемых служб, она передаст вам код ошибки Win32 ERROR_INTERNET_INVALID_OPERATION.

При открытии файла указатель файла находится на смещении 0, в начале файла.

> [!NOTE]
> Использование `Seek` может привести к неявному вызову [Флеша](#flush).

### <a name="example"></a>Пример

  Смотрите пример реализации базового класса [(CFile::Seek](../../mfc/reference/cfile-class.md#seek)).

## <a name="cinternetfilesetreadbuffersize"></a><a name="setreadbuffersize"></a>CInternetFile::SetReadBufferSize

Вызов исправления этого члена для установки размера `CInternetFile`временного буфера чтения, используемого объектом, полученным из-производного объекта.

```
BOOL SetReadBufferSize(UINT nReadSize);
```

### <a name="parameters"></a>Параметры

*nReadSize*<br/>
Требуемый размер буфера в байтах.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Remarks

Базовые AIS WinInet не выполняют буферизации, поэтому выберите размер буфера, который позволяет приложению эффективно считывать данные, независимо от объема данных, которые будут читаться. Если каждый вызов [для чтения](#read) обычно включает в себя большой aount данных (например, четыре или более килобайт), вам не нужно буфера. Однако, если `Read` вы звоните, чтобы получить небольшие куски данных, или если вы используете [ReadString](#readstring) для чтения отдельных строк одновременно, то буфер чтения улучшает производительность приложения.

По умолчанию `CInternetFile` объект не предоставляет буферизации для чтения. Если вы называете эту функцию участника, вы должны быть уверены, что файл был открыт для доступа к чтению.

Вы можете увеличить размер буфера в любое время, но уменьшение буфера не будет иметь эффекта. Если вы позвоните [ReadString](#readstring) без первого вызова, `SetReadBufferSize`вы получите буфер 4096 байтов.

## <a name="cinternetfilesetwritebuffersize"></a><a name="setwritebuffersize"></a>CInternetFile::SetWriteBufferSize

Вызов исправления этого члена для установки размера `CInternetFile`временного буфера записи, используемого объектом, полученным из-производного объекта.

```
BOOL SetWriteBufferSize(UINT nWriteSize);
```

### <a name="parameters"></a>Параметры

*nWriteSize*<br/>
Размер буфера в байтах.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Remarks

Базовые AA WinInet не выполняют буферизации, поэтому выберите размер буфера, который позволяет приложению эффективно записывать данные независимо от объема записываемых данных. Если каждый вызов [для записи](#write) обычно включает в себя большой объем данных (например, четыре или более килобайт за один раз), вам не нужно буфера. Однако, если вы называете [Write,](#write) чтобы написать небольшие фрагменты данных, буфер записи улучшает производительность приложения.

По умолчанию `CInternetFile` объект не предоставляет буферизации для записи. Если вы называете эту функцию участника, вы должны быть уверены, что файл был открыт для доступа к записи. Вы можете изменить размер буфера записи в любое время, но это вызывает неявный вызов [Флеша.](#flush)

## <a name="cinternetfilewrite"></a><a name="write"></a>CInternetFile::Write

Вызов эту функцию участника, чтобы записать в данную память, *lpvBuf*, указанное количество байтов, *nCount*.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Параметры

*lpBuf*<br/>
Указатель на первый байт, который будет написан.

*Ncount*<br/>
Упогоняет количество байтов, которые должны быть написаны.

### <a name="remarks"></a>Remarks

Если при написании данных возникает какая-либо ошибка, функция бросает объект [CInternetException,](../../mfc/reference/cinternetexception-class.md) описывающий ошибку.

## <a name="cinternetfilewritestring"></a><a name="writestring"></a>CInternetFile::WriteString

Эта функция записывает строку с нулевым завершением в связанный файл.

```
virtual void WriteString(LPCTSTR pstr);
```

### <a name="parameters"></a>Параметры

*pstr*<br/>
Указатель на строку, содержащую содержимое, подкоторойчьпод которой будет написано.

### <a name="remarks"></a>Remarks

Если при написании данных возникает какая-либо ошибка, функция бросает объект [CInternetException,](../../mfc/reference/cinternetexception-class.md) описывающий ошибку.

## <a name="see-also"></a>См. также раздел

[Класс CStdioFile](../../mfc/reference/cstdiofile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)
