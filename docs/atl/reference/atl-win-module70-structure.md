---
title: "_ATL_WIN_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_WIN_MODULE70"
  - "ATL::_ATL_WIN_MODULE70"
  - "ATL._ATL_WIN_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_WIN_MODULE70 structure"
  - "ATL_WIN_MODULE70 structure"
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# _ATL_WIN_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используемый кодом над окнами в библиотеки ATL.  
  
## Синтаксис  
  
```  
  
      struct _ATL_WIN_MODULE70{  
   UNIT cbSize;  
   CRITICAL_SECTION m_csWindowCreate;  
   _AtlCreateWndData* m_pCreateWndList;  
   CSimpleArray<ATOM> m_rgWindowClassAtoms;  
};  
```  
  
## Члены  
 `cbSize`  
 Размер структуры, используемый для управления версиями.  
  
 `m_csWindowCreate`  
 Используемый для сериализации доступ к коду регистрации окна.  Используемый внутри библиотеки ATL.  
  
 **m\_pCreateWndList**  
 Используемый для привязки окна к их объектам.  Используемый внутри библиотеки ATL.  
  
 **m\_rgWindowClassAtoms**  
 Используемый для отслеживания регистрации класса окна таким образом, чтобы они могли быть правильно регистрации при завершении.  Используемый внутри библиотеки ATL.  
  
## Заметки  
 [\_ATL\_WIN\_MODULE](../Topic/_ATL_WIN_MODULE.md) определено как typedef `_ATL_WIN_MODULE70`.  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [Структуры](../../atl/reference/atl-structures.md)