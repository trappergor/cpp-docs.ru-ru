---
title: "Ошибка компилятора C3384 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3384
dev_langs: C++
helpviewer_keywords: C3384
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d62e977dfa9663adacb7d7b4e78642a4e2b5dcb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3384"></a>Ошибка компилятора C3384
"параметр_типа": ограничение значения и ссылочное ограничение взаимно исключают друг друга  
  
 Невозможно ограничить универсальный тип до `value class` и `ref class`.  
  
 В разделе [ограничений для параметров универсального типа (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 При компиляции следующего примера возникнет ошибка C3384.  
  
```  
// C3384.cpp  
// compile with: /c /clr  
generic <typename T>  
where T : ref class  
where T : value class   // C3384  
ref class List {};  
```