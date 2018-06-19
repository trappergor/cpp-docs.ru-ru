---
title: Предупреждение (уровень 4) C4324 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4324
dev_langs:
- C++
helpviewer_keywords:
- C4324
ms.assetid: 420fa929-d9c0-40b4-8808-2d8ad3ca8090
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c34d2fb963be790cfd28f08dd4339fa8ac200c6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298981"
---
# <a name="compiler-warning-level-4-c4324"></a>Предупреждение компилятора (уровень 4) C4324
«имя_структуры»: структура была дополнена нулями из-за __declspec(align())  
  
 Заполнение было добавлено в конце структуры, так как указан [__declspec(align)](../../cpp/align-cpp.md) значение.  
  
 Например следующий код приводит к возникновению ошибки C4324:  
  
```  
// C4324.cpp  
// compile with: /W4  
struct __declspec(align(32)) A  
{  
   char a;  
};   // C4324  
  
int main()  
{  
}  
```