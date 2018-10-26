---
title: Класс CPictureHolder | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
dev_langs:
- C++
helpviewer_keywords:
- CPictureHolder [MFC], CPictureHolder
- CPictureHolder [MFC], CreateEmpty
- CPictureHolder [MFC], CreateFromBitmap
- CPictureHolder [MFC], CreateFromIcon
- CPictureHolder [MFC], CreateFromMetafile
- CPictureHolder [MFC], GetDisplayString
- CPictureHolder [MFC], GetPictureDispatch
- CPictureHolder [MFC], GetType
- CPictureHolder [MFC], Render
- CPictureHolder [MFC], SetPictureDispatch
- CPictureHolder [MFC], m_pPict
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef97b1340d91d672b64a403fd70cec69861a05ba
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062110"
---
# <a name="cpictureholder-class"></a>Класс CPictureHolder

Реализует свойство рисунка, который позволяет пользователю отображать изображение в элементе управления.

## <a name="syntax"></a>Синтаксис

```
class CPictureHolder
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPictureHolder::CPictureHolder](#cpictureholder)|Создает объект `CPictureHolder`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPictureHolder::CreateEmpty](#createempty)|Создает пустой объект `CPictureHolder`.|
|[CPictureHolder::CreateFromBitmap](#createfrombitmap)|Создает `CPictureHolder` объекта из растрового изображения.|
|[CPictureHolder::CreateFromIcon](#createfromicon)|Создает `CPictureHolder` объект из значка.|
|[CPictureHolder::CreateFromMetafile](#createfrommetafile)|Создает `CPictureHolder` объект из метафайл.|
|[CPictureHolder::GetDisplayString](#getdisplaystring)|Извлекает строку, отображаемую в браузере свойств контейнера элемента управления.|
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|Возвращает `CPictureHolder` объекта `IDispatch` интерфейс.|
|[CPictureHolder::GetType](#gettype)|Сообщает ли `CPictureHolder` объект является точечный рисунок, метафайл или значка.|
|[CPictureHolder::Render](#render)|Отображает изображение.|
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|Наборы `CPictureHolder` объекта `IDispatch` интерфейс.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CPictureHolder::m_pPict](#m_ppict)|Указатель на объект рисунка.|

## <a name="remarks"></a>Примечания

`CPictureHolder` не имеет базового класса.

С помощью стандартных свойств изображения разработчик может указать точечного рисунка, значка или метафайла для отображения.

Сведения о создании настраиваемых свойствах изображения, см. в статье [элементы управления MFC ActiveX: использование изображений в элементе управления ActiveX](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CPictureHolder`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

##  <a name="cpictureholder"></a>  CPictureHolder::CPictureHolder

Создает объект `CPictureHolder`.

```
CPictureHolder();
```

##  <a name="createempty"></a>  CPictureHolder::CreateEmpty

Создает пустой `CPictureHolder` объекта и подключает ее к `IPicture` интерфейс.

```
BOOL CreateEmpty();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект успешно создан; в противном случае 0.

##  <a name="createfrombitmap"></a>  CPictureHolder::CreateFromBitmap

Использует для инициализации объекта рисунок в точечный рисунок `CPictureHolder`.

```
BOOL CreateFromBitmap(
    UINT idResource);

BOOL CreateFromBitmap(
    CBitmap* pBitmap,
    CPalette* pPal = NULL,
    BOOL bTransferOwnership = TRUE);

