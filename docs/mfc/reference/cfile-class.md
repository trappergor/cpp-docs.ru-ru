---
title: Класс CFile
ms.date: 06/12/2018
f1_keywords:
- CFile
- AFX/CFile
- AFX/CFile::CFile
- AFX/CFile::Abort
- AFX/CFile::Close
- AFX/CFile::Duplicate
- AFX/CFile::Flush
- AFX/CFile::GetFileName
- AFX/CFile::GetFilePath
- AFX/CFile::GetFileTitle
- AFX/CFile::GetLength
- AFX/CFile::GetPosition
- AFX/CFile::GetStatus
- AFX/CFile::LockRange
- AFX/CFile::Open
- AFX/CFile::Read
- AFX/CFile::Remove
- AFX/CFile::Rename
- AFX/CFile::Seek
- AFX/CFile::SeekToBegin
- AFX/CFile::SeekToEnd
- AFX/CFile::SetFilePath
- AFX/CFile::SetLength
- AFX/CFile::SetStatus
- AFX/CFile::UnlockRange
- AFX/CFile::Write
- AFX/CFile::hFileNull
- AFX/CFile::m_hFile
- AFX/CFile::m_pTM
helpviewer_keywords:
- CFile [MFC], CFile
- CFile [MFC], Abort
- CFile [MFC], Close
- CFile [MFC], Duplicate
- CFile [MFC], Flush
- CFile [MFC], GetFileName
- CFile [MFC], GetFilePath
- CFile [MFC], GetFileTitle
- CFile [MFC], GetLength
- CFile [MFC], GetPosition
- CFile [MFC], GetStatus
- CFile [MFC], LockRange
- CFile [MFC], Open
- CFile [MFC], Read
- CFile [MFC], Remove
- CFile [MFC], Rename
- CFile [MFC], Seek
- CFile [MFC], SeekToBegin
- CFile [MFC], SeekToEnd
- CFile [MFC], SetFilePath
- CFile [MFC], SetLength
- CFile [MFC], SetStatus
- CFile [MFC], UnlockRange
- CFile [MFC], Write
- CFile [MFC], hFileNull
- CFile [MFC], m_hFile
- CFile [MFC], m_pTM
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
ms.openlocfilehash: 4ba37d481db73fb0556659ede267b3474c3f32f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373921"
---
# <a name="cfile-class"></a>Класс CFile

Базовый класс для файловых классов Microsoft Foundation Class.

## <a name="syntax"></a>Синтаксис

