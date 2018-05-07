---
title: Класс CDialogEx | Документы Microsoft
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
ms.openlocfilehash: 42da6afd054f05bb37ac0b4ea8bf497a31e433b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|Задает цвет фона диалогового окна.|  
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|Задает фоновое изображение диалогового окна.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы использовать класс `CDialogEx`, сформируйте класс диалогового окна из класса `CDialogEx` вместо класса `CDialog`.  
  
 Изображения диалогового окна хранятся в файле ресурсов. Платформа автоматически удаляет все изображения, загруженные из файла ресурсов. Чтобы программно удалить текущее фоновое изображение, вызовите [CDialogEx::SetBackgroundImage](#setbackgroundimage) метод или реализовать `OnDestroy` обработчика событий. При вызове [CDialogEx::SetBackgroundImage](#setbackgroundimage) метод, передайте `HBITMAP` параметр в качестве маркера изображения. Объект `CDialogEx` будет распоряжаться изображением и может удалить его, если для флажка `m_bAutoDestroyBmp` установлено значение `TRUE`.  
  
 Объект `CDialogEx` объект может быть родителем [CMFCPopupMenu класс](../../mfc/reference/cmfcpopupmenu-class.md) объекта. [Класса CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) вызывает `CDialogEx::SetActiveMenu` метод при [CMFCPopupMenu класса](../../mfc/reference/cmfcpopupmenu-class.md) открывается объект. После этого `CDialogEx` объект обрабатывает любые события меню, пока [CMFCPopupMenu класса](../../mfc/reference/cmfcpopupmenu-class.md) объект закрыт.  
  
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
 [in] `nIDTemplate`  
 Идентификатор ресурса шаблона диалоговых окон.  
  
 [in] `lpszTemplateName`  
 Имя ресурса шаблона диалоговых окон.  
  
 [in] `pParent`  
 Указатель на родительское окно. Значение по умолчанию — `NULL`.  
  
 [in] `pParentWnd`  
 Указатель на родительское окно. Значение по умолчанию — `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setbackgroundcolor"></a>  CDialogEx::SetBackgroundColor  
 Задает цвет фона диалогового окна.  
  
```  
void SetBackgroundColor(
    COLORREF color,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 Значение цвета RGB.  
  
 [in] `bRepaint`  
 `TRUE` Чтобы немедленно обновить экрана. в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
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
 [in] `hBitmap`  
 Дескриптор фоновое изображение.  
  
 [in] `uiBmpResId`  
 Идентификатор ресурса фонового изображения.  
  
 [in] `location`  
 Один из `CDialogEx::BackgroundLocation` значения, указывающие расположение образа. Допустимые значения: BACKGR_TILE, BACKGR_TOPLEFT, BACKGR_TOPRIGHT, BACKGR_BOTTOMLEFT и BACKGR_BOTTOMRIGHT. Значение по умолчанию — BACKGR_TILE.  
  
 [in] `bAutoDestroy`  
 `TRUE` Чтобы автоматически удалить фоновое изображение; в противном случае `FALSE`.  
  
 [in] `bRepaint`  
 `TRUE` Чтобы немедленно перерисовывает диалоговое окно. в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Во втором методе перегрузки синтаксис, `TRUE` Если метод выполнен успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Изображения, которое можно указать не растягивается область диалогового окна клиента.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)   
 [Класс CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)
