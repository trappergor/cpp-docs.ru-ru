---
title: Класс COleStreamFile | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9304c4e3dfd559b296c69b274c1462f2f973a04d
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852762"
---
# <a name="colestreamfile-class"></a>Класс COleStreamFile
Представляет поток данных (`IStream`) в составном файле как часть структурированного хранения OLE.  
  
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
|[COleStreamFile::CreateStream](#createstream)|Создает поток, который связывается с объектом.|  
|[COleStreamFile::Detach](#detach)|Отменяет связь из объекта потока.|  
|[COleStreamFile::GetStream](#getstream)|Возвращает текущий поток.|  
|[COleStreamFile::OpenStream](#openstream)|Безопасно открывает поток, который связывается с объектом.|  
  
## <a name="remarks"></a>Примечания  
 `IStorage` Объект должен существовать прежде, чем поток можно открыть или создать применяется в поток в памяти.  
  
 `COleStreamFile` аналогичен обработки объектов [CFile](../../mfc/reference/cfile-class.md) объектов.  
  
 Дополнительные сведения о работе с потоками и хранилищами см. в статье [контейнеры: составные файлы](../../mfc/containers-compound-files.md)...  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) и [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) в пакете Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="attach"></a>  COleStreamFile::Attach  
 Связывает предоставленный поток OLE с `COleStreamFile` объекта.  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>Параметры  
 *lpStream*  
 Указывает поток OLE (`IStream`) нужно связать с объектом. Не может принимать значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Объект не должен уже быть связан с потоком OLE.  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) в пакете Windows SDK.  
  
##  <a name="colestreamfile"></a>  COleStreamFile::COleStreamFile  
 Создает объект `COleStreamFile`.  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lpStream*  
 Указатель на поток OLE, связываемое с объектом.  
  
### <a name="remarks"></a>Примечания  
 Если *lpStream* имеет значение NULL, объект не связан с потоком OLE, в противном случае объект связан с в предоставленный поток OLE.  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) в пакете Windows SDK.  
  
##  <a name="creatememorystream"></a>  COleStreamFile::CreateMemoryStream  
 Безопасно создает новый поток из глобальной общей памяти, где сбоя — это обычный, ожидаемое условие.  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pError*  
 Указывает на [CFileException](../../mfc/reference/cfileexception-class.md) объект или значение NULL, указывающее состояние завершения операции создания. Укажите этот параметр, если вы хотите отслеживать возможные исключения, возникающие при попытке создания потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток создан успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Память выделяется подсистемой OLE.  
  
 Дополнительные сведения см. в разделе [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980) в пакете Windows SDK.  
  
##  <a name="createstream"></a>  COleStreamFile::CreateStream  
 Безопасно создает новый поток в объекте предоставленного хранилища, где сбоя — это обычный, ожидаемое условие.  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lpStorage*  
 Указывает OLE-объекта хранилища, содержащий поток должен быть создан. Не может принимать значение NULL.  
  
 *lpszStreamName*  
 Имя потока, который должен быть создан. Не может принимать значение NULL.  
  
 *nOpenFlags*  
 Режим доступа для использования при открытии потока. Монопольное, чтения и записи и создать режимов, используемых по умолчанию. Полный список доступных режимов, см. в разделе [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 *pError*  
 Указывает на [CFileException](../../mfc/reference/cfileexception-class.md) объект или значение NULL. Укажите этот параметр, если вы хотите отслеживать возможные исключения, возникающие при попытке создания потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток создан успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Будет создано исключение файлов, если не удается открыть и *pError* не равно NULL.  
  
 Дополнительные сведения см. в разделе [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020) в пакете Windows SDK.  
  
##  <a name="detach"></a>  COleStreamFile::Detach  
 Отменяет связь поток, из объекта без закрытия потоков.  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на поток (`IStream`), был связан с объектом.  
  
### <a name="remarks"></a>Примечания  
 Поток должен быть закрыт каким-либо другим образом, перед завершением работы программы.  
  
 Дополнительные сведения см. в разделе [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) в пакете Windows SDK.  
  
##  <a name="getstream"></a>  COleStreamFile::GetStream  
 Вызывайте эту функцию для возврата указателя на текущий поток.  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс текущего потока ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)).  
  
##  <a name="openstream"></a>  COleStreamFile::OpenStream  
 Открывает существующий поток.  
  
```  
BOOL OpenStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lpStorage*  
 Указывает OLE-объекта хранилища, содержащий поток для открытия. Не может принимать значение NULL.  
  
 *lpszStreamName*  
 Имя потока для открытия. Не может принимать значение NULL.  
  
 *nOpenFlags*  
 Режим доступа для использования при открытии потока. Эксклюзивные и по умолчанию используются режимы чтения и записи. Полный список доступных режимов, см. в разделе [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 *pError*  
 Указывает на [CFileException](../../mfc/reference/cfileexception-class.md) объект или значение NULL. Укажите этот параметр, если вы хотите отслеживать возможные исключения, возникающие при попытке открыть поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поток открыт успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Будет создано исключение файлов, если не удается открыть и *pError* не равно NULL.  
  
 Дополнительные сведения см. в разделе [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025) в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс CFile](../../mfc/reference/cfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



