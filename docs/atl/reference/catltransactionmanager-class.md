---
title: Класс CAtlTransactionManager
ms.date: 11/04/2016
f1_keywords:
- CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::Close
- ATLTRANSACTIONMANAGER/ATL::Commit
- ATLTRANSACTIONMANAGER/ATL::Create
- ATLTRANSACTIONMANAGER/ATL::CreateFile
- ATLTRANSACTIONMANAGER/ATL::DeleteFile
- ATLTRANSACTIONMANAGER/ATL::FindFirstFile
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributesEx
- ATLTRANSACTIONMANAGER/ATL::GetHandle
- ATLTRANSACTIONMANAGER/ATL::IsFallback
- ATLTRANSACTIONMANAGER/ATL::MoveFile
- ATLTRANSACTIONMANAGER/ATL::RegCreateKeyEx
- ATLTRANSACTIONMANAGER/ATL::RegDeleteKey
- ATLTRANSACTIONMANAGER/ATL::RegOpenKeyEx
- ATLTRANSACTIONMANAGER/ATL::Rollback
- ATLTRANSACTIONMANAGER/ATL::SetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::m_bFallback
- ATLTRANSACTIONMANAGER/ATL::m_hTransaction
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
ms.openlocfilehash: 031d72903d72af77f6929072e4605d32d81585a3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270206"
---
# <a name="catltransactionmanager-class"></a>Класс CAtlTransactionManager

