---
title: "Структура DELETEITEMSTRUCT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DELETEITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 93be7b23ae713caea5fa64e437fe792c550589f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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


