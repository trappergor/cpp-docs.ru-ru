---
title: "_ATL_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_MODULE70"
  - "ATL::_ATL_MODULE70"
  - "ATL._ATL_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_MODULE70 structure"
  - "ATL_MODULE70 structure"
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
caps.latest.revision: 16
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Содержит сведения, используемые каждым модулем библиотеки ATL.  
  
## Синтаксис  
  
```  
  
      struct _ATL_MODULE70{  
   UINT cbSize;  
   LONG m_nLockCnt;  
   _ATL_TERMFUNC_ELEM* m_pTermFuncs;  
   CComCriticalSection m_csStaticDataInitAndTypeInfo;  
};  
```  
  
## Члены  
 `cbSize`  
 Размер структуры, используемый для управления версиями.  
  
 `m_nLockCnt`  
 Значение счетчика ссылок, чтобы указать, как долго модуль должен оставаться в активном состоянии.  
  
 **m\_pTermFuncs**  
 Отслеживает функции, которые были зарегистрированы вызываться при завершении работы библиотеки ATL.  
  
 **m\_csStaticDataInitAndTypeInfo**  
 Используемый, чтобы координировать доступ к внутренним данным в многопоточном ситуациях.  
  
## Заметки  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md) определено как typedef `_ATL_MODULE70`.  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [Структуры](../../atl/reference/atl-structures.md)