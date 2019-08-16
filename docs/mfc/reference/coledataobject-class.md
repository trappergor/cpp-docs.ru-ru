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
ms.openlocfilehash: c25fd7e91c59d7bea06325fbb27471d8f90f589d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504251"
---
# <a name="coledataobject-class"></a>Класс Коледатаобжект

Используется в передаче данных для извлечения данных в разных форматах из буфера обмена путем перетаскивания или из встроенного элемента OLE.

## <a name="syntax"></a>Синтаксис

```
class COleDataObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Коледатаобжект:: Коледатаобжект](#coledataobject)|Создает объект `COleDataObject`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Коледатаобжект:: Attach](#attach)|Присоединяет указанный объект данных OLE к `COleDataObject`.|
|[Коледатаобжект:: Аттачклипбоард](#attachclipboard)|Присоединяет объект данных, расположенный в буфере обмена.|
|[Коледатаобжект:: Бегиненумформатс](#beginenumformats)|Подготавливается к одному или нескольким `GetNextFormat` последовательным вызовам.|
|[Коледатаобжект::D етач](#detach)|Отсоединяет связанный `IDataObject` объект.|
|[Коледатаобжект:: GetData](#getdata)|Копирует данные из присоединенного объекта OLE данных в указанном формате.|
|[Коледатаобжект:: Жетфиледата](#getfiledata)|Копирует данные из присоединенного объекта OLE данных в `CFile` указатель в указанном формате.|
|[Коледатаобжект:: Жетглобалдата](#getglobaldata)|Копирует данные из присоединенного объекта OLE данных в объект `HGLOBAL` в указанном формате.|
|[Коледатаобжект:: Жетнекстформат](#getnextformat)|Возвращает следующий доступный формат данных.|
|[Коледатаобжект:: Исдатааваилабле](#isdataavailable)|Проверяет, доступны ли данные в указанном формате.|
|[Коледатаобжект:: Release](#release)|Отсоединяет и освобождает связанный `IDataObject` объект.|

## <a name="remarks"></a>Примечания

`COleDataObject`не имеет базового класса.

Эти виды передачи данных включают источник и назначение. Источник данных реализуется как объект класса [COleDataSource](../../mfc/reference/coledatasource-class.md) . Каждый раз, когда в целевом приложении отбрасываются данные или запрос на выполнение операции вставки из буфера обмена, необходимо создать объект `COleDataObject` класса.

Этот класс позволяет определить, существуют ли данные в указанном формате. Можно также перечислить доступные форматы данных или проверить, доступен ли данный формат, а затем извлечь данные в предпочтительном формате. Извлечение объектов может осуществляться различными способами, включая использование [кфиле](../../mfc/reference/cfile-class.md), хглобал или `STGMEDIUM` структуры.

Дополнительные сведения см. в описании структуры [стгмедиум](/windows/win32/api/objidl/ns-objidl-stgmedium) в Windows SDK.

Дополнительные сведения об использовании объектов данных в приложении см. в статье [объекты данных и источники данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`COleDataObject`

## <a name="requirements"></a>Требования

**Заголовок:** афксоле. h

##  <a name="attach"></a>Коледатаобжект:: Attach

Вызовите эту функцию, чтобы `COleDataObject` связать объект с объектом данных OLE.

```
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Параметры

*лпдатаобжект*<br/>
Указывает на объект данных OLE.

*бауторелеасе*<br/>
Значение true, если объект OLE Data следует освободить при `COleDataObject` уничтожении объекта; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) в Windows SDK.

##  <a name="attachclipboard"></a>Коледатаобжект:: Аттачклипбоард

Вызовите эту функцию, чтобы присоединить объект данных, который в данный момент находится `COleDataObject` в буфере обмена, к объекту.

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  Вызов этой функции блокирует буфер обмена до освобождения этого объекта данных. Объект данных освобождается в деструкторе для `COleDataObject`. Дополнительные сведения см. в разделе [опенклипбоард](/windows/win32/api/winuser/nf-winuser-openclipboard) и [Клосеклипбоард](/windows/win32/api/winuser/nf-winuser-closeclipboard) в документе Win32.

##  <a name="beginenumformats"></a>Коледатаобжект:: Бегиненумформатс

Вызовите эту функцию, чтобы подготовиться к `GetNextFormat` последующим вызовам для получения списка форматов данных из элемента.

```
void BeginEnumFormats();
```

### <a name="remarks"></a>Примечания

После вызова `BeginEnumFormats`, сохраняется расположение первого формата, поддерживаемого этим объектом данных. Последовательные вызовы на `GetNextFormat` будут перечислять список доступных форматов в объекте данных.

