---
title: Класс COleDataObject
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
ms.openlocfilehash: 8b9565382de8ae731c166f60a0d1994c1b948a7b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753907"
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
|[ColeDataObject::COleDataObject](#coledataobject)|Формирует объект `COleDataObject`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeDataObject::Attach](#attach)|Прикрепляет указанный объект `COleDataObject`данных OLE к .|
|[COleDataObject::AttachClipboard](#attachclipboard)|Прикрепляет объект данных, нашедшую на Clipboard.|
|[ColeDataObject::BeginEnumФорматы](#beginenumformats)|Готовится к одному `GetNextFormat` или большему последующему вызову.|
|[ColeDataObject::Detach](#detach)|Отсеивает `IDataObject` связанный объект.|
|[ColeDataObject::GetData](#getdata)|Копии данных с прилагаемого объекта данных OLE в указанном формате.|
|[ColeDataObject::GetFileData](#getfiledata)|Копирует данные с присоединенного `CFile` объекта данных OLE в указатель в указанном формате.|
|[ColeDataObject::GetGlobalData](#getglobaldata)|Копирует данные с прилагаемого `HGLOBAL` объекта данных OLE в указанный формат.|
|[ColeDataObject::GetNextFormat](#getnextformat)|Возвращает следующий доступный формат данных.|
|[ColeDataObject::IsData Available](#isdataavailable)|Проверяет, доступны ли данные в определенном формате.|
|[ColeDataObject::Release](#release)|Отсоединяет и высвобождает связанный `IDataObject` объект.|

## <a name="remarks"></a>Remarks

`COleDataObject`не имеет базового класса.

Эти виды передачи данных включают источник и пункт назначения. Источник данных реализован как объект класса [COleDataSource.](../../mfc/reference/coledatasource-class.md) Всякий раз, когда приложение назначения имеет данные, упавввв в нем `COleDataObject` или попросите выполнить операцию пасты из Clipboard, должен быть создан объект класса.

Этот класс позволяет определить, существуют ли данные в определенном формате. Вы также можете перечислить доступные форматы данных или проверить, доступен ли данный формат, а затем получить данные в предпочтительном формате. Поиск объектов может осуществляться несколькими способами, включая использование [CFile,](../../mfc/reference/cfile-class.md) `STGMEDIUM` HGLOBAL или структуры.

Для получения дополнительной [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) информации, см.

Для получения дополнительной информации об использовании объектов данных в приложении смотрите статью [«Объекты данных и источники данных» (OLE).](../../mfc/data-objects-and-data-sources-ole.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`COleDataObject`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="coledataobjectattach"></a><a name="attach"></a>ColeDataObject::Attach

Вызовите эту `COleDataObject` функцию, чтобы связать объект с объектом данных OLE.

```cpp
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Параметры

*lpDataObject*<br/>
Указывает на объект данных OLE.

*bAutoRelease*<br/>
TRUE, если объект данных OLE `COleDataObject` должен быть освобожден при уничтожении объекта; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Для получения дополнительной [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) информации см.

## <a name="coledataobjectattachclipboard"></a><a name="attachclipboard"></a>COleDataObject::AttachClipboard

Вызовите эту функцию, чтобы прикрепить объект `COleDataObject` данных, который в настоящее время находится на буфере обмена, к объекту.

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

> [!NOTE]
> Вызов этой функции блокирует Clipboard до тех пор, пока этот объект данных не будет освобожден. Объект данных высвобождается в `COleDataObject`деструктору для . Для получения дополнительной информации смотрите [OpenClipboard](/windows/win32/api/winuser/nf-winuser-openclipboard) и [CloseClipboard](/windows/win32/api/winuser/nf-winuser-closeclipboard) в документе Win32.

## <a name="coledataobjectbeginenumformats"></a><a name="beginenumformats"></a>ColeDataObject::BeginEnumФорматы

Вызовите эту функцию, `GetNextFormat` чтобы подготовиться к последующим вызовам для извлечения списка форматов данных из элемента.

```cpp
void BeginEnumFormats();
```

### <a name="remarks"></a>Remarks

После вызова `BeginEnumFormats`в сохранено положение первого формата, поддерживаемого этим объектом данных. Последовательные `GetNextFormat` вызовы будут перечислять список доступных форматов в объекте данных.

Чтобы проверить наличие данных в данном формате, используйте [COleDataObject::IsDataAvailable](#isdataavailable).

Для получения дополнительной информации см. [IDataObject::EnumFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) в Windows SDK.

## <a name="coledataobjectcoledataobject"></a><a name="coledataobject"></a>ColeDataObject::COleDataObject

Формирует объект `COleDataObject`.

```
COleDataObject();
```

### <a name="remarks"></a>Remarks

Вызов на [COleDataObject::Attach](#attach) или [COleDataObject::AttachClipboard](#attachclipboard) должен `COleDataObject` быть сделан до вызова других функций.

> [!NOTE]
> Так как один из параметров для перетаскивания обработчиков является указателем на `COleDataObject`, нет необходимости вызывать этот конструктор для поддержки перетаскивания и падения.

## <a name="coledataobjectdetach"></a><a name="detach"></a>ColeDataObject::Detach

Вызовите эту функцию, чтобы отделить `COleDataObject` объект от связанного с ним объекта данных OLE, не выпуская объект данных.

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отсоединительный объект данных OLE.

### <a name="remarks"></a>Remarks

## <a name="coledataobjectgetdata"></a><a name="getdata"></a>ColeDataObject::GetData

Вызов ими функции для извлечения данных из элемента в указанном формате.

```
BOOL GetData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат, в котором данные должны быть возвращены. Этот параметр может быть одним из предопределенных форматов Clipboard или значением, возвращенным родной функцией Windows [RegisterClipboardFormat.](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)

*lpStgMedium*<br/>
Указывает на структуру [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) которая будет получать данные.

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) описывающую формат, в котором данные должны быть возвращены. Предоставьте значение для этого параметра, если вы хотите указать дополнительную информацию о формате за пределами формата Clipboard, указанного *cfFormat.* Если это NULL, значения по умолчанию используются `FORMATETC` для других полей в структуре.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации [см. IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)и [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Для получения дополнительной информации, [см. RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

## <a name="coledataobjectgetfiledata"></a><a name="getfiledata"></a>ColeDataObject::GetFileData

Вызовите эту `CFile` функцию для создания или-производного `CFile`объекта `CFile` и для извлечения данных в указанном формате в указатель.

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат, в котором данные должны быть возвращены. Этот параметр может быть одним из предопределенных форматов Clipboard или значением, возвращенным родной функцией Windows [RegisterClipboardFormat.](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) описывающую формат, в котором данные должны быть возвращены. Предоставьте значение для этого параметра, если вы хотите указать дополнительную информацию о формате за пределами формата Clipboard, указанного *cfFormat.* Если это NULL, значения по умолчанию используются `FORMATETC` для других полей в структуре.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CFile` новый или `CFile`полученный объект, содержащий данные в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

В зависимости от среды, в которую хранятся данные, `CFile` `CSharedFile`фактический `COleStreamFile`тип, указанный значением возврата, может быть, или .

> [!NOTE]
> Объект, `CFile` к которым имеет доступ возвратное значение этой функции, принадлежит вызывающему. Абонент несет ответственность за **удаление** `CFile` объекта, тем самым закрыв файл.

Для получения дополнительной информации [см.](/windows/win32/api/objidl/ns-objidl-formatetc)

Для получения дополнительной информации, [см. RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

## <a name="coledataobjectgetglobaldata"></a><a name="getglobaldata"></a>ColeDataObject::GetGlobalData

Вызовите эту функцию, чтобы выделить глобальный блок памяти и получить данные в указанном формате в HGLOBAL.

```
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат, в котором данные должны быть возвращены. Этот параметр может быть одним из предопределенных форматов Clipboard или значением, возвращенным родной функцией Windows [RegisterClipboardFormat.](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) описывающую формат, в котором данные должны быть возвращены. Предоставьте значение для этого параметра, если вы хотите указать дополнительную информацию о формате за пределами формата Clipboard, указанного *cfFormat.* Если это NULL, значения по умолчанию используются `FORMATETC` для других полей в структуре.

### <a name="return-value"></a>Возвращаемое значение

Ручка глобального блока памяти, содержащая данные в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации [см.](/windows/win32/api/objidl/ns-objidl-formatetc)

Для получения дополнительной информации, [см. RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

## <a name="coledataobjectgetnextformat"></a><a name="getnextformat"></a>ColeDataObject::GetNextFormat

Позвоните в эту функцию неоднократно, чтобы получить все форматы, доступные для извлечения данных из элемента.

```
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) которая получает информацию о формате при возврате вызова функции.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если другой формат доступен; в противном случае 0.

### <a name="remarks"></a>Remarks

После звонка в [COleDataObject::BeginEnumFormats](#beginenumformats)сохраняется положение первого формата, поддерживаемого этим объектом данных. Последовательные `GetNextFormat` вызовы будут перечислять список доступных форматов в объекте данных. Используйте эти функции для списка доступных форматов.

Чтобы проверить наличие данного формата, позвоните [COleDataObject::IsDataAvailable](#isdataavailable).

Для получения дополнительной информации см. [IEnumXXXX::Далее](/previous-versions/ms695273\(v=vs.85\)) в Windows SDK.

## <a name="coledataobjectisdataavailable"></a><a name="isdataavailable"></a>ColeDataObject::IsData Available

Позвоните в эту функцию, чтобы определить, доступен ли определенный формат для извлечения данных из элемента OLE.

```
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат данных Clipboard, который будет использоваться в структуре, на которую указывает *lpFormatEtc*. Этот параметр может быть одним из предопределенных форматов Clipboard или значением, возвращенным родной функцией Windows [RegisterClipboardFormat.](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) описывающую желаемый формат. Укажите значение для этого параметра только в том случае, если вы хотите указать дополнительную информацию о формате за пределами формата Clipboard, указанного *cfFormat.* Если это NULL, значения по умолчанию используются `FORMATETC` для других полей в структуре.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если данные доступны в указанном формате; в противном случае 0.

### <a name="remarks"></a>Remarks

Эта функция полезна `GetData` `GetFileData`перед `GetGlobalData`вызовом, или .

Для получения дополнительной информации [см. IDataObject::QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) и [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Для получения дополнительной информации, [см. RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

### <a name="example"></a>Пример

  Смотрите пример [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata).

## <a name="coledataobjectrelease"></a><a name="release"></a>ColeDataObject::Release

Вызовите эту функцию, чтобы освободить право собственности `COleDataObject` на объект [IDataObject,](/windows/win32/api/objidl/nn-objidl-idataobject) который ранее был связан с объектом.

```cpp
void Release();
```

### <a name="remarks"></a>Remarks

Это `IDataObject` было связано `Attach` с `AttachClipboard` `COleDataObject` вызовом или явно или по рамкам. Если параметр *bAutoRelease* `Attach` является `IDataObject` FALSE, объект не будет выпущен. В этом случае, абонент несет ответственность `IDataObject` за освобождение вызова [IUnknown::Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release).

## <a name="see-also"></a>См. также раздел

[MFC Образец HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDataSource](../../mfc/reference/coledatasource-class.md)<br/>
[Класс ColeClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Класс ColeServerItem](../../mfc/reference/coleserveritem-class.md)
