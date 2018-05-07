---
title: Класс CAtlTemporaryFile | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49adcb572e355c62e6f21081eb033496e60e2369
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="catltemporaryfile-class"></a>Класс CAtlTemporaryFile
Этот класс предоставляет методы для создания и использования временного файла.  
  
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
|[CAtlTemporaryFile::Close](#close)|Вызовите этот метод для закрытия во временный файл и либо удалите его содержимое, или сохранять их под указанным именем файла.|  
|[CAtlTemporaryFile::Create](#create)|Вызовите этот метод, чтобы создать временный файл.|  
|[CAtlTemporaryFile::Flush](#flush)|Этот метод используется для принудительного любые данные, оставшиеся в буфере файла для записи во временный файл.|  
|[CAtlTemporaryFile::GetPosition](#getposition)|Этот метод используется для получения текущего положения указателя файла.|  
|[CAtlTemporaryFile::GetSize](#getsize)|Этот метод вызывается для получения размера в байтах временного файла.|  
|[CAtlTemporaryFile::HandsOff](#handsoff)|Этот метод вызывается для отмените сопоставление файла с `CAtlTemporaryFile` объекта.|  
|[CAtlTemporaryFile::HandsOn](#handson)|Вызовите этот метод, чтобы открыть существующий временный файл и поместите указатель в конец файла.|  
|[CAtlTemporaryFile::LockRange](#lockrange)|Этот метод вызывается для блокировки области в файле, чтобы предотвратить доступ к нему другими процессами.|  
|[CAtlTemporaryFile::Read](#read)|Этот метод используется для чтения данных из временного файла, начиная с позиции, указываемой параметром указателя файла.|  
|[CAtlTemporaryFile::Seek](#seek)|Этот метод используется для перемещения указателя файла временный файл.|  
|[CAtlTemporaryFile::SetSize](#setsize)|Вызовите этот метод, чтобы задать размер временного файла.|  
|[CAtlTemporaryFile::TempFileName](#tempfilename)|Этот метод используется для получения имени временного файла.|  
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|Этот метод используется для снятия блокировки области временного файла.|  
|[CAtlTemporaryFile::Write](#write)|Этот метод используется для записи данных во временный файл, начиная с позиции, указываемой параметром указателя файла.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlTemporaryFile::operator ДЕСКРИПТОРА](#operator_handle)|Возвращает дескриптор во временный файл.|  
  
## <a name="remarks"></a>Примечания  
 `CAtlTemporaryFile` упрощает процесс создания и использования временного файла. Файл является автоматически с именем, открытия, закрытия и удален. Если содержимое файла требуется закрытия файла, они могут быть сохранены в новый файл с указанным именем.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlfile.h  
  
## <a name="example"></a>Пример  
 Далее приведен пример [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="catltemporaryfile"></a>  CAtlTemporaryFile::CAtlTemporaryFile  
 Конструктор.  
  
```
CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Файл не открыт в действительности, пока выполняется вызов [CAtlTemporaryFile::Create](#create).  
  
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
 Вызовите этот метод для закрытия во временный файл и либо удалите его содержимое, или сохранять их под указанным именем файла.  
  
```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *szNewName*  
 Имя нового файла для хранения временных файлов в содержимое. Если этот аргумент равен NULL, содержимое временный файл удаляется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="create"></a>  CAtlTemporaryFile::Create  
 Вызовите этот метод, чтобы создать временный файл.  
  
```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszDir`  
 Путь для временного файла. Если это значение NULL, [GetTempPath](http://msdn.microsoft.com/library/windows/desktop/aa364992) будет вызываться для присвоения пути.  
  
 `dwDesiredAccess`  
 Необходимый доступ. В разделе `dwDesiredAccess` в [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="flush"></a>  CAtlTemporaryFile::Flush  
 Этот метод используется для принудительного любые данные, оставшиеся в буфере файла для записи во временный файл.  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Аналогично [CAtlTemporaryFile::HandsOff](#handsoff), за исключением того, что файл не закрыт.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="getposition"></a>  CAtlTemporaryFile::GetPosition  
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
 Чтобы изменить положение указателя файла, используйте [CAtlTemporaryFile::Seek](#seek).  
  
##  <a name="getsize"></a>  CAtlTemporaryFile::GetSize  
 Этот метод вызывается для получения размера в байтах временного файла.  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nLen`  
 Число байтов в файле.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
##  <a name="handsoff"></a>  CAtlTemporaryFile::HandsOff  
 Этот метод вызывается для отмените сопоставление файла с `CAtlTemporaryFile` объекта.  
  
```
HRESULT HandsOff() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 `HandsOff` и [CAtlTemporaryFile::HandsOn](#handson) используются для отмените сопоставление файла из объекта и присоединяет ее повторно, при необходимости. `HandsOff` будет принудительно любые данные, оставшиеся в буфере файла для записи во временный файл и закройте файл. Если вы хотите закрыть и окончательно удалить файл или если вы хотите закрыть и сохранить содержимое файла с заданным именем, используйте [CAtlTemporaryFile::Close](#close).  
  
##  <a name="handson"></a>  CAtlTemporaryFile::HandsOn  
 Вызовите этот метод, чтобы открыть существующий временный файл и поместите указатель в конец файла.  
  
```
HRESULT HandsOn() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 [CAtlTemporaryFile::HandsOff](#handsoff) и `HandsOn` используются для отмените сопоставление файла из объекта и присоединяет ее повторно, при необходимости.  
  
##  <a name="lockrange"></a>  CAtlTemporaryFile::LockRange  
 Этот метод вызывается для блокировки области во временном файле, чтобы предотвратить доступ к нему другими процессами.  
  
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
 Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Можно заблокировать более одной области файла, но не перекрывающихся областей разрешены. Чтобы успешно разблокировать области, используйте [CAtlTemporaryFile::UnlockRange](#unlockrange), обеспечивая диапазона байтов в точности соответствует области, которая ранее была заблокирована. `LockRange` не объединять смежных областей; Если заблокированные две области располагаются рядом, необходимо разблокировать каждого отдельно.  
  
##  <a name="operator_handle"></a>  CAtlTemporaryFile::operator ДЕСКРИПТОРА  
 Возвращает дескриптор во временный файл.  
  
```  
operator HANDLE() throw();
```  
  
##  <a name="read"></a>  CAtlTemporaryFile::Read  
 Этот метод используется для чтения данных из временного файла, начиная с позиции, указываемой параметром указателя файла.  
  
```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pBuffer`  
 Указатель на буфер, который будет получать данные, считанные из файла.  
  
 `nBufSize`  
 Размер буфера в байтах.  
  
 `nBytesRead`  
 Количество прочитанных байтов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFile::Read](../../atl/reference/catlfile-class.md#read). Чтобы изменить положение указателя файла, вызовите [CAtlTemporaryFile::Seek](#seek).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="seek"></a>  CAtlTemporaryFile::Seek  
 Этот метод используется для перемещения указателя файла временный файл.  
  
```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nOffset`  
 Смещение в байтах от начала точки, заданной параметром *dwFrom.*  
  
 `dwFrom`  
 Начальная точка (FILE_BEGIN, FILE_CURRENT или FILE_END).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek). Чтобы получить текущее положение указателя файла, вызовите [CAtlTemporaryFile::GetPosition](#getposition).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="setsize"></a>  CAtlTemporaryFile::SetSize  
 Вызовите этот метод, чтобы задать размер временного файла.  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nNewLen`  
 Новая длина файла в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize). При возвращении указатель файла помещается в конец файла.  
  
##  <a name="tempfilename"></a>  CAtlTemporaryFile::TempFileName  
 Этот метод используется для получения имени временного файла.  
  
```
LPCTSTR TempFileName() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `LPCTSTR` указывает имя файла.  
  
### <a name="remarks"></a>Примечания  
 Имя файла формируется в [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile) вызовом [GetTempFile](http://msdn.microsoft.com/library/windows/desktop/aa364991)функции пакета SDK для Windows. Расширение файла всегда будет «TFR» для временного файла.  
  
##  <a name="unlockrange"></a>  CAtlTemporaryFile::UnlockRange  
 Этот метод используется для снятия блокировки области временного файла.  
  
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
 Вызовы [CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange).  
  
##  <a name="write"></a>  CAtlTemporaryFile::Write  
 Этот метод используется для записи данных во временный файл, начиная с позиции, указываемой параметром указателя файла.  
  
```
HRESULT Write(  
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pBuffer`  
 Буфер, содержащий данные для записи в файл.  
  
 `nBufSize`  
 Число байтов, переданных из буфера.  
  
 `pnBytesWritten`  
 Число записанных байтов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFile::Write](../../atl/reference/catlfile-class.md#write).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CAtlFile](../../atl/reference/catlfile-class.md)
