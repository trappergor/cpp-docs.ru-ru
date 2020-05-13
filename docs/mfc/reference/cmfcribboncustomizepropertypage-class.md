---
title: Класс CMFCRibbonCustomizePropertyPage
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
ms.openlocfilehash: 57fbd1e1f574beebff8baab014e7ab615f56333f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754170"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>Класс CMFCRibbonCustomizePropertyPage

Реализует пользовательскую страницу для **настраиваемых** диалоговых коробок в приложениях на основе ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|Формирует объект `CMFCRibbonCustomizePropertyPage`.|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCRibbonCustomEPropertyPage:AddCustomКатегория](#addcustomcategory)|Добавляет пользовательскую категорию в комбо-коробку **Команд.**|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCRibbonНастройкаНедвижимостьСтраница::OnOK](#onok)|Вызывается системой, когда пользователь нажимает **OK** на **настраиваемый диалоговый** ящик.|

## <a name="remarks"></a>Remarks

Если вы хотите добавить пользовательские команды в поле **настраиваемых** диалогов, необходимо обрабатывать AFX_WM_ON_RIBBON_CUSTOMIZE сообщение. В обработчике сообщений `CMFCRibbonCustomizePropertyPage` мгновенно объект в стеке. Создайте список пользовательских команд, `AddCustomCategory` а затем позвоните, чтобы добавить новую страницу в поле **настраиваемых** диалогов.

## <a name="example"></a>Пример

В следующем примере показано, `CMFCRibbonCustomizePropertyPage` как построить объект и добавить пользовательскую категорию.

[!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

[CMFCRibbonНастройкаНедвижимостьСтраница](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribboncustomizedialog.h

## <a name="cmfcribboncustomizepropertypageaddcustomcategory"></a><a name="addcustomcategory"></a>CMFCRibbonCustomEPropertyPage:AddCustomКатегория

Добавляет пользовательскую категорию в комбо-коробку **Команд.**

```cpp
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*lpszName*|(в) Определяет пользовательское название категории.|
|*lstIDS*|(в) Содержит идоты команд ленты, которые будут отображаться в пользовательской категории.|

### <a name="remarks"></a>Remarks

Этот метод добавляет категорию под названием *lpszName* в комбо-поле **Команд.** Когда пользователь выбирает категорию, команды, указанные в *lstIDS,* отображаются в списке команд.

## <a name="cmfcribboncustomizepropertypagecmfcribboncustomizepropertypage"></a><a name="cmfcribboncustomizepropertypage"></a>CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage

Формирует объект `CMFCRibbonCustomizePropertyPage`.

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>Параметры

*pRibbonBar*<br/>
(в) Указатель на ребератор управления, для которого варианты для настройки.

## <a name="cmfcribboncustomizepropertypageonok"></a><a name="onok"></a>CMFCRibbonНастройкаНедвижимостьСтраница::OnOK

Calleld системой, когда пользователь нажимает **OK** на **настраиваемый** диалоговый ящик.

```
virtual void OnOK();
```

### <a name="remarks"></a>Remarks

Реализация по умолчанию применяет параметры, выбранные в поле **настраиваемых** диалогов, к панели инструментов быстрого доступа.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
