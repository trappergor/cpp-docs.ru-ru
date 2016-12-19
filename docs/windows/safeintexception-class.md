---
title: "Класс SafeIntException | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeIntException Class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeIntException - класс"
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
caps.latest.revision: 8
caps.handback.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Класс SafeIntException
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс `SafeInt` использует `SafeIntException`, чтобы определить, почему математическая операция не может быть завершена.  
  
## Синтаксис  
  
```  
class SafeIntException;  
```  
  
## Члены  
  
### Открытые конструкторы  
 [SafeIntException::SafeIntException](../Topic/SafeIntException::SafeIntException.md)  
 Создает объект `SafeIntException`.  
  
## Заметки  
 [Класс SafeInt](../windows/safeint-class.md) один класс, который использует класс `SafeIntException`.  
  
## Иерархия наследования  
 [SafeIntException Class](../windows/safeintexception-class.md)  
  
## Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** msl::utilities  
  
## См. также  
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeInt](../windows/safeint-class.md)