---
title: Неустранимая ошибка C1019 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1019
dev_langs:
- C++
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 119ff2df1554467762c0b960e80ad4c241517628
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198681"
---
# <a name="fatal-error-c1019"></a>Неустранимая ошибка C1019
непредвиденный #else  
  
 Директива `#else` находится за пределами конструкции `#if`, `#ifdef`или `#ifndef` . Используйте `#else` только в одной из этих конструкций.  
  
 При компиляции следующего примера возникнет ошибка C1019:  
  
```  
// C1019.cpp  
#else   // C1019  
#endif  
  
int main() {}  
```  
  
 Возможное решение  
  
```  
// C1019b.cpp  
#if 1  
#else  
#endif  
  
int main() {}  
```