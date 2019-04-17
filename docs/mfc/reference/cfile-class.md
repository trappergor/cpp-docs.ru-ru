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
ms.openlocfilehash: db499ffa5f1d82b6e3622287f86132930a929102
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768555"
---
# <a name="cfile-class"></a>Класс CFile

Базовый класс для файловых классов Microsoft Foundation Class.

## <a name="syntax"></a>Синтаксис

```
class CFile : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CFile::CFile](#cfile)|Создает `CFile` объекта из дескриптора путь или файл.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CFile::Abort](#abort)|Закрывает файл, игнорируя все предупреждения и ошибки.|
|[CFile::Close](#close)|Закрывает файл и удаляет объект.|
|[CFile::Duplicate](#duplicate)|Создает дубликат объекта на основе этого файла.|
|[CFile::Flush](#flush)|Очищает все еще записываемые данные.|
|[CFile::GetFileName](#getfilename)|Извлекает имя выбранного файла.|
|[CFile::GetFilePath](#getfilepath)|Получает полный путь к выбранному файлу.|
|[CFile::GetFileTitle](#getfiletitle)|Извлекает заголовок выбранного файла.|
|[CFile::GetLength](#getlength)|Получает длину файла.|
|[CFile::GetPosition](#getposition)|Извлекает указатель текущего файла.|
|[CFile::GetStatus](#getstatus)|Получает сведения о состоянии открыть файл, либо в статическая версия, получает состояние указанного файла (статический, виртуальные функции).|
|[CFile::LockRange](#lockrange)|Блокировка диапазона байтов в файле.|
|[CFile::Open](#open)|Безопасно открывает файл с возможностью тестирования ошибки.|
|[CFile::Read](#read)|Операции чтения (без буферизации) данные из файла в текущей позиции файла.|
|[CFile::Remove](#remove)|Удаляет указанный файл (статическую функцию).|
|[CFile::Rename](#rename)|Переименовывает указанный файл (статическую функцию).|
|[CFile::Seek](#seek)|Помещает текущий указатель файла.|
|[CFile::SeekToBegin](#seektobegin)|Помещает текущий указатель файла в начале файла.|
|[CFile::SeekToEnd](#seektoend)|Помещает текущий указатель файла в конце файла.|
|[CFile::SetFilePath](#setfilepath)|Задает полный путь к выбранному файлу.|
|[CFile::SetLength](#setlength)|Изменяет размер файла.|
|[CFile::SetStatus](#setstatus)|Задает состояние указанного файла (статический, виртуальные функции).|
|[CFile::UnlockRange](#unlockrange)|Снимает блокировку диапазона байтов в файле.|
|[CFile::Write](#write)|Операции записи (без буферизации) данные в файле в текущую позицию в файле.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CFile::operator ДЕСКРИПТОР](#operator_handle)|Дескриптор `CFile` объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CFile::hFileNull](#hfilenull)|Определяет, если `CFile` объект имеет допустимый дескриптор.|
|[CFile::m_hFile](#m_hfile)|Обычно содержит дескриптор файла операционной системы.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CFile::m_pTM](#m_ptm)|Указатель на `CAtlTransactionManager` объект.|

## <a name="remarks"></a>Примечания

Он непосредственно предоставляет службы ввода вывода без буферизации, двоичная диска, а также косвенно поддерживает текстовые файлы и файлы памяти через его производных классов. `CFile` работает в сочетании с `CArchive` класс для поддержки сериализации объектов Microsoft Foundation Class.

Иерархические отношения между этого класса и его производных классов позволяет программе работать на всех файловых объектов через полиморфных `CFile` интерфейс. Например, файл памяти ведет себя как файл на диске.

Используйте `CFile` и его производных классов для общего назначения дискового ввода-вывода. Используйте `ofstream` или другие классы iostream Microsoft для форматированный текст, отправляемый файл на диске.

Как правило, автоматически при открытии файл на диске `CFile` Создание и уничтожение закрыт на. Статические функции-члены позволяют запрашивать состояние файла, не открывая файл.

Дополнительные сведения об использовании `CFile`, см. в статьях [файлы в MFC](../../mfc/files-in-mfc.md) и [обработка файлов](../../c-runtime-library/file-handling.md) в *Справочник по библиотеке времени выполнения*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CFile`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="abort"></a>  CFile::Abort

