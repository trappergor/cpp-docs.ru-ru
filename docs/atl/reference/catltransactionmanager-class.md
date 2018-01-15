---
title: "Класс catltransactionmanager. | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
helpviewer_keywords: CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0def8aa809cd1ccc115ccc2a09b1ae752316098f
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="catltransactionmanager-class"></a>Класс catltransactionmanager.
Catltransactionmanager класс предоставляет оболочку для функции диспетчера транзакций ядра (KTM).  
  
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
|[~ Catltransactionmanager.](#dtor)|Деструктор catltransactionmanager.|  
|[Catltransactionmanager.](#catltransactionmanager)|Конструктор catltransactionmanager.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Закрыть](#close)|Закрывает один дескриптор транзакции.|  
|[Фиксация](#commit)|Запросы, что транзакция быть зафиксирована.|  
|[Создание](#create)|Создает дескриптор транзакции.|  
|[CreateFile](#createfile)|Создает или открывает файл, файловый поток или каталоге, что и транзакционных операций.|  
|[DeleteFile](#deletefile)|Удаляет существующий файл как транзакционных операций.|  
|[FindFirstFile](#findfirstfile)|Осуществляет поиск файла или вложенной папки в каталоге как транзакционных операций.|  
|[GetFileAttributes](#getfileattributes)|Получает атрибуты файловой системы для заданного файла или каталога в виде транзакционных операций.|  
|[GetFileAttributesEx](#getfileattributesex)|Получает атрибуты файловой системы для заданного файла или каталога в виде транзакционных операций.|  
|[GetHandle](#gethandle)|Возвращает дескриптор транзакции.|  
|[IsFallback](#isfallback)|Определяет, включены ли резервный вызовов.|  
|[MoveFile](#movefile)|Перемещение существующего файла или каталога, включая его дочерние элементы в качестве транзакционных операций.|  
|[RegCreateKeyEx](#regcreatekeyex)|Создает указанный раздел реестра и связывает его с транзакцией. Если ключ уже существует, функция открывает его.|  
|[RegDeleteKey](#regdeletekey)|Удаляет раздел и его значения из указанного представления платформой реестра как транзакционных операций.|  
|[Ошибка](#regopenkeyex)|Открывает указанный раздел реестра и связывает его с транзакцией.|  
|[Откат](#rollback)|Запросы, будет выполнен откат транзакции.|  
|[SetFileAttributes](#setfileattributes)|Задает атрибуты для файла или каталога в виде транзакционных операций.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[m_bFallback](#m_bfallback)|`TRUE`Если этот резервный механизм поддерживается; `FALSE` в противном случае.|  
|[m_hTransaction](#m_htransaction)|Дескриптор транзакции.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltransactionmanager.h  
  
##  <a name="dtor"></a>~ Catltransactionmanager.  
 Деструктор catltransactionmanager.  
  
```
virtual ~CAtlTransactionManager();
```  
  
### <a name="remarks"></a>Примечания  
 В обычной обработки транзакция автоматически зафиксирована и закрыт. Если деструктор вызывается во время очистки исключения, транзакции откат и закрыт.  
  
##  <a name="catltransactionmanager"></a>Catltransactionmanager.  
 Конструктор catltransactionmanager.  
  
```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bFallback`  
 `TRUE`Указывает поддержку fallback. При сбое транзакции функции класса автоматически вызывает функцию «без использования транзакций». `FALSE`Указывает вызовы не «базовом».  
  
 `bAutoCreateTransaction`  
 `TRUE`Указывает, автоматически созданный обработчик транзакции в конструкторе. `FALSE`Указывает, что он не.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="close"></a>Закрыть  
 Закрывает дескриптор транзакции.  
  
```
inline BOOL Close();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `CloseHandle` функции. Метод автоматически вызывается в деструкторе.  
  
##  <a name="commit"></a>Фиксация  
 Запросы, что транзакция быть зафиксирована.  
  
```
inline BOOL Commit();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `CommitTransaction` функции. Метод автоматически вызывается в деструкторе.  
  
##  <a name="create"></a>Создание  
 Создает дескриптор транзакции.  
  
```
inline BOOL Create();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `CreateTransaction` функции. Для проверки  
  
##  <a name="createfile"></a>CreateFile  
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
 `lpFileName`  
 Имя объекта будет создана или открыта.  
  
 `dwDesiredAccess`  
 Доступ с объектом, который можно интерпретировать как чтение, запись, оба или ни одного (ноль). Наиболее часто используемые значения являются GENERIC_READ и GENERIC_WRITE: GENERIC_READ &#124; GENERIC_WRITE.  
  
 `dwShareMode`  
 Режим общего доступа объектом, который может быть чтение, запись и оба, удалить, все они или нет: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.  
  
 `lpSecurityAttributes`  
 Указатель на структуру SECURITY_ATTRIBUTES, которая содержит дескриптор безопасности необязательно, а также определяет, могут ли возвращаемый дескриптор наследоваться дочерними процессами. Значением параметра может быть `NULL`.  
  
 `dwCreationDisposition`  
 Действия, предпринимаемые для файлов, которые существуют и не существуют. Этот параметр должен иметь одно из следующих значений, которые нельзя использовать вместе: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING или TRUNCATE_EXISTING.  
  
 `dwFlagsAndAttributes`  
 Атрибуты и флаги файла. Этот параметр может содержать любое сочетание доступные атрибуты (FILE_ATTRIBUTE_ *). Все остальные атрибуты файла переопределить FILE_ATTRIBUTE_NORMAL. Этот параметр также может содержать сочетание флагов (FILE_FLAG_\*) для управления поведение буферизации, доступ к режимы и другие специальные флаги. Их сочетание с любой FILE_ATTRIBUTE_\* значения.  
  
 `hTemplateFile`  
 Допустимый дескриптор файла шаблона с GENERIC_READ права доступа. Файл шаблона предоставляет атрибуты файла и расширенных атрибутов для создаваемого файла. Этот параметр может иметь значение `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор, который может использоваться для доступа к объекту.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `CreateFileTransacted` функции.  
  
##  <a name="deletefile"></a>DeleteFile  
 Удаляет существующий файл как транзакционных операций.  
  
```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFileName`  
 Имя файла, предназначенного для удаления.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `DeleteFileTransacted` функции.  
  
##  <a name="findfirstfile"></a>FindFirstFile  
 Осуществляет поиск файла или вложенной папки в каталоге как транзакционных операций.  
  
```
inline HANDLE FindFirstFile(
  LPCTSTR lpFileName,
  WIN32_FIND_DATA* pNextInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFileName`  
 Каталог или путь и имя файла для поиска. Этот параметр может содержать подстановочные знаки, например звездочки (*) или вопросительный знак ().  
  
 `pNextInfo`  
 Указатель на структуру WIN32_FIND_DATA, который получает сведения о найденного файла или вложенной папки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращается дескриптор поиска, используемый в последующем вызове для `FindNextFile` или `FindClose`. Если функция завершается сбоем или не удается найти файлы из строки поиска в `lpFileName` параметр, возвращаемое значение является INVALID_HANDLE_VALUE.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `FindFirstFileTransacted` функции.  
  
##  <a name="getfileattributes"></a>GetFileAttributes  
 Получает атрибуты файловой системы для заданного файла или каталога в виде транзакционных операций.  
  
```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFileName`  
 Имя файла или каталога.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `GetFileAttributesTransacted` функции.  
  
##  <a name="getfileattributesex"></a>GetFileAttributesEx  
 Получает атрибуты файловой системы для заданного файла или каталога в виде транзакционных операций.  
  
```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFileName`  
 Имя файла или каталога.  
  
 `fInfoLevelId`  
 Уровень извлекаемых данных атрибута.  
  
 `lpFileInformation`  
 Указатель на буфер, получающий сведения об атрибутах. Тип данных атрибута, хранящийся в этот буфер определяется по значению `fInfoLevelId`. Если `fInfoLevelId` параметр имеет GetFileExInfoStandard, то этот параметр указывает на структуру WIN32_FILE_ATTRIBUTE_DATA.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `GetFileAttributesTransacted` функции.  
  
##  <a name="gethandle"></a>GetHandle  
 Возвращает дескриптор транзакции.  
  
```
HANDLE GetHandle() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор транзакции для класса. Возвращает `NULL` Если `CAtlTransactionManager` не присоединен к дескриптору.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isfallback"></a>IsFallback  
 Определяет, включены ли резервный вызовов.  
  
```
BOOL IsFallback() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` является класс поддерживает резервной вызовов. В противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_bfallback"></a>m_bFallback  
 `TRUE`Если этот резервный механизм поддерживается; `FALSE` в противном случае.  
  
```
BOOL m_bFallback;
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_htransaction"></a>m_hTransaction  
 Дескриптор транзакции.  
  
```
HANDLE m_hTransaction;
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="movefile"></a>MoveFile  
 Перемещение существующего файла или каталога, включая его дочерние элементы в качестве транзакционных операций.  
  
```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpOldFileName`  
 Текущее имя существующий файл или каталог на локальном компьютере.  
  
 `lpNewFileName`  
 Новое имя для файла или каталога. Это имя не должно существовать. Новый файл может быть в другой файловой системы или диск. Новый каталог должен быть на том же диске.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `MoveFileTransacted` функции.  
  
##  <a name="regcreatekeyex"></a>RegCreateKeyEx  
 Создает указанный раздел реестра и связывает его с транзакцией. Если ключ уже существует, функция открывает его.  
  
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
 `hKey`  
 Дескриптор, чтобы открыть раздел реестра.  
  
 `lpSubKey`  
 Имя раздела, который открывает эту функцию, или создает.  
  
 `dwReserved`  
 Этот параметр зарезервирован и должен быть равен нулю.  
  
 `lpClass`  
 Пользовательский класс этот ключ. Этот параметр можно пропустить. Этот параметр может иметь значение NULL.  
  
 `dwOptions`  
 Этот параметр может принимать одно из следующих значений: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE или REG_OPTION_VOLATILE.  
  
 `samDesired`  
 Маска, указывающая права доступа к этому ключу.  
  
 `lpSecurityAttributes`  
 Указатель на структуру SECURITY_ATTRIBUTES, которое определяет, может ли возвращаемый дескриптор наследоваться дочерними процессами. Если `lpSecurityAttributes` — `NULL`, дескриптор не наследуется.  
  
 `phkResult`  
 Указатель на переменную, которая получает дескриптор открытого или созданный ключ. Если ключ не является одним из стандартных реестра, вызовите `RegCloseKey` работать после завершения использования дескриптора.  
  
 `lpdwDisposition`  
 Указатель на переменную, которая получает одно из следующих методов обработки значений: REG_CREATED_NEW_KEY или REG_OPENED_EXISTING_KEY.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевое значение ошибки, определенные в файле Winerror.h.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `RegCreateKeyTransacted` функции.  
  
##  <a name="regdeletekey"></a>RegDeleteKey  
 Удаляет раздел и его значения из указанного представления платформой реестра как транзакционных операций.  
  
```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`hKey`|Дескриптор, чтобы открыть раздел реестра.|  
|`lpSubKey`|Имя ключа для удаления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевое значение ошибки, определенные в файле Winerror.h.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `RegDeleteKeyTransacted` функции.  
  
##  <a name="regopenkeyex"></a>Ошибка  
 Открывает указанный раздел реестра и связывает его с транзакцией.  
  
```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```  
  
### <a name="parameters"></a>Параметры  
 `hKey`  
 Дескриптор, чтобы открыть раздел реестра.  
  
 `lpSubKey`  
 Имя раздела реестра, который должен быть открыт.  
  
 `ulOptions`  
 Этот параметр зарезервирован и должен быть равен нулю.  
  
 `samDesired`  
 Маска, указывающая права доступа к этому ключу.  
  
 `phkResult`  
 Указатель на переменную, которая получает дескриптор открытого или созданный ключ. Если ключ не является одним из стандартных реестра, вызовите `RegCloseKey` работать после завершения использования дескриптора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевое значение ошибки, определенные в файле Winerror.h  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `RegOpenKeyTransacted` функции.  
  
##  <a name="rollback"></a>Откат  
 Запросы, будет выполнен откат транзакции.  
  
```
inline BOOL Rollback();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `RollbackTransaction` функции.  
  
##  <a name="setfileattributes"></a>SetFileAttributes  
 Задает атрибуты для файла или каталога в виде транзакционных операций.  
  
```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFileName`  
 Имя файла или каталога.  
  
 `dwAttributes`  
 Атрибуты файлов установки для файла. Дополнительные сведения см. в разделе [SetFileAttributesTransacted](http://go.microsoft.com/fwlink/p/?linkid=158699).  
  
### <a name="remarks"></a>Примечания  
 Эта оболочка вызывает `SetFileAttributesTransacted` функции.  
  
## <a name="see-also"></a>См. также  
 [Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)