Чтобы проверить доступность данных в определенном формате, используйте [коледатаобжект:: исдатааваилабле](#isdataavailable).

Дополнительные сведения см. в разделе [IDataObject:: енумформатетк](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) в Windows SDK.

##  <a name="coledataobject"></a>Коледатаобжект:: Коледатаобжект

Создает объект `COleDataObject`.

```
COleDataObject();
```

### <a name="remarks"></a>Примечания

Перед вызовом других `COleDataObject` функций необходимо выполнить вызов [коледатаобжект:: Attach](#attach) или [коледатаобжект:: аттачклипбоард](#attachclipboard) .

> [!NOTE]
>  Поскольку один из параметров обработчиков перетаскивания является указателем `COleDataObject`на, нет необходимости вызывать этот конструктор для поддержки перетаскивания.

##  <a name="detach"></a>Коледатаобжект::D етач

Вызовите эту функцию, чтобы `COleDataObject` отсоединить объект от связанного объекта данных OLE, не освобождая объект данных.

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на Отсоединенный объект данных OLE.

### <a name="remarks"></a>Примечания

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
Указывает на структуру [стгмедиум](/windows/win32/api/objidl/ns-objidl-stgmedium) , которая будет принимать данные.

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую формат, в котором должны возвращаться данные. Укажите значение для этого параметра, если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если он имеет значение null, для других полей в `FORMATETC` структуре используются значения по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata), [стгмедиум](/windows/win32/api/objidl/ns-objidl-stgmedium)и [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в разделе [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

##  <a name="getfiledata"></a>Коледатаобжект:: Жетфиледата

Эта функция вызывается для создания `CFile` `CFile`объекта, производного от, и для получения данных в указанном формате `CFile` в указатель.

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*кфформат*<br/>
Формат, в котором должны возвращаться данные. Этот параметр может быть одним из стандартных форматов буфера обмена или значением, возвращаемым собственной функцией [Регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Windows.

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую формат, в котором должны возвращаться данные. Укажите значение для этого параметра, если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если он имеет значение null, для других полей в `FORMATETC` структуре используются значения по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый `CFile` или `CFile`производный объект, содержащий данные, если они успешно выполнены; в противном случае — null.

### <a name="remarks"></a>Примечания

В зависимости от среднего значения, в котором хранятся данные, фактическим типом, на который указывает возвращаемое значение, `CFile`может `CSharedFile`быть, `COleStreamFile`или.

> [!NOTE]
>  `CFile` Объект, к которому обращается возвращаемое значение этой функции, принадлежит вызывающему объекту. Тем самым ответственность за **Удаление** `CFile` объекта осуществляется вызывающим объектом, тем самым закрывая файл.

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
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую формат, в котором должны возвращаться данные. Укажите значение для этого параметра, если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если он имеет значение null, для других полей в `FORMATETC` структуре используются значения по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Маркер глобального блока памяти, содержащего данные в случае успешного выполнения; в противном случае — NULL.

### <a name="remarks"></a>Примечания

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

### <a name="remarks"></a>Примечания

После вызова [коледатаобжект:: бегиненумформатс](#beginenumformats)сохраняется расположение первого формата, поддерживаемого этим объектом данных. Последовательные вызовы на `GetNextFormat` будут перечислять список доступных форматов в объекте данных. Используйте эти функции, чтобы получить список доступных форматов.

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
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую нужный формат. Укажите значение для этого параметра, только если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если он имеет значение null, для других полей в `FORMATETC` структуре используются значения по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если данные доступны в указанном формате. в противном случае — 0.

### <a name="remarks"></a>Примечания

Эта функция полезна перед `GetData`вызовом `GetFileData`, или `GetGlobalData`.

Дополнительные сведения см. в разделе [IDataObject:: куерижетдата](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) и [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в разделе [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [CRichEditView:: куерякцептдата](../../mfc/reference/cricheditview-class.md#queryacceptdata).

##  <a name="release"></a>Коледатаобжект:: Release

Вызовите эту функцию, чтобы освободить владение объектом [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) , который ранее был связан с `COleDataObject` объектом.

```
void Release();
```

### <a name="remarks"></a>Примечания

Объект `IDataObject` был связан `COleDataObject` с объектом путем вызова `Attach` или `AttachClipboard` явно или платформой. Если `Attach` параметр *бауторелеасе* `IDataObject` имеет значение false, объект не будет освобожден. В этом случае вызывающий объект отвечает за освобождение `IDataObject` с помощью вызова [IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release).

## <a name="see-also"></a>См. также

[Пример MFC для примера HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Пример OCLIENT MFC](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDataSource](../../mfc/reference/coledatasource-class.md)<br/>
[Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)
