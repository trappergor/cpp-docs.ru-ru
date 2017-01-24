---
title: "Предупреждение средств компоновщика LNK4096 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4096"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4096"
ms.assetid: ef6fba38-59a1-4d86-bcac-cadf44d87a36
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение средств компоновщика LNK4096
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

значение \/BASE "number" недопустимо для Windows 95 и Windows 98; образ может не запускаться  
  
 Указанный базовый адрес является недопустимым.  У исполняемых файлов Windows 95 и Windows 98 базовый адрес должен быть больше 0x400000.  Дополнительные сведения о базовых адресах см. в описании параметра компоновщика [\/BASE](../../build/reference/base-base-address.md).