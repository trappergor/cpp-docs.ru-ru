---
title: "_ATL_COM_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::_ATL_COM_MODULE70"
  - "ATL._ATL_COM_MODULE70"
  - "_ATL_COM_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_COM_MODULE70 structure"
  - "ATL_COM_MODULE70 structure"
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# _ATL_COM_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Общий Модель COM\- связанными кодом в библиотеки ATL.  
  
## Синтаксис  
  
```  
  
      struct _ATL_COM_MODULE70{  
   UINT cbSize;  
   HINSTANCE m_hInstTypeLib;  
   _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;  
   _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;  
   CRITICAL_SECTION m_csObjMap;  
};  
```  
  
## Члены  
 `cbSize`  
 Размер структуры, используемый для управления версиями.  
  
 `m_hInstTypeLib`  
 Экземпляр маркера на библиотеку типов для данного модуля.  
  
 **m\_ppAutoObjMapFirst**  
 Адрес элемента массива, указывающий начало записей сопоставления объекта для данного модуля.  
  
 **m\_ppAutoObjMapLast**  
 Адрес элемента массива, указывающий конец записей сопоставления объекта для данного модуля.  
  
 `m_csObjMap`  
 Критическая секция для сериализации доступ к записям сопоставления объекта.  Используемый внутри библиотеки ATL.  
  
## Заметки  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md) определено как typedef `_ATL_COM_MODULE70`.  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [Структуры](../../atl/reference/atl-structures.md)