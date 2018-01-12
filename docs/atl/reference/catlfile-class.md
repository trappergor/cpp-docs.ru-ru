---
title: "Класс CAtlFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
helpviewer_keywords: CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a66e697a3599e7bfeef0f1d5d147e19b668222ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="catlfile-class"></a>Класс CAtlFile
Этот класс предоставляет тонкую оболочку вокруг Windows API обработки файлов.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlFile : public CHandle
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlFile::CAtlFile](#catlfile)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlFile::Create](#create)|Этот метод используется для создания или открытия файла.|  
|[CAtlFile::Flush](#flush)|Этот метод вызывается для удаления буферов для файла и потере всех буферизованных данных для записи в файл.|  
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|Этот метод вызывается для получения результатов операции перекрывающихся в файле.|  
|[CAtlFile::GetPosition](#getposition)|Этот метод вызывается для получения текущего положения указателя файла из файла.|  
|[CAtlFile::GetSize](#getsize)|Этот метод вызывается для получения размера файла в байтах.|  
|[CAtlFile::LockRange](#lockrange)|Этот метод вызывается для блокировки области в файле, чтобы предотвратить доступ к нему другими процессами.|  
|[CAtlFile::Read](#read)|Этот метод вызывается для чтения данных из файла, начиная с позиции, указываемой параметром указателя файла.|  
|[CAtlFile::Seek](#seek)|Этот метод используется для перемещения файла указателя файла.|  
|[CAtlFile::SetSize](#setsize)|Этот метод используется для изменения размера файла.|  
|[CAtlFile::UnlockRange](#unlockrange)|Этот метод используется для снятия блокировки области файла.|  
|[CAtlFile::Write](#write)|Этот метод используется для записи данных в файл, начиная с позиции, указываемой параметром указателя файла.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CAtlFile::m_pTM](#m_ptm)|Указатель на `CAtlTransactionManager` объект|  
  
## <a name="remarks"></a>Примечания  
 Этот класс используется при потребности обработки файлов относительно просты, но дополнительные абстракции, чем Windows API является обязательным, не включая зависимости MFC.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CHandle](../../atl/reference/chandle-class.md)  
  
 `CAtlFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlfile.h  
  
##  <a name="catlfile"></a>CAtlFile::CAtlFile  
 Конструктор.  
  
```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `file`  
 Объект файла.  
  
 `hFile`  
 Дескриптор файла.  
  
 `pTM`  
 Указатель на объект CAtlTransactionManager.  
  
### <a name="remarks"></a>Примечания  
 Конструктор копии передает право владения дескриптора файла из исходных `CAtlFile` в созданный объект.  
  
##  <a name="create"></a>CAtlFile::Create  
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
 *szFilename*  
 Имя файла.  
  
 `dwDesiredAccess`  
 Необходимый доступ. В разделе `dwDesiredAccess` в [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) в Windows SDK.  
  
 `dwShareMode`  
 Режим общего доступа. В разделе `dwShareMode` в **CreateFile**.  
  
 `dwCreationDisposition`  
 Расположение для создания. В разделе `dwCreationDisposition` в **CreateFile**.  
  
 `dwFlagsAndAttributes`  
 Флаги и атрибуты. В разделе `dwFlagsAndAttributes` в **CreateFile**.  
  
 `lpsa`  
 Атрибуты безопасности. В разделе *lpSecurityAttributes* в **CreateFile**.  
  
 `hTemplateFile`  
 Файл шаблона. В разделе `hTemplateFile` в **CreateFile**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) для создания или открытия файла.  
  
##  <a name="flush"></a>CAtlFile::Flush  
 Этот метод вызывается для удаления буферов для файла и потере всех буферизованных данных для записи в файл.  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [FlushFileBuffers](http://msdn.microsoft.com/library/windows/desktop/aa364439) очистки буферизованных данных в файл.  
  
##  <a name="getoverlappedresult"></a>CAtlFile::GetOverlappedResult  
 Этот метод вызывается для получения результатов операции перекрывающихся в файле.  
  
```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pOverlapped`  
 Перекрывающиеся структуры. В разделе `lpOverlapped` в [GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209) в Windows SDK.  
  
 *dwBytesTransferred*  
 Переданных байтов. В разделе *lpNumberOfBytesTransferred* в `GetOverlappedResult`.  
  
 `bWait`  
 Параметр ожидания. В разделе `bWait` в `GetOverlappedResult`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209) для получения результатов операции перекрывающихся в файле.  
  
##  <a name="getposition"></a>CAtlFile::GetPosition  
 Этот метод используется для получения текущего положения указателя файла.  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Позиция, в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) для получения текущего положения указателя файла.  
  
##  <a name="getsize"></a>CAtlFile::GetSize  
 Этот метод вызывается для получения размера файла в байтах.  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nLen`  
 Число байтов в файле.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [GetFileSize](http://msdn.microsoft.com/library/windows/desktop/aa364955) получить размер файла в байтах.  
  
##  <a name="lockrange"></a>CAtlFile::LockRange  
 Этот метод вызывается для блокировки области в файле, чтобы предотвратить доступ к нему другими процессами.  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Позиция в файле, где должна начинаться блокировки.  
  
 `nCount`  
 Длина диапазона байтов будет заблокирован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [LockFile](http://msdn.microsoft.com/library/windows/desktop/aa365202) для блокировки области в файле. Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Можно заблокировать более одной области файла, но не перекрывающихся областей разрешены. При снятии блокировки области, с помощью [CAtlFile::UnlockRange](#unlockrange), диапазон байтов должно точно соответствовать ранее заблокированной области. `LockRange`не объединять смежных областей; Если заблокированные две области располагаются рядом, необходимо разблокировать каждого отдельно.  
  
##  <a name="m_ptm"></a>CAtlFile::m_pTM  
 Указатель на `CAtlTransactionManager` объект.  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="read"></a>CAtlFile::Read  
 Этот метод вызывается для чтения данных из файла, начиная с позиции, указываемой параметром указателя файла.  
  
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
 `pBuffer`  
 Указатель на буфер, который будет получать данные, считанные из файла.  
  
 `nBufSize`  
 Размер буфера в байтах.  
  
 `nBytesRead`  
 Количество прочитанных байтов.  
  
 `pOverlapped`  
 Перекрывающиеся структуры. В разделе `lpOverlapped` в [ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467) в Windows SDK.  
  
 `pfnCompletionRoutine`  
 Подпрограммы завершения. В разделе *lpCompletionRoutine* в [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Первые три формы вызвать [ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467), последний [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) для чтения данных из файла. Используйте [CAtlFile::Seek](#seek) для перемещения указателя файла.  
  
##  <a name="seek"></a>CAtlFile::Seek  
 Этот метод используется для перемещения файла указателя файла.  
  
```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nOffset`  
 Смещение от начальной точки, заданной параметром `dwFrom`.  
  
 `dwFrom`  
 Начальная точка (FILE_BEGIN, FILE_CURRENT или FILE_END).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) для перемещения указателя файла.  
  
##  <a name="setsize"></a>CAtlFile::SetSize  
 Этот метод используется для изменения размера файла.  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nNewLen`  
 Новая длина файла в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) и [SetEndOfFile](http://msdn.microsoft.com/library/windows/desktop/aa365531) для изменения размера файла. При возвращении указатель файла помещается в конец файла.  
  
##  <a name="unlockrange"></a>CAtlFile::UnlockRange  
 Этот метод используется для снятия блокировки области файла.  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Позиция в файле, где должна начинаться снятие блокировки.  
  
 `nCount`  
 Длина диапазона байтов должен быть разблокирован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [UnlockFile](http://msdn.microsoft.com/library/windows/desktop/aa365715) для разблокировки области файла.  
  
##  <a name="write"></a>CAtlFile::Write  
 Этот метод используется для записи данных в файл, начиная с позиции, указываемой параметром указателя файла.  
  
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
 `pBuffer`  
 Буфер, содержащий данные для записи в файл.  
  
 `nBufSize`  
 Число байтов, переданных из буфера.  
  
 `pOverlapped`  
 Перекрывающиеся структуры. В разделе `lpOverlapped` в [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747) в Windows SDK.  
  
 `pfnCompletionRoutine`  
 Подпрограммы завершения. В разделе *lpCompletionRoutine* в [WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748) в Windows SDK.  
  
 `pnBytesWritten`  
 Записанных байтов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Первые три формы вызвать [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747), последний вызовы [WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748) для записи данных в файл. Используйте [CAtlFile::Seek](#seek) для перемещения указателя файла.  
  
## <a name="see-also"></a>См. также  
 [Образец Marquee](../../visual-cpp-samples.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CHandle](../../atl/reference/chandle-class.md)
