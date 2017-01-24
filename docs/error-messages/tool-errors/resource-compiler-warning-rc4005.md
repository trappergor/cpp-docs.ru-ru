---
title: "Предупреждение компилятора ресурсов RC4005 | Microsoft Docs"
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
  - "RC4005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4005"
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора ресурсов RC4005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": изменение макроопределения  
  
 Идентификатор определен дважды.  При компиляции используется второе макроопределение.  
  
 Это предупреждение отображается в случае одновременного определения макроса в командной строке и в коде с помощью директивы `#define`.  Также предупреждение может быть связано с импортом макроса из включаемых файлов.  
  
 Чтобы устранить предупреждение, удалите одно из определений или используйте директиву `#undef` перед вторым определением.