```
class CFile : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFile::CFile](#cfile)|Строит `CFile` объект из стержня или ручки файла.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFile::Аборт](#abort)|Закрывает файл, игнорируя все предупреждения и ошибки.|
|[CFile::Закрыть](#close)|Закрывает файл и удаляет объект.|
|[CFile::Duplicate](#duplicate)|Строит дубликат объекта на основе этого файла.|
|[CFile::Флеш](#flush)|Сбрасывает все данные, которые еще не написаны.|
|[CFile::GetFileName](#getfilename)|Извлекает имя файла выбранного файла.|
|[CFile::GetFilePath](#getfilepath)|Извлекает полный путь файла выбранного файла.|
|[CFile::GetFileTitle](#getfiletitle)|Извлекает название выбранного файла.|
|[CFile::GetLength](#getlength)|Извлекает длину файла.|
|[CFile::GetPosition](#getposition)|Извлекает текущий указатель файла.|
|[CFile::GetStatus](#getstatus)|Получает состояние открытого файла, или в статической версии, получает состояние указанного файла (статическая, виртуальная функция).|
|[CFile::LockRange](#lockrange)|Блокировки ряда байтов в файле.|
|[CFile::Открыто](#open)|Безопасно открывает файл с опцией тестирования ошибок.|
|[CFile::Читать](#read)|Читает (небуферизированные) данные из файла в текущем положении файла.|
|[CFile::Удалить](#remove)|Удаляет указанный файл (статическая функция).|
|[CFile::Переименовать](#rename)|Переименовывает указанный файл (статическая функция).|
|[CFile::Ищите](#seek)|Позиции текущего указателя файла.|
|[CFile::SeekTobegin](#seektobegin)|Позиции текущего указателя файла в начале файла.|
|[CFile::SeekToend](#seektoend)|Позиции текущего указателя файла в конце файла.|
|[CFile::SetFilePath](#setfilepath)|Устанавливает полный путь файла выбранного файла.|
|[CFile::SetLength](#setlength)|Изменяет длину файла.|
|[CFile::SetStatus](#setstatus)|Устанавливает состояние указанного файла (статическая, виртуальная функция).|
|[CFile::UnlockRange](#unlockrange)|Открывает ряд байтов в файле.|
|[CFile::Запись](#write)|Записывает (небуферированные) данные в файле к текущему положению файла.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CFile::оператор HANDLE](#operator_handle)|Ручка к `CFile` объекту.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CFile:hFileNull](#hfilenull)|Определяет, имеет `CFile` ли объект действительную ручку.|
|[CFile::m_hFile](#m_hfile)|Обычно содержит ручку файла операционной системы.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CFile::m_pTM](#m_ptm)|Указатель на объект `CAtlTransactionManager`.|

## <a name="remarks"></a>Remarks

Он непосредственно предоставляет небуферные, двоичные дисковые услуги ввода/вывода, и он косвенно поддерживает текстовые файлы и файлы памяти через свои производные классы. `CFile`работает совместно с `CArchive` классом для поддержки сериализации объектов класса Microsoft Foundation.

Иерархическое отношение между этим классом и его производными классами позволяет `CFile` вашей программе работать на всех файловых объектах через полиморфный интерфейс. Файл памяти, например, ведет себя как дисковый файл.

Использование `CFile` и его производные классы для диска вв/о общего назначения. Использование `ofstream` или `iostream` другие классы Майкрософт для отформатированных текстовых сообщений, отправленных в дисковый файл.

Как правило, дисковый файл `CFile` автоматически открывается при конструкции и закрывается при уничтожении. Функции static-члена позволяют вам допросить состояние файла без открытия файла.

Для получения дополнительной `CFile`информации об использовании , см. [статьи Файлы в MFC](../../mfc/files-in-mfc.md) и [обработки файлов](../../c-runtime-library/file-handling.md) в *Run-Time Библиотека Справка*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CFile`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cfileabort"></a><a name="abort"></a>CFile::Аборт

Закрывает файл, связанный с этим объектом, и делает файл недоступным для чтения или записи.

```
virtual void Abort();
```

### <a name="remarks"></a>Remarks

Если вы еще не закрыли файл перед уничтожением объекта, деструктор закрывает его для вас.

При обработке `CFile::Abort` исключений, отличается от `CFile::Close` двумя важными способами. Во-первых, `Abort` функция не будет бросать исключение на сбои, потому что сбои игнорируются `Abort`. Во-вторых, `Abort` не будет **ASSERT,** если файл не был открыт или был закрыт ранее.

Если вы использовали **новый** для выделения `CFile` объекта на куче, то вы должны удалить его после закрытия файла. `Abort`устанавливает `m_hFile` `CFile::hFileNull`на .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]

## <a name="cfilecfile"></a><a name="cfile"></a>CFile::CFile

Создает и инициализирует объект `CFile`.

