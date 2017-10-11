---
title: "Ошибка компилятора C3172 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3172
dev_langs:
- C++
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6f6bc65ad1f62139e7131e7bb4fbd07a59cb9dd9
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3172"></a>Ошибка компилятора C3172
«имя_модуля»: невозможно указать другие атрибуты idl_module в проекте  
  
 [idl_module](../../windows/idl-module.md) атрибуты с тем же имя, но разные `dllname` или `version` параметров были найдены в двух файлах при компиляции. Только один уникальный `idl_module` атрибут можно задать на каждую компиляцию.  
  
 Идентичные `idl_module` атрибуты могут быть заданы в более чем один файл исходного кода.  
  
 Например если следующие `idl_module` обнаружены атрибуты:  
  
```  
// C3172.cpp  
[module(name="MyMod")];  
[ idl_module(name="x", dllname="file.dll", version="1.1") ];  
int main() {}  
```  
  
 Затем:  
  
```  
// C3172b.cpp  
// compile with: C3172.cpp  
// C3172 expected  
[ idl_module(name="x", dllname="file.dll", version="1.0") ];  
```  
  
 компилятор создаст ошибку C3172 (запишите значения разных версий).
