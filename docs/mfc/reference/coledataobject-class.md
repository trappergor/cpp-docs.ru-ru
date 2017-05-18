---
title: "Класс COleDataObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDataObject
- AFXOLE/COleDataObject
- AFXOLE/COleDataObject::COleDataObject
- AFXOLE/COleDataObject::Attach
- AFXOLE/COleDataObject::AttachClipboard
- AFXOLE/COleDataObject::BeginEnumFormats
- AFXOLE/COleDataObject::Detach
- AFXOLE/COleDataObject::GetData
- AFXOLE/COleDataObject::GetFileData
- AFXOLE/COleDataObject::GetGlobalData
- AFXOLE/COleDataObject::GetNextFormat
- AFXOLE/COleDataObject::IsDataAvailable
- AFXOLE/COleDataObject::Release
dev_langs:
- C++
helpviewer_keywords:
- drag and drop [C++], MFC support
- Clipboard [C++], OLE support
- uniform data transfer
- OLE [C++], uniform data transfer
- Clipboard [C++], MFC support
- OLE Clipboard [C++], support
- IDataObject interface, MFC encapsulation
- data transfer [C++]
- data transfer [C++], OLE
- OLE data transfer [C++]
- COleDataObject class
- uniform data transfer, OLE
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
caps.latest.revision: 20
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f30ca208252fe81f1e47d9e8f817cb9137656540
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="coledataobject-class"></a>Класс COleDataObject
Используется в передаче данных для извлечения данных в разных форматах из буфера обмена путем перетаскивания или из встроенного элемента OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDataObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDataObject::COleDataObject](#coledataobject)|Создает объект `COleDataObject`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDataObject::Attach](#attach)|Присоединяет указанный OLE-объект данных для `COleDataObject`.|  
|[COleDataObject::AttachClipboard](#attachclipboard)|Присоединяет объект данных, который находится в буфере обмена.|  
|[COleDataObject::BeginEnumFormats](#beginenumformats)|Подготовка для одного или более последующих `GetNextFormat` вызовов.|  
|[COleDataObject::Detach](#detach)|Отсоединяет связанный `IDataObject` объекта.|  
|[COleDataObject::GetData](#getdata)|Копирует данные из подключенных OLE-объекта данных в указанном формате.|  
|[COleDataObject::GetFileData](#getfiledata)|Копирует данные из подключенных OLE-объекта данных в `CFile` указатель в указанном формате.|  
|[COleDataObject::GetGlobalData](#getglobaldata)|Копирует данные из подключенных OLE-объекта данных в `HGLOBAL` в указанном формате.|  
|[COleDataObject::GetNextFormat](#getnextformat)|Возвращает следующий формат данных доступны.|  
|[COleDataObject::IsDataAvailable](#isdataavailable)|Проверяет, доступен ли данные в указанном формате.|  
|[COleDataObject::Release](#release)|Отключает и освобождает связанные `IDataObject` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COleDataObject`не имеет базового класса.  
  
 Эти виды передачи данных включают источника и назначения. Источник данных реализуется как объект [COleDataSource](../../mfc/reference/coledatasource-class.md) класса. Каждый раз, когда приложение назначения содержит данные, удалить его или будет предложено выполнить операцию вставки из буфера обмена, объект `COleDataObject` необходимо создать класс.  
  
 Этот класс позволяет определить, существует ли данные в указанном формате. Можно также Перечислить доступные форматы данных или проверить, доступен ли данный формат и получить данные в желаемом формате. Извлечение объектов может осуществляться несколькими различными способами, включая использование [CFile](../../mfc/reference/cfile-class.md), `HGLOBAL`, или **STGMEDIUM** структуры.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения об использовании объектов данных в приложении см. в статье [объектов данных и источников данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `COleDataObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="attach"></a>COleDataObject::Attach  
 Эта функция вызывается для связывания `COleDataObject` объекта с данным объектом OLE.  
  
```  
void Attach(
    LPDATAOBJECT lpDataObject,  
    BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *lpDataObject*  
 Указывает на объект данных OLE.  
  
 `bAutoRelease`  
 **Значение TRUE,** Если OLE-объекта данных следует освободить после `COleDataObject` объектов уничтожено; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="attachclipboard"></a>COleDataObject::AttachClipboard  
 Эта функция вызывается для присоединения объекта данных, в данный момент в буфере обмена для `COleDataObject` объекта.  
  
```  
BOOL AttachClipboard();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  При вызове этой функции блокировки буфера до освобождения этого объекта данных. Объект данных выпускается в деструктор `COleDataObject`. Дополнительные сведения см. в разделе [OpenClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649048) и [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) в документации Win32.  
  
##  <a name="beginenumformats"></a>COleDataObject::BeginEnumFormats  
 Эта функция вызывается для подготовки для последующих вызовов `GetNextFormat` для получения списка форматов данных из элемента.  
  
```  
void BeginEnumFormats();
```  
  
### <a name="remarks"></a>Примечания  
 После вызова `BeginEnumFormats`, хранится позицию первого формат, поддерживаемый этим объектом данных. Последовательные вызовы `GetNextFormat` Перечисляет список доступных форматов в объект данных.  
  
 Чтобы проверить доступность данных в заданном формате, используйте [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Дополнительные сведения см. в разделе [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="coledataobject"></a>COleDataObject::COleDataObject  
 Создает объект `COleDataObject`.  
  
```  
COleDataObject();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов [COleDataObject::Attach](#attach) или [COleDataObject::AttachClipboard](#attachclipboard) необходимо сделать перед вызовом других `COleDataObject` функции.  
  
> [!NOTE]
>  Так как один из параметров для обработчиков и перетащите указатель `COleDataObject`, нет необходимости вызывать этот конструктор для поддержки операции перетаскивания.  
  
##  <a name="detach"></a>COleDataObject::Detach  
 Эта функция вызывается для отсоединения `COleDataObject` объект из связанного объекта OLE данных без освобождения объекта данных.  
  
```  
LPDATAOBJECT Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект данных OLE, была отсоединена.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getdata"></a>COleDataObject::GetData  
 Эта функция вызывается для получения данных из элемента в указанном формате.  
  
```  
BOOL GetData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат, в котором возвращаются данные. Этот параметр может иметь один из стандартных форматов буфера обмена или значение, возвращенное собственного Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpStgMedium`  
 Указывает [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуру, которая будет получать данные.  
  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором возвращаются данные. Укажите значение для этого параметра, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getfiledata"></a>COleDataObject::GetFileData  
 Эта функция вызывается для создания `CFile` или `CFile`-производный объект и извлечь данные в указанном формате в `CFile` указателя.  
  
```  
CFile* GetFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат, в котором возвращаются данные. Этот параметр может иметь один из стандартных форматов буфера обмена или значение, возвращенное собственного Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором возвращаются данные. Укажите значение для этого параметра, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый `CFile` или `CFile`-производный объект, содержащий данные, если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 В зависимости от носителя, данные хранятся в, фактический тип, на который указывает возвращаемое значение может быть `CFile`, `CSharedFile`, или `COleStreamFile`.  
  
> [!NOTE]
>  `CFile` Объект, к которому возвращаемое значение функции владеет участник. За это отвечает вызывающему объекту **удаление** `CFile` объекта, тем самым закрытия файла.  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getglobaldata"></a>COleDataObject::GetGlobalData  
 Вызов этой функции необходимо выделить блок памяти глобальных, так и для получения данных в указанном формате в `HGLOBAL`.  
  
```  
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат, в котором возвращаются данные. Этот параметр может иметь один из стандартных форматов буфера обмена или значение, возвращенное собственного Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором возвращаются данные. Укажите значение для этого параметра, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор блока глобальной памяти, содержащего данные, если выполнено успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getnextformat"></a>COleDataObject::GetNextFormat  
 Эта функция используется несколько раз, чтобы получить все форматы, доступные для извлечения данных из элемента.  
  
```  
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуру, которая получает сведения о форматировании при возвращении вызова функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если доступен другой формат; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 После вызова [COleDataObject::BeginEnumFormats](#beginenumformats), хранится позицию первого формат, поддерживаемый этим объектом данных. Последовательные вызовы `GetNextFormat` Перечисляет список доступных форматов в объект данных. Используйте эти функции, чтобы получить список доступных форматов.  
  
 Чтобы проверить доступность данного формата, вызовите [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Дополнительные сведения см. в разделе [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isdataavailable"></a>COleDataObject::IsDataAvailable  
 Эта функция вызывается для проверки наличия определенного формата для извлечения данных из объекта OLE.  
  
```  
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат данных буфера обмена для использования в структуре, на который указывает `lpFormatEtc`. Этот параметр может иметь один из стандартных форматов буфера обмена или значение, возвращенное собственного Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры описания требуемого формата. Укажите значение для этого параметра только в том случае, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если данные недоступны в указанном формате. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна, перед вызовом метода `GetData`, `GetFileData`, или `GetGlobalData`.  
  
 Дополнительные сведения см. в разделе [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata).  
  
##  <a name="release"></a>COleDataObject::Release  
 Эта функция вызывается для освобождения владения [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) объект, который был ранее связан с `COleDataObject` объекта.  
  
```  
void Release();
```  
  
### <a name="remarks"></a>Примечания  
 `IDataObject` Была связана с `COleDataObject` путем вызова **присоединить** или `AttachClipboard` явно или платформой. Если `bAutoRelease` параметр **присоединить** — **FALSE**, `IDataObject` объект не удаляется. В этом случае вызывающий объект отвечает за освобождение `IDataObject` путем вызова [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDataSource-класс](../../mfc/reference/coledatasource-class.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Класса, производного от COleServerItem](../../mfc/reference/coleserveritem-class.md)

