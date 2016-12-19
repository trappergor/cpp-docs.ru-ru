---
title: "Структура IsSame | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::IsSame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsSame - структура"
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура IsSame
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template <  
   typename T1,  
   typename T2  
>  
struct IsSame;  
template <  
   typename T1  
>  
struct IsSame<T1, T1>;  
```  
  
#### Параметры  
 `T1`  
 Тип.  
  
 `T2`  
 Другой тип.  
  
## Заметки  
 Определяет, совпадает ли один указанный тип с другим указанными типом.  
  
## Члены  
  
### Открытые константы  
  
|Имя|Описание|  
|---------|--------------|  
|[Константа IsSame::value](../windows/issame-value-constant.md)|Указывает, совпадает ли один тип с другим.|  
  
## Иерархия наследования  
 `IsSame`  
  
## Требования  
 **Заголовок:** internal.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)