Закрывает файл, связанный с данным объектом и он становится недоступным для чтения или записи.

```
virtual void Abort();
```

### <a name="remarks"></a>Примечания

Если файл не закрыт перед удалением объекта, деструктор закрывает его для вас.

При обработке исключений, `CFile::Abort` отличается от `CFile::Close` два важных отличия. Во-первых, `Abort` функцию не вызывать исключения в случае сбоев, поскольку сбои будут пропускаться `Abort`. Во-вторых, `Abort` не **ASSERT** Если файл не был открыт или закрыт ранее.

Если вы использовали **новый** выделить `CFile` объекта в куче, а затем необходимо удалить его после закрытия файла. `Abort` Задает `m_hFile` для `CFile::hFileNull`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]

##  <a name="cfile"></a>  CFile::CFile

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

*nOpenFlags*<br/>
Побитовое сочетание (ИЛИ) параметров доступа к указанному файлу. Возможные параметры см. в разделе "Заметки".

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Примечания

В следующих пяти таблицах перечислены доступные параметры для *nOpenFlags* параметра.

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
|`CFile::typeText`|Задает текстовый режим со специальной обработкой пар перевода строки возврата каретки (используется только в производных классах).|
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
|`CFile::modeCreate`|Создает новый файл, если файл не существует. Если файл уже существует, перезаписываются и задано значение нулевой длины.|
|`CFile::modeNoTruncate`|Создает файл, если он не существует. В противном случае файл присоединяется к объекту `CFile`.|

Выберите соответствующие параметры кэширования файлов, описанные далее. По умолчанию система использует схему кэширования общего назначения, которая недоступна в виде параметра.

|Значение|Описание|
|-----------|-----------------|
|`CFile::osNoBuffer`|Система не использует промежуточный кэш для файла. Этот параметр отменяет использование следующих двух параметров.|
|`CFile::osRandomAccess`|Файловый кэш оптимизирован для случайного доступа. Не используйте этот параметр вместе с параметром последовательного сканирования.|
|`CFile::osSequentialScan`|Файловый кэш оптимизирован для последовательного доступа. Не используйте этот параметр вместе с параметром случайного доступа.|
|`CFile::osWriteThrough`|Операции записи выполняются без задержки.|

Выберите следующий параметр безопасности, чтобы дескриптор файла не наследовался. По умолчанию любые новые дочерние процессы могут использовать дескриптор файла.

|Значение|Описание|
|-----------|-----------------|
|`CFile::modeNoInherit`|Запрещает дочерним процессам использовать дескриптор файла.|

