---
title: Структура MEASUREITEMSTRUCT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MEASUREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- MEASUREITEMSTRUCT structure [MFC]
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff015fdaf9e37d919459cadc8e4c35c4b795b3f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372274"
---
# <a name="measureitemstruct-structure"></a>Структура MEASUREITEMSTRUCT
`MEASUREITEMSTRUCT` Структура сообщает Windows размеры определяемые владельцем элемента управления или меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagMEASUREITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    UINT itemWidth;  
    UINT itemHeight;  
    DWORD itemData  
} MEASUREITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>Параметры  
 `CtlType`  
 Содержит тип элемента управления. Ниже приведены значения для типов элементов управления.  
  
- **ODT_COMBOBOX** рисуемый владельцем поле со списком  
  
- **ODT_LISTBOX** рисуемый владельцем поле со списком  
  
- **ODT_MENU** рисуемый владельцем меню  
  
 `CtlID`  
 Содержит идентификатор элемента управления для поля со списком, списка или кнопки. Этот элемент не используется для меню.  
  
 `itemID`  
 Содержит идентификатор пункта меню меню или идентификатор элемента списка поле для переменной высоты со списком или списка. Этот элемент не используется для фиксированной высоты со списком или списка или кнопки.  
  
 *itemWidth*  
 Задает ширину для элемента меню. Владелец элемента меню рисуемый владельцем, необходимо указать этот член, перед возвратом из сообщения.  
  
 *itemHeight*  
 Указывает высоту отдельного элемента в поле со списком или меню. Перед возвратом из сообщения, владельцем поле со списком рисуемого владельцем список или элемент меню необходимо заполнить этот член. Максимальная высота элемента списка — 255.  
  
 `itemData`  
 Для поля со списком или списка этот элемент содержит значение, которое было передано в список с помощью одной из следующих структур:  
  
- [CComboBox::AddString](../../mfc/reference/ccombobox-class.md#addstring)  
  
- [CComboBox::InsertString](../../mfc/reference/ccombobox-class.md#insertstring)  
  
- [CListBox::AddString](../../mfc/reference/clistbox-class.md#addstring)  
  
- [CListBox::InsertString](../../mfc/reference/clistbox-class.md#insertstring)  
  
 Для меню этот элемент содержит значение, которое было передано в меню с помощью одной из следующих структур:  
  
- [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)  
  
- [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)  
  
- [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)  
  
 Это позволяет правильно обработать взаимодействия пользователя с элементом управления Windows. Не удалось заполнить соответствующие элементы в `MEASUREITEMSTRUCT` структуры приведет к неправильной работы элемента управления.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)

