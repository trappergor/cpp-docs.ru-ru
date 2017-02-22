---
title: "Стандартные программы проверки данных диалоговых окон | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "стандартное диалоговое окно, процедуры проверки данных"
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Стандартные программы проверки данных диалоговых окон
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом разделе перечислены стандартные процедуры \(DDV\) проверки данных диалогового окна, используемые для общих элементов управления диалогового окна MFC.  
  
> [!NOTE]
>  Стандартные процедуры обмена данными с диалоговым окном определены в файле заголовка afxdd\_.h.  Тем не менее, приложения должны включать afxwin.h.  
  
### DDV\-функции  
  
|||  
|-|-|  
|[DDV\_MaxChars](../Topic/DDV_MaxChars.md)|Проверьте число символов в данном значения элементов управления не превышает заданного максимума.|  
|[DDV\_MinMaxByte](../Topic/DDV_MinMaxByte.md)|Проверьте заданное значение элемента управления не превышает заданный диапазон **byte**.|  
|[DDV\_MinMaxDateTime](../Topic/DDV_MinMaxDateTime.md)|Проверьте заданное значение элемента управления не превышает диапазон заданного момента времени.|  
|[DDV\_MinMaxDouble](../Topic/DDV_MinMaxDouble.md)|Проверьте заданное значение элемента управления не превышает заданный диапазон **double**.|  
|[DDV\_MinMaxDWord](../Topic/DDV_MinMaxDWord.md)|Проверьте заданное значение элемента управления не превышает заданный диапазон **dword**.|  
|[DDV\_MinMaxFloat](../Topic/DDV_MinMaxFloat.md)|Проверьте заданное значение элемента управления не превышает заданный диапазон **плавающее**.|  
|[DDV\_MinMaxInt](../Topic/DDV_MinMaxInt.md)|Проверьте заданное значение элемента управления не превышает заданный диапазон **int**.|  
|[DDV\_MinMaxLong](../Topic/DDV_MinMaxLong.md)|Проверьте заданное значение элемента управления не превышает заданный диапазон **long**.|  
|[DDV\_MinMaxLongLong](../Topic/DDV_MinMaxLongLong.md)|Проверьте заданное значение элемента управления не превышает заданный диапазон **LONGLONG**.|  
|[DDV\_MinMaxMonth](../Topic/DDV_MinMaxMonth.md)|Проверьте заданное значение элемента управления не превышает заданный диапазон дат.|  
|[DDV\_MinMaxShort](../Topic/DDV_MinMaxShort.md)|Проверьте заданное значение элемента управления не превышает заданный диапазон **short**.|  
|[DDV\_MinMaxSlider](../Topic/DDV_MinMaxSlider.md)|Подтверждает, что данный элемент управления "ползунок" значение находится в заданном диапазоне.|  
|[DDV\_MinMaxUInt](../Topic/DDV_MinMaxUInt.md)|Проверьте заданное значение элемента управления не превышает заданный диапазон **uint**.|  
|[DDV\_MinMaxULongLong](../Topic/DDV_MinMaxULongLong.md)|Проверьте заданное значение элемента управления не превышает заданный диапазон **ULONGLONG**.|  
  
## См. также  
 [Стандартные сведения диалогового окна обмен процедуры](../Topic/Standard%20Dialog%20Data%20Exchange%20Routines.md)   
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)