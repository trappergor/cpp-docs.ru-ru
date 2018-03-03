---
title: "Предупреждение (уровень 1) C4742 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4742
dev_langs:
- C++
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da12d4d1e5e8b6f9be6c21601e04f08d1b269cec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4742"></a>Предупреждение компилятора (уровень 1) C4742
«переменная» имеет различное выравнивание в «файл1» и «файл2»: номер и номер  
  
 Внешняя переменная, которая была определена в двух файлах или ссылаться на имеет различное выравнивание в этих файлах. Это предупреждение выдается в том случае, если компилятор обнаруживает, что `__alignof` переменной в *file1* отличается от `__alignof` переменной в *file2*. Причиной может быть использование несовместимых типов при объявлении переменной в разных файлах или с помощью несоответствующий `#pragma pack` в разных файлах.  
  
 Чтобы устранить это предупреждение, используйте то же определение типа или используйте разные имена для переменных.  
  
 Дополнительные сведения см. в разделе [пакет](../../preprocessor/pack.md) и [оператор __alignof](../../cpp/alignof-operator.md).  
  
## <a name="example"></a>Пример  
 Это первый файл, который определяет тип.  
  
```  
// C4742a.c  
// compile with: /c  
struct X {  
   char x, y, z, w;  
} global;  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4742.  
  
```  
// C4742b.c  
// compile with: C4742a.c /W1 /GL  
// C4742 expected  
extern struct X {  
   int a;  
} global;  
  
int main() {  
   global.a = 0;  
}  
```