BOOL CreateFromBitmap(
    HBITMAP hbm,
    HPALETTE hpal = NULL,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Параметры

*idResource*<br/>
Идентификатор ресурса для ресурса точечного рисунка.

*pBitmap*<br/>
Указатель на [CBitmap](../../mfc/reference/cbitmap-class.md) объекта.

*pPal*<br/>
Указатель на [CPalette](../../mfc/reference/cpalette-class.md) объекта.

*bTransferOwnership*<br/>
Указывает ли объект изображения будет задавать принадлежность объекта точечного рисунка и палитру.

*hbm*<br/>
Дескриптор точечного рисунка из которого `CPictureHolder` создается объект.

*hpal*<br/>
Дескриптор к палитре, используемой для визуализации точечного рисунка.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект успешно создан; в противном случае 0.

### <a name="remarks"></a>Примечания

Если *bTransferOwnership* имеет значение TRUE, вызывающий объект не следует использовать растрового изображения или возвращает объект палитры никоим образом после этого вызова. Если *bTransferOwnership* имеет значение FALSE, вызывающий объект отвечает за обеспечение растрового изображения и палитру объекты остаются действительными в течение времени существования объекта-рисунка.

##  <a name="createfromicon"></a>  CPictureHolder::CreateFromIcon

Использует значок, чтобы инициализировать объект рисунка в `CPictureHolder`.

```
BOOL CreateFromIcon(
    UINT idResource);

BOOL CreateFromIcon(
    HICON hIcon,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Параметры

*idResource*<br/>
Идентификатор ресурса для ресурса точечного рисунка.

*hIcon*<br/>
Дескриптор значка, из которой `CPictureHolder` создается объект.

*bTransferOwnership*<br/>
Указывает, будет ли объект изображения стать владельцем объект значка.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект успешно создан; в противном случае 0.

### <a name="remarks"></a>Примечания

Если *bTransferOwnership* имеет значение TRUE, вызывающий объект не следует использовать объект значка никоим образом после возвращения этого вызова. Если *bTransferOwnership* имеет значение FALSE, вызывающий объект отвечает за то, что объект значка, который будет действовать в течение времени существования объекта-рисунка.

##  <a name="createfrommetafile"></a>  CPictureHolder::CreateFromMetafile

Используется для инициализации объекта рисунок в метафайл `CPictureHolder`.

```
BOOL CreateFromMetafile(
    HMETAFILE hmf,
    int xExt,
    int yExt,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Параметры

*hmf*<br/>
Дескриптор метафайла, используемый для создания `CPictureHolder` объекта.

*xExt*<br/>
X экстент рисунка.

*yExt*<br/>
Y область рисунка.

*bTransferOwnership*<br/>
Показывает, будет ли объект изображения выполнять владения объектом метафайла.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект успешно создан; в противном случае 0.

### <a name="remarks"></a>Примечания

Если *bTransferOwnership* имеет значение TRUE, вызывающий объект не следует использовать объект метафайла никоим образом после возвращения этого вызова. Если *bTransferOwnership* имеет значение FALSE, вызывающий объект отвечает за обеспечение метафайла объект остается действительным в течение времени существования объекта-рисунка.

##  <a name="getdisplaystring"></a>  CPictureHolder::GetDisplayString

Получает строку, который отображается в обозревателе свойств контейнера.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Параметры

*strValue*<br/>
Ссылка на [CString](../../atl-mfc-shared/reference/cstringt-class.md) , предназначенный для отображения строки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если строка успешно извлечено; в противном случае 0.

##  <a name="getpicturedispatch"></a>  CPictureHolder::GetPictureDispatch

Эта функция возвращает указатель на `CPictureHolder` объекта `IPictureDisp` интерфейс.

```
LPPICTUREDISP GetPictureDispatch();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CPictureHolder` объекта `IPictureDisp` интерфейс.

### <a name="remarks"></a>Примечания

Вызывающий объект должен вызвать `Release` для этого указателя, когда завершит работу с ней.

##  <a name="gettype"></a>  CPictureHolder::GetType

Указывает, является ли изображение точечного рисунка, метафайла или значка.

```
short GetType();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, указывающее тип изображения. Ниже приведены возможные значения и их описание.

|Значение|Значение|
|-----------|-------------|
|PICTYPE_UNINITIALIZED|`CPictureHolder` Объект unititialized.|
|PICTYPE_NONE|`CPictureHolder` объект является пустой.|
|PICTYPE_BITMAP|Рисунок является точечным рисунком.|
|PICTYPE_METAFILE|Рисунок представляет собой метафайл.|
|PICTYPE_ICON|Изображен значок.|

##  <a name="m_ppict"></a>  CPictureHolder::m_pPict

Указатель на `CPictureHolder` объекта `IPicture` интерфейс.

```
LPPICTURE m_pPict;
```

##  <a name="render"></a>  CPictureHolder::Render

Выполняет визуализацию изображения в прямоугольник, который ссылается *rcRender*.

```
void Render(
    CDC* pDC,
    const CRect& rcRender,
    const CRect& rcWBounds);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель для контекста отображения, в котором изображен к просмотру.

*rcRender*<br/>
Прямоугольник, в котором изображен к просмотру.

*rcWBounds*<br/>
Прямоугольник, представляющий ограничивающий прямоугольник объекта, Подготовка к просмотру на рисунке. Для элемента управления, этот прямоугольник определяется *rcBounds* параметр, передаваемый переопределение [COleControl::OnDraw](../../mfc/reference/colecontrol-class.md#ondraw).

##  <a name="setpicturedispatch"></a>  CPictureHolder::SetPictureDispatch

Подключается `CPictureHolder` объект `IPictureDisp` интерфейс.

```
void SetPictureDispatch(LPPICTUREDISP pDisp);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
Указатель на новый `IPictureDisp` интерфейс.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFontHolder](../../mfc/reference/cfontholder-class.md)
