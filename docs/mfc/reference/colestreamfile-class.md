---
title: "Класс COleStreamFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
dev_langs: C++
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efb042f87e10bec9fff53fcb1d22d56ed3c68ef3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="colestreamfile-class"></a>Класс COleStreamFile
Представляет поток данных ( `IStream`) в составном файле как часть структурированного хранения OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleStreamFile : public CFile  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleStreamFile::COleStreamFile](#colestreamfile)|Создает объект `COleStreamFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleStreamFile::Attach](#attach)|Связывает поток с объектом.|  
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|Создает поток из глобальной памяти и связывает его с объектом.|  
|[COleStreamFile::CreateStream](#createstream)|Создает поток и связывает его с объектом.|  
|[COleStreamFile::Detach](#detach)|Отсоединяет из объекта потока.|  
|[COleStreamFile::GetStream](#getstream)|Возвращает текущий поток.|  
|[COleStreamFile::OpenStream](#openstream)|Безопасно открывает поток и связывает его с объектом.|  
  
## <a name="remarks"></a>Примечания  
 `IStorage` Объект должен существовать прежде, чем поток, можно открыть или создать применяется в поток памяти.  
  
 `COleStreamFile`аналогичен обработки объектов [CFile](../../mfc/reference/cfile-class.md) объектов.  
  
 Дополнительные сведения о работе с потоками и хранилищами см. в статье [контейнеры: составных файлов](../../mfc/containers-compound-files.md)...  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) и [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) в Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="attach"></a>COleStreamFile::Attach  
 Связывает предоставленный поток OLE с `COleStreamFile` объекта.  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>Параметры  
 `lpStream`  
 Указывает поток OLE ( `IStream`) необходимо сопоставить с объектом. Не может быть **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Объект не должен уже быть связан с потоком OLE.  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) в Windows SDK.  
  
##  <a name="colestreamfile"></a>COleStreamFile::COleStreamFile  
 Создает объект `COleStreamFile`.  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpStream`  
 Указатель на поток OLE, связываемое с этим объектом.  
  
### <a name="remarks"></a>Примечания  
 Если `lpStream` — **NULL**, объект не связан с потоком OLE, в противном случае объект связан с предоставленный поток OLE.  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) в Windows SDK.  
  
##  <a name="creatememorystream"></a>COleStreamFile::CreateMemoryStream  
 Безопасно создает новый поток из глобальной общей памяти где нормальный, ожидаемое условие сбоя.  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pError`  
 Указывает на [CFileException](../../mfc/reference/cfileexception-class.md) объекта или **NULL** указывает состояние завершения операции создания. Укажите этот параметр, если вы хотите отслеживать возможные исключения, возникающие при попытке создания потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Объем памяти, занимаемый подсистемы OLE.  
  
 Дополнительные сведения см. в разделе [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980) в Windows SDK.  
  
##  <a name="createstream"></a>COleStreamFile::CreateStream  
 Безопасно создает новый поток в объекте указанное хранилище, где нормальный, ожидаемое условие сбоя.  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpStorage`  
 Указывает OLE-объекта хранилища, содержащий поток должен быть создан. Не может быть **NULL**.  
  
 `lpszStreamName`  
 Имя потока, который должен быть создан. Не может быть **NULL**.  
  
 `nOpenFlags`  
 Режим доступа для использования при открытии потока. Монопольной, чтение и запись и создайте режимов, используемых по умолчанию. Полный список доступных режимов см. в разделе [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Указывает на [CFileException](../../mfc/reference/cfileexception-class.md) объекта или **NULL**. Укажите этот параметр, если вы хотите отслеживать возможные исключения, возникающие при попытке создания потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Файл исключение в случае открытия и `pError` не **NULL**.  
  
 Дополнительные сведения см. в разделе [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020) в Windows SDK.  
  
##  <a name="detach"></a>COleStreamFile::Detach  
 Отсоединяет поток, из объекта без закрытия потока.  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на поток ( `IStream`), был связан с объектом.  
  
### <a name="remarks"></a>Примечания  
 Поток должен быть закрыт иным образом, перед завершением работы программы.  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) в Windows SDK.  
  
##  <a name="getstream"></a>COleStreamFile::GetStream  
 Эта функция вызывается для возврата указателя для текущего потока.  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий интерфейс потока ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)).  
  
##  <a name="openstream"></a>COleStreamFile::OpenStream  
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
 Указывает OLE-объекта хранилища, содержащий поток должен быть открыт. Не может быть **NULL**.  
  
 `lpszStreamName`  
 Имя потока для открытия. Не может быть **NULL**.  
  
 `nOpenFlags`  
 Режим доступа для использования при открытии потока. Эксклюзивное и чтение и запись режимов, используемых по умолчанию. Полный список доступных режимов см. в разделе [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Указывает на [CFileException](../../mfc/reference/cfileexception-class.md) объекта или **NULL**. Укажите этот параметр, если вы хотите отслеживать возможные исключения, возникающие при попытке открыть поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток открыт успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Файл исключение в случае открытия и `pError` не **NULL**.  
  
 Дополнительные сведения см. в разделе [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



