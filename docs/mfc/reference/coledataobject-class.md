---
title: Класс Коледатаобжект
ms.date: 11/04/2016
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
ms.openlocfilehash: e706489a84ad564949e2c2d3d193173fc19b9828
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883671"
---
# <a name="coledataobject-class"></a>Класс Коледатаобжект

Используется в передаче данных для извлечения данных в разных форматах из буфера обмена путем перетаскивания или из встроенного элемента OLE.

## <a name="syntax"></a>Синтаксис

```
class COleDataObject
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Коледатаобжект:: Коледатаобжект](#coledataobject)|Формирует объект `COleDataObject`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Коледатаобжект:: Attach](#attach)|Присоединяет указанный объект данных OLE к `COleDataObject`.|
|[Коледатаобжект:: Аттачклипбоард](#attachclipboard)|Присоединяет объект данных, расположенный в буфере обмена.|
|[Коледатаобжект:: Бегиненумформатс](#beginenumformats)|Подготавливается к одному или нескольким последующим вызовам `GetNextFormat`.|
|[Коледатаобжект::D етач](#detach)|Отсоединяет связанный объект `IDataObject`.|
|[Коледатаобжект:: GetData](#getdata)|Копирует данные из присоединенного объекта OLE данных в указанном формате.|
|[Коледатаобжект:: Жетфиледата](#getfiledata)|Копирует данные из присоединенного объекта OLE данных в указатель `CFile` в указанном формате.|
|[Коледатаобжект:: Жетглобалдата](#getglobaldata)|Копирует данные из присоединенного объекта OLE данных в `HGLOBAL` в указанном формате.|
|[Коледатаобжект:: Жетнекстформат](#getnextformat)|Возвращает следующий доступный формат данных.|
|[Коледатаобжект:: Исдатааваилабле](#isdataavailable)|Проверяет, доступны ли данные в указанном формате.|
|[Коледатаобжект:: Release](#release)|Отсоединяет и освобождает связанный объект `IDataObject`.|

## <a name="remarks"></a>Remarks

`COleDataObject` не имеет базового класса.

Эти виды передачи данных включают источник и назначение. Источник данных реализуется как объект класса [COleDataSource](../../mfc/reference/coledatasource-class.md) . Каждый раз, когда в целевом приложении отбрасываются данные или запрос на выполнение операции вставки из буфера обмена, необходимо создать объект класса `COleDataObject`.

Этот класс позволяет определить, существуют ли данные в указанном формате. Можно также перечислить доступные форматы данных или проверить, доступен ли данный формат, а затем извлечь данные в предпочтительном формате. Извлечение объектов можно выполнить несколькими способами, включая использование [кфиле](../../mfc/reference/cfile-class.md), хглобал или структуры `STGMEDIUM`.

Дополнительные сведения см. в описании структуры [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) в Windows SDK.

Дополнительные сведения об использовании объектов данных в приложении см. в статье [объекты данных и источники данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`COleDataObject`

## <a name="requirements"></a>Требования

**Заголовок:** афксоле. h

##  <a name="attach"></a>Коледатаобжект:: Attach

Вызовите эту функцию, чтобы связать объект `COleDataObject` с объектом данных OLE.

```
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Параметры

*лпдатаобжект*<br/>
Указывает на объект данных OLE.

*бауторелеасе*<br/>
Значение TRUE, если объект данных OLE следует освободить при уничтожении объекта `COleDataObject`; в противном случае — FALSE.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) в Windows SDK.

##  <a name="attachclipboard"></a>Коледатаобжект:: Аттачклипбоард

Вызовите эту функцию, чтобы присоединить объект данных, который в данный момент находится в буфере обмена, к объекту `COleDataObject`.

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

> [!NOTE]
>  Вызов этой функции блокирует буфер обмена до освобождения этого объекта данных. Объект данных освобождается в деструкторе для `COleDataObject`. Дополнительные сведения см. в разделе [опенклипбоард](/windows/win32/api/winuser/nf-winuser-openclipboard) и [Клосеклипбоард](/windows/win32/api/winuser/nf-winuser-closeclipboard) в документе Win32.

##  <a name="beginenumformats"></a>Коледатаобжект:: Бегиненумформатс

Вызовите эту функцию, чтобы подготовиться к последующим вызовам `GetNextFormat` для получения списка форматов данных из элемента.

```
void BeginEnumFormats();
```

### <a name="remarks"></a>Remarks

После вызова `BeginEnumFormats`сохраняется расположение первого формата, поддерживаемого этим объектом данных. Последовательные вызовы `GetNextFormat` будут перечислять список доступных форматов в объекте данных.

