---
title: "Ошибка средств компоновщика LNK1188 | Microsoft Docs"
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
  - "LNK1188"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1188"
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK1188
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BADFIXUPSECTION:: недопустимый целевой объект адресной привязки "символ"; возможно, раздел нулевой длины  
  
 Во время компоновки VxD в конечном объекте перемещения был пропущен раздел.  При использовании LINK386 \(устаревшая версия\) можно было использовать запись OMF GROUP \(созданную при помощи директивы MASM GROUP\), чтобы комбинировать раздел нулевой длины с другим разделом, имеющим ненулевую длину.  Формат COFF не поддерживает директивы GROUP и разделы нулевой длины.  Данная ошибка может возникнуть при автоматическом преобразовании LINK данного типа объектов OMF в COFF.