Конструктор по умолчанию инициализирует члены, но не присоединяет файл к объекту `CFile`. После использования этого конструктора, используйте [CFile::Open](#open) метод, чтобы открыть файл и присоединить его к `CFile` объекта.

Конструктор с одним параметром инициализирует члены и присоединяет существующий файл к объекту `CFile`.

Конструктор с двумя параметрами инициализирует члены и пытается открыть указанный файл. Если конструктор успешно открывает заданный файл, он присоединяется к объекту `CFile`. В противном случае конструктор возвращает указатель на объект `CInvalidArgException`. Дополнительные сведения об обработке исключений см. в разделе [исключения](../../mfc/exception-handling-in-mfc.md).

Если объект `CFile` успешно открывает указанный файл, он закрывается автоматически при удалении объекта `CFile`. В противном случае необходимо явно закрыть файл, после отмены его присоединения к объекту `CFile`.

### <a name="example"></a>Пример

В следующем коде показано использование `CFile`.

[!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]

##  <a name="close"></a>  CFile::Close

Закрывает файл, связанный с данным объектом и он становится недоступным для чтения или записи.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

Если файл не закрыт перед удалением объекта, деструктор закрывает его для вас.

Если вы использовали **новый** выделить `CFile` объекта в куче, а затем необходимо удалить его после закрытия файла. `Close` Задает `m_hFile` для `CFile::hFileNull`.

### <a name="example"></a>Пример

См. в примере [CFile::CFile](#cfile).

##  <a name="duplicate"></a>  CFile::Duplicate

Создает дубликат `CFile` объекта для заданного файла.

```
virtual CFile* Duplicate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на копию `CFile` объекта.

### <a name="remarks"></a>Примечания

Это эквивалентно функции времени выполнения C `_dup`.

##  <a name="flush"></a>  CFile::Flush

Заставляет все данные, остающихся в буфере файл для записи в файл.

```
virtual void Flush();
```

### <a name="remarks"></a>Примечания

Использование `Flush` не гарантирует, что очистка `CArchive` буферов. Если вы используете архив, вызвать [CArchive::Flush](../../mfc/reference/carchive-class.md#flush) первого.

### <a name="example"></a>Пример

См. в примере [CFile::SetFilePath](#setfilepath).

##  <a name="getfilename"></a>  CFile::GetFileName

Вызовите эту функцию-член для извлечения имени указанного файла.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя файла

### <a name="remarks"></a>Примечания

Например, при вызове `GetFileName` создать сообщение для пользователя о файле `c:\windows\write\myfile.wri`, имя файла, `myfile.wri`, возвращается.

Чтобы вернуть весь путь к файлу, включая имя, вызовите [GetFilePath](#getfilepath). Чтобы вернуть название файла ( `myfile`), вызовите [GetFileTitle](#getfiletitle).

### <a name="example"></a>Пример

Этот фрагмент кода откроется системы. INI-файл в каталоге WINDOWS. Если найден, пример выводит на экран имя и путь и название, как показано в разделе выходных данных:

[!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]

##  <a name="getfilepath"></a>  CFile::GetFilePath

Вызовите эту функцию-член для получения полного пути для указанного файла.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Полный путь к указанному файлу.

### <a name="remarks"></a>Примечания

Например, при вызове `GetFilePath` создать сообщение для пользователя о файле `c:\windows\write\myfile.wri`, путь к файлу, `c:\windows\write\myfile.wri`, возвращается.

Чтобы вернуть только имя файла (`myfile.wri`), вызовите [GetFileName](#getfilename). Чтобы вернуть название файла (`myfile`), вызовите [GetFileTitle](#getfiletitle).

### <a name="example"></a>Пример

См. в примере [GetFileName](#getfilename).

##  <a name="getfiletitle"></a>  CFile::GetFileTitle

Вызовите эту функцию-член для извлечения заголовок файла (отображаемое имя) для файла.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название базового файла.

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [GetFileTitle](/windows/desktop/api/commdlg/nf-commdlg-getfiletitlea) извлекаемого название файла. При успешном выполнении метод возвращает строку, система будет использовать для отображения имени файла для пользователя. В противном случае вызывает метод [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) для извлечения имени файла (включая расширение файла) базового файла. Таким образом расширение файла будет не всегда быть включен в строку заголовка возвращенного файла. Дополнительные сведения см. в разделе [GetFileTitle](/windows/desktop/api/commdlg/nf-commdlg-getfiletitlea) и [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) в пакете Windows SDK.

Чтобы вернуть весь путь к файлу, включая имя, вызовите [GetFilePath](#getfilepath). Чтобы вернуть только имя файла, вызовите [GetFileName](#getfilename).

### <a name="example"></a>Пример

См. в примере [GetFileName](#getfilename).

##  <a name="getlength"></a>  CFile::GetLength

Получает логический текущую длину файла в байтах.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]

##  <a name="getposition"></a>  CFile::GetPosition

Получает текущее значение указателя файла, который может использоваться в последующих вызовах `Seek`.

```
virtual ULONGLONG GetPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]

##  <a name="getstatus"></a>  CFile::GetStatus

Этот метод извлекает сведения о состоянии, связанные с данной `CFile` экземпляр объекта или заданного пути к файлу.

```
BOOL GetStatus(CFileStatus& rStatus) const;

static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*rStatus*<br/>
Ссылку на предоставленное пользователем `CFileStatus` структуры, который будет получать сведения о состоянии. `CFileStatus` Структура содержит следующие поля:

- `CTime m_ctime` Дата и время создания файла.

- `CTime m_mtime` Дата и время последнего изменения файла.

- `CTime m_atime` Дата и время последнего доступа к файлу для чтения.

- `ULONGLONG m_size` Логический размер файла в байтах, указанная в команду DIR.

- `BYTE m_attribute` Байт атрибут файла.

- `char m_szFullName[_MAX_PATH]` Абсолютное имя файла в наборе символов Windows.

*lpszFileName*<br/>
Строка в кодировке Windows набор, путь к требуемому файлу. Путь может быть относительным или абсолютным, или он может содержать сетевой путь.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если сведения о состоянии для указанного файла успешно получила; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Версия нестатических `GetStatus` извлекает сведения о состоянии из открытого файла, связанного с данной `CFile` объекта.  Статическую версию `GetStatus` получает состояние файла из заданного пути к файлу без фактически при открытии файла. Это полезно для тестирования права на доступ и существование файла.

`m_attribute` Членом `CFileStatus` структуры ссылается на набор атрибутов файла. `CFile` Класс предоставляет **атрибут** тип перечисления, поэтому файл атрибуты могут быть заданы в виде символов:

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

##  <a name="hfilenull"></a>  CFile::hFileNull

Определяет наличие допустимого дескриптора файла для `CFile` объекта.

```
static AFX_DATA const HANDLE hFileNull;
```

### <a name="remarks"></a>Примечания

Эта константа используется для определения, если `CFile` объект имеет допустимого дескриптора файла.

В следующем примере демонстрируется эта операция:

[!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]

##  <a name="lockrange"></a>  CFile::LockRange

Блокировка диапазона байтов в открытом файле, исключения, если файл уже заблокирован.

```
virtual void LockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Параметры

*dwPos*<br/>
Смещение в байтах от начала диапазона байтов для блокировки.

*dwCount*<br/>
Число байтов в диапазоне для блокировки.

### <a name="remarks"></a>Примечания

Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Вы можете заблокировать более одной области файла, но разрешены не перекрывающихся областей.

При снятии блокировки области, с помощью `UnlockRange` функция-член, диапазон байтов должен точно соответствовать регион, который ранее был заблокирован. `LockRange` Функция не объединяет смежные разделы; Если два заблокированных раздела являются смежными, каждый регион необходимо разблокировать отдельно.

> [!NOTE]
>  Эта функция недоступна для `CMemFile`-производного класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

##  <a name="m_hfile"></a>  CFile::m_hFile

Содержит дескриптор файла операционной системы для открытого файла.

```
HANDLE m_hFile;
```

### <a name="remarks"></a>Примечания

`m_hFile` — это открытая переменная типа целое число без знака. Он содержит `CFile::hFileNull` (пустой файл операционной системы — независимый от индикатора) Если не был назначен дескриптор.

Использование `m_hFile` не рекомендуется, поскольку его значение зависит от производного класса. `m_hFile` выполняется открытый член для удобства в поддержке неполиморфных использование класса.

##  <a name="m_ptm"></a>  CFile::m_pTM

Указатель на `CAtlTransactionManager` объект.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Примечания

##  <a name="open"></a>  CFile::Open

Перегружен. `Open` предназначен для использования со значением по умолчанию `CFile` конструктор.

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
Строка, — это путь к требуемому файлу. Путь может быть относительным, абсолютное или сетевое имя (UNC).

*nOpenFlags*<br/>
Целое число без знака, определяющий его совместное использование и режимом доступа. Он указывает действие, выполняемое при открытии файла. Параметры могут быть объединены с помощью побитового или ( **&#124;** ) оператор. Разрешение на доступ один параметр одну общую папку требуются и; `modeCreate` и `modeNoInherit` режимы являются необязательными. См. в разделе [CFile](#cfile) конструктор для списка параметры режима.

*pError*<br/>
Указатель на существующий объект исключения файлов, который получит состояние сбоя операции.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если открыть прошла успешно; в противном случае 0. *PError* параметр имеет смысл только в том случае, если возвращается значение 0.

### <a name="remarks"></a>Примечания

Две функции, которые образуют «безопасных» метод для открытия файла, где сбоя — это обычный, ожидаемое условие.

Хотя `CFile` конструктор выдаст исключение в случае ошибки `Open` возвращает значение FALSE для условий ошибок. `Open` по-прежнему можно инициализировать [CFileException](../../mfc/reference/cfileexception-class.md) объект для описания ошибки, тем не менее. Если вы не указали *pError* параметра, или если передается значение NULL *pError*, `Open` будет возвращать значение FALSE и создает исключение `CFileException`. Если передать указатель в существующий `CFileException`, и `Open` возникает ошибка, функция будет заполнить сведения, описывающие эту ошибку. В ни один из вариантов будет `Open` к возникновению исключения.

В следующей таблице описаны возможные результаты `Open`.

|`pError`|Произошла ошибка|Возвращаемое значение|Содержимое CFileException|
|--------------|------------------------|------------------|----------------------------|
|NULL|Нет|true|Н/Д|
|указатель на `CFileException`|Нет|true|без изменений|
|NULL|Да|false|Н/Д|
|указатель на `CFileException`|Да|false|инициализирован для описания ошибки|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]

[!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]

##  <a name="operator_handle"></a>  CFile::operator ДЕСКРИПТОР

Этот оператор используется для передачи дескриптора `CFile` объекта функции, такие как [ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex) и [функции GetFileTime](/windows/desktop/api/fileapi/nf-fileapi-getfiletime) которые предполагают `HANDLE`.

```
operator HANDLE() const;
```

##  <a name="read"></a>  CFile::Read

Считывает данные в буфер из файла, связанного с `CFile` объекта.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Параметры

*/ / lpBuf*<br/>
Указатель на буфер, предоставленный пользователем, который принимает данные, считанные из файла.

*nCount*<br/>
Максимальное число байтов, считываемых из файла. Для файлов в текстовом режиме пары перевода строки возврата каретки, рассматриваются как одиночные символы.

### <a name="return-value"></a>Возвращаемое значение

Количество байтов, переданных в буфер. Обратите внимание, что для всех `CFile` классы, возвращаемое значение может быть меньше, чем *nCount* если достигнут конец файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]

