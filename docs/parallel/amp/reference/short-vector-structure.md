---
title: "Структура short_vector | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::short_vector"
dev_langs: 
  - "C++"
ms.assetid: e4f50b8f-1150-437d-b58c-79c5fb883708
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Структура short_vector
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

short\_vector предоставляет метапрограммные определения, которые полезны для общих случаев программирования коротких векторов.  
  
## Синтаксис  
  
```  
template<  
   typename _Scalar_type,  
   int _Size  
>  
struct short_vector;  
template<>  
struct short_vector<unsigned int, 1>;  
template<>  
struct short_vector<unsigned int, 2>;  
template<>  
struct short_vector<unsigned int, 3>;  
template<>  
struct short_vector<unsigned int, 4>;  
template<>  
struct short_vector<int, 1>;  
template<>  
struct short_vector<int, 2>;  
template<>  
struct short_vector<int, 3>;  
template<>  
struct short_vector<int, 4>;  
template<>  
struct short_vector<float, 1>;  
template<>  
struct short_vector<float, 2>;  
template<>  
struct short_vector<float, 3>;  
template<>  
struct short_vector<float, 4>;  
template<>  
struct short_vector<unorm, 1>;  
template<>  
struct short_vector<unorm, 2>;  
template<>  
struct short_vector<unorm, 3>;  
template<>  
struct short_vector<unorm, 4>;  
template<>  
struct short_vector<norm, 1>;  
template<>  
struct short_vector<norm, 2>;  
template<>  
struct short_vector<norm, 3>;  
template<>  
struct short_vector<norm, 4>;  
template<>  
struct short_vector<double, 1>;  
template<>  
struct short_vector<double, 2>;  
template<>  
struct short_vector<double, 3>;  
template<>  
struct short_vector<double, 4>;  
```  
  
#### Параметры  
 `_Scalar_type`  
 `_Size`  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
|`type`||  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор short\_vector::short\_vector](../Topic/short_vector::short_vector%20Constructor.md)||  
  
## Иерархия наследования  
 `short_vector`  
  
## Требования  
 **Заголовок:** amp\_short\_vectors.h  
  
 **Пространство имен:** Concurrency::graphics  
  
## См. также  
 [Пространство имен Concurrency::graphics](../../../parallel/amp/reference/concurrency-graphics-namespace.md)