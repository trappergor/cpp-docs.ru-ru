---
title: "Функции обмена данными в диалоговых окнах для CRecordView и CDaoRecordView | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO [C++], поддержка обмена данными диалоговых окон (DDX)"
  - "базы данных [C++], поддержка обмена данными диалоговых окон (DDX)"
  - "DDX (обмен данными диалоговых окон) [C++], поддержка баз данных"
  - "DDX (обмен данными диалоговых окон) [C++], функции"
  - "DDX_Field - функции"
  - "ODBC [C++], поддержка обмена данными диалоговых окон (DDX)"
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Функции обмена данными в диалоговых окнах для CRecordView и CDaoRecordView
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом разделе перечислены функции DDX\_Field, используемые для обмена данными между [CRecordset](../Topic/CRecordset%20Class.md) и формой формой [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).  
  
> [!NOTE]
>  Функции DDX\_Field подобно функции DDX в этом они обмениваются данными с элементами управления в форме.  Но в отличие от DDX, они обмениваются данными с полями представления связанного объекта набора записей, а не с полями самими представления.  Классы `CRecordView` и `CDaoRecordView` Дополнительные сведения в разделе в.  
  
### Функции DDX\_Field  
  
|||  
|-|-|  
|[DDX\_FieldCBIndex](../Topic/DDX_FieldCBIndex.md)|Целочисленные данные передачи между элементом данных полей набора записей и индекс текущего выделения в поле со списком в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|  
|[DDX\_FieldCBString](../Topic/DDX_FieldCBString.md)|Данные `CString` передачи между элементом данных полей набора записей и элементом управления "Поле ввода" поля со списком в `CRecordView` или `CDaoRecordView`.  При перемещении данных из набора записей к элементу управления, эта функция выделяет элемент в поле со списком, которое начинается с символами в данной строке.|  
|[DDX\_FieldCBStringExact](../Topic/DDX_FieldCBStringExact.md)|Данные `CString` передачи между элементом данных полей набора записей и элементом управления "Поле ввода" поля со списком в `CRecordView` или `CDaoRecordView`.  При перемещении данных из набора записей к элементу управления, эта функция выделяет элемент в поле со списком, точно соответствует указанной строке.|  
|[DDX\_FieldCheck](../Topic/DDX_FieldCheck.md)|Логические передачи данных между элементом данных полей набора записей и флажком в `CRecordView` или `CDaoRecordView`.|  
|[DDX\_FieldLBIndex](../Topic/DDX_FieldLBIndex.md)|Целочисленные данные передачи между элементом данных полей набора записей и индекс текущего выделения в `CRecordView` или `CDaoRecordView`.|  
|[DDX\_FieldLBString](../Topic/DDX_FieldLBString.md)|Управление передачи данных по [CString](../../atl-mfc-shared/reference/cstringt-class.md) между элементом управления и списка элементов данных полей набора записей.  При перемещении данных из набора записей к элементу управления, эта функция выделяет элемент в списке, который начинается с символами в указанной строке.|  
|[DDX\_FieldLBStringExact](../Topic/DDX_FieldLBStringExact.md)|Управление передачи данных по `CString` между элементом управления и списка элементов данных полей набора записей.  При перемещении данных из набора записей к элементу управления, эта функция выделяет первого элемента, который точно соответствует указанной строке.|  
|[DDX\_FieldRadio](../Topic/DDX_FieldRadio.md)|Целочисленные данные передачи между элементом данных полей набора записей и группой в составе переключатели в `CRecordView` или `CDaoRecordView`.|  
|[DDX\_FieldScroll](../Topic/DDX_FieldScroll.md)|Возвращает или задает позицию прокрутки элемента управления полосы прокрутки в `CRecordView` или `CDaoRecordView`.  Вызовите из функции [DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md).|  
|[DDX\_FieldText](../Topic/DDX_FieldText.md)|Перегруженные версии доступны для передачи `int`, **uint**, **long**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **плавающее**, **double**, **short**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), [COleCurrency](../Topic/COleCurrency%20Class.md) и данные между элементом данных полей набора записей и полем ввода в `CRecordView` или `CDaoRecordView`.|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)