Еще один пример см. в разделе [CFile::Open](#open).

##  <a name="remove"></a>  CFile::Remove

Эта статическая функция удаляет файл, указанный в пути.

```
static void PASCAL Remove(
    LPCTSTR lpszFileName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Строка, — это путь к требуемому файлу. Путь может быть относительным или абсолютным и может содержать имя сети.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Примечания

Он не удаляет каталог.

`Remove` Функция-член вызывает исключение, если подключенный файл открыт или если файл не может быть удален. Это эквивалентно команде DEL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]

##  <a name="rename"></a>  CFile::Rename

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

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Примечания

Невозможно переименовать каталоги. Это эквивалентно команде REN.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]

##  <a name="seek"></a>  CFile::Seek

Перемещает файловый указатель в открытом файле.

```
virtual ULONGLONG Seek(
LONGLONG lOff,
UINT nFrom);
```

### <a name="parameters"></a>Параметры

*lOff*<br/>
Число байтов, чтобы переместить указатель файла. Положительные значения переместить указатель файла в конце файла; отрицательные значения переместить указатель файла для начала файла.

*nFrom*<br/>
Позиция для поиска из. Возможные значения в разделе "Примечания".

### <a name="return-value"></a>Возвращаемое значение

Положение указателя файла, если метод был выполнен успешно; в противном случае возвращаемое значение не определено и указатель на `CFileException` возникает исключение.

### <a name="remarks"></a>Примечания

В следующей таблице перечислены возможные значения для *nFrom* параметра.

|Значение|Описание|
|-----------|-----------------|
|`CFile::begin`|Поиск с начала файла.|
|`CFile::current`|Поиск от текущего расположения указателя файла.|
|`CFile::end`|Поиск с конца файла.|

При открытии файла, указатель файла находится на 0 в начале файла.

Указатель файла можно задать в позицию после конца файла. В этом случае размер файла увеличивается, пока запись в файле.

Обработчик исключений для этого метода необходимо удалить объект исключения, после обработки исключения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]

##  <a name="seektobegin"></a>  CFile::SeekToBegin

Задает значение указателя файла в начало файла.

```
void SeekToBegin();
```

### <a name="remarks"></a>Примечания

`SeekToBegin()` равно `Seek( 0L, CFile::begin )`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

##  <a name="seektoend"></a>  CFile::SeekToEnd

Задает значение указателя файла в логический конец файла.

```
ULONGLONG SeekToEnd();
```

### <a name="return-value"></a>Возвращаемое значение

Длина файла в байтах.

### <a name="remarks"></a>Примечания

`SeekToEnd()` равно `CFile::Seek( 0L, CFile::end )`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

##  <a name="setfilepath"></a>  CFile::SetFilePath

Вызывайте эту функцию, чтобы указать путь к файлу; Например, если путь к файлу вариант недоступен, если [CFile](../../mfc/reference/cfile-class.md) объект создан, вызовите `SetFilePath` его.

```
virtual void SetFilePath(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Параметры

*lpszNewName*<br/>
Указатель на строку, указав новый путь.

### <a name="remarks"></a>Примечания

> [!NOTE]
> `SetFilePath` Откройте файл или необходимо создать файл; он просто связывает `CFile` объекта с использованием пути, который затем может использоваться.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]

##  <a name="setlength"></a>  CFile::SetLength

Вызывайте эту функцию, чтобы изменить длину файла.

```
virtual void SetLength(ULONGLONG dwNewLen);
```

### <a name="parameters"></a>Параметры

*dwNewLen*<br/>
Необходимая длина файла в байтах. Это значение может быть больше или меньше текущей длины файла. Файл будет расширенных или усечен соответствующим образом.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  С помощью `CMemFile`, мог вызывать эту функцию `CMemoryException` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]

