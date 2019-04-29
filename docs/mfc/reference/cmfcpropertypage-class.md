---
title: Класс CMFCPropertyPage
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
ms.openlocfilehash: 62e33da998f1e5332436d887c38d3fd65526561b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310493"
---
# <a name="cmfcpropertypage-class"></a>Класс CMFCPropertyPage

`CMFCPropertyPage` Класс поддерживает отображение всплывающих меню на странице свойств.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|Создает объект `CMFCPropertyPage`.|
|`CMFCPropertyPage::~CMFCPropertyPage`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCPropertyPage::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|`CMFCPropertyPage::OnSetActive`|Эта функция-член вызывается платформой при страницы, выбранный пользователем и становится активной страницей. (Переопределяет [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|
|`CMFCPropertyPage::PreTranslateMessage`|Преобразует сообщения окна перед их диспетчеризацией в [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) функции Windows. Дополнительные сведения и синтаксис методов, см. в разделе [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CPropertyPage::PreTranslateMessage`.)|

## <a name="remarks"></a>Примечания

`CMFCPropertyPage` Класс представляет отдельные страницы вкладки свойств, также известный как диалоговое окно вкладки.

Используйте `CMFCPropertyPage` класса вместе с [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) класса. Чтобы использовать меню на странице свойств, замените все вхождения `CPropertyPage` класса `CMFCPropertyPage` класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpropertypage.h

##  <a name="cmfcpropertypage"></a>  CMFCPropertyPage::CMFCPropertyPage

Создает объект `CMFCPropertyPage`.

```
CMFCPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption=0);

CMFCPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption=0);
```

### <a name="parameters"></a>Параметры

*nIDTemplate*<br/>
Идентификатор ресурса шаблона для этой страницы.

*nIDCaption*<br/>
Идентификатор ресурса метки для размещения на вкладке этой страницы. Если значение равно 0, то имя получается из шаблон диалогового окна для этой страницы. Значение по умолчанию — 0.

*lpszTemplateName*<br/>
Указывает имя шаблона для этой страницы. Не может принимать значение NULL.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Дополнительные сведения о параметрах конструктора, см. в разделе [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)
