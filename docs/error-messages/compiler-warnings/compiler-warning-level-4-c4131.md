---
title: Предупреждение (уровень 4) C4131 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4131
dev_langs:
- C++
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6563d5faf3a9f050deb3cb7831c1a908739c8532
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291994"
---
# <a name="compiler-warning-level-4-c4131"></a>Предупреждение компилятора (уровень 4) C4131
"функция": используется декларатор старого стиля  
  
 Указанное объявление функции имеет отличную от прототипа форму.  
  
 Использующие старый стиль объявления функций следует преобразовать в форму прототипа.  
  
 В следующем примере показан старый стиль объявления функции:  
  
```  
// C4131.c  
// compile with: /W4 /c  
void addrec( name, id ) // C4131 expected  
char *name;  
int id;  
{ }  
```  
  
 В следующем примере показана форма прототипа:  
  
```  
void addrec( char *name, int id )  
{ }  
```