Класс CAtlTransactionManager предоставляет оболочку для функции диспетчера транзакций ядра (KTM).

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAtlTransactionManager;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[~CAtlTransactionManager](#dtor)|Деструктор CAtlTransactionManager.|
|[CAtlTransactionManager](#catltransactionmanager)|Конструктор CAtlTransactionManager.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Закрыть](#close)|Закрывает один дескриптор транзакции.|
|[Фиксации](#commit)|Запросы, что транзакция быть зафиксирована.|
|[Создание](#create)|Создает дескриптор транзакции.|
|[CreateFile](#createfile)|Создает или открывает файл, файловый поток или каталоге, что и транзакционных операций.|
|[DeleteFile](#deletefile)|Удаляет существующий файл в качестве транзакционных операций.|
|[FindFirstFile](#findfirstfile)|Осуществляет поиск файла или подкаталога в каталоге как транзакционных операций.|
|[GetFileAttributes](#getfileattributes)|Получает атрибуты файловой системы для заданного файла или каталога в виде транзакционных операций.|
|[GetFileAttributesEx](#getfileattributesex)|Получает атрибуты файловой системы для заданного файла или каталога в виде транзакционных операций.|
|[GetHandle](#gethandle)|Возвращает дескриптор транзакции.|
|[IsFallback](#isfallback)|Определяет, включены ли резервный вызовы.|
|[MoveFile](#movefile)|Перемещает файл или каталог, включая его дочерние элементы, как транзакционных операций.|
|[RegCreateKeyEx](#regcreatekeyex)|Создает указанный раздел реестра, который связывается с транзакцией. Если ключ уже существует, функция открывает его.|
|[RegDeleteKey](#regdeletekey)|Удаляет подраздел и его значения из указанного представления платформы реестра как транзакционных операций.|
|[Функция RegOpenKeyEx](#regopenkeyex)|Открывает указанный раздел реестра, который связывается с транзакцией.|
|[Откат](#rollback)|Запросы, для которых будет выполнен откат транзакции.|
|[SetFileAttributes](#setfileattributes)|Задает атрибуты для файла или каталога в виде транзакционных операций.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|Значение TRUE, если резервный вариант поддерживается; Значение FALSE в противном случае.|
|[m_hTransaction](#m_htransaction)|Дескриптор транзакции.|

## <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** atltransactionmanager.h

##  <a name="dtor"></a>  ~ CAtlTransactionManager

Деструктор CAtlTransactionManager.

```
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>Примечания

Обычной обработке, транзакция автоматически зафиксирована и закрыт. Если деструктор вызывается во время очистки исключения, транзакции является откат и закрыт.

##  <a name="catltransactionmanager"></a>  CAtlTransactionManager

Конструктор CAtlTransactionManager.

```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>Параметры

*bFallback*<br/>
Значение TRUE указывает, поддержка резервирования. При сбое транзакционные функции класса автоматически вызывает функцию «без использования транзакций». Значение FALSE указывает вызовы не «базовом».

*bAutoCreateTransaction*<br/>
Значение TRUE указывает, что обработчик транзакций автоматически создается в конструкторе. Значение FALSE указывает, что нет.

### <a name="remarks"></a>Примечания

##  <a name="close"></a>  Закрыть

Закрывает дескриптор транзакции.

```
inline BOOL Close();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `CloseHandle` функции. Метод автоматически вызывается в деструкторе.

##  <a name="commit"></a>  Фиксации

Запросы, что транзакция быть зафиксирована.

```
inline BOOL Commit();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `CommitTransaction` функции. Метод автоматически вызывается в деструкторе.

##  <a name="create"></a>  Создание

Создает дескриптор транзакции.

```
inline BOOL Create();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `CreateTransaction` функции. Проверьте, нет ли

##  <a name="createfile"></a>  CreateFile

Создает или открывает файл, файловый поток или каталоге, что и транзакционных операций.

```
inline HANDLE CreateFile(
    LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```

### <a name="parameters"></a>Параметры

*lpFileName*<br/>
Имя объекта для создания или открытия.

*dwDesiredAccess*<br/>
Доступ к объекту, который сформулировать чтение, запись, оба или ни одного (ноль). Наиболее часто используемые значения GENERIC_READ и GENERIC_WRITE: GENERIC_READ &#124; GENERIC_WRITE.

*dwShareMode*<br/>
Режим общего доступа объекта, который может быть чтение, запись и оба, удаление, все они или нет: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.

*lpSecurityAttributes*<br/>
Указатель на структуру SECURITY_ATTRIBUTES, которая содержит дескриптор безопасности необязательно, а также определяет, может ли возвращаемый дескриптор быть унаследован дочерними процессами. Параметр может иметь значение NULL.

*dwCreationDisposition*<br/>
Действия, предпринимаемые для файлов, которые существуют и не существуют. Этот параметр должен иметь одно из следующих значений, которые нельзя использовать вместе: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING или TRUNCATE_EXISTING.

*dwFlagsAndAttributes*<br/>
Атрибуты файла и флаги. Этот параметр может содержать любое сочетание доступных файловых атрибутов (FILE_ATTRIBUTE_ *). Все другие атрибуты файла переопределить FILE_ATTRIBUTE_NORMAL. Этот параметр может также содержать комбинации флагов (FILE_FLAG_\*) для управления поведением буферизации, доступ к режимы и другие специальные флаги. Их сочетание с любой FILE_ATTRIBUTE_\* значения.

*hTemplateFile*<br/>
Допустимый дескриптор файла шаблона с GENERIC_READ права доступа. Файл шаблона предоставляет атрибуты файла и дополнительные атрибуты для файла, который создается. Этот параметр может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор, который может использоваться для доступа к объекту.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `CreateFileTransacted` функции.

##  <a name="deletefile"></a>  DeleteFile

Удаляет существующий файл в качестве транзакционных операций.

```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Параметры

*lpFileName*<br/>
Имя файла, предназначенного для удаления.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `DeleteFileTransacted` функции.

##  <a name="findfirstfile"></a>  FindFirstFile

Осуществляет поиск файла или подкаталога в каталоге как транзакционных операций.

```
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>Параметры

*lpFileName*<br/>
Каталог или путь и имя файла для поиска. Этот параметр может содержать подстановочные знаки, например звездочку (*) или вопросительный знак ().

*pNextInfo*<br/>
Указатель на структуру WIN32_FIND_DATA, получающий сведения о найденного файла или подкаталога.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращается дескриптор поиска, используемые в последующем вызове `FindNextFile` или `FindClose`. Если функция завершается ошибкой, или не удается найти файлы из строки поиска в *lpFileName* параметр, возвращаемое значение имеет значение INVALID_HANDLE_VALUE.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `FindFirstFileTransacted` функции.

##  <a name="getfileattributes"></a>  GetFileAttributes

Получает атрибуты файловой системы для заданного файла или каталога в виде транзакционных операций.

```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Параметры

*lpFileName*<br/>
Имя файла или каталога.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `GetFileAttributesTransacted` функции.

##  <a name="getfileattributesex"></a>  GetFileAttributesEx

Получает атрибуты файловой системы для заданного файла или каталога в виде транзакционных операций.

```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```

### <a name="parameters"></a>Параметры

*lpFileName*<br/>
Имя файла или каталога.

*fInfoLevelId*<br/>
Уровень извлекаемых данных атрибута.

*lpFileInformation*<br/>
Указатель на буфер, получающий сведения об атрибутах. Тип данных атрибута, который хранится в этот буфер определяется по значению *fInfoLevelId*. Если *fInfoLevelId* параметр имеет GetFileExInfoStandard, то этот параметр указывает на структуру WIN32_FILE_ATTRIBUTE_DATA.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `GetFileAttributesTransacted` функции.

##  <a name="gethandle"></a>  GetHandle

Возвращает дескриптор транзакции.

```
HANDLE GetHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор транзакции для класса. Возвращает значение NULL, если `CAtlTransactionManager` не присоединен к дескриптору.

### <a name="remarks"></a>Примечания

##  <a name="isfallback"></a>  IsFallback

Определяет, включены ли резервный вызовы.

```
BOOL IsFallback() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, является вызовы резервный класс поддерживает. Значение FALSE в противном случае.

### <a name="remarks"></a>Примечания

##  <a name="m_bfallback"></a>  m_bFallback

Значение TRUE, если резервный вариант поддерживается; Значение FALSE в противном случае.

```
BOOL m_bFallback;
```

### <a name="remarks"></a>Примечания

##  <a name="m_htransaction"></a>  m_hTransaction

Дескриптор транзакции.

```
HANDLE m_hTransaction;
```

### <a name="remarks"></a>Примечания

##  <a name="movefile"></a>  MoveFile

Перемещает файл или каталог, включая его дочерние элементы, как транзакционных операций.

```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>Параметры

*lpOldFileName*<br/>
Имя текущего существующий файл или каталог на локальном компьютере.

*lpNewFileName*<br/>
Новое имя для файла или каталога. Это имя не должно уже существовать. Новый файл может быть на разных файловой системы или диска. Новый каталог должен быть на одном диске.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `MoveFileTransacted` функции.

##  <a name="regcreatekeyex"></a>  RegCreateKeyEx

Создает указанный раздел реестра, который связывается с транзакцией. Если ключ уже существует, функция открывает его.

```
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```

### <a name="parameters"></a>Параметры

*открываемый раздел hKey*<br/>
Дескриптор, чтобы открыть раздел реестра.

*lpSubKey*<br/>
Имя раздела, который открывает эту функцию, или создает.

*dwReserved*<br/>
Этот параметр зарезервирован и должен быть равен нулю.

*lpClass*<br/>
Пользовательский класс этот ключ. Этот параметр могут игнорироваться. Этот параметр может иметь значение NULL.

*dwOptions*<br/>
Этот параметр может принимать одно из следующих значений: REG_OPTION_BACKUP_RESTORE REG_OPTION_NON_VOLATILE и REG_OPTION_VOLATILE.

*samDesired*<br/>
Маска, которая указывает права доступа для ключа.

*lpSecurityAttributes*<br/>
Указатель на структуру SECURITY_ATTRIBUTES, которое определяет, может ли возвращаемый дескриптор быть унаследован дочерними процессами. Если *lpSecurityAttributes* имеет значение NULL, дескриптор не наследуется.

*phkResult*<br/>
Указатель на переменную, которая получает дескриптор открыт или созданный ключ. Если ключ не является одним из предопределенных реестра, вызвать `RegCloseKey` функционировать после завершения использования дескриптора.

*lpdwDisposition*<br/>
Указатель на переменную, которая получает один из следующих методов обработки значений: REG_CREATED_NEW_KEY или REG_OPENED_EXISTING_KEY.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевого значения ошибки, определенный в Winerror.h.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `RegCreateKeyTransacted` функции.

##  <a name="regdeletekey"></a>  RegDeleteKey

Удаляет подраздел и его значения из указанного представления платформы реестра как транзакционных операций.

```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*открываемый раздел hKey*|Дескриптор, чтобы открыть раздел реестра.|
|*lpSubKey*|Имя ключа для удаления.|

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевого значения ошибки, определенный в Winerror.h.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `RegDeleteKeyTransacted` функции.

##  <a name="regopenkeyex"></a>  Функция RegOpenKeyEx

Открывает указанный раздел реестра, который связывается с транзакцией.

```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>Параметры

*открываемый раздел hKey*<br/>
Дескриптор, чтобы открыть раздел реестра.

*lpSubKey*<br/>
Имя раздела реестра, чтобы открыть.

*ulOptions*<br/>
Этот параметр зарезервирован и должен быть равен нулю.

*samDesired*<br/>
Маска, которая указывает права доступа для ключа.

*phkResult*<br/>
Указатель на переменную, которая получает дескриптор открыт или созданный ключ. Если ключ не является одним из предопределенных реестра, вызвать `RegCloseKey` функционировать после завершения использования дескриптора.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевого значения ошибки, определенный в Winerror.h

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `RegOpenKeyTransacted` функции.

##  <a name="rollback"></a>  Откат

Запросы, для которых будет выполнен откат транзакции.

```
inline BOOL Rollback();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `RollbackTransaction` функции.

##  <a name="setfileattributes"></a>  SetFileAttributes

Задает атрибуты для файла или каталога в виде транзакционных операций.

```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>Параметры

*lpFileName*<br/>
Имя файла или каталога.

*dwAttributes*<br/>
Атрибуты файла, которые следует задать для файла. Дополнительные сведения см. в разделе [SetFileAttributesTransacted](/windows/desktop/api/winbase/nf-winbase-setfileattributestransacteda).

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `SetFileAttributesTransacted` функции.

## <a name="see-also"></a>См. также

[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)
