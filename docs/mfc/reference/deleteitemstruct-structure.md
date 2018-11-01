---
title: Структура DELETEITEMSTRUCT
ms.date: 11/04/2016
f1_keywords:
- DELETEITEMSTRUCT
helpviewer_keywords:
- DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
ms.openlocfilehash: dd1f48fd584016dab740bc8a6bd05ff3b756e41b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486887"
---
# <a name="deleteitemstruct-structure"></a>Структура DELETEITEMSTRUCT

`DELETEITEMSTRUCT` Структура описывает удаленного определяемый владельцем список или поле со списком элемента.

## <a name="syntax"></a>Синтаксис

```
typedef struct tagDELETEITEMSTRUCT { /* ditms */
    UINT CtlType;
    UINT CtlID;
    UINT itemID;
    HWND hwndItem;
    UINT itemData;
} DELETEITEMSTRUCT;
```

#### <a name="parameters"></a>Параметры

*CtlType*<br/>
Указывает ODT_LISTBOX (-владельцем список) или ODT_COMBOBOX (рисуемое владельцем со списком).

*CtlID*<br/>
Указывает идентификатор в поле со списком или в поле со списком.

*Идентификатор элемента*<br/>
Указывает индекс элемента в список или поле со списком для удаления.

*hwndItem*<br/>
Определяет элемент управления.

*itemData*<br/>
Задает определяемые приложением данные для элемента. Это значение передается в элемент управления в *lParam* параметр сообщения, который добавляет элемент в список или поле со списком.

## <a name="remarks"></a>Примечания

При удалении элемента из списка или поля со списком или при уничтожении список или поле со списком, Windows отправляет сообщение WM_DELETEITEM владельца для каждого удаляемого элемента. *LParam* параметр сообщения содержит указатель на структуру.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)

