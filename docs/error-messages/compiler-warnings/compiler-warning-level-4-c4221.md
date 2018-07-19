---
title: Предупреждение (уровень 4) C4221 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4221
dev_langs:
- C++
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e602eb662533207a1f2957d3b11a0823e4b83af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293199"
---
# <a name="compiler-warning-level-4-c4221"></a>Предупреждение компилятора (уровень 4) C4221
использовано нестандартное расширение: «идентификатор»: не удается инициализировать с помощью адреса автоматической переменной  
  
 С расширениями по умолчанию Майкрософт (/Ze) можно инициализировать агрегированный тип (**массива**, `struct`, или **объединение**) адрес локальной переменной (автоматический).  
  
## <a name="example"></a>Пример  
  
```  
// C4221.c  
// compile with: /W4  
struct S  
{  
   int *i;  
};  
  
void func()  
{  
   int j;  
   struct S s1 = { &j };   // C4221  
}  
  
int main()  
{  
}  
```  
  
 Подобная инициализация не допускается в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).