```
CFile();
CFile(CAtlTransactionManager* pTM);
CFile(HANDLE hFile);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags,
CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Параметры

*hFile*<br/>
Дескриптор файла, который будет присоединен к объекту `CFile`.

*lpszFileName*<br/>
Относительный или полный путь к файлу, который будет присоединен к объекту `CFile`.

*nОткрытыефлаги*<br/>
Побитовое сочетание (ИЛИ) параметров доступа к указанному файлу. Возможные параметры см. в разделе "Заметки".

*Ptm*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Remarks

В следующих пяти таблицах перечислялись возможные варианты параметра *nOpenFlags.*

Выберите только один из следующих параметров режима доступа к файлу. Режим доступа к файлу по умолчанию — `CFile::modeRead`, т. е. только для чтения.

|Значение|Описание|
|-----------|-----------------|
|`CFile::modeRead`|Запрашивает доступ только для чтения.|
|`CFile::modeWrite`|Запрашивает доступ только для записи.|
|`CFile::modeReadWrite`|Запрашивает доступ для чтения и записи.|

Выберите один из следующих параметров режима символов.

|Значение|Описание|
|-----------|-----------------|
|`CFile::typeBinary`|Задает двоичный режим (используется только в производных классах).|
|`CFile::typeText`|Устанавливает текстовый режим со специальной обработкой для каретных пар кормов возврата (используется только в производных классах).|
|`CFile::typeUnicode`|Задает режим Юникода (используется только в производных классах). Текст записывается в файл в формате Юникод, если приложение использует конфигурацию Юникода. Данные BOM в файл не записываются.|

Выберите только один из следующих параметров режима общего доступа к файлу. Режим общего доступа к файлу по умолчанию — `CFile::shareExclusive`, т. е. эксклюзивный доступ.

|Значение|Описание|
|-----------|-----------------|
|`CFile::shareDenyNone`|Нет ограничений по общему доступу.|
|`CFile::shareDenyRead`|Запрет доступа для чтения для всех других пользователей.|
|`CFile::shareDenyWrite`|Запрет доступа для записи для всех других пользователей.|
|`CFile::shareExclusive`|Запрет доступа для чтения и записи для всех других пользователей.|

Выберите первый или и первый, и второй из следующих параметров режима создания файла. Режим создания по умолчанию — `CFile::modeNoTruncate`, т. е. открывается существующий файл.

|Значение|Описание|
|-----------|-----------------|
|`CFile::modeCreate`|Создает новый файл, если файл не существует. Если файл уже существует, он перезаписан и первоначально настроен на нулевую длину.|
|`CFile::modeNoTruncate`|Создает новый файл, если файл не существует; в противном случае, если файл уже существует, он прикрепляется к объекту. `CFile`|

Выберите соответствующие параметры кэширования файлов, описанные далее. По умолчанию система использует схему кэширования общего назначения, которая недоступна в качестве опции.

|Значение|Описание|
|-----------|-----------------|
|`CFile::osNoBuffer`|Система не использует промежуточный кэш для файла. Этот параметр отменяет использование следующих двух параметров.|
|`CFile::osRandomAccess`|Файловый кэш оптимизирован для случайного доступа. Не используйте как этот вариант, так и последовательный вариант сканирования.|
|`CFile::osSequentialScan`|Файловый кэш оптимизирован для последовательного доступа. Не используйте как эту опцию, так и опцию случайного доступа.|
|`CFile::osWriteThrough`|Операции записи выполняются без промедления.|

Выберите следующий параметр безопасности, чтобы дескриптор файла не наследовался. По умолчанию любые новые дочерние процессы могут использовать дескриптор файла.

|Значение|Описание|
|-----------|-----------------|
|`CFile::modeNoInherit`|Запрещает дочерним процессам использовать дескриптор файла.|

Конструктор по умолчанию инициализирует члены, `CFile` но не прикрепляет файл к объекту. После использования этого конструктора используйте [метод CFile::Open,](#open) чтобы `CFile` открыть файл и прикрепить его к объекту.

Конструктор с одним параметром инициализирует члены и присоединяет существующий файл к объекту `CFile`.

Конструктор с двумя параметрами инициализирует члены и пытается открыть указанный файл. Если конструктор успешно открывает заданный файл, он присоединяется к объекту `CFile`. В противном случае конструктор возвращает указатель на объект `CInvalidArgException`. Для получения дополнительной информации о том, как обрабатывать исключения, [см.](../../mfc/exception-handling-in-mfc.md)

Если `CFile` объект успешно открывает указанный файл, он автоматически `CFile` закрывает этот файл при уничтожении объекта; в противном случае необходимо явно закрыть файл после того, `CFile` как он больше не подключен к объекту.

### <a name="example"></a>Пример

В следующем коде показано использование `CFile`.

[!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]

## <a name="cfileclose"></a><a name="close"></a>CFile::Закрыть

Закрывает файл, связанный с этим объектом, и делает файл недоступным для чтения или записи.

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

Если вы еще не закрыли файл перед уничтожением объекта, деструктор закрывает его для вас.

Если вы использовали **новый** для выделения `CFile` объекта на куче, то вы должны удалить его после закрытия файла. `Close`устанавливает `m_hFile` `CFile::hFileNull`на .

### <a name="example"></a>Пример

Смотрите пример [для CFile::CFile](#cfile).

## <a name="cfileduplicate"></a><a name="duplicate"></a>CFile::Duplicate

Строит дубликат `CFile` объекта для данного файла.

```
virtual CFile* Duplicate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на дубликат `CFile` объекта.

### <a name="remarks"></a>Remarks

Эта функция эквивалентна функции `_dup`C run-time.

## <a name="cfileflush"></a><a name="flush"></a>CFile::Флеш

Принудя любые данные, оставшиеся в буфере файла, чтобы быть записаны в файл.

