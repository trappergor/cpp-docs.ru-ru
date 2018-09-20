---
title: Класс COleDataObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 498b35f5894e1eeb4cf05110aa7a643df1f43fff
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392662"
---
# <a name="coledataobject-class"></a>Класс COleDataObject

Используется в передаче данных для извлечения данных в разных форматах из буфера обмена путем перетаскивания или из встроенного элемента OLE.

## <a name="syntax"></a>Синтаксис

```
class COleDataObject
```

## <a name="members"></a>Участники

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
|[COleDataObject::GetNextFormat](#getnextformat)|Возвращает следующий формат данных, которые доступны.|
|[COleDataObject::IsDataAvailable](#isdataavailable)|Проверяет, доступен ли данные в указанном формате.|
|[COleDataObject::Release](#release)|Отсоединяет и освобождает связанные `IDataObject` объекта.|

## <a name="remarks"></a>Примечания

`COleDataObject` не имеет базового класса.

Эти виды передачи данных включают источник и назначение. Источник данных реализуется в виде объекта [COleDataSource](../../mfc/reference/coledatasource-class.md) класса. Каждый раз, когда целевое приложение содержит данные, удаляющиеся при его или предлагается для выполнения операции вставки из буфера обмена, объект `COleDataObject` класс должен создаваться.

Этот класс позволяет определить, существует ли данные в указанном формате. Можно также Перечислить доступные форматы данных или проверьте, доступен ли заданного формата и затем получить данные в нужный формат. Получение объекта можно выполнить несколькими способами, включая использование [CFile](../../mfc/reference/cfile-class.md), HGLOBAL, или это `STGMEDIUM` структуры.

Дополнительные сведения см. в разделе [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) структуры в пакете Windows SDK.

Дополнительные сведения об использовании объектов данных в приложении см. в статье [объекты данных и источники данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`COleDataObject`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

##  <a name="attach"></a>  COleDataObject::Attach

Вызывайте эту функцию, чтобы связать `COleDataObject` объекта с данным объектом OLE.

```
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Параметры

*lpDataObject*<br/>
Указывает на объект данных OLE.

*bAutoRelease*<br/>
Значение TRUE, если данные OLE-объекта должен быть выпущен, когда `COleDataObject` объект уничтожено; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) в пакете Windows SDK.

##  <a name="attachclipboard"></a>  COleDataObject::AttachClipboard

Вызывайте эту функцию для присоединения объекта данных, который используется в настоящий момент в буфере обмена для `COleDataObject` объекта.

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  Вызов этой функции блокирует буфера обмена, пока этот объект данных. Объект данных будет выпущен в деструктор для `COleDataObject`. Дополнительные сведения см. в разделе [OpenClipboard](/windows/desktop/api/winuser/nf-winuser-openclipboard) и [CloseClipboard](/windows/desktop/api/winuser/nf-winuser-closeclipboard) в документации Win32.

##  <a name="beginenumformats"></a>  COleDataObject::BeginEnumFormats

Вызывайте эту функцию, чтобы подготовить для последующих вызовов `GetNextFormat` для получения списка форматов данных из элемента.

```
void BeginEnumFormats();
```

### <a name="remarks"></a>Примечания

После вызова `BeginEnumFormats`, хранится положение первый формат, поддерживаемый этим объектом данных. Последовательные вызовы `GetNextFormat` Перечисляет список доступных форматов в объекте данных.

Чтобы проверить доступность данных в заданном формате, используйте [COleDataObject::IsDataAvailable](#isdataavailable).

Дополнительные сведения см. в разделе [IDataObject::EnumFormatEtc](/windows/desktop/api/objidl/nf-objidl-idataobject-enumformatetc) в пакете Windows SDK.

##  <a name="coledataobject"></a>  COleDataObject::COleDataObject

Создает объект `COleDataObject`.

```
COleDataObject();
```

### <a name="remarks"></a>Примечания

Вызов [COleDataObject::Attach](#attach) или [COleDataObject::AttachClipboard](#attachclipboard) необходимо вызывать до вызова другой `COleDataObject` функции.

> [!NOTE]
>  Так как один из параметров в обработчики перетаскивания и вставки — это указатель на `COleDataObject`, нет необходимости вызывать этот конструктор для поддержки операции перетаскивания.

##  <a name="detach"></a>  COleDataObject::Detach

Вызывайте эту функцию для отсоединения `COleDataObject` объект из связанного объекта OLE данных без освобождения объекта данных.

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект данных OLE, была отсоединена.

### <a name="remarks"></a>Примечания

##  <a name="getdata"></a>  COleDataObject::GetData

Вызывайте эту функцию для получения данных из элемента в указанном формате.

```
BOOL GetData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат, в которой используются данные, должны быть возвращены. Этот параметр может принимать одно из стандартных форматов буфера обмена, или значение, возвращенное собственный Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) функции.

*lpStgMedium*<br/>
Указывает на [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) структуру, которая будет получать данные.

*lpFormatEtc*<br/>
Указывает на [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структуры, описывающие формат, в которой используются данные, должны быть возвращены. Укажите значение для этого параметра, если вы хотите указать дополнительный формат сведений, чем формат буфера обмена, определяемое *cfFormat*. Если он имеет значение NULL, значения по умолчанию используются для других полей в `FORMATETC` структуры.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium), и [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) в пакете Windows SDK.

Дополнительные сведения см. в разделе [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) в пакете Windows SDK.

##  <a name="getfiledata"></a>  COleDataObject::GetFileData

Вызывайте эту функцию для создания `CFile` или `CFile`-объект, производной от и для получения данных в указанном формате в `CFile` указатель.

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат, в которой используются данные, должны быть возвращены. Этот параметр может принимать одно из стандартных форматов буфера обмена, или значение, возвращенное собственный Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) функции.

*lpFormatEtc*<br/>
Указывает на [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структуры, описывающие формат, в которой используются данные, должны быть возвращены. Укажите значение для этого параметра, если вы хотите указать дополнительный формат сведений, чем формат буфера обмена, определяемое *cfFormat*. Если он имеет значение NULL, значения по умолчанию используются для других полей в `FORMATETC` структуры.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый `CFile` или `CFile`-производный объект, содержащий данные, если успешно; в противном случае — NULL.

### <a name="remarks"></a>Примечания

В зависимости от носителя, данные хранятся в, фактический тип, на которые указывает возвращаемое значение может быть `CFile`, `CSharedFile`, или `COleStreamFile`.

> [!NOTE]
>  `CFile` Принадлежит вызывающий объект, к которому возвращаемое значение функции. Он отвечает за вызывающему объекту **удалить** `CFile` объекта, тем самым закрытия файла.

Дополнительные сведения см. в разделе [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) в пакете Windows SDK.

Дополнительные сведения см. в разделе [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) в пакете Windows SDK.

##  <a name="getglobaldata"></a>  COleDataObject::GetGlobalData

Вызывайте эту функцию для выделения блока глобальной памяти и для извлечения данных в указанном формате в HGLOBAL.

```
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат, в которой используются данные, должны быть возвращены. Этот параметр может принимать одно из стандартных форматов буфера обмена, или значение, возвращенное собственный Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) функции.

*lpFormatEtc*<br/>
Указывает на [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структуры, описывающие формат, в которой используются данные, должны быть возвращены. Укажите значение для этого параметра, если вы хотите указать дополнительный формат сведений, чем формат буфера обмена, определяемое *cfFormat*. Если он имеет значение NULL, значения по умолчанию используются для других полей в `FORMATETC` структуры.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор блока глобальной памяти, содержащего данные, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) в пакете Windows SDK.

Дополнительные сведения см. в разделе [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) в пакете Windows SDK.

##  <a name="getnextformat"></a>  COleDataObject::GetNextFormat

Вызовите эту функцию для получения всех форматов, доступных для извлечения данных из элемента.

```
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структуру, которая получает сведения о форматировании при возвращении вызова функции.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если доступен другой формат; в противном случае 0.

### <a name="remarks"></a>Примечания

После вызова [COleDataObject::BeginEnumFormats](#beginenumformats), хранится положение первый формат, поддерживаемый этим объектом данных. Последовательные вызовы `GetNextFormat` Перечисляет список доступных форматов в объекте данных. Используйте эти функции, чтобы получить список доступных форматов.

Чтобы проверить доступность заданного формата, вызовите [COleDataObject::IsDataAvailable](#isdataavailable).

Дополнительные сведения см. в разделе [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) в пакете Windows SDK.

##  <a name="isdataavailable"></a>  COleDataObject::IsDataAvailable

Вызывайте эту функцию, чтобы определить, доступно ли конкретный формат для извлечения данных из объекта OLE.

```
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат данных буфера обмена для использования в структуре, на которые указывают *lpFormatEtc*. Этот параметр может принимать одно из стандартных форматов буфера обмена, или значение, возвращенное собственный Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) функции.

*lpFormatEtc*<br/>
Указывает на [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структуры, описывающий нужный формат. Укажите значение для этого параметра только в том случае, если вы хотите указать дополнительный формат сведений, чем формат буфера обмена, определяемое *cfFormat*. Если он имеет значение NULL, значения по умолчанию используются для других полей в `FORMATETC` структуры.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если данные недоступны в указанном формате; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция полезна, перед вызовом `GetData`, `GetFileData`, или `GetGlobalData`.

Дополнительные сведения см. в разделе [IDataObject::QueryGetData](/windows/desktop/api/objidl/nf-objidl-idataobject-querygetdata) и [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) в пакете Windows SDK.

Дополнительные сведения см. в разделе [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata).

##  <a name="release"></a>  COleDataObject::Release

Эта функция вызывается для освобождения владения [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) объект, который был ранее связан с `COleDataObject` объекта.

```
void Release();
```

### <a name="remarks"></a>Примечания

`IDataObject` Был связан с параметром `COleDataObject` путем вызова `Attach` или `AttachClipboard` явным образом или платформой. Если *bAutoRelease* параметр `Attach` имеет значение FALSE, `IDataObject` объект не будет освобожден. В этом случае вызывающий объект несет ответственность за освобождение `IDataObject` путем вызова [IUnknown::Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release).

## <a name="see-also"></a>См. также

[Пример MFC HIERSVR](../../visual-cpp-samples.md)<br/>
[Пример MFC OCLIENT](../../visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDataSource](../../mfc/reference/coledatasource-class.md)<br/>
[Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)
