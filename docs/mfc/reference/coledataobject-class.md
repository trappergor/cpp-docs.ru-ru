---
title: "Класс COleDataObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- COleDataObject [MFC], COleDataObject
- COleDataObject [MFC], Attach
- COleDataObject [MFC], AttachClipboard
- COleDataObject [MFC], BeginEnumFormats
- COleDataObject [MFC], Detach
- COleDataObject [MFC], GetData
- COleDataObject [MFC], GetFileData
- COleDataObject [MFC], GetGlobalData
- COleDataObject [MFC], GetNextFormat
- COleDataObject [MFC], IsDataAvailable
- COleDataObject [MFC], Release
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e88736c6255118141d49fbd85134fffbeaeba6db
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|[COleDataObject::Release](#release)|Отсоединяет и освобождает связанные `IDataObject` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COleDataObject`не имеет базового класса.  
  
 Эти виды передачи данных включают источник и назначение. Источник данных реализуется в виде объекта [COleDataSource](../../mfc/reference/coledatasource-class.md) класса. Каждый раз, когда целевое приложение содержит данные, удалить его или будет предложено выполнить операцию вставки из буфера обмена, объект `COleDataObject` необходимо создать класс.  
  
 Этот класс позволяет определить, существует ли данные в указанном формате. Можно также Перечислить доступные форматы данных или проверьте, доступен ли данный формат и затем извлечение данных в предпочтительном формате. Получение объекта можно выполнить различными способами, включая использование [CFile](../../mfc/reference/cfile-class.md), `HGLOBAL`, или **STGMEDIUM** структуры.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры в Windows SDK.  
  
 Дополнительные сведения об использовании объектов данных в приложении см. в статье [объектов данных и источники данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `COleDataObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="attach"></a>COleDataObject::Attach  
 Вызывайте эту функцию, чтобы связать `COleDataObject` объект с OLE-объекта данных.  
  
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
 Дополнительные сведения см. в разделе [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) в Windows SDK.  
  
##  <a name="attachclipboard"></a>COleDataObject::AttachClipboard  
 Вызывайте эту функцию, чтобы присоединить объект данных, который в настоящее время находится в буфере обмена, чтобы `COleDataObject` объекта.  
  
```  
BOOL AttachClipboard();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Вызов этой функции блокировки буфера обмена, пока этот объект данных не будет освобождена. Объект данных освобождается в деструкторе для `COleDataObject`. Дополнительные сведения см. в разделе [OpenClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649048) и [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) в документации Win32.  
  
##  <a name="beginenumformats"></a>COleDataObject::BeginEnumFormats  
 Эта функция вызывается для подготовки для последующих вызовов `GetNextFormat` для получения списка форматов данных из элемента.  
  
```  
void BeginEnumFormats();
```  
  
### <a name="remarks"></a>Примечания  
 После вызова `BeginEnumFormats`, хранится позицию первого формат, поддерживаемый этот объект данных. Последующие вызовы `GetNextFormat` Перечисляет список доступных форматов в объект данных.  
  
 Чтобы проверить доступность данных в заданном формате, используйте [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Дополнительные сведения см. в разделе [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) в Windows SDK.  
  
##  <a name="coledataobject"></a>COleDataObject::COleDataObject  
 Создает объект `COleDataObject`.  
  
```  
COleDataObject();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов [COleDataObject::Attach](#attach) или [COleDataObject::AttachClipboard](#attachclipboard) необходимо сделать перед вызовом других `COleDataObject` функции.  
  
> [!NOTE]
>  Так как один из параметров для обработчиков и перетащите указатель `COleDataObject`, нет необходимости вызвать этот конструктор для поддержки операции перетаскивания.  
  
##  <a name="detach"></a>COleDataObject::Detach  
 Эта функция вызывается для отсоединения `COleDataObject` объект из связанного объекта данных OLE без освобождения объекта данных.  
  
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
 Формат, в которой используются данные, должны быть возвращены. Этот параметр может принимать одно из стандартных форматов буфера обмена или значения, возвращенного приложениями Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpStgMedium`  
 Указывает на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуру, которая будет получать данные.  
  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором возвращаемых данных. Укажите значение для этого параметра, если вы хотите указать формат дополнительных сведений Помимо буфера обмена с форматом, заданным `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в Windows SDK.  
  
##  <a name="getfiledata"></a>COleDataObject::GetFileData  
 Эта функция вызывается для создания `CFile` или `CFile`-производного объекта и для получения данных в указанном формате в `CFile` указателя.  
  
```  
CFile* GetFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат, в которой используются данные, должны быть возвращены. Этот параметр может принимать одно из стандартных форматов буфера обмена или значения, возвращенного приложениями Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором возвращаемых данных. Укажите значение для этого параметра, если вы хотите указать формат дополнительных сведений Помимо буфера обмена с форматом, заданным `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый `CFile` или `CFile`-производный объект, содержащий данные, если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 В зависимости от носителя, данные хранятся в, фактический тип, на который указывает возвращаемое значение может быть `CFile`, `CSharedFile`, или `COleStreamFile`.  
  
> [!NOTE]
>  `CFile` Вызывающий объект является владельцем объекта, доступ к этой функции возвращаемое значение. Отвечает вызывающему объекту **удаление** `CFile` объекта, тем самым закрытия файла.  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в Windows SDK.  
  
##  <a name="getglobaldata"></a>COleDataObject::GetGlobalData  
 Вызывайте эту функцию для размещения блока глобальной памяти и для получения данных в указанном формате в `HGLOBAL`.  
  
```  
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат, в которой используются данные, должны быть возвращены. Этот параметр может принимать одно из стандартных форматов буфера обмена или значения, возвращенного приложениями Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором возвращаемых данных. Укажите значение для этого параметра, если вы хотите указать формат дополнительных сведений Помимо буфера обмена с форматом, заданным `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор блока глобальной памяти, содержащего данные в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в Windows SDK.  
  
##  <a name="getnextformat"></a>COleDataObject::GetNextFormat  
 Вызывайте эту функцию, чтобы получить все форматы, доступные для извлечения данных из элемента.  
  
```  
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуру, которая получает сведения о форматировании, при возвращении вызова функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если другой формат доступен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 После вызова [COleDataObject::BeginEnumFormats](#beginenumformats), хранится позицию первого формат, поддерживаемый этот объект данных. Последующие вызовы `GetNextFormat` Перечисляет список доступных форматов в объект данных. Используйте эти функции, чтобы вывести список доступных форматов.  
  
 Чтобы проверить доступность данного формата, вызовите [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Дополнительные сведения см. в разделе [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) в Windows SDK.  
  
##  <a name="isdataavailable"></a>COleDataObject::IsDataAvailable  
 Эта функция вызывается для определения доступности для извлечения данных из объекта OLE определенного формата.  
  
```  
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат данных буфер обмена для использования в структуре, на который указывает `lpFormatEtc`. Этот параметр может принимать одно из стандартных форматов буфера обмена или значения, возвращенного приложениями Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающий требуемого формата. Укажите значение для этого параметра только в том случае, если вы хотите указать формат дополнительных сведений Помимо буфера обмена с форматом, заданным `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если данные недоступны в указанном формате. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна перед вызовом `GetData`, `GetFileData`, или `GetGlobalData`.  
  
 Дополнительные сведения см. в разделе [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata).  
  
##  <a name="release"></a>COleDataObject::Release  
 Эта функция вызывается для освобождения владения [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) объект, который был ранее связан с `COleDataObject` объекта.  
  
```  
void Release();
```  
  
### <a name="remarks"></a>Примечания  
 `IDataObject` Была связана с `COleDataObject` путем вызова **присоединение** или `AttachClipboard` явным образом или платформой. Если `bAutoRelease` параметр **присоединение** — **FALSE**, `IDataObject` объект не будет освобожден. В этом случае вызывающий объект отвечает за освобождение `IDataObject` путем вызова [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDataSource-класс](../../mfc/reference/coledatasource-class.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)
