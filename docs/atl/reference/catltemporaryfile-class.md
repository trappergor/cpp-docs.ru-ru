---
title: "Класс CAtlTemporaryFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9673c5a137feddb0eb696945ec6abeb5f3cb062e
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="catltemporaryfile-class"></a>Класс CAtlTemporaryFile
Этот класс предоставляет методы для создания и использования временного файла.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlTemporaryFile
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|Конструктор.|  
|[CAtlTemporaryFile:: ~ CAtlTemporaryFile](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlTemporaryFile::Close](#close)|Вызовите этот метод для закрытия во временный файл и либо удалите его содержимое, или сохранять их под именем указанного файла.|  
|[CAtlTemporaryFile::Create](#create)|Вызовите этот метод, чтобы создать временный файл.|  
|[CAtlTemporaryFile::Flush](#flush)|Этот метод используется для принудительного любые данные, оставшиеся в буфере файл для записи во временный файл.|  
|[CAtlTemporaryFile::GetPosition](#getposition)|Этот метод используется для получения указателя позиции в текущем файле.|  
|[CAtlTemporaryFile::GetSize](#getsize)|Вызовите этот метод, чтобы получить размер временного файла в байтах.|  
|[CAtlTemporaryFile::HandsOff](#handsoff)|Этот метод вызывается для — файл отделяется от `CAtlTemporaryFile` объекта.|  
|[CAtlTemporaryFile::HandsOn](#handson)|Вызовите этот метод, чтобы открыть существующий временный файл и поместите указатель в конец файла.|  
|[CAtlTemporaryFile::LockRange](#lockrange)|Вызовите этот метод, чтобы заблокировать регион, в файле, чтобы предотвратить доступ к нему других процессов.|  
|[CAtlTemporaryFile::Read](#read)|Этот метод используется для чтения данных из временного файла, начиная с позиции указателя файла.|  
|[CAtlTemporaryFile::Seek](#seek)|Этот метод используется для перемещения указателя файла временный файл.|  
|[CAtlTemporaryFile::SetSize](#setsize)|Вызовите этот метод, чтобы задать размер временного файла.|  
|[CAtlTemporaryFile::TempFileName](#tempfilename)|Этот метод используется для получения имени временного файла.|  
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|Этот метод вызывается для разблокировки области временного файла.|  
|[CAtlTemporaryFile::Write](#write)|Этот метод используется для записи данных во временный файл, начиная с позиции указателя файла.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlTemporaryFile::operator ДЕСКРИПТОРА](#operator_handle)|Возвращает дескриптор во временный файл.|  
  
## <a name="remarks"></a>Примечания  
 `CAtlTemporaryFile`упрощает процесс создания и использования временного файла. Файл будет автоматически с именем, открыт, закрытых и удаленных. Если содержимое файла требуется закрытия файла, они могут сохраняться в новый файл с указанным именем.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlfile.h  
  
## <a name="example"></a>Пример  
 В примере показано [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="catltemporaryfile"></a>CAtlTemporaryFile::CAtlTemporaryFile  
 Конструктор.  
  
```
CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Файл не открыт в действительности, пока выполняется вызов [CAtlTemporaryFile::Create](#create).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#73;](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlTemporaryFile:: ~ CAtlTemporaryFile  
 Деструктор  
  
```
~CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызывает деструктор [CAtlTemporaryFile::Close](#close).  
  
##  <a name="close"></a>CAtlTemporaryFile::Close  
 Вызовите этот метод для закрытия во временный файл и либо удалите его содержимое, или сохранять их под именем указанного файла.  
  
```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *szNewName*  
 Имя нового файла для хранения временных файлов в содержимое. Если этот аргумент равен NULL, содержимое временный файл удаляется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="create"></a>CAtlTemporaryFile::Create  
 Вызовите этот метод, чтобы создать временный файл.  
  
```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszDir`  
 Путь для временного файла. Если имеет значение NULL, [GetTempPath](http://msdn.microsoft.com/library/windows/desktop/aa364992) будет вызываться для присвоения пути.  
  
 `dwDesiredAccess`  
 Необходимый доступ. В разделе `dwDesiredAccess` в [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="flush"></a>CAtlTemporaryFile::Flush  
 Этот метод используется для принудительного любые данные, оставшиеся в буфере файл для записи во временный файл.  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Аналогично [CAtlTemporaryFile::HandsOff](#handsoff), за исключением того, что файл не закрыт.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="getposition"></a>CAtlTemporaryFile::GetPosition  
 Этот метод используется для получения указателя позиции в текущем файле.  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Позиция, в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Чтобы изменить положение указателя файла, используйте [CAtlTemporaryFile::Seek](#seek).  
  
##  <a name="getsize"></a>CAtlTemporaryFile::GetSize  
 Вызовите этот метод, чтобы получить размер временного файла в байтах.  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nLen`  
 Число байтов в файле.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
##  <a name="handsoff"></a>CAtlTemporaryFile::HandsOff  
 Этот метод вызывается для — файл отделяется от `CAtlTemporaryFile` объекта.  
  
```
HRESULT HandsOff() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 `HandsOff`и [CAtlTemporaryFile::HandsOn](#handson) — файл отделяется от объекта, и снова присоедините ее при необходимости. `HandsOff`будет принудительно любые данные, оставшиеся в буфере файл для записи во временный файл и закройте файл. Если вы хотите закрыть и окончательно удалить файл или если вы хотите закрыть и сохранить содержимое файла с заданным именем, используйте [CAtlTemporaryFile::Close](#close).  
  
##  <a name="handson"></a>CAtlTemporaryFile::HandsOn  
 Вызовите этот метод, чтобы открыть существующий временный файл и поместите указатель в конец файла.  
  
```
HRESULT HandsOn() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 [CAtlTemporaryFile::HandsOff](#handsoff) и `HandsOn` — файл отделяется от объекта, и снова присоедините ее при необходимости.  
  
##  <a name="lockrange"></a>CAtlTemporaryFile::LockRange  
 Вызовите этот метод, чтобы заблокировать регион во временном файле, чтобы предотвратить доступ к нему других процессов.  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Позиция в файле, где должна начаться блокировки.  
  
 `nCount`  
 Длина диапазона байтов должен быть заблокирован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Можно заблокировать более одной области файла, но разрешено не перекрывающихся областей. Для успешной разблокировки области, используйте [CAtlTemporaryFile::UnlockRange](#unlockrange), обеспечивая диапазона байтов в точности соответствует области, который ранее был заблокирован. `LockRange`не объединять смежных областей; Если два заблокированные области являются смежными, необходимо разблокировать каждого отдельно.  
  
##  <a name="operator_handle"></a>CAtlTemporaryFile::operator ДЕСКРИПТОРА  
 Возвращает дескриптор во временный файл.  
  
```  
operator HANDLE() throw();
```  
  
##  <a name="read"></a>CAtlTemporaryFile::Read  
 Этот метод используется для чтения данных из временного файла, начиная с позиции указателя файла.  
  
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
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFile::Read](../../atl/reference/catlfile-class.md#read). Чтобы изменить положение указателя файла, вызовите [CAtlTemporaryFile::Seek](#seek).  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="seek"></a>CAtlTemporaryFile::Seek  
 Этот метод используется для перемещения указателя файла временный файл.  
  
```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nOffset`  
 Смещение в байтах от начальной точки, заданной параметром *dwFrom.*  
  
 `dwFrom`  
 Начальная точка (FILE_BEGIN, FILE_CURRENT или FILE_END).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek). Чтобы получить текущее положение указателя в файле, вызвать [CAtlTemporaryFile::GetPosition](#getposition).  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="setsize"></a>CAtlTemporaryFile::SetSize  
 Вызовите этот метод, чтобы задать размер временного файла.  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nNewLen`  
 Новая длина файла в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize). При возвращении указатель файла помещается в конец файла.  
  
##  <a name="tempfilename"></a>CAtlTemporaryFile::TempFileName  
 Этот метод используется для получения имени временного файла.  
  
```
LPCTSTR TempFileName() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `LPCTSTR` указывает имя файла.  
  
### <a name="remarks"></a>Примечания  
 Имя файла формируется в [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile) с помощью вызова [GetTempFile](http://msdn.microsoft.com/library/windows/desktop/aa364991) [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] функции. Расширение файла всегда будет «TFR» для временного файла.  
  
##  <a name="unlockrange"></a>CAtlTemporaryFile::UnlockRange  
 Этот метод вызывается для разблокировки области временного файла.  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Позиция в файле, где должно начинаться unlock.  
  
 `nCount`  
 Длина диапазона байтов должен быть разблокирован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange).  
  
##  <a name="write"></a>CAtlTemporaryFile::Write  
 Этот метод используется для записи данных во временный файл, начиная с позиции указателя файла.  
  
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
 Число байтов, передаваемых из буфера.  
  
 `pnBytesWritten`  
 Число записанных байтов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFile::Write](../../atl/reference/catlfile-class.md#write).  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CAtlFile](../../atl/reference/catlfile-class.md)

