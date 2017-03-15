---
title: "Класс COleStreamFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleStreamFile
dev_langs:
- C++
helpviewer_keywords:
- data streams [C++]
- streams [C++], OLE
- data streams [C++], OLE
- structured storage in OLE
- OLE structured storage [C++]
- OLE [C++], streams of data
- COleStreamFile class
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0840d365f4179da0ad680256688eaf9484cb3cd8
ms.lasthandoff: 02/24/2017

---
# <a name="colestreamfile-class"></a>Класс COleStreamFile
Представляет поток данных ( `IStream`) в составном файле как часть структурированного хранения OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleStreamFile : public CFile  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleStreamFile::COleStreamFile](#colestreamfile)|Создает объект `COleStreamFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleStreamFile::Attach](#attach)|Связывает поток с объектом.|  
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|Создает поток из глобальной памяти и связывает его с объектом.|  
|[COleStreamFile::CreateStream](#createstream)|Создает поток и связывает его с объектом.|  
|[COleStreamFile::Detach](#detach)|Отсоединяет из объекта потока.|  
|[COleStreamFile::GetStream](#getstream)|Возвращает текущий поток.|  
|[COleStreamFile::OpenStream](#openstream)|Безопасно открывает поток и связывает его с объектом.|  
  
## <a name="remarks"></a>Примечания  
 `IStorage` Объект должен существовать до потока можно открыть или создать применяется в поток памяти.  
  
 `COleStreamFile`иначе, чем обработки объектов [CFile](../../mfc/reference/cfile-class.md) объектов.  
  
 Дополнительные сведения об управлении потоками и хранилищами см. в статье [контейнеров: составные файлы](../../mfc/containers-compound-files.md)...  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) и [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="a-nameattacha--colestreamfileattach"></a><a name="attach"></a>COleStreamFile::Attach  
 Связывает предоставленный поток OLE с `COleStreamFile` объекта.  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>Параметры  
 `lpStream`  
 Указывает поток OLE ( `IStream`), сопоставляемое с объектом. Не может быть **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Объект не должен уже быть связан с потоком OLE.  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecolestreamfilea--colestreamfilecolestreamfile"></a><a name="colestreamfile"></a>COleStreamFile::COleStreamFile  
 Создает объект `COleStreamFile`.  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpStream`  
 Указатель на поток OLE, сопоставляемое с объектом.  
  
### <a name="remarks"></a>Примечания  
 Если `lpStream` — **NULL**, объект не связан с потоком OLE, в противном случае — объект связан с предоставленный поток OLE.  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecreatememorystreama--colestreamfilecreatememorystream"></a><a name="creatememorystream"></a>COleStreamFile::CreateMemoryStream  
 Безопасно создает новый поток из глобальной, общей памяти где normal, ожидаемое условие сбоя.  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pError`  
 Указывает [CFileException](../../mfc/reference/cfileexception-class.md) объекта или **NULL** указывает состояние выполнения операции создания. Укажите этот параметр, если вы хотите отслеживать возможные исключения, возникающие при попытке создания потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Память выделяется подсистемой OLE.  
  
 Дополнительные сведения см. в разделе [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecreatestreama--colestreamfilecreatestream"></a><a name="createstream"></a>COleStreamFile::CreateStream  
 Безопасно создает новый поток в объект указанного хранилища, где обычный, ожидаемое условие сбоя.  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpStorage`  
 Указывает хранилище OLE-объекта, содержащий поток должен быть создан. Не может быть **NULL**.  
  
 `lpszStreamName`  
 Имя потока, который должен быть создан. Не может быть **NULL**.  
  
 `nOpenFlags`  
 Режим доступа для использования при открытии потока. Эксклюзивный, чтение и запись и создайте режимов, используемых по умолчанию. Полный список доступных режимов см. в разделе [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Указывает [CFileException](../../mfc/reference/cfileexception-class.md) объекта или **NULL**. Укажите этот параметр, если вы хотите отслеживать возможные исключения, возникающие при попытке создания потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Будет создано исключение файлов, если не удается открыть и `pError` не **NULL**.  
  
 Дополнительные сведения см. в разделе [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedetacha--colestreamfiledetach"></a><a name="detach"></a>COleStreamFile::Detach  
 Отсоединяет поток, из объекта без его закрытия.  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на поток ( `IStream`), был связан с объектом.  
  
### <a name="remarks"></a>Примечания  
 Поток должен быть закрыт иным образом, прежде чем программа завершает.  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetstreama--colestreamfilegetstream"></a><a name="getstream"></a>COleStreamFile::GetStream  
 Эта функция вызывается для возврата указателя для текущего потока.  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс текущего потока ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)).  
  
##  <a name="a-nameopenstreama--colestreamfileopenstream"></a><a name="openstream"></a>COleStreamFile::OpenStream  
 Открывает существующий поток.  
  
```  
BOOL OpenStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpStorage`  
 Указывает хранилище OLE-объекта, содержащий поток для открытия. Не может быть **NULL**.  
  
 `lpszStreamName`  
 Имя потока для открытия. Не может быть **NULL**.  
  
 `nOpenFlags`  
 Режим доступа для использования при открытии потока. Эксклюзивное и режимов, используемых по умолчанию чтение и запись. Полный список доступных режимов см. в разделе [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Указывает [CFileException](../../mfc/reference/cfileexception-class.md) объекта или **NULL**. Укажите этот параметр, если вы хотите отслеживать возможные исключения, возникающие при попытке открыть поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток открыт успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Будет создано исключение файлов, если не удается открыть и `pError` не **NULL**.  
  
 Дополнительные сведения см. в разделе [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




