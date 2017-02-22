---
title: "__readcr4 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readcr4"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __readcr4"
ms.assetid: b841a27b-fe0d-4ee9-b76b-f91d3eb061fa
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __readcr4
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Читает реестр CR4 и возвращает его значение.  
  
## Синтаксис  
  
```  
unsigned __int64 __readcr4(void);  
```  
  
## Возвращаемое значение  
 Значение в регистре CR4.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__readcr4`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Этот встроенный доступен только в режиме ядра и процедура доступна только в качестве внутреннего элемента.  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)