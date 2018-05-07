---
title: Структура DELETEITEMSTRUCT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DELETEITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f56a09742276c7fcb1bd66ff1a36b1d17cdf882
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
 `CtlType`  
 Указывает **ODT_LISTBOX** (определяемый владельцем список) или **ODT_COMBOBOX** (определяемые владельцем со списком).  
  
 `CtlID`  
 Указывает идентификатор списка или поля со списком.  
  
 `itemID`  
 Указывает индекс элемента в список или поле со списком удаляется.  
  
 `hwndItem`  
 Определяет элемент управления.  
  
 `itemData`  
 Указывает определяемые приложением данные для элемента. Это значение передается в элемент управления в **lParam** сообщения, который добавляет элемент в список или поле со списком.  
  
## <a name="remarks"></a>Примечания  
 При удалении элемента из списка или поля со списком или при удалении списка или поля со списком, Windows посылает `WM_DELETEITEM` сообщение с владельцем для каждого удаляемого элемента. **LParam** сообщения содержит указатель на эту структуру.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)


