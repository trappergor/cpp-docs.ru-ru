---
title: Класс CDockState | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
dev_langs:
- C++
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e8cde676795067005406f3eba86bdda7082f272
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435601"
---
# <a name="cdockstate-class"></a>Класс CDockState

Сериализуемый класс `CObject` для загрузки, выгрузки или очистки состояния одной или нескольких закрепляемых панелей элементов управления в постоянной памяти (файле).

## <a name="syntax"></a>Синтаксис

```
class CDockState : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDockState::Clear](#clear)|Удаляет сведения о состоянии закрепления.|
|[CDockState::GetVersion](#getversion)|Возвращает номер версии сохраненного состояния панели.|
|[CDockState::LoadState](#loadstate)|Извлекает сведения о состоянии из реестра или. INI-файл.|
|[CDockState::SaveState](#savestate)|Сохраняет сведения о состоянии в реестре или INI-файл.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|Массив указателей на сохраненный закрепить сведения о состоянии с одной записью для каждую панель элементов управления.|

## <a name="remarks"></a>Примечания

Состояние закрепления включает размер и положение строки и ли она закреплена. При получении сохраненного закрепить состояние, `CDockState` проверяет строки позиции и, если панель не отображается с текущими параметрами экрана, `CDockState` масштабирует панель размещения, так что стали видны. Основная цель `CDockState` для хранения состояния автоматического весь ряд панелей элементов управления и разрешить, чтобы сохранить состояние и загружен в реестр, приложение. INI-файл, или в двоичной форме, как часть `CArchive` содержимое объекта.

Панели может быть любой фиксируемый элемент управления, линейчатым диаграммам, включая панели инструментов, строка состояния или диалогового окна. `CDockState` объекты записи и чтения на или из файла с помощью `CArchive` объекта.

[CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) извлечение сведений о состоянии всех фрейма окна `CControlBar` объектов и помещает его в `CDockState` объекта. После этого можно написать содержимое `CDockState` объекта в хранилище с помощью [Serialize](../../mfc/reference/cobject-class.md#serialize) или [CDockState::SaveState](#savestate). Если позже вы хотите восстановить состояние панелей элементов управления в окне фрейма, ее можно загружать в состояние с `Serialize` или [CDockState::LoadState](#loadstate), затем с помощью [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) для применения сохраненного состояние для панелей элементов управления окна фрейма.

Дополнительные сведения о закрепляемых панелей элементов управления, см. в статьях [панелей элементов управления](../../mfc/control-bars.md), [панели инструментов: закрепленные и плавающие](../../mfc/docking-and-floating-toolbars.md), и [фрейма Windows](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>Требования

**Заголовок:** afxadv.h

##  <a name="clear"></a>  CDockState::Clear

Вызывайте эту функцию, чтобы очистить все сведения о закреплении, хранящиеся в `CDockState` объекта.

```
void Clear();
```

### <a name="remarks"></a>Примечания

Сюда входят не только ли панель закреплена или нет, но размер и положение строки, так и ли он отображается.

##  <a name="getversion"></a>  CDockState::GetVersion

Вызывайте эту функцию, чтобы получить номер версии сохраненного состояния панели.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Возвращаемое значение

1, если строке хранимые сведения старше текущей строки состояния. 2, если строке хранимые сведения совпадает со значением текущего состояния панели.

### <a name="remarks"></a>Примечания

Поддержка версий включает измененный панели, чтобы добавить новые свойства постоянных и по-прежнему иметь возможность обнаружить и загрузить постоянное состояние, созданные в более ранней версии строки.

##  <a name="loadstate"></a>  CDockState::LoadState

Вызывайте эту функцию для получения сведений о состоянии из реестра или. INI-файл.

```
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
Указывает на null-teminated строка, задающая имя раздела в файле настройки или ключ в реестре Windows, где хранятся сведения о состоянии.

### <a name="remarks"></a>Примечания

Имя профиля — часть приложения. INI-файл или реестр, который содержит сведения о панели состоянии. Панель сведений о состоянии элементов управления можно сохранить в реестре или. INI-файл с `SaveState`.

##  <a name="m_arrbarinfo"></a>  CDockState::m_arrBarInfo

Объект `CPtrArray` объект, который представляет собой массив указателей на параметры панели хранимых управления к каждую панель элементов управления, который сохраненные сведения о состоянии в `CDockState` объекта.

```
CPtrArray m_arrBarInfo;
```

##  <a name="savestate"></a>  CDockState::SaveState

Вызывайте эту функцию, чтобы сохранить сведения о состоянии в реестре или. INI-файл.

```
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
Указывает на null-teminated строка, задающая имя раздела в файле настройки или ключ в реестре Windows, где хранятся сведения о состоянии.

### <a name="remarks"></a>Примечания

Имя профиля — часть приложения. INI-файл или реестр, содержащий сведения о состоянии на панели управления. `SaveState` также сохраняет текущий размер экрана. Сведения о панели управления можно получить из реестра или. INI-файл с `LoadState`.

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

