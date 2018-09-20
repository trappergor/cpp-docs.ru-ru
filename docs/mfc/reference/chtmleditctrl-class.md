---
title: Класс CHtmlEditCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditCtrl [MFC], CHtmlEditCtrl
- CHtmlEditCtrl [MFC], Create
- CHtmlEditCtrl [MFC], GetDHtmlDocument
- CHtmlEditCtrl [MFC], GetStartDocument
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ab9a94663e2c374c0671afc6d4d093559ae1a69
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412405"
---
# <a name="chtmleditctrl-class"></a>Класс CHtmlEditCtrl

Предоставляет функциональные возможности элемента управления ActiveX WebBrowser в окне MFC.

## <a name="syntax"></a>Синтаксис

```
class CHtmlEditCtrl: public CWnd,
    public CHtmlEditCtrlBase<CHtmlEditCtrl>
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|Создает объект `CHtmlEditCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHtmlEditCtrl::Create](#create)|Создает элемент управления WebBrowser ActiveX и присоединяет его к `CHtmlEditCtrl` объекта. Эта функция автоматически переводит элемент управления WebBrowser ActiveX в режиме редактирования.|
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|Извлекает [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) интерфейса в документе, загруженные в элемента управления WebBrowser в контейнере.|
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|Извлекает URL-адрес документа по умолчанию для загрузки элемента управления WebBrowser в контейнере.|

## <a name="remarks"></a>Примечания

Размещенного элемента управления WebBrowser, элемент управления автоматически переводится в режим редактирования, после его создания.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHtmlEditCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxhtml.h

##  <a name="chtmleditctrl"></a>  CHtmlEditCtrl::CHtmlEditCtrl

Создает объект `CHtmlEditCtrl`.

```
CHtmlEditCtrl();
```

##  <a name="create"></a>  CHtmlEditCtrl::Create

Создает элемент управления WebBrowser ActiveX и присоединяет его к `CHtmlEditCtrl` объекта. Режим редактирования WebBrowser ActiveX, элемент управления автоматически переходит к документа по умолчанию и затем помещается в этой функцией.

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*lpszWindowName*<br/>
Этот параметр не используется.

*dwStyle*<br/>
Этот параметр не используется.

*Rect*<br/>
Задает размер и положение элемента управления.

*pParentWnd*<br/>
Указывает родительскому окну элемента управления. Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления.

*pContext*<br/>
Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="getdhtmldocument"></a>  CHtmlEditCtrl::GetDHtmlDocument

Извлекает [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) интерфейса в документе, загруженные в элемента управления WebBrowser в контейнере

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Параметры

*ppDocument*<br/>
Интерфейс документа.

##  <a name="getstartdocument"></a>  CHtmlEditCtrl::GetStartDocument

Извлекает URL-адрес документа по умолчанию для загрузки элемента управления WebBrowser в контейнере.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