##  <a name="setstatus"></a>  CFile::SetStatus

Задает состояние файла, связанного с расположение этого файла.

```
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,
    const CFileStatus& status,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Строка, — это путь к требуемому файлу. Путь может быть относительным или абсолютным и может содержать имя сети.

*status*<br/>
Буфер, содержащий новые сведения о состоянии. Вызовите `GetStatus` функцию-член для сбора `CFileStatus` структура с текущими значениями и внесите необходимые изменения. Если значение равно 0, соответствующий элемент состояния не обновляется. См. в разделе [GetStatus](#getstatus) функция-член описание `CFileStatus` структуры.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Примечания

Чтобы задать время, измените `m_mtime` поле *состояние*.

Следует учитывать, что при вызове `SetStatus` при попытке изменить только атрибуты файла и `m_mtime` член структуры состояния файла имеет ненулевое значение, атрибуты также могут быть затронуты (изменение метка может иметь побочные эффекты на времени атрибуты). Если вы хотите только изменить атрибуты файла, сначала задайте `m_mtime` член структуры состояния файла нуля, а затем отправить вызов `SetStatus`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]

##  <a name="unlockrange"></a>  CFile::UnlockRange

Снимает блокировку диапазона байтов в открытом файле.

```
virtual void UnlockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Параметры

*dwPos*<br/>
Смещение в байтах от начала диапазона байтов для разблокирования.

*dwCount*<br/>
Число байтов в диапазоне для разблокировки.

### <a name="remarks"></a>Примечания

См. в описании [LockRange](#lockrange) функция-член для сведения.

> [!NOTE]
>  Эта функция недоступна для `CMemFile`-производного класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

##  <a name="write"></a>  CFile::Write

Записывает данные из буфера к файлу, связанному с `CFile` объекта.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Параметры

*/ / lpBuf*<br/>
Указатель на предоставленный пользователем буфер, содержащий данные для записи в файл.

*nCount*<br/>
Число байтов, передаваемых из буфера. Для файлов в текстовом режиме пары перевода строки возврата каретки, рассматриваются как одиночные символы.

### <a name="remarks"></a>Примечания

`Write` вызывает исключение в ответ на несколько условий, включая условия переполнения диска.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]

Кроме того, см. в примерах [CFile::CFile](#cfile) и [CFile::Open](#open).

## <a name="see-also"></a>См. также

[Пример MFC ФУНКЦИЙ](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CStdioFile](../../mfc/reference/cstdiofile-class.md)<br/>
[Класс CMemFile](../../mfc/reference/cmemfile-class.md)
