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
ms.openlocfilehash: 8c790ca249f34a3c9b36d1bd77dafdc4a91bd352
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288913"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>Класс CMFCRibbonCustomizePropertyPage

Реализует пользовательскую страницу для **Настройка** диалоговое окно в приложениях, основанных на Ribbon.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|Создает объект `CMFCRibbonCustomizePropertyPage`.|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание:|
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|Добавляет пользовательскую категорию для **команды** поле со списком.|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|Вызывается системой, когда пользователь щелкает **ОК** на **Настройка** диалоговое окно.|

## <a name="remarks"></a>Примечания

Если вы хотите добавить пользовательские команды **Настройка** диалоговом окне необходимо обрабатывать сообщения AFX_WM_ON_RIBBON_CUSTOMIZE. В обработчике сообщений, создать экземпляр `CMFCRibbonCustomizePropertyPage` объект в стеке. Создать список пользовательских команд, а затем вызвать `AddCustomCategory` для добавления новой страницы, **Настройка** диалоговое окно.

## <a name="example"></a>Пример

В следующем примере демонстрируется создание `CMFCRibbonCustomizePropertyPage` объекта и добавления пользовательской категории.

[!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

[CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribboncustomizedialog.h

##  <a name="addcustomcategory"></a>  CMFCRibbonCustomizePropertyPage::AddCustomCategory

Добавляет пользовательскую категорию для **команды** поле со списком.

```
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*lpszName*|[in] Задает имя пользовательской категории.|
|*lstIDS*|[in] Содержит идентификаторы команд ленты для отображения в пользовательской категории.|

### <a name="remarks"></a>Примечания

Этот метод добавляет категорию с именем *lpszName* для **команды** поле со списком. Когда пользователь выбирает категорию, команды, которые указаны в *lstIDS* отображаются в списке команд.

##  <a name="cmfcribboncustomizepropertypage"></a>  CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage

Создает объект `CMFCRibbonCustomizePropertyPage`.

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>Параметры

*pRibbonBar*<br/>
[in] Указатель на элемент управления ленты, для которого параметры для настройки.

##  <a name="onok"></a>  CMFCRibbonCustomizePropertyPage::OnOK

Calleld системой, когда пользователь щелкает **ОК** на **Настройка** диалоговое окно.

```
virtual void OnOK();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию применяет параметры, выбранные в **Настройка** диалоговое окно в панель быстрого доступа.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
