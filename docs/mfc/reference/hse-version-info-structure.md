---
title: "Структура HSE_VERSION_INFO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "HSE_VERSION_INFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HSE_VERSION_INFO - структура"
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Структура HSE_VERSION_INFO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эта структура указана параметру `pVer` в функции\-члене `CHttpServer::GetExtensionVersion`.  Он предоставляет номер версии ISA и текстовое описание ISA.  
  
## Синтаксис  
  
```  
  
      typedef struct _HSE_VERSION_INFO {  
   DWORD dwExtensionVersion;  
   CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### Параметры  
 *dwExtensionVersion*  
 Номер версии ISA.  
  
 *lpszExtensionDesc*  
 Текстовое описание ISA.  Реализация по умолчанию содержит текст местозаполнителя; переопределение `CHttpServer::GetExtensionVersion`, чтобы предоставить собственное описание.  
  
## Требования  
 **Header:** httpext.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)