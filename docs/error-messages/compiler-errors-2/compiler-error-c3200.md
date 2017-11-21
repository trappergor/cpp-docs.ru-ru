---
title: "Ошибка компилятора C3200 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3200
dev_langs: C++
helpviewer_keywords: C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e4e1df5fb5c3da260ec5eba75d25e74207fbf8e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3200"></a>Ошибка компилятора C3200
«шаблон»: недопустимый аргумент шаблона для параметра шаблона «параметр», требуется класс-шаблон  
  
 Передан недопустимый аргумент шаблона класса. Шаблон класса ожидает шаблон в качестве параметра. В следующем примере вызов `Y<int, int> aY` создаст C3200. Первый параметр должен быть шаблоном, такой как `Y<X, int> aY`.  
  
```  
// C3200.cpp  
template<typename T>  
class X  
{  
};  
  
template<template<typename U> class T1, typename T2>  
class Y  
{  
};  
  
int main()  
{  
   Y<int, int> y;   // C3200  
}  
```