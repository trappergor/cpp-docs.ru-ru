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
ms.openlocfilehash: 5c2814f963ea4814e0d7585e0e4d6dda26c1f04d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321329"
---
# <a name="catltransactionmanager-class"></a>Класс CAtlTransactionManager

Класс CAtlTransactionManager предоставляет обертку для функций менеджера по транзакциям ядра (KTM).

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CAtlTransactionManager;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[«CAtlTransactionManager](#dtor)|CAtlTransactionManager деструктор.|
|[CAtlTransactionManager](#catltransactionmanager)|Конструктор CAtlTransactionManager.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Закрыть](#close)|Закрывает одну ручку транзакции.|
|[Commit](#commit)|Запросы на совершение транзакции.|
|[Создать](#create)|Создает ручку транзакции.|
|[CreateFile](#createfile)|Создает или открывает файл, поток файлов или каталог в качестве операции.|
|[DeleteFile](#deletefile)|Удаляет существующий файл в качестве операции.|
|[FindFirstFile](#findfirstfile)|Поиск каталога для файла или субдиректоров в качестве операции.|
|[GetFileАтрибуты](#getfileattributes)|Извлекает атрибуты файловой системы для определенного файла или каталога в качестве операции.|
|[GetFileAttributesEx](#getfileattributesex)|Извлекает атрибуты файловой системы для определенного файла или каталога в качестве операции.|
|[GetHandle](#gethandle)|Возвращает ручку транзакции.|
|[IsFallback](#isfallback)|Определяет, включены ли обратные вызовы.|
|[MoveFile](#movefile)|Перемещение существующего файла или каталога, включая его детей, в качестве операции.|
|[RegCreateKeyEx](#regcreatekeyex)|Создает указанный ключ реестра и связывает его с транзакцией. Если ключ уже существует, функция открывает его.|
|[RegDeleteKey](#regdeletekey)|Удаляет подключку и его значения из указанного представления реестра, конкретного платформы, как операцию.|
|[RegOpenKeyEx](#regopenkeyex)|Открывает указанный ключ реестра и связывает его с транзакцией.|
|[Отката](#rollback)|Запросы на откат транзакции.|
|[SetFileАтрибуты](#setfileattributes)|Устанавливает атрибуты для файла или каталога как операцию.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|TRUE, если резерв поддерживается; FALSE в противном случае.|
|[m_hTransaction](#m_htransaction)|Ручка транзакции.|

## <a name="remarks"></a>Remarks

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ATL:CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** atltransactionmanager.h

## <a name="catltransactionmanager"></a><a name="dtor"></a>«CAtlTransactionManager

CAtlTransactionManager деструктор.

```
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>Remarks

При обычной обработке транзакция автоматически завоевывается и закрывается. Если деструктор вызывается во время отвечения, транзакция откатывается и закрывается.

## <a name="catltransactionmanager"></a><a name="catltransactionmanager"></a>CAtlTransactionManager

Конструктор CAtlTransactionManager.

```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>Параметры

*bFallback*<br/>
TRUE указывает на резервное копирование поддержки. Если сбой сработала функция, класс автоматически вызывает "неспроизнеденную" функцию. FALSE указывает на отсутствие "откатных" вызовов.

*bAutoCreateТранспаприс*<br/>
TRUE указывает, что обработчик транзакций создается автоматически в конструкторе. FALSE указывает, что это не так.

### <a name="remarks"></a>Remarks

## <a name="close"></a><a name="close"></a>Закрыть

Закрывает ручку транзакции.

```
inline BOOL Close();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Remarks

Эта обертка `CloseHandle` вызывает функцию. Метод автоматически вызывается в деструкторе.

## <a name="commit"></a><a name="commit"></a>Совершить

Запросы на совершение транзакции.

```
inline BOOL Commit();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Remarks

Эта обертка `CommitTransaction` вызывает функцию. Метод автоматически вызывается в деструкторе.

## <a name="create"></a><a name="create"></a>Создать

Создает ручку транзакции.

```
inline BOOL Create();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Remarks

Эта обертка `CreateTransaction` вызывает функцию. Проверить его на

## <a name="createfile"></a><a name="createfile"></a>Createfile

Создает или открывает файл, поток файлов или каталог в качестве операции.

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
Название объекта, который будет создан или открыт.

*dwDesiredAccess*<br/>
Доступ к объекту, который может быть обобщен как читать, писать, как, или ни (ноль). Наиболее часто используемыми значениями являются GENERIC_READ, GENERIC_WRITE или оба: GENERIC_READ &#124; GENERIC_WRITE.

*dwShareMode*<br/>
Режим совместного использования объекта, который может быть прочитан, написать, как, удалить, все из них, или нет: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.

*lpSecurityАтрибуты*<br/>
Указатель на структуру SECURITY_ATTRIBUTES, содержащую дополнительный дескриптор безопасности, а также определяет, может ли возвращенная ручка быть унаследована детскими процессами. Параметр может быть NULL.

*dwCreationDisposition*<br/>
Действие, чтобы взять на файлы, которые существуют и не существуют. Этот параметр должен быть одним из следующих значений, которые не могут быть объединены: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING или TRUNCATE_EXISTING.

*dwFlagsAndАтрибуты*<br/>
Атрибуты файла и флаги. Этот параметр может включать любую комбинацию доступных атрибутов файла (FILE_ATTRIBUTE_). Все остальные атрибуты файлов переопределяют FILE_ATTRIBUTE_NORMAL. Этот параметр может также содержать\*комбинации флагов (FILE_FLAG_) для управления поведением буферизации, режимов доступа и других флагов специального назначения. Они сочетаются\* с любыми FILE_ATTRIBUTE_ значениями.

*hTemplateFile*<br/>
Действительная ручка для файла шаблона с правом доступа GENERIC_READ. Файл шаблона поставляет атрибуты файла и расширенные атрибуты для создаваемого файла. Этот параметр может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку, которая может быть использована для доступа к объекту.

### <a name="remarks"></a>Remarks

Эта обертка `CreateFileTransacted` вызывает функцию.

## <a name="deletefile"></a><a name="deletefile"></a>DeleteFile

Удаляет существующий файл в качестве операции.

```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Параметры

*lpFileName*<br/>
Имя файла, предназначенного для удаления.

### <a name="remarks"></a>Remarks

Эта обертка `DeleteFileTransacted` вызывает функцию.

## <a name="findfirstfile"></a><a name="findfirstfile"></a>FindFirstFile

Поиск каталога для файла или субдиректоров в качестве операции.

```
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>Параметры

*lpFileName*<br/>
Каталог или путь, и имя файла для поиска. Этот параметр может включать символы подстановочных знаков, такие как звездочка (я) или вопросительный знак ().

*pNextInfo*<br/>
Указатель на WIN32_FIND_DATA структуру, которая получает информацию об найденном файле или субдиректоре.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата — это ручка поиска, используемая в последующем вызове `FindNextFile` или `FindClose`. Если функция не удается или не может найти файлы из строки поиска в параметре *lpFileName,* значение возврата INVALID_HANDLE_VALUE.

### <a name="remarks"></a>Remarks

Эта обертка `FindFirstFileTransacted` вызывает функцию.

## <a name="getfileattributes"></a><a name="getfileattributes"></a>GetFileАтрибуты

Извлекает атрибуты файловой системы для определенного файла или каталога в качестве операции.

```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Параметры

*lpFileName*<br/>
Имя файла или каталога.

### <a name="remarks"></a>Remarks

Эта обертка `GetFileAttributesTransacted` вызывает функцию.

## <a name="getfileattributesex"></a><a name="getfileattributesex"></a>GetFileAttributesEx

Извлекает атрибуты файловой системы для определенного файла или каталога в качестве операции.

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
Уровень атрибута информации для получения.

*lpFileInformation*<br/>
Указатель на буфер, который получает информацию об атрибуте. Тип информации об атрибутах, хранящейся в этом буфере, определяется значением *fInfoLevelId.* Если параметр *fInfoLevelId* - GetFileExInfoStandard, то этот параметр указывает на WIN32_FILE_ATTRIBUTE_DATA структуру.

### <a name="remarks"></a>Remarks

Эта обертка `GetFileAttributesTransacted` вызывает функцию.

## <a name="gethandle"></a><a name="gethandle"></a>GetHandle

Возвращает ручку транзакции.

```
HANDLE GetHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку транзакции для класса. Возвращает NULL, `CAtlTransactionManager` если он не прикреплен к ручке.

### <a name="remarks"></a>Remarks

## <a name="isfallback"></a><a name="isfallback"></a>IsFallback

Определяет, включены ли обратные вызовы.

```
BOOL IsFallback() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE это класс поддерживает обратные вызовы. FALSE в противном случае.

### <a name="remarks"></a>Remarks

## <a name="m_bfallback"></a><a name="m_bfallback"></a>m_bFallback

TRUE, если резерв поддерживается; FALSE в противном случае.

```
BOOL m_bFallback;
```

### <a name="remarks"></a>Remarks

## <a name="m_htransaction"></a><a name="m_htransaction"></a>m_hTransaction

Ручка транзакции.

```
HANDLE m_hTransaction;
```

### <a name="remarks"></a>Remarks

## <a name="movefile"></a><a name="movefile"></a>MoveFile

Перемещение существующего файла или каталога, включая его детей, в качестве операции.

```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>Параметры

*lpOldFileName*<br/>
Текущее имя существующего файла или каталога на локальном компьютере.

*lpNewFileName*<br/>
Новое имя файла или каталога. Это имя уже не должно существовать. Новый файл может быть в другой файловой системе или диске. Новый каталог должен быть на том же диске.

### <a name="remarks"></a>Remarks

Эта обертка `MoveFileTransacted` вызывает функцию.

## <a name="regcreatekeyex"></a><a name="regcreatekeyex"></a>RegCreateKeyEx

Создает указанный ключ реестра и связывает его с транзакцией. Если ключ уже существует, функция открывает его.

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

*hKey*<br/>
Ручка к ключу открытого реестра.

*lpSubKey*<br/>
Имя подключаемого ключа, который эта функция открывает или создает.

*dwReserved*<br/>
Этот параметр зарезервирован и должен быть нулевым.

*lpClass*<br/>
Пользовательский класс этого ключа. Этот параметр может быть проигнорирован. Этот параметр может быть NULL.

*dwOptions*<br/>
Этот параметр может быть одним из следующих значений: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE или REG_OPTION_VOLATILE.

*samDesired*<br/>
Маска, которая определяет права доступа для ключа.

*lpSecurityАтрибуты*<br/>
Указатель на структуру SECURITY_ATTRIBUTES определяет, может ли возвращаемый дескриптор быть унаследован дочерними процессами. Если *lpSecurityAttributes* является NULL, ручка не может быть унаследована.

*phkResult*<br/>
Указатель на переменную, которая получает ручку к открытому или созданного ключу. Если ключ не является одним из предопределенных `RegCloseKey` ключей реестра, позвоните в функцию после того, как вы закончите использовать ручку.

*lpdwDisposition*<br/>
Указатель на переменную, которая получает одно из следующих значений расположения: REG_CREATED_NEW_KEY или REG_OPENED_EXISTING_KEY.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата ERROR_SUCCESS. Если функция выходит из строя, значение возврата является кодом ошибки ненулевого, определенным в Winerror.h.

### <a name="remarks"></a>Remarks

Эта обертка `RegCreateKeyTransacted` вызывает функцию.

## <a name="regdeletekey"></a><a name="regdeletekey"></a>RegDeleteKey

Удаляет подключку и его значения из указанного представления реестра, конкретного платформы, как операцию.

```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*hKey*|Ручка к ключу открытого реестра.|
|*lpSubKey*|Имя ключа, которое будет удалено.|

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата ERROR_SUCCESS. Если функция выходит из строя, значение возврата является кодом ошибки ненулевого, определенным в Winerror.h.

### <a name="remarks"></a>Remarks

Эта обертка `RegDeleteKeyTransacted` вызывает функцию.

## <a name="regopenkeyex"></a><a name="regopenkeyex"></a>RegOpenKeyEx

Открывает указанный ключ реестра и связывает его с транзакцией.

```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Ручка к ключу открытого реестра.

*lpSubKey*<br/>
Название подключаемого ключа реестра, которое будет открыто.

*ulOptions*<br/>
Этот параметр зарезервирован и должен быть нулевым.

*samDesired*<br/>
Маска, которая определяет права доступа для ключа.

*phkResult*<br/>
Указатель на переменную, которая получает ручку к открытому или созданного ключу. Если ключ не является одним из предопределенных `RegCloseKey` ключей реестра, позвоните в функцию после того, как вы закончите использовать ручку.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата ERROR_SUCCESS. Если функция выходит из строя, значение возврата является кодом ошибки без нуля, определенным в Winerror.h

### <a name="remarks"></a>Remarks

Эта обертка `RegOpenKeyTransacted` вызывает функцию.

## <a name="rollback"></a><a name="rollback"></a>Отката

Запросы на откат транзакции.

```
inline BOOL Rollback();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Remarks

Эта обертка `RollbackTransaction` вызывает функцию.

## <a name="setfileattributes"></a><a name="setfileattributes"></a>SetFileАтрибуты

Устанавливает атрибуты для файла или каталога как операцию.

```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>Параметры

*lpFileName*<br/>
Имя файла или каталога.

*dwАтрибуты*<br/>
Атрибуты файла для настройки файла. Для получения дополнительной информации [см. SetFileAttributesTransacted](/windows/win32/api/winbase/nf-winbase-setfileattributestransactedw).

### <a name="remarks"></a>Remarks

Эта обертка `SetFileAttributesTransacted` вызывает функцию.

## <a name="see-also"></a>См. также раздел

[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)
