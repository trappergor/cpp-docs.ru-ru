---
title: Класс COlePropertiesDialog
ms.date: 11/04/2016
f1_keywords:
- COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::DoModal
- AFXODLGS/COlePropertiesDialog::OnApplyScale
- AFXODLGS/COlePropertiesDialog::m_gp
- AFXODLGS/COlePropertiesDialog::m_lp
- AFXODLGS/COlePropertiesDialog::m_op
- AFXODLGS/COlePropertiesDialog::m_psh
- AFXODLGS/COlePropertiesDialog::m_vp
helpviewer_keywords:
- COlePropertiesDialog [MFC], COlePropertiesDialog
- COlePropertiesDialog [MFC], DoModal
- COlePropertiesDialog [MFC], OnApplyScale
- COlePropertiesDialog [MFC], m_gp
- COlePropertiesDialog [MFC], m_lp
- COlePropertiesDialog [MFC], m_op
- COlePropertiesDialog [MFC], m_psh
- COlePropertiesDialog [MFC], m_vp
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
ms.openlocfilehash: e574f535609ec9401bd76badf11fa7e05cc0c619
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224401"
---
# <a name="colepropertiesdialog-class"></a>Класс COlePropertiesDialog

Инкапсулирует стандартное диалоговое окно свойств объекта OLE Windows.

## <a name="syntax"></a>Синтаксис

