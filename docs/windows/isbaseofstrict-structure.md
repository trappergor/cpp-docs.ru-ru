---
title: "Структура IsBaseOfStrict | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::IsBaseOfStrict"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsBaseOfStrict - структура"
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Структура IsBaseOfStrict
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
#### Параметры  
 `Base`  
 Базовый тип.  
  
 `Derived`  
 Производный тип.  
  
## Примечания  
 Проверяет, является ли один тип базовым для другого.  
  
 Первый шаблон проверяет, является ли тип производным от базового типа, что может возвращать **true** или **false**.  Второй шаблон проверяет, является ли тип производным от самого себя, что всегда создает **false**.  
  
## Члены  
  
### Открытые константы  
  
|Имя|Описание|  
|---------|--------------|  
|[Константа IsBaseOfStrict::value](../Topic/IsBaseOfStrict::value%20Constant.md)|Указывает, является ли один тип базовым для другого.|  
  
## Иерархия наследования  
 `IsBaseOfStrict`  
  
## Требования  
 **Заголовок:** internal.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)