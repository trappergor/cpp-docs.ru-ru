---
title: "Структура COMPAREITEMSTRUCT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COMPAREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- COMPAREITEMSTRUCT structure
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 6c38c3e362f2e97cb51f5474aaa0bc05098b1ec2
ms.lasthandoff: 02/24/2017

---
# <a name="compareitemstruct-structure"></a>Структура COMPAREITEMSTRUCT
`COMPAREITEMSTRUCT` Структура предоставляет список идентификаторов и данных приложений для двух элементов в отсортированном, определяемые владельцем списка или поля со списком.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagCOMPAREITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    HWND hwndItem;  
    UINT itemID1;  
    DWORD itemData1;  
    UINT itemID2;  
    DWORD itemData2;  
} COMPAREITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>Параметры  
 `CtlType`  
 **ODT_LISTBOX** (который определяет список рисование владельцем) или **ODT_COMBOBOX** (указывает поле со списком рисование владельцем).  
  
 `CtlID`  
 Идентификатор элемента управления для списка или поля со списком.  
  
 `hwndItem`  
 Дескриптор окна элемента управления.  
  
 *itemID1*  
 Индекс первого элемента в список или поле со списком сравниваемых.  
  
 *itemData1*  
 Предоставляемый приложением данных сравниваемых первого элемента. Это значение было передано в вызове, добавлен элемент в поле со списком или списка.  
  
 *itemID2*  
 Индекс второго элемента в список или поле со списком сравниваемых.  
  
 *itemData2*  
 Предоставляемый приложением данных сравниваемых второго элемента. Это значение было передано в вызове, добавлен элемент в поле со списком или списка.  
  
## <a name="remarks"></a>Примечания  
 Каждый раз, когда приложение добавляет новый элемент определяемые владельцем список или поле со списком создаются с **CBS_SORT** или **LBS_SORT** стиль, Windows отправляет владельца `WM_COMPAREITEM` сообщение. `lParam` Параметр сообщения содержит длинный указатель `COMPAREITEMSTRUCT` структуры. При получении сообщения, владелец сравнивает два элемента и возвращает значение, указывающее, какой элемент сортируется до другого.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)


