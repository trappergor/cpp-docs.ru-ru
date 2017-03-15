---
title: "Allocating and Releasing Memory for a BSTR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "bstr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "строки BSTR, выделение памяти"
  - "память [C++], освобождение"
  - "выделение памяти, строки BSTR"
  - "memory deallocation, BSTR memory"
  - "memory deallocation, string memory"
  - "строки [C++], освобождение"
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Allocating and Releasing Memory for a BSTR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При создании `BSTR` и передает их между com\-объектом, необходимо позаботиться обработать память используется во избежание утечки памяти.  При `BSTR` остается в интерфейсе, необходимо освободить свою память после завершения с ней.  Однако при `BSTR` передает из интерфейса, получающий объект является обязанностью для управления памятью.  
  
 Обычно правила для выделения и освобождения памяти, выделенная для `BSTR` s следующим образом:  
  
-   При вызове в функцию, ожидающую аргумент `BSTR` необходимо выделить память для `BSTR` до вызова и освобождение его.  Примеры.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_1.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_2.cpp)]  
  
-   При вызове из функции, которая получает `BSTR`, необходимо самостоятельно освободить строку.  Примеры.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_3.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_4.cpp)]  
  
-   При реализации функции, возвращающей `BSTR` выберите строку, но не освободите его.  Получение функцию освобождает память.  Примеры.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_5.cpp)]  
  
## См. также  
 [Строки](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md)   
 [SysAllocString](http://msdn.microsoft.com/ru-ru/9e0437a2-9b4a-4576-88b0-5cb9d08ca29b)   
 [SysFreeString](http://msdn.microsoft.com/ru-ru/8f230ee3-5f6e-4cb9-a910-9c90b754dcd3)