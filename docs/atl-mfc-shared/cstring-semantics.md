---
title: "CString Semantics | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "операторы назначения, assigning CString objects"
  - "CString objects, assignment semantics"
  - "semantics in Cstring"
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CString Semantics
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Даже если объекты [CString](../atl-mfc-shared/reference/cstringt-class.md) динамические объекты, которые могут увеличиваться, они действуют как встроенные типы\-примитивы и простые классы.  Каждый объект `CString` представляющая уникальное значение.  Объекты `CString` должны быть подуманы как строки фактических, а не как указатели на строки.  
  
 Можно присвоить один объект **CString**  в другой.  Однако при изменении одного из 2 объектов `CString` другой объект `CString` не изменяется, как показано в следующем примере:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/CPP/cstring-semantics_1.cpp)]  
  
 Обратите внимание, что в примере 2 объекта `CString` "считаются равными", поскольку они представляют одну и ту же строку символов.  Класс `CString` перегружает оператор равенства \(`==`\) для сравнения 2 объекта `CString` на основе их значения \(содержимое\), а не их идентификатора \(адрес\).  
  
## См. также  
 [Строки](../atl-mfc-shared/strings-atl-mfc.md)