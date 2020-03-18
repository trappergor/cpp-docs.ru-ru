---
title: Класс Кмфкриббонсепаратор
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
ms.openlocfilehash: 65321cb80c80a5f4c6b3cf9c67e85b1bfb6f9d11
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445603"
---
# <a name="cmfcribbonseparator-class"></a>Класс Кмфкриббонсепаратор

Реализует Разделитель ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonSeparator : public CMFCRibbonBaseElement
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Description|
|[Кмфкриббонсепаратор:: Кмфкриббонсепаратор](#cmfcribbonseparator)|Формирует объект `CMFCRibbonSeparator`.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Description|
|[Кмфкриббонсепаратор:: Аддтолистбокс](#addtolistbox)|Добавляет разделитель в список **команд** диалогового окна **Настройка** . (Переопределяет [метод CMFCRibbonBaseElement:: аддтолистбокс](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|
|`CMFCRibbonSeparator::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCRibbonSeparator::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|

### <a name="protected-methods"></a>Защищенные методы

|||
|-|-|
|Имя|Description|
|[Кмфкриббонсепаратор:: CopyFrom](#copyfrom)|Метод Copy, устанавливающий переменные-члены разделителя из другого объекта.|
|[Кмфкриббонсепаратор:: Жетрегуларсизе](#getregularsize)|Возвращает размер разделителя.|
|[Кмфкриббонсепаратор::](#isseparator)|Указывает, является ли это разделителем.|
|[Кмфкриббонсепаратор:: IsTabStop](#istabstop)|Указывает, является ли данная позиция клавишей табуляции.|
|[Кмфкриббонсепаратор:: OnDraw](#ondraw)|Вызывается системой для рисования разделителя на ленте или на панели быстрого доступа.|
|[Кмфкриббонсепаратор:: Ондравонлист](#ondrawonlist)|Вызывается системой для рисования разделителя в списке **команд** .|

## <a name="remarks"></a>Remarks

Разделитель ленты — это вертикальная или горизонтальная линия, которая логически разделяет элементы ленты. Разделитель может быть нарисован на элементе управления Ribbon, главном меню приложения, строке состояния ленты и панели быстрого доступа.

Чтобы использовать разделитель в приложении, создайте новый объект и добавьте его в главное меню приложения, как показано ниже:

```
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```

Вызовите [CMFCRibbonPanel:: аддсепаратор](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) , чтобы добавить разделители на панели ленты. Разделители выделяются и добавляются внутри метода `AddSeparator`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[кмфкриббонсепаратор](../../mfc/reference/cmfcribbonseparator-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxbaseribbonelement.h

##  <a name="addtolistbox"></a>Кмфкриббонсепаратор:: Аддтолистбокс

Добавляет разделитель в список **команд** диалогового окна **Настройка** .

```
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,
    BOOL bDeep);
```

### <a name="parameters"></a>Параметры

*пвндлистбокс*<br/>
окне Указатель на список **команд** , в который добавляется разделитель.

*бдип*<br/>
окне Игнорируют.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс строки в списке, заданном параметром *пвндлистбокс*.

##  <a name="cmfcribbonseparator"></a>Кмфкриббонсепаратор:: Кмфкриббонсепаратор

Формирует объект `CMFCRibbonSeparator`.

```
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```

### <a name="parameters"></a>Параметры

*бишориз*<br/>
окне Если значение равно TRUE, разделитель является горизонтальным; Если значение равно FALSE, разделитель является вертикальным.

### <a name="remarks"></a>Remarks

В меню приложения используются горизонтальные разделители. В панелях инструментов используются вертикальные разделители.

### <a name="example"></a>Пример

В следующем примере показано, как создать объект класса `CMFCRibbonSeparator`.

[!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]

##  <a name="copyfrom"></a>Кмфкриббонсепаратор:: CopyFrom

Метод Copy, устанавливающий переменные-члены разделителя из другого объекта.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Параметры

*Src*<br/>
окне Исходный элемент ленты, из которого производится копирование.

##  <a name="getregularsize"></a>Кмфкриббонсепаратор:: Жетрегуларсизе

Возвращает размер разделителя.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на содержимое устройства.

### <a name="return-value"></a>Возвращаемое значение

Размер разделителя в данном контексте устройства.

##  <a name="isseparator"></a>Кмфкриббонсепаратор::

Указывает, является ли это разделителем.

```
virtual BOOL IsSeparator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Для этого класса всегда имеет значение TRUE.

##  <a name="istabstop"></a>Кмфкриббонсепаратор:: IsTabStop

Указывает, является ли данная позиция клавишей табуляции.

```
virtual BOOL IsTabStop() const;
```

### <a name="return-value"></a>Возвращаемое значение

Для этого класса всегда имеет значение FALSE.

### <a name="remarks"></a>Remarks

Разделитель ленты не является вкладкой табуляции.

##  <a name="ondraw"></a>Кмфкриббонсепаратор:: OnDraw

Вызывается системой для рисования разделителя на ленте или на панели быстрого доступа.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на контекст устройства.

##  <a name="ondrawonlist"></a>Кмфкриббонсепаратор:: Ондравонлист

Вызывается системой для рисования разделителя в списке **команд** .

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Description|
|*pDC*|окне Указатель на контекст устройства.|
|*стртекст*|окне Текст, отображаемый в списке.|
|*нтекстоффсет*|окне Интервал между текстом и левой стороной ограничивающего прямоугольника.|
|*rect*|окне Задает ограничивающий прямоугольник.|
|*бисселектед*|окне Игнорируют.|
|*бхигхлигхтед*|окне Игнорируют.|

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
