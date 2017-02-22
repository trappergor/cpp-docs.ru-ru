---
title: "__readcr3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readcr3"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __readcr3"
ms.assetid: e24392c3-cad7-4788-8f31-94bf2e9e0053
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __readcr3
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Читает реестр CR3 и возвращает его значение.  
  
## Синтаксис  
  
```  
unsigned __int64 __readcr3(void);  
```  
  
## Возвращаемое значение  
 Значение в регистре CR3.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__readcr3`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Этот встроенный доступен только в режиме ядра и процедура доступна только в качестве внутреннего элемента.  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)