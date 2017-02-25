---
title: "Обработчики полей со списками | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_CBN_KILLFOCUS"
  - "ON_CBN_ERRSPACE"
  - "ON_CBN_EDITCHANGE"
  - "ON_CBN_CLOSEUP"
  - "ON_CBN_DBLCLK"
  - "ON_CBN_EDITUPDATE"
  - "ON_CBN_DROPDOWN"
  - "ON_CBN_SELENDOK"
  - "ON_CBN_SELCHANGE"
  - "ON_CBN_SETFOCUS"
  - "ON_CBN_SELENDCANCEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "поля со списком, обработчики"
  - "ON_CBN_CLOSEUP"
  - "ON_CBN_DBLCLK"
  - "ON_CBN_DROPDOWN"
  - "ON_CBN_EDITCHANGE"
  - "ON_CBN_EDITUPDATE"
  - "ON_CBN_ERRSPACE"
  - "ON_CBN_KILLFOCUS"
  - "ON_CBN_SELCHANGE"
  - "ON_CBN_SELENDCANCEL"
  - "ON_CBN_SELENDOK"
  - "ON_CBN_SETFOCUS"
ms.assetid: 7f092412-01b7-4242-95ec-41ba506b9d71
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Обработчики полей со списками
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записи следующего сопоставления соответствуют прототипам функции.  
  
|Запись сопоставления|Прототип функции|  
|--------------------------|----------------------|  
|ON\_CBN\_CLOSEUP \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\)|  
|ON\_CBN\_DBLCLK \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_CBN\_DROPDOWN \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_CBN\_EDITCHANGE \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_CBN\_EDITUPDATE \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_CBN\_ERRSPACE \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_CBN\_KILLFOCUS \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_CBN\_SELCHANGE \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_CBN\_SELENDCANCEL \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_CBN\_SELENDOK \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_CBN\_SETFOCUS \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
  
## См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)