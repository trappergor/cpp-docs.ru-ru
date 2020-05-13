---
title: Класс CHtmlEditDoc
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
ms.openlocfilehash: 8b500f651da1a73040fdb0469f2f023babe25e85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352173"
---
# <a name="chtmleditdoc-class"></a>Класс CHtmlEditDoc

С [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), обеспечивает функциональность платформы для редактирования WebBrowser в контексте архитектуры просмотра документов MFC.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CHtmlEditDoc : public CDocument
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHtmlEditDoc::HtmlEditDoc](#chtmleditdoc)|Формирует объект `CHtmlEditDoc`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHtmlEditDoc::GetView](#getview)|Извлекает `CHtmlEditView` объект, прикрепленный к этому документу.|
|[CHtmlEditDoc::Изменено](#ismodified)|Возвращает вопрос о том, содержит ли элемент WebBrowser, связанный с ней, документ, который был изменен пользователем.|
|[CHtmlEditDoc::OpenURL](#openurl)|Открывает URL-адрес.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>Требования

**Заголовок:** afxhtml.h

## <a name="chtmleditdocchtmleditdoc"></a><a name="chtmleditdoc"></a>CHtmlEditDoc::HtmlEditDoc

Формирует объект `CHtmlEditDoc`.

```
CHtmlEditDoc();
```

## <a name="chtmleditdocgetview"></a><a name="getview"></a>CHtmlEditDoc::GetView

Извлекает объект [CHtmlEditView,](../../mfc/reference/chtmleditview-class.md) прикрепленный к этому документу.

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `CHtmlEditView` объект документа.

## <a name="chtmleditdocismodified"></a><a name="ismodified"></a>CHtmlEditDoc::Изменено

Возвращает вопрос о том, содержит ли элемент WebBrowser, связанный с ней, документ, который был изменен пользователем.

```
virtual BOOL IsModified();
```

## <a name="chtmleditdocopenurl"></a><a name="openurl"></a>CHtmlEditDoc::OpenURL

Открывает URL-адрес.

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Параметры

*lpszURL*<br/>
URL-адрес, который нужно открыть.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="see-also"></a>См. также раздел

[Образец HTMLEdit](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
