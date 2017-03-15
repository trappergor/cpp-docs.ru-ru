---
title: "Класс DontUseNewUseMake | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::DontUseNewUseMake"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DontUseNewUseMake - класс"
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Класс DontUseNewUseMake
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
class DontUseNewUseMake;  
```  
  
## Заметки  
 Запрещает использовать оператор `new` в RuntimeClass.  Следовательно, необходимо использовать [Make \- функцию](../windows/make-function.md).  
  
## Члены  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор DontUseNewUseMake::operator new](../windows/dontusenewusemake-operator-new-operator.md)|Перегружает оператор `new` и препятствует его использованию в RuntimeClass.|  
  
## Иерархия наследования  
 `DontUseNewUseMake`  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)   
 [Функция Make](../windows/make-function.md)