---
title: "Выделение и освобождение памяти для BSTR | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: bstr
dev_langs: C++
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 282ceac05587452fad750f05b642c0ffd5b929a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>Выделение и освобождение памяти для BSTR
При создании `BSTR`s и передавать их между объектами COM, необходимо соблюдать осторожность в обработке памяти, они используют во избежание утечки памяти. Когда `BSTR` остается в интерфейсе, вам необходимо освобождать память при выполняются с ним. Тем не менее, когда `BSTR` передает из интерфейса, получающий объект отвечает за его управление памятью.  
  
 В общем случае правила для выделения и освобождения памяти выделенной для `BSTR`s, следующим образом:  
  
-   При вызове в функцию, ожидающую `BSTR` аргумент, необходимо выделить память для `BSTR` перед вызовом и после его освобождения. Пример:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]  
  
-   При вызове функции, которая возвращает `BSTR`, необходимо освободить строку самостоятельно. Пример:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]  
  
-   При реализации функции, которая возвращает `BSTR`, выделите строку, но не освободить. Получения функция освобождает память. Пример:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)   
 [SysAllocString](https://msdn.microsoft.com/library/windows/desktop/ms221458.aspx)   
 [SysFreeString](https://msdn.microsoft.com/library/windows/desktop/ms221481.aspx)

