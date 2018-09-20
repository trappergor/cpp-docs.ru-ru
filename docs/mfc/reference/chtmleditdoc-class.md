---
title: Класс CHtmlEditDoc | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77219f4cac64faf2604c427a2c4abf3babfd26a3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425373"
---
# <a name="chtmleditdoc-class"></a>Класс CHtmlEditDoc

С помощью [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), предоставляет функции платформы редактирования WebBrowser в контексте архитектуры представления документов MFC.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CHtmlEditDoc : public CDocument
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|Создает объект `CHtmlEditDoc`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHtmlEditDoc::GetView](#getview)|Извлекает `CHtmlEditView` объект присоединен к этому документу.|
|[CHtmlEditDoc::IsModified](#ismodified)|Возвращает, содержит ли элемент управления WebBrowser связанного представления документа, которые были изменены пользователем.|
|[CHtmlEditDoc::OpenURL](#openurl)|Открывает URL-адрес.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>Требования

**Заголовок:** afxhtml.h

##  <a name="chtmleditdoc"></a>  CHtmlEditDoc::CHtmlEditDoc

Создает объект `CHtmlEditDoc`.

```
CHtmlEditDoc();
```

##  <a name="getview"></a>  CHtmlEditDoc::GetView

Извлекает [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) объект присоединен к этому документу.

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на документ `CHtmlEditView` объекта.

##  <a name="ismodified"></a>  CHtmlEditDoc::IsModified

Возвращает, содержит ли элемент управления WebBrowser связанного представления документа, которые были изменены пользователем.

```
virtual BOOL IsModified();
```

##  <a name="openurl"></a>  CHtmlEditDoc::OpenURL

Открывает URL-адрес.

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Параметры

*lpszURL*<br/>
URL-адрес, чтобы открыть.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

## <a name="see-also"></a>См. также

[Пример HTMLEdit](../../visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

