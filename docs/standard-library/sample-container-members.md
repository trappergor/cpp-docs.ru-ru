---
title: "Члены образца контейнера | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы контейнеров"
ms.assetid: dc5a1998-a31b-4adf-b888-8abe5b87a4e0
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Члены образца контейнера
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  В этом разделе в документации Visual C\+\+ как нефункциональный пример контейнеров, используемых в стандартной библиотеке C\+\+.  Дополнительные сведения см. в разделе [Контейнеров STL](../standard-library/stl-containers.md).  
  
## Ссылка  
  
## Определения типов  
  
|||  
|-|-|  
|[const\_iterator](../standard-library/container-class-const-iterator.md)|Описание объекта, который можно использовать в качестве константной итератор для контролируемой последовательности.|  
|[const\_reference](../standard-library/container-class-const-reference.md)|Описание объекта, который можно использовать в качестве константной ссылки на элемент контролируемой последовательности.|  
|[const\_reverse\_iterator](../standard-library/container-class-const-reverse-iterator.md)|Описание объекта, который можно использовать как постоянный обратный итератор для контролируемой последовательности.|  
|[difference\_type](../Topic/Container%20Class::difference_type.md)|Описывает объект, который может представлять различие между адресами любого 2 элементов в контролируемой последовательности.|  
|[итератор](../standard-library/container-class-iterator.md)|Описание объекта, который можно использовать как итератор для контролируемой последовательности.|  
|[Ссылка](../Topic/Container%20Class::reference.md)|Описание объекта, который можно использовать как ссылку на элемент контролируемой последовательности.|  
|[reverse\_iterator](../standard-library/container-class-reverse-iterator.md)|Описание объекта, который можно использовать в качестве обратного итератор для контролируемой последовательности.|  
|[size\_type](../standard-library/container-class-size-type.md)|Описывает объект, который может представлять любой длины контролируемой последовательности.|  
|[value\_type](../standard-library/container-class-value-type.md)|Синоним является шаблона для параметра **Ty**.|  
  
## Функции\-члены  
  
|||  
|-|-|  
|[begin](../standard-library/container-class-begin.md)|Возвращает итератор, указывающим на первый элемент последовательности \(или просто за пределы пустой последовательности\).|  
|[clear](../standard-library/container-class-clear.md)|Вызывает функцию [erase](../standard-library/container-class-erase.md)\( [begin](../standard-library/container-class-begin.md), [end](../Topic/Container%20Class::end.md)\).|  
|[empty](../standard-library/container-class-empty.md)|Возвращает **true**  для пустой контролируемой последовательности.|  
|[end](../Topic/Container%20Class::end.md)|Возвращает итератор, указывающий только за пределы последовательности.|  
|[erase](../standard-library/container-class-erase.md)|Удаляет элемент.|  
|[max\_size](../standard-library/container-class-max-size.md)|Возвращает длину самой длинной последовательности, объект может элемент управления, при расчете времени независимо от длины контролируемой последовательности.|  
|[rbegin](../Topic/Container%20Class::rbegin.md)|Возвращает обратный итератор, который указывает только за пределы контролируемой последовательности, обозначая начало обратной последовательности.|  
|[rend](../standard-library/container-class-rend.md)|Функция\-член возвращает обратный итератор, указывающим на первый элемент последовательности \(или просто за пределы пустой последовательности\), обозначая обратной конец последовательности.|  
|[size](../standard-library/container-class-size.md)|Возвращает длину контролируемой последовательности, при расчете времени независимо от длины контролируемой последовательности.|  
|[буфер обмена](../Topic/Container%20Class::swap.md)|Замена из последовательности между **\*this** и `_Right`.|