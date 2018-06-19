---
title: Ошибка компилятора предупреждение (уровень 1) C4075 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4075
dev_langs:
- C++
helpviewer_keywords:
- C4075
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9a0d9fb3808af9ed05454b5b07d471303abc654
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282887"
---
# <a name="compiler-warning-level-1-c4075"></a>Предупреждение компилятора (уровень 1) C4075
инициализаторы в неопознанной области инициализации  
  
 Директива [#pragma init_seg](../../preprocessor/init-seg.md) использует неизвестное имя раздела. Компилятор игнорирует команду **pragma** .  
  
 В следующем примере возникает ошибка C4075.  
  
```  
// C4075.cpp  
// compile with: /W1  
#pragma init_seg("mysegg")   // C4075  
  
// try..  
// #pragma init_seg(user)  
  
int main() {  
}  
```