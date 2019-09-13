---
title: Класс Кмфкпропертипаже
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
ms.openlocfilehash: 4be584135ef789d7fbe3b1743ac0ad6ce66ac5b1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505043"
---
# <a name="cmfcpropertypage-class"></a>Класс Кмфкпропертипаже

`CMFCPropertyPage` Класс поддерживает отображение всплывающих меню на странице свойств.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кмфкпропертипаже:: Кмфкпропертипаже](#cmfcpropertypage)|Создает объект `CMFCPropertyPage`.|
|`CMFCPropertyPage::~CMFCPropertyPage`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCPropertyPage::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|`CMFCPropertyPage::OnSetActive`|Эта функция-член вызывается платформой при выборе пользователем страницы и становится активной страницей. (Переопределяет [CPropertyPage:: онсетактиве](../../mfc/reference/cpropertypage-class.md#onsetactive).)|
|`CMFCPropertyPage::PreTranslateMessage`|Преобразует сообщения окна до их отправки в функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) . Дополнительные сведения и синтаксис методов см. в разделе [CWnd::P ретранслатемессаже](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CPropertyPage::PreTranslateMessage`.)|

## <a name="remarks"></a>Примечания

`CMFCPropertyPage` Класс представляет отдельные страницы на странице свойств, которые в противном случае называются диалоговым окном «вкладка».

Используйте класс вместе с классом [кмфкпропертишит.](../../mfc/reference/cmfcpropertysheet-class.md) `CMFCPropertyPage` Чтобы использовать меню на странице свойств, замените все вхождения `CPropertyPage` класса `CMFCPropertyPage` классом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[кмфкпропертипаже](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкспропертипаже. h

##  <a name="cmfcpropertypage"></a>Кмфкпропертипаже:: Кмфкпропертипаже

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

*нидтемплате*<br/>
Идентификатор ресурса шаблона для этой страницы.

*нидкаптион*<br/>
Идентификатор ресурса метки, помещаемой на вкладку этой страницы. Если значение равно 0, имя получается из шаблона диалогового окна для этой страницы. Значение по умолчанию — 0.

*лпсзтемплатенаме*<br/>
Указывает на имя шаблона для этой страницы. Не может принимать значение NULL.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Дополнительные сведения о параметрах конструктора см. в разделе [CPropertyPage:: CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)
