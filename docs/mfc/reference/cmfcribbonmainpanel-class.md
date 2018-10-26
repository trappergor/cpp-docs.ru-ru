---
title: Класс CMFCRibbonMainPanel | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e23e883c143b1c65d4f150092193a7a693a34269
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065243"
---
# <a name="cmfcribbonmainpanel-class"></a>Класс CMFCRibbonMainPanel

Реализует панель ленты, которое отображается при нажатии кнопки [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md).

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonMainPanel : public CMFCRibbonPanel
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Конструктор по умолчанию.|
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonMainPanel::Add](#add)|Добавляет элемент ленты в левой части панели кнопку приложения. (Переопределяет [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).)|
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Добавляет текстовую строку меню списка последних файлов.|
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|Добавляет элемент ленты в нижней части окна приложения панель ленты.|
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|Добавляет элемент ленты справа панели кнопку приложения.|
|`CMFCRibbonMainPanel::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Возвращает прямоугольник, представляющий область элемента главной панели ленты.|
|`CMFCRibbonMainPanel::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|

## <a name="remarks"></a>Примечания

Платформа отображает `CMFCRibbonMainPanel` при открытии панели приложения. Он содержит три панели:

- Левая панель содержит команды, связанные с файлами, такие как **откройте**, **Сохранить**, **печати**, и **закрыть**. Чтобы добавить команду на эту панель, вызовите [CMFCRibbonMainPanel::Add](#add).

- На правой панели содержатся параметры, измените команду, выбранного в области слева. Например, если щелкнуть **Сохранить как** на левой панели правой панели можно отобразить типы файлов. Чтобы добавить элемент в эту область, вызовите [CMFCRibbonMainPanel::AddToRight](#addtoright).

- На нижней панели содержит кнопки, чтобы изменить параметры приложения и выйти из программы. Чтобы добавить элемент в эту область, вызовите [CMFCRibbonMainPanel::AddToBottom](#addtobottom).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRibbonMainPanel.h

##  <a name="add"></a>  CMFCRibbonMainPanel::Add

Добавляет элемент ленты в левой части панели кнопку приложения.

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>Параметры

*pElem*<br/>
[in, out] Указатель на элемент, добавляемый на главной панели ленты.

### <a name="remarks"></a>Примечания

Добавляет элемент ленты на панель. Элементы, добавленные с помощью этого метода будет находиться в левом столбце главной панели.

##  <a name="addrecentfileslist"></a>  CMFCRibbonMainPanel::AddRecentFilesList

Добавляет текстовую строку меню списка последних файлов.

```
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
Строка, добавляемый в список последних файлов.

*nWidth*<br/>
Задает ширину в пикселях панели списка последних файлов.

### <a name="remarks"></a>Примечания

##  <a name="addtobottom"></a>  CMFCRibbonMainPanel::AddToBottom

Добавляет элемент ленты в нижней части окна приложения панель ленты.

```
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>Параметры

*pElem*<br/>
[in, out] Указатель на элемент, добавляемый в нижней части главной панели ленты.

### <a name="remarks"></a>Примечания

##  <a name="addtoright"></a>  CMFCRibbonMainPanel::AddToRight

Добавляет элемент ленты справа панели кнопку приложения.

```
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>Параметры

*pElem*<br/>
Указатель на элемент ленты, добавляемых к правой части главной панели.

*nWidth*<br/>
Задает ширину в пикселях элементов на правой панели.

### <a name="remarks"></a>Примечания

Эта функция используется для добавления элемента ленты в правую панель. Правая панель обычно отображается список последних файлов, но можно добавить любой другой ленте элемент здесь.

##  <a name="getcommandsframe"></a>  CMFCRibbonMainPanel::GetCommandsFrame

Возвращает прямоугольник, представляющий область элемента главной панели ленты.

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>Возвращаемое значение

Прямоугольник, представляющий область элемента главной панели ленты.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)
