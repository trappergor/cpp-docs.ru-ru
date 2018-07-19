---
title: Структура COMPAREITEMSTRUCT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COMPAREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- COMPAREITEMSTRUCT structure [MFC]
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c42f356cb323bb7690b6c39b1fc7bd9ce0485f3
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850593"
---
# <a name="compareitemstruct-structure"></a>Структура COMPAREITEMSTRUCT
`COMPAREITEMSTRUCT` Структура предоставляет список идентификаторов и данных, предоставляемую приложением, для двух элементов в отсортированный, определяемый владельцем список или поле со списком.  
  
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
 *CtlType*  
 ODT_LISTBOX (который указывает рисуемый владельцем поле со списком) или ODT_COMBOBOX (который указывает рисуемый владельцем поле со списком).  
  
 *CtlID*  
 Идентификатор элемента управления для списка или поля со списком.  
  
 *hwndItem*  
 Дескриптор окна элемента управления.  
  
 *itemID1*  
 Индекс первого элемента в список или поле со списком с которым производится сравнение.  
  
 *itemData1*  
 Предоставляемую приложением данные первого элемента с которым производится сравнение. Это значение было передано в вызове, добавившего элемент в поле со списком или списка.  
  
 *itemID2*  
 Индекс второго элемента в список или поле со списком с которым производится сравнение.  
  
 *itemData2*  
 Предоставляемую приложением данных второго элемента с которым производится сравнение. Это значение было передано в вызове, добавившего элемент в поле со списком или списка.  
  
## <a name="remarks"></a>Примечания  
 Каждый раз, когда приложение добавляет новый элемент-владельцем список или поле со списком, созданных с помощью стиля CBS_SORT или LBS_SORT, Windows отправляет владельца WM_COMPAREITEM сообщение. *LParam* параметр сообщения содержит длинный указатель на `COMPAREITEMSTRUCT` структуры. При получении сообщения, владелец сравнивает два элемента и возвращает значение, указывающее, какой элемент сортирует перед другими.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)