```
virtual void Flush();
```

### <a name="remarks"></a>Remarks

Использование `Flush` не гарантирует промывки `CArchive` буферов. Если вы используете архив, позвоните [cArchive::Flush](../../mfc/reference/carchive-class.md#flush) в первую очередь.

### <a name="example"></a>Пример

Смотрите пример [для CFile::SetFilePath](#setfilepath).

## <a name="cfilegetfilename"></a><a name="getfilename"></a>CFile::GetFileName

Вызовите эту функцию участника, чтобы получить имя указанного файла.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя файла.

### <a name="remarks"></a>Remarks

Например, при `GetFileName` вызове для создания сообщения пользователю о файле `c:\windows\write\myfile.wri`возвращается имя `myfile.wri`файла.

Чтобы вернуть весь путь файла, включая имя, позвоните [в GetFilePath](#getfilepath). Чтобы вернуть название файла `myfile`( , позвоните [GetFileTitle](#getfiletitle).

### <a name="example"></a>Пример

Этот фрагмент кода открывает SYSTEM. Файл INI в каталоге WINDOWS. Если найдено, пример распечатает имя и путь и название, как показано в разделе Выход:

[!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]

## <a name="cfilegetfilepath"></a><a name="getfilepath"></a>CFile::GetFilePath

Вызов эту функцию участника, чтобы получить полный путь указанного файла.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Полный путь указанного файла.

### <a name="remarks"></a>Remarks

Например, при `GetFilePath` вызове для создания сообщения пользователю о файле `c:\windows\write\myfile.wri`возвращается путь `c:\windows\write\myfile.wri`файла.

Чтобы вернуть только имя файла (`myfile.wri`, позвоните [GetFileName](#getfilename). Чтобы вернуть название файла`myfile`( , позвоните [GetFileTitle](#getfiletitle).

### <a name="example"></a>Пример

Смотрите пример [GetFileName](#getfilename).

## <a name="cfilegetfiletitle"></a><a name="getfiletitle"></a>CFile::GetFileTitle

Вызовите эту функцию участника, чтобы получить название файла (имя дисплея) для файла.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название базового файла.

### <a name="remarks"></a>Remarks

Этот метод вызывает [GetFileTitle](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew) для получения названия файла. В случае успеха метод возвращает строку, которую система будет использовать для отображения имени файла пользователю. В противном случае метод вызывает [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) для получения имени файла (включая расширение файла) базового файла. Это означает, что расширение файла не всегда включено в строку заголовка возвращенного файла. Для получения дополнительной информации смотрите [GetFileTitle](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew) и [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) в Windows SDK.

Чтобы вернуть весь путь файла, включая имя, позвоните [в GetFilePath](#getfilepath). Чтобы вернуть только имя файла, позвоните [GetFileName](#getfilename).

### <a name="example"></a>Пример

Смотрите пример [GetFileName](#getfilename).

## <a name="cfilegetlength"></a><a name="getlength"></a>CFile::GetLength

Получает текущую логическую длину файла в байтах.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]

## <a name="cfilegetposition"></a><a name="getposition"></a>CFile::GetPosition

Получает текущее значение указателя файла, которое может `Seek`быть использовано в последующих вызовах.

```
virtual ULONGLONG GetPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Файл указатель.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]

## <a name="cfilegetstatus"></a><a name="getstatus"></a>CFile::GetStatus

Этот метод получает информацию о `CFile` состоянии, относящуюся к данному экземпляру объекта или данному пути файла.

```
BOOL GetStatus(CFileStatus& rStatus) const;

static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*rStatus*<br/>
Ссылка на предоставленную `CFileStatus` пользователем структуру, которая будет получать информацию о состоянии. Структура `CFileStatus` имеет следующие поля:

- `CTime m_ctime`Дата и время создания файла.

- `CTime m_mtime`Дата и время последнего изменения файла.

- `CTime m_atime`Дата и время, когда файл был последним доступом для чтения.

- `ULONGLONG m_size`Логический размер файла в байтах, как сообщает командование DIR.

- `BYTE m_attribute`Атрибут байт файла.

- `char m_szFullName[_MAX_PATH]`Абсолютное имя файла в наборе символов Windows.

*lpszFileName*<br/>
Строка в наборе символов Windows, которая является путь к желаемому файлу. Путь может быть относительным или абсолютным, или он может содержать имя сетевого пути.

*Ptm*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если информация о состоянии указанного файла успешно получена; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Нестатическая версия `GetStatus` получения информации о состоянии открытого `CFile` файла, связанного с данным объектом.  Статическая версия `GetStatus` получения статуса файла из заданного пути файла без фактического открытия файла. Эта версия полезна для тестирования прав на наличие и доступ к файлу.

Член `m_attribute` `CFileStatus` структуры относится к набору атрибутов файлов. Класс `CFile` предоставляет тип перечисления **attribute,** поэтому атрибуты файла могут быть определены символически:

```
enum Attribute {
    normal =    0x00,
    readOnly =  0x01,
    hidden =    0x02,
    system =    0x04,
    volume =    0x08,
    directory = 0x10,
    archive =   0x20
    };
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#10](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]

## <a name="cfilehfilenull"></a><a name="hfilenull"></a>CFile:hFileNull

Определяет наличие действительной ручки файла `CFile` для объекта.

```
static AFX_DATA const HANDLE hFileNull;
```

### <a name="remarks"></a>Remarks

Эта константа используется `CFile` для определения того, имеет ли объект действительную ручку файла.

Следующий пример демонстрирует эту операцию:

[!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]

## <a name="cfilelockrange"></a><a name="lockrange"></a>CFile::LockRange

Блокировка ряда байтов в открытом файле, бросая исключение, если файл уже заблокирован.

```
virtual void LockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Параметры

*dwPos*<br/>
Байт смещение начала диапазона байт для блокировки.

*dwCount*<br/>
Количество байтов в диапазоне для блокировки.

### <a name="remarks"></a>Remarks

Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Можно заблокировать несколько областей файла, но перекрывающиеся области не допускаются.

При разблокировке региона `UnlockRange` с помощью функции члена диапазон байт должен точно соответствовать региону, который ранее был заблокирован. Функция `LockRange` не объединяет смежные области. Если два заблокированных региона смываются, необходимо разблокировать каждый регион по отдельности.

> [!NOTE]
> Эта функция недоступна для `CMemFile`класса -производные.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilem_hfile"></a><a name="m_hfile"></a>CFile::m_hFile

Содержит ручку файла операционной системы для открытого файла.

```
HANDLE m_hFile;
```

### <a name="remarks"></a>Remarks

`m_hFile`является публичной переменной типа UINT. Он `CFile::hFileNull`содержит индикатор пустого файла, независимый от операционной системы, если ручка не была назначена.

Использование `m_hFile` не рекомендуется, потому что значение участника зависит от производного класса. `m_hFile`становится публичным членом для удобства в поддержке неполиморфного использования класса.

## <a name="cfilem_ptm"></a><a name="m_ptm"></a>CFile::m_pTM

Указатель на `CAtlTransactionManager` объект.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Remarks

## <a name="cfileopen"></a><a name="open"></a>CFile::Открыто

Перегружен. `Open`предназначен для использования с `CFile` конструктором по умолчанию.

```
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Строка, содержащая путь к нужному файлу. Путь может быть относительным, абсолютным или сетевым названием (UNC).

*nОткрытыефлаги*<br/>
UINT, определяющий режим совместного использования и доступа файла. Он определяет действие, предпринимаемое при открытии файла. Вы можете комбинировать варианты с помощью оператора bitwise-OR **(&#124;).** Требуется одно разрешение на доступ и один опцион на участие; `modeCreate` режимы `modeNoInherit` и режимы не являются обязательными. Посмотреть конструктор [CFile](#cfile) для списка вариантов режима.

*pОшибка*<br/>
Указатель на существующий объект исключения файлов, который получит статус сбойной операции.

*Ptm*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если открытый был успешным; в противном случае 0. Параметр *pError* имеет смысл только в случае возврата 0.

### <a name="remarks"></a>Remarks

Эти `Open` две функции являются "безопасными" методами для открытия файла, где сбой является нормальным, ожидаемым условием.

В `CFile` то время как конструктор бросает исключение `Open` в состоянии ошибки, возвращает FALSE для условий ошибки. `Open`однако, для описания ошибки может быть инициирован [объект CFileException.](../../mfc/reference/cfileexception-class.md) Если вы не поставляете параметр *pError,* или если `Open` вы проходите NULL для `CFileException` *pError*, возвращает FALSE и не бросает . Если вы передаете указатель `CFileException`на `Open` существующий, и сталкивается с ошибкой, функция заполняет его информацией, описывающей эту ошибку. `Open`не бросает исключение в любом случае.

В следующей таблице описаны возможные результаты `Open`.

|`pError`|Ошибка|Возвращаемое значение|Содержимое CFileException|
|--------------|------------------------|------------------|----------------------------|
|NULL|нет|TRUE|Недоступно|
|ptr к`CFileException`|нет|TRUE|без изменений|
|NULL|Да|FALSE|Недоступно|
|ptr к`CFileException`|Да|FALSE|инициализировано для описания ошибки|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]

[!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]

## <a name="cfileoperator-handle"></a><a name="operator_handle"></a>CFile::оператор HANDLE

Используйте этот оператор, чтобы `CFile` передать ручку объекту таким функциям, `HANDLE`как [ReadFileEx](/windows/win32/api/fileapi/nf-fileapi-readfileex) и [GetFileTime,](/windows/win32/api/fileapi/nf-fileapi-getfiletime) которые ожидают .

```
operator HANDLE() const;
```

## <a name="cfileread"></a><a name="read"></a>CFile::Читать

Считывает данные в буфер `CFile` из файла, связанного с объектом.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Параметры

*lpBuf*<br/>
Указатель на буфер, поставляемый пользователем, который должен получать данные, считываемые из файла.

*Ncount*<br/>
Максимальное количество байтов, которые можно прочитать из файла. Для файлов текстового режима пары каналов возврата каретных линий учитываются как одиночные символы.

### <a name="return-value"></a>Возвращаемое значение

Количество байтов, переданных в буфер. Для `CFile` всех классов значение возврата может быть меньше *nCount,* если конец файла был достигнут.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]

Для другого примера см. [CFile::Открытый](#open).

## <a name="cfileremove"></a><a name="remove"></a>CFile::Удалить

Эта статическая функция удаляет файл, указанный по пути.

```
static void PASCAL Remove(
    LPCTSTR lpszFileName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Строка, которая является путь к желаемому файлу. Путь может быть относительным или абсолютным и может содержать имя сети.

*Ptm*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Remarks

`Remove`не будет удалять каталог.

Функция `Remove` участника выбрасывает исключение, если подключенный файл открыт или если файл не может быть удален. Эта функция эквивалентна команде DEL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]

## <a name="cfilerename"></a><a name="rename"></a>CFile::Переименовать

Эта статическая функция переименовывает указанный файл.

```
static void PASCAL Rename(
    LPCTSTR lpszOldName,
    LPCTSTR lpszNewName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*lpszOldName*<br/>
Старый путь.

*lpszNewName*<br/>
Новый путь.

*Ptm*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Remarks

Каталоги не могут быть переименованы. Эта функция эквивалентна команде REN.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]

## <a name="cfileseek"></a><a name="seek"></a>CFile::Ищите

Перемещает указатель файла в открытый файл.

```
virtual ULONGLONG Seek(
LONGLONG lOff,
UINT nFrom);
```

### <a name="parameters"></a>Параметры

*lOff*<br/>
Количество байтов для перемещения указателя файла. Положительные значения перемещают указатель файла в конце файла; отрицательные значения перемещают указатель файла к началу файла.

*nОт*<br/>
Позиция, от которую нужно стремиться. Смотрите раздел Замечания для возможных значений.

### <a name="return-value"></a>Возвращаемое значение

Положение указателя файла, если метод был успешным; в противном случае значение возврата не определено и выбрасывается указатель `CFileException` на исключение.

### <a name="remarks"></a>Remarks

В следующей таблице перечислены возможные значения параметра *nFrom.*

|Значение|Описание|
|-----------|-----------------|
|`CFile::begin`|Ищите с самого начала файла.|
|`CFile::current`|Ищите из текущего местоположения указателя файла.|
|`CFile::end`|Ищите из конца файла.|

При открытии файла указатель файла размещается на 0, запуск файла.

Можно настроить указатель файла в положение за пределами конца файла. Если вы это сделаете, размер файла не увеличивается до тех пор, пока вы не напишете в файл.

Обработчик исключений для этого метода должен удалить объект исключения после обработки исключения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]

## <a name="cfileseektobegin"></a><a name="seektobegin"></a>CFile::SeekTobegin

Устанавливает значение указателя файла к началу файла.

```
void SeekToBegin();
```

### <a name="remarks"></a>Remarks

`SeekToBegin()` эквивалентно правилу `Seek( 0L, CFile::begin )`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfileseektoend"></a><a name="seektoend"></a>CFile::SeekToend

Устанавливает значение указателя файла на логический конец файла.

```
ULONGLONG SeekToEnd();
```

### <a name="return-value"></a>Возвращаемое значение

Длина файла в байтах.

### <a name="remarks"></a>Remarks

`SeekToEnd()` эквивалентно правилу `CFile::Seek( 0L, CFile::end )`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfilesetfilepath"></a><a name="setfilepath"></a>CFile::SetFilePath

Вызовите эту функцию, чтобы указать траекторию файла. Например, если путь файла недоступен при построении объекта `SetFilePath` [CFile,](../../mfc/reference/cfile-class.md) позвоните, чтобы предоставить его.

```
virtual void SetFilePath(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Параметры

*lpszNewName*<br/>
Указатель на строку, определяющую новый путь.

### <a name="remarks"></a>Remarks

> [!NOTE]
> `SetFilePath`не открывает файл и не создает файл; он просто связывает `CFile` объект с именем пути, которое затем может быть использовано.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]

## <a name="cfilesetlength"></a><a name="setlength"></a>CFile::SetLength

Вызовите эту функцию, чтобы изменить длину файла.

```
virtual void SetLength(ULONGLONG dwNewLen);
```

### <a name="parameters"></a>Параметры

*dwNewLen*<br/>
Пожеланная длина файла в байтах. Это значение может быть больше или меньше текущей длины файла. Файл будет расширен или усечен по мере необходимости.

### <a name="remarks"></a>Remarks

> [!NOTE]
> С `CMemFile`помощью этой `CMemoryException` функции может быть забрасывать объект.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]

## <a name="cfilesetstatus"></a><a name="setstatus"></a>CFile::SetStatus

Устанавливает состояние файла, связанного с этим местоположением файла.

```
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,
    const CFileStatus& status,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Строка, которая является путь к желаемому файлу. Путь может быть относительным или абсолютным и может содержать имя сети.

*состояние*<br/>
Буфер, содержащий новую информацию о состоянии. Вызов `GetStatus` функции участника для `CFileStatus` предварительного заполнения структуры текущими значениями, а затем внедвите изменения по мере необходимости. Если значение 0, то элемент соответствующего статуса не обновляется. Ознакомьтесь с функцией участника `CFileStatus` [GetStatus](#getstatus) для описания структуры.

*Ptm*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Remarks

Чтобы установить время, `m_mtime` измените поле *статуса.*

При попытке сделать вызов `SetStatus` в попытке изменить только атрибуты `m_mtime` файла, а элемент структуры статуса файла незеро, атрибуты также могут быть затронуты (изменение временной отметки может иметь побочные эффекты на атрибуты). Если требуется изменить только атрибуты файла, `m_mtime` сначала установите состав структуры статуса файла `SetStatus`к нулю, а затем позвоните в систему .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]

## <a name="cfileunlockrange"></a><a name="unlockrange"></a>CFile::UnlockRange

Открывает ряд байтов в открытом файле.

```
virtual void UnlockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Параметры

*dwPos*<br/>
Байт смещение начала диапазона байт для разблокировки.

*dwCount*<br/>
Количество байтов в диапазоне для разблокировки.

### <a name="remarks"></a>Remarks

Подробнее о функции участника [LockRange](#lockrange) смотрите.

> [!NOTE]
> Эта функция недоступна `CMemFile`для класса -производные.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilewrite"></a><a name="write"></a>CFile::Запись

Записывает данные из буфера `CFile` в файл, связанный с объектом.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Параметры

*lpBuf*<br/>
Указатель на буфер, поставляемый пользователем, содержащий данные, которые должны быть записаны в файл.

*Ncount*<br/>
Количество байтов, которые будут перенесены из буфера. Для файлов текстового режима пары каналов возврата каретных линий учитываются как одиночные символы.

### <a name="remarks"></a>Remarks

`Write`бросает исключение в ответ на несколько условий, в том числе диск-полное состояние.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]

Также смотрите примеры для [CFile::CFile](#cfile) и [CFile::Открытый](#open).

## <a name="see-also"></a>См. также раздел

[MFC Образец DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CStdioFile](../../mfc/reference/cstdiofile-class.md)<br/>
[Класс CMemFile](../../mfc/reference/cmemfile-class.md)
