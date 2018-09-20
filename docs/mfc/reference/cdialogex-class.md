---
title: Класс CDialogEx | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
dev_langs:
- C++
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02a8ae81ea94c47cd11beae0b3ed0eacee77db07
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386305"
---
# <a name="cdialogex-class"></a>Класс CDialogEx

Класс `CDialogEx` задает цвет фона и фоновое изображение для диалогового окна.

## <a name="syntax"></a>Синтаксис

```
class CDialogEx : public CDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDialogEx::CDialogEx](#cdialogex)|Создает объект `CDialogEx`.|
|`CDialogEx::~CDialogEx`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Cdialogex::setbackgroundcolor при использовании](#setbackgroundcolor)|Задает цвет фона диалогового окна.|
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|Задает фоновое изображение диалогового окна.|

## <a name="remarks"></a>Примечания

Чтобы использовать класс `CDialogEx`, сформируйте класс диалогового окна из класса `CDialogEx` вместо класса `CDialog`.

Изображения диалогового окна хранятся в файле ресурсов. Платформа автоматически удаляет все изображения, загруженные из файла ресурсов. Чтобы программно удалить текущее фоновое изображение, вызовите [CDialogEx::SetBackgroundImage](#setbackgroundimage) метод или реализуйте `OnDestroy` обработчик событий. При вызове [CDialogEx::SetBackgroundImage](#setbackgroundimage) метод, передав `HBITMAP` параметра в виде маркера изображения. Объект `CDialogEx` будет распоряжаться изображением и может удалить его, если для флажка `m_bAutoDestroyBmp` установлено значение `TRUE`.

Объект `CDialogEx` объект может быть родителем [класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) объекта. [Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) вызывает `CDialogEx::SetActiveMenu` метод при [класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) открывается объект. После этого `CDialogEx` объект обрабатывает любые события меню до [класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) объект закрыт.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxdialogex.h

##  <a name="cdialogex"></a>  CDialogEx::CDialogEx

Создает объект `CDialogEx`.

```
CDialogEx(
    UINT nIDTemplate,
    CWnd* pParent=NULL);


CDialogEx(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd=NULL);
```

### <a name="parameters"></a>Параметры

*nIDTemplate*<br/>
[in] Идентификатор ресурса шаблона диалогового окна.

*lpszTemplateName*<br/>
[in] Имя ресурса шаблона диалогового окна.

*pParent*<br/>
[in] Указатель на родительское окно. Значение по умолчанию имеет значение NULL.

*pParentWnd*<br/>
[in] Указатель на родительское окно. Значение по умолчанию имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="setbackgroundcolor"></a>  Cdialogex::setbackgroundcolor при использовании

Задает цвет фона диалогового окна.

```
void SetBackgroundColor(
    COLORREF color,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
[in] Значение цвета RGB.

*bRepaint*<br/>
[in] Значение TRUE, чтобы немедленно обновить экрана; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

##  <a name="setbackgroundimage"></a>  CDialogEx::SetBackgroundImage

Задает фоновое изображение диалогового окна.

```
void SetBackgroundImage(
    HBITMAP hBitmap,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bAutoDestroy=TRUE,
    BOOL bRepaint=TRUE);


BOOL SetBackgroundImage(
    UINT uiBmpResId,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
[in] Дескриптор для фонового изображения.

*uiBmpResId*<br/>
[in] Идентификатор ресурса фонового изображения.

*расположение*<br/>
[in] Один из `CDialogEx::BackgroundLocation` значения, указывающие расположение образа. Допустимые значения: BACKGR_TILE, BACKGR_TOPLEFT, BACKGR_TOPRIGHT, BACKGR_BOTTOMLEFT и BACKGR_BOTTOMRIGHT. Значение по умолчанию — BACKGR_TILE.

*bAutoDestroy*<br/>
[in] Значение TRUE, чтобы автоматически удалить фоновое изображение; в противном случае — значение FALSE.

*bRepaint*<br/>
[in] Значение TRUE, чтобы немедленно перерисовывает диалоговое окно. в противном случае — значение FALSE.

### <a name="return-value"></a>Возвращаемое значение

Во втором методе перегружать синтаксис, значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вами изображение не растягивается область диалогового окна клиента.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)<br/>
[Класс CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)
