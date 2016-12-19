---
title: "Функции обратного вызова, используемые MFC | Microsoft Docs"
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
  - "vc.mfc.functions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функции обратного вызова"
  - "функции обратного вызова, MFC - библиотека"
  - "функции [C++], обратный вызов"
  - "MFC - библиотека, функции обратного вызова"
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функции обратного вызова, используемые MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

3 Функции обратного вызова отображаются в библиотеки Microsoft Foundation Class.  Описание функций обратного вызова, передаваемых в [CDC::EnumObjects](../Topic/CDC::EnumObjects.md), [CDC::GrayString](../Topic/CDC::GrayString.md) и [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md) ниже в этом разделе.  Для общего потребления функций обратного вызова см. раздел комментария этих функций\-членов.  Обратите внимание, что все функции обратного вызова исключений MFC ловушки перед возвратом в Windows, поскольку исключения нельзя вызывать через границы обратного вызова.  Дополнительные сведения о исключения см. в статье [Исключения](../../mfc/exception-handling-in-mfc.md).  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)