```
class COlePropertiesDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|Создает объект `COlePropertiesDialog`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COlePropertiesDialog::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|Вызывается платформой при изменении масштабирования элемента документа.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[COlePropertiesDialog::m_gp](#m_gp)|Структура, используемая для инициализации страница «Общие» `COlePropertiesDialog` объекта.|
|[COlePropertiesDialog::m_lp](#m_lp)|Структура, используемая для инициализации на страницу «Link» `COlePropertiesDialog` объекта.|
|[COlePropertiesDialog::m_op](#m_op)|Структура, используемая для инициализации `COlePropertiesDialog` объекта.|
|[COlePropertiesDialog::m_psh](#m_psh)|Структура, используемая для добавления дополнительных пользовательских свойств.|
|[COlePropertiesDialog::m_vp](#m_vp)|Структура, используемая для настройки на странице «Представление» `COlePropertiesDialog` объекта.|

## <a name="remarks"></a>Примечания

Общие диалоговые окна свойств объекта OLE предоставляют простой способ отображения и изменения свойств элемента документа OLE в соответствии со стандартами Windows. В частности, эти свойства включают сведения о файле, представленного элемента документа, параметры отображения значка и масштабирования изображения и информацией на ссылка элемента (если элемент связан).

Чтобы использовать `COlePropertiesDialog` следует сначала создать объект с помощью `COlePropertiesDialog` конструктор. После создания диалоговое окно, вызовите `DoModal` функцию-член для отображения в диалоговом окне, а также позволяет пользователям для изменения свойств элемента. `DoModal` Возвращает, является ли пользователь выбрал ОК (IDOK) или кнопку Отмена (IDCANCEL). Помимо кнопки "ОК" и "Отмена" имеется кнопка "Применить". Когда пользователь выбирает применить, любые изменения, внесенные в свойства элемента документа, применяются к элементу и его изображение обновляется автоматически, но остается активным.

[M_psh](#m_psh) данные-член — это указатель на `PROPSHEETHEADER` структуры и в большинстве случаев не требуется доступ к ней явным образом. Единственное исключение — при необходимости дополнительные страницы свойств за пределы страницы Общие представления и ссылки по умолчанию. В этом случае можно изменить `m_psh` данные-член для включения настраиваемых страниц перед вызовом `DoModal` функция-член.

Дополнительные сведения о диалоговых окнах OLE см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePropertiesDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

##  <a name="colepropertiesdialog"></a>  COlePropertiesDialog::COlePropertiesDialog

Создает объект `COlePropertiesDialog`.

```
COlePropertiesDialog(
    COleClientItem* pItem,
    UINT nScaleMin = 10,
    UINT nScaleMax = 500,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на элемент документа, свойства которого осуществляется доступ.

*nScaleMin*<br/>
Минимальный масштаб в процентах для изображения элемента документа.

*nScaleMax*<br/>
Максимальный масштаб в процентах для изображения элемента документа.

*pParentWnd*<br/>
Указатель на родительский объект или владельца диалогового окна.

### <a name="remarks"></a>Примечания

Быть производным от общих классов диалоговых окон свойств объекта OLE `COlePropertiesDialog` для реализации масштабирования для элементов документа. Все диалоговые окна реализованы с помощью экземпляра этого класса не будет поддерживать масштабирование элемента документа.

По умолчанию общее диалоговое окно свойств объекта OLE содержит три страницы по умолчанию:

- Общие

   Эта страница содержит системные сведения для файла, представленного элемента выбранного документа. На этой странице пользователя можно преобразовать выбранный элемент в другой тип.

- Просмотр

   Эта страница содержит параметры для отображения элемента, изменять значок и изменение масштабирования изображения.

- Ссылка

   Эта страница содержит параметры для изменения расположения связанного элемента и обновление связанного элемента. На этой странице пользователь может разорвать эту связь, выбранного элемента.

Чтобы добавить страницы, не реализованных по умолчанию, измените [m_psh](#m_psh) переменную-член перед выходом из конструктора вашей `COlePropertiesDialog`-производного класса. Это расширенную реализацию `COlePropertiesDialog` конструктора.

##  <a name="domodal"></a>  COlePropertiesDialog::DoModal

Вызывайте эту функцию члена, чтобы отобразить диалоговое окно общих свойств объекта OLE Windows и позволяет пользователю просмотреть или изменить различные свойства элемента документа.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

IDOK и IDCANCEL, если выполнение прошло успешно; в противном случае 0. IDOK и IDCANCEL являются константы, указывающие, является ли пользователь выбрал кнопку ОК или "Отмена".

Если возвращается IDCANCEL, можно вызвать Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) функцию, чтобы определить, произошла ли ошибка.

##  <a name="m_gp"></a>  COlePropertiesDialog::m_gp

Структура типа [OLEUIGNRLPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuignrlpropsa), которое используется для инициализации странице "Общие" диалогового окна свойств объекта OLE.

```
OLEUIGNRLPROPS m_gp;
```

### <a name="remarks"></a>Примечания

Эта страница показывает тип и размер внедрения и разрешает пользователю доступ к диалоговое окно "преобразование". Эта страница показывает конечный объект ссылки, является ли объект ссылки.

Дополнительные сведения о `OLEUIGNRLPROPS` структуры, см. в Windows SDK.

##  <a name="m_lp"></a>  COlePropertiesDialog::m_lp

Структура типа [OLEUILINKPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuilinkpropsa), которое используется для инициализации ссылки страницы диалогового окна свойств объекта OLE.

```
OLEUILINKPROPS m_lp;
```

### <a name="remarks"></a>Примечания

Эта страница показывает расположение связанного элемента и позволяет пользователю обновлять или прервать, ссылку на элемент.

Дополнительные сведения о `OLEUILINKPROPS` структуры, см. в Windows SDK.

##  <a name="m_op"></a>  COlePropertiesDialog::m_op

Структура типа [OLEUIOBJECTPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiobjectpropsa), которое используется для инициализации общее диалоговое окно свойств объекта OLE.

```
OLEUIOBJECTPROPS m_op;
```

### <a name="remarks"></a>Примечания

Эта структура содержит элементы, используемые для инициализации страницы представлений, ссылки и Общие.

Дополнительные сведения см. в разделе OLEUIOBJECTPROPS и [OLEUILINKPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuilinkpropsa) структур в пакете Windows SDK.

##  <a name="m_psh"></a>  COlePropertiesDialog::m_psh

Структура типа [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2), члены которой хранения характеристики объекта диалогового окна.

```
PROPSHEETHEADER m_psh;
```

### <a name="remarks"></a>Примечания

После построения `COlePropertiesDialog` объекта, можно использовать `m_psh` для задания различных аспектов диалоговом окне перед вызовом `DoModal` функция-член.

При изменении `m_psh` элемент данных напрямую, переопределяет любое поведение по умолчанию.

Дополнительные сведения о `PROPSHEETHEADER` структуры, см. в Windows SDK.

##  <a name="m_vp"></a>  COlePropertiesDialog::m_vp

Структура типа [OLEUIVIEWPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiviewpropsa), которое используется для инициализации представления страницы диалогового окна свойств объекта OLE.

```
OLEUIVIEWPROPS m_vp;
```

### <a name="remarks"></a>Примечания

Эта страница позволяет пользователю переключаться между «content» и «культовой» представления объекта, и изменения масштаба в контейнере. Он также позволяет пользователю доступ к диалоговому окну Смена значка, когда отображается объект в виде значка.

Дополнительные сведения о `OLEUIVIEWPROPS` структуры, см. в Windows SDK.

##  <a name="onapplyscale"></a>  COlePropertiesDialog::OnApplyScale

Вызывается платформой, когда изменилось значение масштаба и был выбран ОК или применить.

```
virtual BOOL OnApplyScale(
    COleClientItem* pItem,
    int nCurrentScale,
    BOOL bRelativeToOrig);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на элемент документа, свойства которого осуществляется доступ.

*nCurrentScale*<br/>
Числовое значение шкалы диалоговое окно.

*bRelativeToOrig*<br/>
Указывает ли масштабирование применяется к исходному размеру элемента документа.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если обработан; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не выполняет никаких действий. Необходимо переопределить эту функцию, чтобы включить элементы управления масштабирования.

> [!NOTE]
>  Перед отображением общее диалоговое окно свойств объекта OLE, платформа вызывает эту функцию со значением NULL для *pItem* и значение - 1 для *nCurrentScale*. Это позволяет определить, должна быть включена масштабирования элементов управления.

## <a name="see-also"></a>См. также

[Пример MFC Кр](../../overview/visual-cpp-samples.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Класс CPropertyPage](../../mfc/reference/cpropertypage-class.md)
