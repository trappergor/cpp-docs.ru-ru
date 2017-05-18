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
- DELETEITEMSTRUCT structure
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f5936cbb863cf8ace851609cb1dc8352e21f9456
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="deleteitemstruct-structure"></a>Структура DELETEITEMSTRUCT
`DELETEITEMSTRUCT` Структура описывает удаленного пользовательского списка или поле со списком элемента.  
  
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
 Указывает **ODT_LISTBOX** (определяемые владельцем списка) или **ODT_COMBOBOX** (определяемые владельцем списком).  
  
 `CtlID`  
 Задает идентификатор для списка или поля со списком.  
  
 `itemID`  
 Указывает индекс элемента в список или поле со списком удаляется.  
  
 `hwndItem`  
 Определяет элемент управления.  
  
 `itemData`  
 Задает определяемые приложением данные элемента. Это значение передается в элемент управления в **lParam** сообщения, который добавляет элемент в список или поле со списком.  
  
## <a name="remarks"></a>Примечания  
 При удалении элемента из списка или поля со списком или при удалении списка или поля со списком Windows отправляет `WM_DELETEITEM` сообщение владельца для каждого удаляемого элемента. **LParam** сообщения содержит указатель на структуру.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)