Чтобы проверить доступность данных в определенном формате, используйте [коледатаобжект:: исдатааваилабле](#isdataavailable).

Дополнительные сведения см. в разделе [IDataObject:: енумформатетк](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) в Windows SDK.

##  <a name="coledataobject"></a>Коледатаобжект:: Коледатаобжект

Формирует объект `COleDataObject`.

```
COleDataObject();
```

### <a name="remarks"></a>Remarks

Перед вызовом других `COleDataObject` функций необходимо выполнить вызов [коледатаобжект:: Attach](#attach) или [Коледатаобжект:: аттачклипбоард](#attachclipboard) .

> [!NOTE]
>  Поскольку один из параметров обработчиков перетаскивания является указателем на `COleDataObject`, нет необходимости вызывать этот конструктор для поддержки перетаскивания.

##  <a name="detach"></a>Коледатаобжект::D етач

Вызовите эту функцию, чтобы отсоединить объект `COleDataObject` от связанного объекта данных OLE, не освобождая объект данных.

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на Отсоединенный объект данных OLE.

### <a name="remarks"></a>Remarks

##  <a name="getdata"></a>Коледатаобжект:: GetData

Вызывайте эту функцию для получения данных из элемента в указанном формате.

```
BOOL GetData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*кфформат*<br/>
Формат, в котором должны возвращаться данные. Этот параметр может быть одним из стандартных форматов буфера обмена или значением, возвращаемым собственной функцией [Регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Windows.

*лпстгмедиум*<br/>
Указывает на структуру [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) , которая будет принимать данные.

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую формат, в котором должны возвращаться данные. Укажите значение для этого параметра, если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если значение равно NULL, то для других полей в структуре `FORMATETC` используются значения по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata), [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)и [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в разделе [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

##  <a name="getfiledata"></a>Коледатаобжект:: Жетфиледата

Вызовите эту функцию, чтобы создать `CFile` или `CFile`производный объект и получить данные в указанном формате в указатель `CFile`.

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*кфформат*<br/>
Формат, в котором должны возвращаться данные. Этот параметр может быть одним из стандартных форматов буфера обмена или значением, возвращаемым собственной функцией [Регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Windows.

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую формат, в котором должны возвращаться данные. Укажите значение для этого параметра, если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если значение равно NULL, то для других полей в структуре `FORMATETC` используются значения по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый `CFile` или `CFile`-производный объект, содержащий данные в случае успеха; в противном случае — NULL.

### <a name="remarks"></a>Remarks

В зависимости от среднего значения, в котором хранятся данные, фактический тип, на который указывает возвращаемое значение, может быть `CFile`, `CSharedFile`или `COleStreamFile`.

> [!NOTE]
>  Объект `CFile`, к которому обращается возвращаемое значение этой функции, принадлежит вызывающему объекту. Тем самым ответственность за **Удаление** объекта `CFile` осуществляется вызывающей стороной, тем самым закрывая файл.

Дополнительные сведения см. в разделе [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в разделе [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

##  <a name="getglobaldata"></a>Коледатаобжект:: Жетглобалдата

Вызывайте эту функцию для выделения глобального блока памяти и получения данных в указанном формате в объект ХГЛОБАЛ.

```
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*кфформат*<br/>
Формат, в котором должны возвращаться данные. Этот параметр может быть одним из стандартных форматов буфера обмена или значением, возвращаемым собственной функцией [Регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Windows.

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую формат, в котором должны возвращаться данные. Укажите значение для этого параметра, если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если значение равно NULL, то для других полей в структуре `FORMATETC` используются значения по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Маркер глобального блока памяти, содержащего данные в случае успешного выполнения; в противном случае — NULL.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в разделе [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

##  <a name="getnextformat"></a>Коледатаобжект:: Жетнекстформат

Вызывайте эту функцию несколько раз, чтобы получить все форматы, доступные для извлечения данных из элемента.

```
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```

### <a name="parameters"></a>Параметры

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , которая получает сведения о формате при возврате вызова функции.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если доступен другой формат; в противном случае — 0.

### <a name="remarks"></a>Remarks

После вызова [коледатаобжект:: бегиненумформатс](#beginenumformats)сохраняется расположение первого формата, поддерживаемого этим объектом данных. Последовательные вызовы `GetNextFormat` будут перечислять список доступных форматов в объекте данных. Используйте эти функции, чтобы получить список доступных форматов.

Чтобы проверить доступность определенного формата, вызовите [коледатаобжект:: исдатааваилабле](#isdataavailable).

Дополнительные сведения см. в разделе [иенумкскскскс:: Next](/previous-versions//ms695273\(v=vs.85\)) в Windows SDK.

##  <a name="isdataavailable"></a>Коледатаобжект:: Исдатааваилабле

Вызовите эту функцию, чтобы определить, доступен ли определенный формат для извлечения данных из OLE-элемента.

```
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*кфформат*<br/>
Формат данных буфера обмена, используемый в структуре, на которую указывает *лпформатетк*. Этот параметр может быть одним из стандартных форматов буфера обмена или значением, возвращаемым собственной функцией [Регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Windows.

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую нужный формат. Укажите значение для этого параметра, только если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если значение равно NULL, то для других полей в структуре `FORMATETC` используются значения по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если данные доступны в указанном формате. в противном случае — 0.

### <a name="remarks"></a>Remarks

Эта функция полезна перед вызовом `GetData`, `GetFileData`или `GetGlobalData`.

Дополнительные сведения см. в разделе [IDataObject:: куерижетдата](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) и [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в разделе [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [CRichEditView:: куерякцептдата](../../mfc/reference/cricheditview-class.md#queryacceptdata).

##  <a name="release"></a>Коледатаобжект:: Release

Вызовите эту функцию, чтобы освободить владение объектом [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) , который ранее был связан с объектом `COleDataObject`.

```
void Release();
```

### <a name="remarks"></a>Remarks

`IDataObject` связан с `COleDataObject` путем вызова `Attach` или `AttachClipboard` явно или с помощью платформы. Если параметр *бауторелеасе* `Attach` имеет значение false, объект `IDataObject` не будет освобожден. В этом случае вызывающий объект отвечает за освобождение `IDataObject` путем вызова [IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release).

## <a name="see-also"></a>См. также раздел

[Пример MFC для примера HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Пример OCLIENT MFC](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDataSource](../../mfc/reference/coledatasource-class.md)<br/>
[Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)
